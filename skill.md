# Skill Registry

The canonical, append-only vocabulary of human competencies for the generalist data-annotation hiring program. This is the human mirror of `skillset.registry.json`. The two files always carry the same `skillset_version` and never disagree on any shared value. The skill-extraction SOP owns and writes both.

Version: 2
Mode: append

## Changelog

- 2026-06-16 v2 APPEND project i2i-pixel-aligned-filter-flux2-nomask: reused S1, S2, S3, S4, S5; added S8 Specification Conformance, S9 Spatial Alignment, S10 Plausibility Assessment, S11 Systematic Coverage. No boundary sharpened. No existing id, name, description, boundary, or prior weight changed.
- 2026-06-16 v1 GENESIS project entity-reference-verification: added S1 to S7.

## Append-only contract

An existing skill's id, name, description, and every prior project weight are permanent. The only changes ever made are additive: a new skill row, a new project weight column on a skill the new project exercises, and a single append-only suffix on a boundary. Ids are assigned in order and never reused or renumbered. Nothing is ever renamed, re-scoped, merged, split, or deleted. A finer sub ability a richer later project reveals is an added sibling with a distinguishing boundary, never a split. A proven duplicate is reconciled by an append-only alias record, never a rename or a delete, so no frozen id ever changes meaning.

## Projects

| Pid | Project |
| --- | --- |
| P1 | entity-reference-verification |
| P2 | i2i-pixel-aligned-filter-flux2-nomask |

## Canonical skills

| id | name | description | boundary | entity-reference-verification | i2i-pixel-aligned-filter-flux2-nomask |
| --- | --- | --- | --- | --- | --- |
| S1 | Instruction Reading | Decompose a stated requirement into the distinct conditions and criteria that govern a judgment before making it. | Distinct from applying those criteria to the evidence and from judging the underlying content. | 4 | 4 |
| S2 | Attention to Detail | Detect small but consequential visual or textual features that determine a judgment. | Distinct from comparing two observations and from deciding how strongly the evidence supports a conclusion. | 5 | 5 |
| S3 | Difference Detection | Identify the specific correspondences and conflicts between two observations, such as matching, missing, or differing features. | Distinct from noticing a single feature in isolation and from ranking options by overall quality. | 5 | 5 |
| S4 | Objectivity | Base a conclusion only on the evidence genuinely relevant to it, excluding incidental signals, surface resemblance, and category-level similarity. | Distinct from calibrating confidence when the relevant evidence is incomplete. | 5 | 4 |
| S5 | Calibrated Judgment | Match the confidence of a conclusion to the clarity and completeness of the available evidence, and recognize when the evidence is too thin to decide at all. | Distinct from judging whether the evidence is relevant, and from recognizing that the source material itself is unfit to judge. | 5 | 3 |
| S6 | Source Validity Judgment | Recognize when the source material itself is unfit for the intended judgment, separate from any difficulty in reaching that judgment. | Distinct from being unable to decide a well-formed case, which is a confidence-calibration outcome. | 3 | |
| S7 | Clear Writing | Express a conclusion and the specific evidence supporting it concisely and concretely, so another reader can audit the reasoning. | Distinct from the correctness of the conclusion being explained. | 4 | |
| S8 | Specification Conformance | Decide whether a realized result fulfills its governing instruction completely and correctly while introducing nothing the instruction did not call for. | Distinct from detecting the raw differences between two observations, which feeds this, and from judging the intrinsic realism of the result. | | 5 |
| S9 | Spatial Alignment | Judge whether elements hold the same position, scale, and framing across two visual fields, independent of what those elements depict. | Distinct from comparing the content of two observations, this concerns only geometric position and scale. | | 5 |
| S10 | Plausibility Assessment | Judge whether an artifact is consistent with real-world physical, anatomical, and structural plausibility, identifying signs of fabrication or breakage. | Distinct from noticing a feature and from comparing against a reference, this evaluates a single artifact against knowledge of how real things look and behave. | | 5 |
| S11 | Systematic Coverage | Work through every item in a fixed set of required checks so that nothing in scope is left unexamined. | Distinct from the acuity to notice a small feature within an item, this ensures every required item is examined at all. | | 3 |

A blank weight cell means the project does not exercise the skill and is read as 0.

## Reconciliation note

APPEND run over project i2i-pixel-aligned-filter-flux2-nomask. PASS A recovered nine competencies blind to the registry. Five bound to frozen skills by meaning and were reused: Instruction Reading to S1, Attention to Detail to S2, Difference Detection to S3, the proposed Criterion Isolation folded into S4 Objectivity as the same restrict-to-relevant-evidence discipline, and the proposed Conservative Calibration folded into S5 Calibrated Judgment as confidence matched to evidence strength. Four had no registry cover and were added: S8 Specification Conformance (the all-and-only instruction verdict), S9 Spatial Alignment (geometric position and scale, content-independent), S10 Plausibility Assessment (real-world plausibility of a single artifact), and S11 Systematic Coverage (exhaustive multi-region inspection). S6 Source Validity Judgment and S7 Clear Writing were not exercised by this project, since it has no abstention gate and no written-justification deliverable, so they carry no weight column for it.
