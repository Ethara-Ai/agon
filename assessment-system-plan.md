# Generalist Assessment System — Project Plan

**Status:** Draft v1 · **Last updated:** 2026-06-15
**Purpose:** One source of truth for how we build, score, and route with the generalist annotator assessment.

---

## 1. What we are building

An **LLM-generated question bank and scoring system** to hire, screen, and route **generalist AI data annotators / AI-output evaluators** (new hires and interns).

An image-capable LLM (**Gemini 3 Pro**) reads our project SOPs, vendor guidelines, and client feedback and produces the questions, their answer keys, and their grading rubrics. Each candidate's answers are scored into a **per-skill profile**, and that profile decides which project they are routed to.

The assessment currently spans four projects:

| Short name | Project | Task in one line |
|---|---|---|
| T2I | `260126-text-to-image-compare` | Compare two AI images against a prompt on four axes + a written justification. |
| Video | `251216-video-artistic-style-reference` | Write a transformation prompt that turns a reference into a target. |
| UI | `260123-high-res-dense-bbox-with-labels` | Describe the function of every boxed element on a screenshot. |
| i2i | `i2i-pixel-aligned-filter-flux2-nomask` | Three independent yes/no checks on one image edit. |

Skills are derived from these SOPs. When a new project arrives we derive its skills the same way, and a hire's per-skill scores route them to whichever project needs those skills.

---

## 2. The two-phase mental model (read this first)

Everything below sits in one of two phases. Keeping them apart is the most important structural decision we make.

- **Build time** — rare, once per project, **human-reviewed**. This is where we spend our accuracy budget: freezing skills, generating the bank, verifying answer keys, piloting.
- **Run time** — per candidate, at scale, **fully automated**. Scoring and routing run with no human in the loop.

```
══ BUILD TIME  (rare · per project · human-reviewed) ════════════════════

  SOPs + vendor guidelines + client feedback
            │
            ▼
   CANONICAL SKILLS  ──►  skill.md  +  skillset.master.json   (frozen, versioned)
            │                         ▲
            ▼                         │ human approves any new skill
   GENERATOR (Gemini 3 Pro)  ─────────┘
   tags every question to a frozen skill name; emits:
     • objective questions  → answer + one-line reason
     • subjective questions → checklist + constraints + pass_condition (a rubric)
            │
            ▼
   ★ HUMAN KEY REVIEW + PILOT ★   (verify keys, retire weak items)
            │
            ▼
   FROZEN QUESTION BANK (versioned)

══ RUN TIME  (per candidate · automated) ═══════════════════════════════

   candidate answers
        ├── objective answers  ──►  CODE checks (answer == key)
        └── subjective answers ──►  LLM JUDGE (rubric-based)
                                          │
                                          ▼
                          per-skill score profile (keyed by frozen skill IDs)
                                          │
                                          ▼
                          MATCHER (plain code: scores × project weights) ──► route to project
```

---

## 3. Skills: one canonical, frozen vocabulary (the foundation)

Every other part of the system keys off skills — questions are tagged by skill, scores roll up by skill, and routing compares a candidate's skill scores to a project's skill needs. **If a skill's name or meaning shifts between runs, scores from different cohorts stop lining up and routing silently breaks.** So the skills vocabulary is defined once, frozen, and governed.

### 3.1 The rule: canonical names and granularity never change

We separate the part that is a permanent contract from the part that is allowed to evolve.

**Frozen forever (the contract):**
- A skill's **ID** (e.g. `S7`).
- A skill's **name** (e.g. *Alignment Perception*).
- A skill's **granularity / scope** — what it covers. A skill is never renamed, never merged into another, and never split into two.

This is what makes a score on *Alignment Perception* mean the same thing in June that it means next year, for every cohort.

**Allowed to evolve each iteration (the living parts):**
- **Adding a brand-new skill** (a new ID) when a new project genuinely needs a competency no existing skill covers — only after human review.
- **Adding a new project's weight column** and **tuning weights**.
- **Sharpening a description's wording** without changing what it means.
- The **version bump** and **changelog** entry.

### 3.2 Two artifacts, kept in sync

| Artifact | What it is | Who reads it |
|---|---|---|
| `skill.md` | The human-readable canonical skills registry. Authoritative. Versioned, with a changelog. **Updated every iteration.** | Humans (review, sign-off) |
| `skillset.master.json` | The machine-readable twin, derived from `skill.md`. | The generator (as the frozen `SKILLSET` input) and the matcher (for routing weights) |

`skill.md` is authoritative; `skillset.master.json` is regenerated to match it whenever it changes. They always carry the same `skillset_version`.

### 3.3 How `skill.md` changes each iteration (governance)

1. **Append-only for skills.** New skills get the next free ID. Existing skills are never edited in a way that changes their identity (no rename, merge, or split).
2. **Human review gate for new skills.** When the generator meets a competency not in the list, it does **not** invent a scored skill — it raises it in `flags` as a *proposed addition*. A human decides whether to add it.
3. **Version + changelog on every change.** Bump `skillset_version` and add a dated line saying what changed and why.
4. **Weights are tunable; meanings are not.** Re-weighting a skill for a project, or adding a project column, is a normal iteration. Re-defining a skill is not.
5. **Regenerate the JSON twin** and re-run any affected banks against the new version.

**Changelog template (top of `skill.md`):**

```
## Changelog
- v1-draft-2026-06-15 — initial canonical set, 15 skills (S1–S15), 4 projects.
- vX-YYYY-MM-DD — <what changed and why>
```

### 3.4 The canonical skill set (v1)

Fifteen skills, plain-word names. Weights are 0 (irrelevant) to 5 (critical) per project. A skill applies to a project when its weight is ≥ 1.

| ID | Skill | T2I | Video | UI | i2i |
|---|---|:--:|:--:|:--:|:--:|
| S1 | Instruction Reading | 5 | 2 | 1 | 5 |
| S2 | Attention to Detail ★ | 5 | 4 | 4 | 5 |
| S3 | Calibrated Judgment ★ | 4 | 4 | 4 | 5 |
| S4 | Objectivity | 5 | 4 | 3 | 4 |
| S5 | Process & Coverage ★ | 3 | 4 | 5 | 4 |
| S6 | Difference Detection | 1 | 5 | 0 | 5 |
| S7 | Alignment Perception → **i2i** | 1 | 0 | 0 | 5 |
| S8 | Artifact Detection | 5 | 1 | 0 | 5 |
| S9 | Comparison → **T2I** | 5 | 1 | 0 | 1 |
| S10 | Quality Judgment → **T2I** | 5 | 2 | 0 | 1 |
| S11 | Counting | 4 | 1 | 1 | 2 |
| S12 | UI Knowledge → **UI** | 0 | 0 | 5 | 0 |
| S13 | Scene Description → **Video** | 1 | 5 | 1 | 0 |
| S14 | Art Vocabulary → **Video** | 1 | 5 | 0 | 0 |
| S15 | Clear Writing | 4 | 5 | 5 | 1 |

- **★ Generalist backbone (S2, S3, S5):** weighted 3–5 across every project. A candidate must clear a floor on these (target 60/100) **before** any project match — a spiky specialist with poor attention, calibration, or process is routed nowhere.
- **Routing signals (→):** each marked skill is near-exclusive to one project (weight 5 there, ≤1 elsewhere), so a strong score on it is the cleanest signal to route a candidate to that project.

Full descriptions live in `skill.md`; the machine copy is `skillset.master.json`.

### 3.5 Open items to settle before freezing v1

1. **i2i inclusion.** Kept in the routing vocabulary so candidates can still be matched to i2i work, but its *test items must use real image pairs* (or programmatically injected flaws), never AI-generated edits — generated pixel-exact edits are not trustworthy ground truth. If i2i is fully dropped, zero its column and remove it.
2. **The weights.** They encode hiring priorities and decide who goes where. Confirm every column with the project owners.
3. **Granularity.** Confirm 15 is the right number — e.g. whether `Scene Description` and `Art Vocabulary` should stay separate.

---

## 4. Architecture and flow

Four stages. The LLM is only in the generator and the subjective judge; scoring of objective items and all routing are plain code.

| Stage | Does | Engine | Output |
|---|---|---|---|
| 0 · Skills | Define/extend the canonical skills | Human + LLM (proposals only) | `skill.md` + `skillset.master.json` |
| 1 · Generator | Author questions + keys + rubrics from SOPs, tagged to frozen skills | Gemini 3 Pro | Question bank JSON (+ images) |
| 2 · Scorer | Grade a candidate's answers | **Code** (objective) + LLM judge (subjective) | Per-skill scores |
| 3 · Matcher | Route a scored candidate to a project | **Code** | Project assignment |

---

## 5. Question bank

- **Two formats.** *Objective* fields have fixed options and a single correct answer. *Subjective* fields are open responses.
- **Objective grading:** the generator emits the correct `answer` + a one-line `reason` tied to the SOP rule. Graded at run time by code (`answer == key`) — free, instant, reproducible.
- **Subjective grading:** the generator emits a **rubric**, not a single golden answer — an item-specific `checklist`, `constraints` from the SOP, and a `pass_condition`. Graded by the LLM judge.
- **Coverage & quality:** every option of every objective field and every valid answer pattern appears at least once; 2–3 trap items per project; items are effortful (not answerable at a glance); no near-duplicates; difficulty tagged.
- **Images:** generated images ship as separate parts bound by a stable `media_id`; the dev pipeline uploads to S3 and backfills the empty `url`. A generated image is **never trusted as the answer key** until an independent check confirms it supports every graded verdict. Dense UI screenshots use real captures.

---

## 6. Scoring

- **Objective → code.** No model. 100% reproducible.
- **Subjective → LLM judge.** Reserved for the genuinely open responses (the written justifications, UI function descriptions, and transformation prompts). The judge grades against the rubric only (checklist + constraints + pass_condition), quotes its evidence, and emits per-field scores — never a pass/fail decision (the platform applies cut scores).
- **Roll-up:** field scores aggregate into the per-skill profile, keyed by the frozen skill IDs.

---

## 7. Routing / matching

- **Deterministic code, never an LLM.** For each project, take the candidate's per-skill scores, multiply by that project's weight column, and rank. The best-fit project wins.
- **Backbone gate first:** a candidate below the floor on S2 / S3 / S5 is not routed regardless of specialist strength.
- **Why code:** a hiring decision must be auditable and reproducible — a candidate should be able to see exactly how their number was computed.

---

## 8. Models

| Job | Engine | Why |
|---|---|---|
| Question generation (incl. images) | **Gemini 3 Pro** | Hardest reasoning task; image-capable; run rarely, so quality matters more than cost. |
| Objective scoring | **Code** | `answer == key`. Free, instant, reproducible. |
| Subjective scoring | **LLM judge** | The only items that need real judgment. Validate against human-graded answers before trusting it. |
| Routing / matching | **Code** | Auditable, fair, reproducible. |

---

## 9. Known issues and how we handle them

| Issue | Risk | How we handle it |
|---|---|---|
| **Skill-name drift** | Two cohorts scored against different skill names → scores don't compare | Canonical frozen vocabulary (§3); never rename/merge/split |
| **Model keys its own questions** | A confidently-wrong key marks a correct candidate wrong | Human review of objective keys (esp. perceptual ones); pilot before trusting scores |
| **AI can't make trustworthy pixel-alignment images** | i2i test images would be unprovable ground truth | Use real image pairs / injected flaws for i2i, not generation |
| **Subjective grading all-or-nothing** | A near-miss fails identically to a backwards answer | Rubric with partial credit (checklist points scored 1.0 / 0.5 / 0.0) |
| **"Deterministic" tasks an LLM only approximates** | Exact counts, even splits, no-two-in-a-row ordering come out wrong | Move these to code that runs after generation |
| **Answer-key leakage** | Scoring-only fields shown to candidates | Documented strip-list separating candidate-visible from scoring-only fields |
| **No validation yet** | Scores trusted before they're proven | Pilot on known-strong vs known-weak responders; check judge-vs-human agreement; pre-register a cut score |

---

## 10. Roadmap / build order

1. **Freeze the canonical skills.** Settle the three open items (§3.5), publish `skill.md` v1, regenerate `skillset.master.json`.
2. **Wire skills into the generator.** Feed `skillset.master.json` as the frozen `SKILLSET` input; regenerate the consolidated bank so every question is tagged to a frozen skill.
3. **Trust the keys.** Human-review objective keys; move deterministic chores (counts, even split, ordering) into post-generation code; add the candidate-visible vs scoring-only strip-list.
4. **Build the matcher.** ~30 lines of code: per-skill scores × weight matrix → route. Apply the backbone gate.
5. **Pilot & calibrate.** Run known-strong/known-weak responders, compute item discrimination, retire weak items, check judge-vs-human agreement, pre-register a cut score.
6. **Document new-project onboarding** (§11) and operate.

---

## 11. Adding a new project (without drift)

1. Run the generator with the **existing frozen `SKILLSET`** as input and the new SOP as the source.
2. The generator **maps** the new project onto existing skills and proposes any genuinely-new competency in `flags` (it never invents a scored skill).
3. A human reviews proposals; approved new skills are **appended** with new IDs and `skill.md` is version-bumped (§3.3).
4. Set the new project's weight column.
5. The matcher routes to the new project automatically from the updated weights — no change to existing skills, so all prior scores stay valid.

---

## 12. Artifacts

| Artifact | Role | Location |
|---|---|---|
| `assessment-system-plan.md` | This plan | this repo |
| `skill.md` | Canonical skills registry (human, authoritative) | this repo |
| `skillset.master.json` | Frozen skills + weights (machine) | this repo |
| `seed-prompt-master-image.md` | Consolidated generator prompt | this repo |
| `output-schema.multi.json` | Output schema for the consolidated bank | this repo |
| `assessment-prompt-master.md` | Run-time scorer for open responses | this repo |
| `seed-prompt-v3.md` (per project) | Single-project generator prompts (precursors) | working area, not yet in repo |

**Versioning:** keep `skill.md` and `skillset.master.json` on the same `skillset_version`. The per-project working copies in the broader working area are superseded by the in-repo versions.
