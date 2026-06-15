# Skill Registry - Entity Reference Verification

Purpose: the canonical skill vocabulary the hiring program scores and routes against
for the Entity Reference Verification task. Maintained append-only. Its machine twin is
skillset.master.json on the same skillset_version.

skillset_version: v1-genesis-2026-06-15
status: DRAFT, genesis run from a single SOP. Routing signals are not yet meaningful
because only one project exists. Add more projects before relying on routing.

## Changelog

- v1-genesis-2026-06-15. Initial set, 10 skills S1 to S10, one project
  entity-reference-verification, derived from the Entity Reference Verification SOP v1.

## Append-only governance

Frozen forever: a skill id, name, and scope. A skill is never renamed, re-scoped,
merged, split, or deleted. Allowed to evolve: a new skill appended with the next free
id, a new project weight column, re-tuned weights, and a sharpened description that does
not change meaning. Every change bumps skillset_version and adds a changelog line. New
skills after genesis arrive only as proposed additions handed in from the upstream bank
build and are appended automatically.

## Projects

| ID | Project | Task in one line | Stimulus source |
|---|---|---|---|
| P1 | entity-reference-verification | Decide whether a yellow-boxed target region and a green-boxed reference show the same real-world entity, pick one of six verdicts, and write a feature-named reason. | real image pairs, identity hinges on fine perceptual detail so generated images are not trustworthy ground truth |

## Canonical skills (S1 to S10)

Weights are 0 irrelevant to 5 critical. A skill applies to a project when its weight is
at least 1.

| ID | Skill | Description | ERV |
|---|---|---|:--:|
| S1 | Instruction Reading | Read the entity type and label first and load the identity criteria that apply to that type before judging the images. | 5 |
| S2 | Attention to Detail ★ | Notice the small construction or marking detail, a strap width, a logo position, a jersey number, a chest marking, that decides identity. | 5 |
| S3 | Calibrated Judgment ★ | Choose definitely only when the deciding feature is clearly visible, drop to likely under doubt, and skip a genuine coin flip rather than guess. | 5 |
| S4 | Objectivity ★ | Judge only on identity signals for the entity type and ignore non-identity content such as outfit, background, lighting, weather, and breed. | 5 |
| S5 | Identity Criteria Knowledge | Know what establishes identity for each entity type, face for a person, construction for a garment, individual markings for an animal, structure for a location. | 5 |
| S6 | Comparison | Weigh the target against the reference feature by feature and decide whether the identity features match or conflict. | 5 |
| S7 | Difference Detection | Spot the specific feature that conflicts between target and reference, such as a moved logo or a number present in one image and absent in the other. | 5 |
| S8 | Visual Quality Assessment | Judge whether a deciding feature is clearly visible or too occluded, distant, folded, or low resolution to support a confident call. | 4 |
| S9 | Data Integrity Screening | Recognize a broken input that must be flagged rather than verified, such as the same image on both sides, a watermark, a wrong box, or a same-photoshoot pair. | 4 |
| S10 | Clear Writing | Write a short reason that names the specific identity features used, so a reviewer can audit the decision from the features alone. | 5 |

★ marks the generalist backbone.

## Generalist backbone

S2, S3, S4 are the backbone. A candidate must clear a floor, target 60 of 100, on these
before any project match. Attention, calibration, and objectivity gate the task, a
candidate weak on them is routed nowhere.

## Routing signals

With one project these are not yet discriminating. The cleanest candidates once more
projects exist are S5 Identity Criteria Knowledge and S9 Data Integrity Screening, both
near-exclusive to verification-style work. Recorded here for continuity, not yet used
for routing.
