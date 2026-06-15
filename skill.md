# Skill Registry — Generalist Assessment

**skillset_version:** `v1-draft-2026-06-15`
**Status:** DRAFT — needs sign-off on (1) i2i inclusion, (2) weights, (3) granularity before it is frozen.

The **canonical, human-authoritative** skill registry for the generalist assessment. Its machine twin is [`skillset.master.json`](skillset.master.json) (fed to the generator as the frozen `SKILLSET` input and read by the matcher for routing weights). The two always carry the same `skillset_version`. See [`assessment-system-plan.md`](assessment-system-plan.md) for how the registry fits the wider system.

## Changelog

- **v1-draft-2026-06-15** — initial canonical set: 15 skills (S1–S15) across 4 projects, with the 0–5 routing-weight matrix, the generalist backbone, and routing signals.

## How this file changes (governance)

**Frozen forever (never changes):** a skill's **ID**, **name**, and **granularity / scope**. A skill is never renamed, never merged, never split. This is what keeps a score on a skill comparable across cohorts and over time.

**Updated each iteration (with a version bump + a changelog line):**
- A **new skill**, appended with the next free ID — only after human review of a generator `flags` proposal. Never invented automatically.
- A **new project's weight column**, or **re-tuned weights**.
- **Sharpened wording** of a description that does not change its meaning.

Rules:
1. Append-only for skills; existing IDs, names, and scopes are immutable.
2. New skills enter only through the human-review gate.
3. Every change bumps `skillset_version` and adds a changelog line.
4. Regenerate `skillset.master.json` to match, on the same version.

## Projects

| ID | Project | Task | Stimulus source |
|---|---|---|---|
| P1 | `260126-text-to-image-compare` | Pairwise image comparison on four axes + justification | generated images |
| P2 | `251216-video-artistic-style-reference` | Reference→target transformation-prompt writing | generated or real |
| P3 | `260123-high-res-dense-bbox-with-labels` | Dense UI annotation of every boxed element | real screenshot |
| P4 | `i2i-pixel-aligned-filter-flux2-nomask` | Three independent yes/no checks on one edit | real pairs / injected, **not** generated |

**i2i note:** kept in the routing vocabulary so people can still be matched to i2i work, but its test items must use real image pairs or programmatically injected flaws — AI-generated pixel-exact edits are not trustworthy ground truth. If i2i is dropped entirely, zero its weight column and remove P4.

## Canonical skills (S1–S15)

Weights are 0 (irrelevant) to 5 (critical) per project. A skill applies to a project when its weight is ≥ 1.

| ID | Skill | Description | T2I | Video | UI | i2i |
|---|---|---|:--:|:--:|:--:|:--:|
| S1 | Instruction Reading | Break the prompt or edit instruction into checkable parts, separating what must change from what must stay, before looking at the media. | 5 | 2 | 1 | 5 |
| S2 | Attention to Detail ★ | Zoom in and notice the small things, like a tiny artifact, an exact placement, or a small position shift, that decide the answer. | 5 | 4 | 4 | 5 |
| S3 | Calibrated Judgment ★ | Know when to pick a winner, call a tie or both bad, choose No, or skip, and never force or guess when genuinely unsure. | 4 | 4 | 4 | 5 |
| S4 | Objectivity | Judge only on what is actually visible, treat two options equally regardless of order, and never add detail that is not there. | 5 | 4 | 3 | 4 |
| S5 | Process & Coverage ★ | Follow the SOP steps, gates, and tools in order, and cover every required box, region, or rated axis before submitting. | 3 | 4 | 5 | 4 |
| S6 | Difference Detection | Compare a before and after, or a reference and target, and spot exactly what changed, moved, was added, or removed. | 1 | 5 | 0 | 5 |
| S7 | Alignment Perception | Detect any shift, zoom, crop, or resize in areas that should have stayed identical, judging position and scale rather than content. | 1 | 0 | 0 | 5 |
| S8 | Artifact Detection | Catch AI generation errors such as extra fingers, warped faces, gibberish text, and broken shapes, without over-flagging deliberate style. | 5 | 1 | 0 | 5 |
| S9 | Comparison | Weigh two outputs against each other fairly on a given axis and decide which one is better. | 5 | 1 | 0 | 1 |
| S10 | Quality Judgment | Tell a sharp, well made image from a blurry, distorted, or off color one. | 5 | 2 | 0 | 1 |
| S11 | Counting | Count objects exactly and tie each attribute, like color or size, to the correct object. | 4 | 1 | 1 | 2 |
| S12 | UI Knowledge | Recognize common applications and know what their buttons, icons, tabs, and menus do. | 0 | 0 | 5 | 0 |
| S13 | Scene Description | Break a scene into objects, people, placement, lighting, and background, and describe each precisely with clear spatial language. | 1 | 5 | 1 | 0 |
| S14 | Art Vocabulary | Use style and art terms correctly, such as photorealistic, dappled shadows, shading, and lighting direction. | 1 | 5 | 0 | 0 |
| S15 | Clear Writing | Explain a decision or a function in a few plain, concrete sentences that point to real evidence, verb led and not padded. | 4 | 5 | 5 | 1 |

★ = generalist backbone.

## Generalist backbone

**S2, S3, S5** are weighted 3–5 across every project. A candidate must clear a floor (target **60/100**) on these before any project match — a spiky specialist with poor attention, calibration, or process is routed nowhere.

## Routing signals

Each of these is near-exclusive to one project (weight 5 there, ≤ 1 elsewhere), so a strong score is the cleanest routing signal:

| Skill | Routes to |
|---|---|
| S7 Alignment Perception | i2i |
| S12 UI Knowledge | UI (high-res dense) |
| S13 Scene Description | Video |
| S14 Art Vocabulary | Video |
| S9 Comparison | T2I |
| S10 Quality Judgment | T2I |

## Open items before freezing v1

1. **i2i inclusion** — keep (real-asset items only) or drop entirely.
2. **Weights** — confirm every column with the project owners.
3. **Granularity** — confirm 15 is right (for example whether S13 and S14 stay separate).
