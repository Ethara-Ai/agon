# Assessment SOPs v2

Three clean, self-contained SOPs for the generalist annotator assessment system. Fresh
rewrites of the earlier drafts, no back-references, each rule stated once.

## The three-SOP flow

    SOP 1  skills-sop.md    (skills maintainer, append-only)
      in:  current skill.md + skillset.master.json + new-skill proposals from SOP 2
           (+ SOPs and feedback as context)
      out: skill.md + skillset.master.json, same skillset_version, append-only

    SOP 2  seed-sop.md      (question-bank generator)
      in:  frozen skillset.master.json + project SOP(s) + goldens [optional]
      out: one question-bank JSON (objective keys + subjective rubrics, every field
           tagged to frozen skills) + images bound by media_id, plus proposed
           additions in flags for any competency no skill covers yet

    SOP 3  scoring-sop.md    (subjective scorer / judge)
      in:  the question bank + a candidate's submission
      out: per-field scores, each carrying the frozen skills that field exercises,
           for code to roll up into the per-skill profile and route on

## How new skills enter the vocabulary

New skills are NOT discovered by SOP 1 reading raw SOPs. They surface from SOP 2: when
the generator builds a bank and meets a competency no frozen skill covers, it records a
proposed addition in flags. SOP 1 then appends that skill to skill.md and
skillset.master.json automatically. There is no human-approval gate. On the next run
the appended skill is part of the frozen skillset like any other.

The one exception is the very first run (GENESIS): with no files yet, SOP 1 builds the
initial skill set from the SOPs directly. After that it only ever appends.

## Append-only law (SOP 1)

skill.md and skillset.master.json are maintained in append-only mode. An existing
skill's id, name, scope, and its weights for existing projects are permanent and are
never rewritten. The only changes are additive: a new skill row with the next free id,
a new project weight column, and the weights that fill it. Ids are never reused or
renumbered. Nothing is deleted, a retired use becomes weight 0. This is what keeps a
score on a skill comparable across cohorts over time.

## Engines (from the system plan)

    SOP 1 skills      human-readable + machine twin, append-only       rare, build time
    SOP 2 generator   image-capable LLM (Gemini 3 Pro)                 rare, build time
    objective scoring plain code, answer equals key                    run time
    SOP 3 subjective  LLM judge against the rubric                     run time
    matcher           plain code, per-skill scores times weight matrix run time

## What changed from the old drafts

- Split the system cleanly into three SOPs: skills maintainer, generator, scorer.
- Made skill.md and skillset.master.json strictly append-only, with no human gate, new
  skills auto-append from the generator's proposed additions.
- The scorer now tags every graded field with the frozen skills it exercises, so the
  per-skill profile roll-up and routing are mechanical.
- Stripped superseded cross-references, decision-id jargon, and duplicated rules.
- House style and the i2i real-asset-only caveat stated once, cleanly.
