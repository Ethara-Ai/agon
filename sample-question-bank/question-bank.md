# Question Bank

**Target project:** entity-reference-verification (P1)

## Provenance

| Field | Value |
| --- | --- |
| Skillset version | 2 |
| Count setting | 25 |
| Type | Objective |
| Arrangement | mixed |
| Pool factor | 1 |
| Performance construct | maximal |
| Realized type mix | 25 objective fields and 0 subjective fields. |
| House style | No em dashes, no semicolons, no emojis, no markdown links, no casual filler, plain text only. |

**Allocation formula**

largest-remainder over the entity-reference-verification weight column with a representation floor of 2 for weight 4 to 5 and 1 for weight 1 to 3, computed over the objective-assessable skills after S7 was reduced out under the Objective type

**Validity rationale**

Content validity is the primary warrant and is fixed a priori by the blueprint, which maps items to the entity-reference-verification weight column so the construct domain is covered in proportion to job criticality. Construct validity is carried by the claim then evidence then task chain, every in-scope and objective-assessable skill is sampled, every weight four or five skill is sampled across more than one item, and a boundary-driven evidence-exclusion list keeps each item deciding on one construct so a low score is attributable to the right skill. Criterion and predictive validity is marked OPEN, no criterion is collected in this pipeline and the deliberate use of generic scenarios in place of the real production task lowers the fidelity that would otherwise drive prediction, so the predictive coefficient remains a hypothesis for a downstream criterion study and is never a property this generator confers.

**Cut score philosophy**

Criterion-referenced. The bank states standard-setting inputs only, a provisional minimally-competent estimate per item and a stated pass target, and applies no cutoff. The downstream scorer owns the arithmetic and the platform owns every cutoff.

**Typical performance gap**

The will-do facet, sustained diligence and consistency across a long production batch, is only partly observable in a short maximal-performance bank and is named here as an out-of-instrument limitation.

### Blueprint table

| Skill ID | Skill name | Project weight | Target quota | Floor | Allocated | Deciding | Traps | Cognitive level |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| S1 | Instruction Reading | 4 | 3.7 | 2 | 4 | 4 | 0 | analyze |
| S2 | Attention to Detail | 5 | 4.63 | 2 | 5 | 5 | 1 | analyze |
| S3 | Difference Detection | 5 | 4.63 | 2 | 5 | 5 | 1 | analyze |
| S4 | Objectivity | 5 | 4.63 | 2 | 4 | 4 | 1 | evaluate |
| S5 | Calibrated Judgment | 5 | 4.63 | 2 | 4 | 4 | 0 | evaluate |
| S6 | Source Validity Judgment | 3 | 2.78 | 1 | 3 | 2 | 0 | evaluate |

## Skillset usage map

| Skill ID | Name | Items |
| --- | --- | --- |
| S1 | Instruction Reading | 3, 9, 15, 21 |
| S2 | Attention to Detail | 1, 7, 13, 19, 24 |
| S3 | Difference Detection | 2, 8, 14, 20, 25 |
| S4 | Objectivity | 4, 10, 16, 22 |
| S5 | Calibrated Judgment | 5, 11, 17, 23 |
| S6 | Source Validity Judgment | 6, 12, 18 |

## Question bank

### Item 1

| Field | Value |
| --- | --- |
| Project | entity-reference-verification |
| Skills | S2 Attention to Detail |
| Is trap | no |
| Cognitive level | analyze |
| Flag for review | no |
| Difficulty | Provisional moderate, to be overwritten by observed p-value. |

**Provisional MCC estimate:** A minimally competent worker isolates the small deciding feature past the salient decoy and selects it. Provisional and non-load-bearing.

**Prompt**

A single shipping label is shown. Decide which statement about the label is correct based only on what the label displays.

**Media**

- `q1-stimulus` (image status: pending, key confidence: low, human key review: yes)
  - placeholder: A printed shipping label. The recipient block reads ASHTON RIVERA, 4127 MAPLE COURT. A large bold service banner across the top reads PRIORITY OVERNIGHT in red and is the most prominent element. The tracking number is printed in small grey type as 7741 2290 0163. In the lower right a small box holds a single printed character, the letter B, which marks the sort zone.

#### Field: Correct statement about the label (`label_feature`)

| Field | Value |
| --- | --- |
| Type | objective |
| Skills | S2 Attention to Detail |
| Unconfirmed | yes |
| Key confidence | low |
| Requires human key review | yes |

Options:

- The lower-right sort-zone box contains the letter B. **(answer)**
- The lower-right sort-zone box contains the letter D.
- The label displays no sort-zone box at all.

**Answer:** The lower-right sort-zone box contains the letter B.

**Reason:** The placeholder states the small lower-right sort-zone box contains the single letter B. The bold red PRIORITY OVERNIGHT banner is a salient decoy that does not bear on the sort zone, and reading B as the similar letter D or overlooking the small box are the attention failures the distractors capture.

---

### Item 2

| Field | Value |
| --- | --- |
| Project | entity-reference-verification |
| Skills | S3 Difference Detection |
| Is trap | no |
| Cognitive level | analyze |
| Flag for review | no |
| Difficulty | Provisional moderate, to be overwritten by observed p-value. |

**Provisional MCC estimate:** A minimally competent worker scans both observations and names the single conflicting field. Provisional and non-load-bearing.

**Prompt**

Two delivery manifests for the same route are shown side by side. Identify the one specific discrepancy between them.

**Media**

- `q2-stimulus` (image status: pending, key confidence: low, human key review: yes)
  - placeholder: Two manifests labeled Copy A and Copy B, each listing four stops. Copy A stop order is 1 Birch Depot, 2 Halden Plant, 3 Corso Mall, 4 Vale Clinic. Copy B stop order is 1 Birch Depot, 2 Halden Plant, 3 Corso Mall, 4 Vale Clinic. The total parcel count reads 58 on Copy A and 58 on Copy B. The driver code reads DRV-204 on Copy A and DRV-240 on Copy B.

#### Field: The single discrepancy between the manifests (`discrepancy`)

| Field | Value |
| --- | --- |
| Type | objective |
| Skills | S3 Difference Detection |
| Unconfirmed | yes |
| Key confidence | low |
| Requires human key review | yes |

Options:

- The two manifests differ in their driver code. **(answer)**
- The two manifests differ in their total parcel count.
- The two manifests differ in their stop order.

**Answer:** The two manifests differ in their driver code.

**Reason:** Every field matches across the two manifests except the driver code, DRV-204 on Copy A against DRV-240 on Copy B. The parcel count reads 58 on both and the stop orders are identical, so the transposed driver code is the only conflict.

---

### Item 3

| Field | Value |
| --- | --- |
| Project | entity-reference-verification |
| Skills | S1 Instruction Reading |
| Is trap | no |
| Cognitive level | analyze |
| Flag for review | no |
| Difficulty | Provisional moderate, to be overwritten by observed p-value. |

**Provisional MCC estimate:** A minimally competent worker parses the instruction and lists every condition with none added or dropped. Provisional and non-load-bearing.

**Prompt**

Read the following coupon rule, then identify which list correctly captures every separate condition a purchase must satisfy to qualify. Rule: The coupon applies to a single order placed in store, only on a weekday, only when the order subtotal is at least forty dollars before tax, and only when the order contains no clearance items. Choose the option that lists the distinct conditions without adding or dropping any.

#### Field: The complete set of stated conditions (`condition_set`)

| Field | Value |
| --- | --- |
| Type | objective |
| Skills | S1 Instruction Reading |
| Unconfirmed | yes |
| Key confidence | high |
| Requires human key review | no |

Options:

- Placed in store, placed on a weekday, subtotal at least forty dollars before tax, and contains no clearance items. **(answer)**
- Placed in store, placed on a weekday, and subtotal at least forty dollars before tax.
- Placed in store, subtotal at least forty dollars before tax, contains no clearance items, and free shipping included.

**Answer:** Placed in store, placed on a weekday, subtotal at least forty dollars before tax, and contains no clearance items.

**Reason:** The rule states four distinct conditions, in store, weekday, subtotal at least forty dollars before tax, and no clearance items. The second option drops the no-clearance condition and the third omits the weekday condition while inventing a free-shipping term the rule never states.

---

### Item 4

| Field | Value |
| --- | --- |
| Project | entity-reference-verification |
| Skills | S4 Objectivity |
| Is trap | no |
| Cognitive level | evaluate |
| Flag for review | no |
| Difficulty | Provisional moderate, to be overwritten by observed p-value. |

**Provisional MCC estimate:** A minimally competent worker keys on the identifying evidence and ignores category resemblance. Provisional and non-load-bearing.

**Prompt**

A reference tool and a candidate tool are shown. Decide whether the candidate is the same individual unit as the reference, using only the evidence that identifies a specific unit.

**Media**

- `q4-stimulus` (image status: pending, key confidence: medium, human key review: yes)
  - placeholder: The reference is a cordless drill, model TX-9, in yellow housing, with engraved unit serial SN-44817 on its base. The candidate is a cordless drill, also model TX-9, also in yellow housing, with engraved unit serial SN-44871 on its base. Both share the same model, color, and battery type. The engraved unit serial is the only unit-specific identifier, and the two differ, SN-44817 against SN-44871.

#### Field: Same individual unit or not (`same_unit_verdict`)

| Field | Value |
| --- | --- |
| Type | objective |
| Skills | S4 Objectivity |
| Unconfirmed | yes |
| Key confidence | medium |
| Requires human key review | yes |

Options:

- The candidate is a different unit, because the unit serials differ. **(answer)**
- The candidate is the same unit, because the model and color match.
- The candidate is the same unit, because both are cordless drills.

**Answer:** The candidate is a different unit, because the unit serials differ.

**Reason:** Only the engraved unit serial identifies a specific unit, and the two differ, SN-44817 against SN-44871. Matching model, color, and product category are category-level resemblances that do not identify an individual unit, so resting the verdict on them is the objectivity failure the distractors capture.

---

### Item 5

| Field | Value |
| --- | --- |
| Project | entity-reference-verification |
| Skills | S5 Calibrated Judgment |
| Is trap | no |
| Cognitive level | evaluate |
| Flag for review | no |
| Difficulty | Provisional moderate, to be overwritten by observed p-value. |

**Provisional MCC estimate:** A minimally competent worker selects the defensible confidence band for the stated evidence. Provisional and non-load-bearing.

**Prompt**

A worker must decide whether two records describe the same person. The only evidence available is that both records share the surname Okonkwo and both list the city Leeds. No given name, date of birth, identifier, or address is available on either record. Choose the conclusion the available evidence defensibly supports.

#### Field: The defensible conclusion (`confidence_band`)

| Field | Value |
| --- | --- |
| Type | objective |
| Skills | S5 Calibrated Judgment |
| Unconfirmed | yes |
| Key confidence | medium |
| Requires human key review | no |

Options:

- The evidence is insufficient to determine whether the records describe the same person. **(answer)**
- The records confirm the same person, because the surname and city match.
- The records describe different people, because no identifier is shared.

**Answer:** The evidence is insufficient to determine whether the records describe the same person.

**Reason:** A shared common surname and city are consistent with many distinct individuals and carry no unique identifier, so the evidence neither confirms nor rules out the same person. Treating the weak partial match as a confirmation, or the absence of a shared identifier as a positive exclusion, both overstate what thin evidence can support.

---

### Item 6

| Field | Value |
| --- | --- |
| Project | entity-reference-verification |
| Skills | S6 Source Validity Judgment |
| Is trap | no |
| Cognitive level | evaluate |
| Flag for review | no |
| Difficulty | Provisional moderate, to be overwritten by observed p-value. |

**Provisional MCC estimate:** A minimally competent worker judges whether the source can support the intended check. Provisional and non-load-bearing.

**Prompt**

A worker is asked to verify a person's date of birth from the document provided. Decide whether the provided document is a fit source for that verification.

**Media**

- `q6-stimulus` (image status: pending, key confidence: medium, human key review: no)
  - placeholder: The provided document is a retail purchase receipt. It shows a store name, an itemized list of three grocery products with prices, a subtotal, a tax line, a total of 23 dollars and 14 cents, and a transaction time stamp. The receipt contains no name and no date of birth. It is fully legible and undamaged.

#### Field: Fit source for the verification or not (`source_fitness`)

| Field | Value |
| --- | --- |
| Type | objective |
| Skills | S6 Source Validity Judgment |
| Unconfirmed | yes |
| Key confidence | medium |
| Requires human key review | no |

Options:

- The document is unfit for the task, because a purchase receipt does not carry a date of birth. **(answer)**
- The document is fit, and the date of birth can be read from the time stamp.
- The document is fit, but the date of birth is too faint to read.

**Answer:** The document is unfit for the task, because a purchase receipt does not carry a date of birth.

**Reason:** A purchase receipt records a transaction and carries no date-of-birth field, so it is structurally unfit for verifying a date of birth regardless of legibility. The transaction time stamp is the sale time and not a birth date, and the receipt is stated to be fully legible, so the defect is the fitness of the source and not difficulty in reading it.

---

### Item 7

| Field | Value |
| --- | --- |
| Project | entity-reference-verification |
| Skills | S2 Attention to Detail |
| Is trap | yes |
| Cognitive level | analyze |
| Flag for review | no |
| Difficulty | Provisional hard, to be overwritten by observed p-value. |

**Provisional MCC estimate:** A minimally competent worker isolates the small deciding feature past the salient decoy and selects it. Provisional and non-load-bearing.

**Prompt**

A single laboratory sample vial label is shown. Decide which statement about the label is correct based only on what it displays.

**Media**

- `q7-stimulus` (image status: pending, key confidence: low, human key review: yes)
  - placeholder: A vial label with a wide bright orange hazard band running across its center, the most prominent element, carrying no text. Above the band the sample name reads SERUM LOT. Below the band, in small black type, the dilution factor is printed as 1 to 100. Beside the dilution factor a small printed batch position reads 7. The number printed beside the dilution factor is the digit 7.

#### Field: Correct statement about the label (`label_feature`)

| Field | Value |
| --- | --- |
| Type | objective |
| Skills | S2 Attention to Detail |
| Unconfirmed | yes |
| Key confidence | low |
| Requires human key review | yes |

Options:

- The batch position printed beside the dilution factor is 7. **(answer)**
- The orange hazard band states the batch position.
- The batch position printed beside the dilution factor is 1.

**Answer:** The batch position printed beside the dilution factor is 7.

**Reason:** The deciding detail is the small batch-position digit printed beside the dilution factor, which is 7. The wide orange hazard band is the most salient element but carries no text, and the 1 in the dilution factor 1 to 100 is not the batch position, so both distractors capture attention failures that follow the salient decoy or grab the wrong small number.

---

### Item 8

| Field | Value |
| --- | --- |
| Project | entity-reference-verification |
| Skills | S3 Difference Detection |
| Is trap | no |
| Cognitive level | analyze |
| Flag for review | no |
| Difficulty | Provisional moderate, to be overwritten by observed p-value. |

**Provisional MCC estimate:** A minimally competent worker scans both observations and names the single conflicting field. Provisional and non-load-bearing.

**Prompt**

Two seating charts for the same room are shown. Identify the one specific discrepancy between them.

**Media**

- `q8-stimulus` (image status: pending, key confidence: low, human key review: yes)
  - placeholder: Two charts labeled Draft 1 and Draft 2, each with three rows of seats. Row A on both is Patel, Nguyen, Olsen. Row B on both is Romano, Singh, Adeyemi. Row C on Draft 1 is Walsh, Costa, Ibarra. Row C on Draft 2 is Walsh, Costa, Ibanez. Every name matches across the two charts except the third seat of row C, Ibarra against Ibanez. Both charts have three rows.

#### Field: The single discrepancy between the charts (`discrepancy`)

| Field | Value |
| --- | --- |
| Type | objective |
| Skills | S3 Difference Detection |
| Unconfirmed | yes |
| Key confidence | low |
| Requires human key review | yes |

Options:

- The charts differ at the third seat of row C. **(answer)**
- The charts differ at the first seat of row A.
- The charts differ in the number of rows.

**Answer:** The charts differ at the third seat of row C.

**Reason:** Every seat assignment matches across the two charts except the third seat of row C, Ibarra on Draft 1 against Ibanez on Draft 2. Row A seat one is Patel on both and both charts have three rows, so neither distractor names a real difference.

---

### Item 9

| Field | Value |
| --- | --- |
| Project | entity-reference-verification |
| Skills | S1 Instruction Reading |
| Is trap | no |
| Cognitive level | analyze |
| Flag for review | no |
| Difficulty | Provisional moderate, to be overwritten by observed p-value. |

**Provisional MCC estimate:** A minimally competent worker parses the instruction and lists every condition with none added or dropped. Provisional and non-load-bearing.

**Prompt**

Read the following parking sign, then identify which list correctly captures every separate condition under which parking is permitted. Sign: Parking permitted only with a valid resident permit, only between 6 in the evening and 8 in the morning, and not at any time on street-cleaning days. Choose the option that lists the distinct conditions without adding or dropping any.

#### Field: The complete set of stated conditions (`condition_set`)

| Field | Value |
| --- | --- |
| Type | objective |
| Skills | S1 Instruction Reading |
| Unconfirmed | yes |
| Key confidence | high |
| Requires human key review | no |

Options:

- A valid resident permit is held, the time is between 6 in the evening and 8 in the morning, and the day is not a street-cleaning day. **(answer)**
- A valid resident permit is held, and the time is between 6 in the evening and 8 in the morning.
- A valid resident permit is held, the time is between 6 in the evening and 8 in the morning, and the vehicle is a passenger car.

**Answer:** A valid resident permit is held, the time is between 6 in the evening and 8 in the morning, and the day is not a street-cleaning day.

**Reason:** The sign states three distinct conditions, a valid resident permit, the evening-to-morning time window, and not a street-cleaning day. The second option drops the street-cleaning condition and the third replaces it with a passenger-car condition the sign never states.

---

### Item 10

| Field | Value |
| --- | --- |
| Project | entity-reference-verification |
| Skills | S4 Objectivity |
| Is trap | no |
| Cognitive level | evaluate |
| Flag for review | no |
| Difficulty | Provisional moderate, to be overwritten by observed p-value. |

**Provisional MCC estimate:** A minimally competent worker keys on the identifying evidence and ignores category resemblance. Provisional and non-load-bearing.

**Prompt**

A reference dog and a candidate dog are shown. Decide whether the candidate is the same registered individual as the reference, using only the evidence that identifies a specific registered animal.

**Media**

- `q10-stimulus` (image status: pending, key confidence: medium, human key review: yes)
  - placeholder: The reference is a beagle with a registered ear-tattoo identifier reading 3KJ. The candidate is a beagle with a registered ear-tattoo identifier reading 3KL. Both are beagles of similar size with the same tri-color coat. The registered ear-tattoo identifier is the only individual identifier, and the two differ, 3KJ against 3KL.

#### Field: Same registered individual or not (`same_individual_verdict`)

| Field | Value |
| --- | --- |
| Type | objective |
| Skills | S4 Objectivity |
| Unconfirmed | yes |
| Key confidence | medium |
| Requires human key review | yes |

Options:

- The candidate is a different registered individual, because the ear-tattoo identifiers differ. **(answer)**
- The candidate is the same registered individual, because both are tri-color beagles.
- The candidate is the same registered individual, because the coats match.

**Answer:** The candidate is a different registered individual, because the ear-tattoo identifiers differ.

**Reason:** The registered ear-tattoo identifier is the only feature that names a specific registered animal, and the two differ, 3KJ against 3KL. Shared breed, size, and coat color are category-level resemblances common to many beagles, so resting the verdict on them is the objectivity failure the distractors capture.

---

### Item 11

| Field | Value |
| --- | --- |
| Project | entity-reference-verification |
| Skills | S5 Calibrated Judgment |
| Is trap | no |
| Cognitive level | evaluate |
| Flag for review | no |
| Difficulty | Provisional moderate, to be overwritten by observed p-value. |

**Provisional MCC estimate:** A minimally competent worker selects the defensible confidence band for the stated evidence. Provisional and non-load-bearing.

**Prompt**

A worker must decide whether two product photos show the same individual collectible figurine. Both figurines are the same limited model in the same paint scheme. The only feature that distinguishes individual units is a hand-numbered base, and in the available evidence the base number is recorded for the reference figurine as 042 of 500 but was not recorded for the candidate figurine. Choose the conclusion the available evidence defensibly supports.

#### Field: The defensible conclusion (`confidence_band`)

| Field | Value |
| --- | --- |
| Type | objective |
| Skills | S5 Calibrated Judgment |
| Unconfirmed | yes |
| Key confidence | medium |
| Requires human key review | no |

Options:

- The evidence is insufficient to determine whether the figurines are the same individual unit, because the candidate base number was not recorded. **(answer)**
- The figurines are the same individual unit, because the model and paint scheme match.
- The figurines are different individual units, because only the reference base number is recorded.

**Answer:** The evidence is insufficient to determine whether the figurines are the same individual unit, because the candidate base number was not recorded.

**Reason:** The hand-numbered base is the only feature that distinguishes individual units, and the candidate number was not recorded, so the evidence cannot confirm or rule out the same unit. A matching model and paint scheme are shared across the whole limited run and do not identify a unit, and a missing record is not positive evidence of a different unit, so both alternatives overstate the available evidence.

---

### Item 12

| Field | Value |
| --- | --- |
| Project | entity-reference-verification |
| Skills | S6 Source Validity Judgment |
| Is trap | no |
| Cognitive level | evaluate |
| Flag for review | no |
| Difficulty | Provisional moderate, to be overwritten by observed p-value. |

**Provisional MCC estimate:** A minimally competent worker judges whether the source can support the intended check. Provisional and non-load-bearing.

**Prompt**

A worker is asked to read a meter's final reading from the photo provided. Decide whether the provided photo is a fit source for that reading.

**Media**

- `q12-stimulus` (image status: pending, key confidence: medium, human key review: yes)
  - placeholder: The photo shows an analog utility meter. The entire dial face is obscured by heavy condensation and glare so that none of the digit wheels can be made out. The meter housing and pipe are visible and in frame, but no digit on the reading is resolvable. The placeholder confirms this is the correct meter and not a different meter, but its reading area is unreadable.

#### Field: Fit source for the reading or not (`source_fitness`)

| Field | Value |
| --- | --- |
| Type | objective |
| Skills | S6 Source Validity Judgment |
| Unconfirmed | yes |
| Key confidence | medium |
| Requires human key review | yes |

Options:

- The photo is unfit for the task, because the reading area is fully obscured and no digit is resolvable. **(answer)**
- The photo is fit, and the final reading is the lowest visible digit.
- The photo is unfit, because it shows a different meter than the one under review.

**Answer:** The photo is unfit for the task, because the reading area is fully obscured and no digit is resolvable.

**Reason:** The dial face is entirely obscured by condensation and glare and no digit is resolvable, so the photo cannot support a meter reading and is unfit for the task. No digit is visible to read, and the placeholder states the meter is the correct one and not a different meter, so the defect is the unreadable reading area and not a wrong subject.

---

### Item 13

| Field | Value |
| --- | --- |
| Project | entity-reference-verification |
| Skills | S2 Attention to Detail |
| Is trap | no |
| Cognitive level | analyze |
| Flag for review | no |
| Difficulty | Provisional moderate, to be overwritten by observed p-value. |

**Provisional MCC estimate:** A minimally competent worker isolates the small deciding feature past the salient decoy and selects it. Provisional and non-load-bearing.

**Prompt**

A single event wristband is shown. Decide which statement about the wristband is correct based only on what it displays.

**Media**

- `q13-stimulus` (image status: pending, key confidence: low, human key review: yes)
  - placeholder: A fabric event wristband printed with a large festival logo and the word ACCESS in big bold letters as its most prominent feature. Along the lower edge, in small print, the access tier is shown as TIER 2. No other tier marking appears on the band.

#### Field: Correct statement about the wristband (`label_feature`)

| Field | Value |
| --- | --- |
| Type | objective |
| Skills | S2 Attention to Detail |
| Unconfirmed | yes |
| Key confidence | low |
| Requires human key review | yes |

Options:

- The small lower-edge tier text reads TIER 2. **(answer)**
- The small lower-edge tier text reads TIER 3.
- The wristband shows no tier text at all.

**Answer:** The small lower-edge tier text reads TIER 2.

**Reason:** The tier is printed small along the lower edge and reads TIER 2. The large ACCESS lettering and festival logo are salient decoys that do not state the tier, and reading the tier as 3 or missing the small tier text entirely are the attention failures the distractors capture.

---

### Item 14

| Field | Value |
| --- | --- |
| Project | entity-reference-verification |
| Skills | S3 Difference Detection |
| Is trap | yes |
| Cognitive level | analyze |
| Flag for review | no |
| Difficulty | Provisional hard, to be overwritten by observed p-value. |

**Provisional MCC estimate:** A minimally competent worker scans both observations and names the single conflicting field. Provisional and non-load-bearing.

**Prompt**

Two ingredient lists for what is claimed to be the same product are shown. Identify the one specific discrepancy between them.

**Media**

- `q14-stimulus` (image status: pending, key confidence: low, human key review: yes)
  - placeholder: Two lists labeled Pack X and Pack Y, each with six ingredients in the same order. Pack X reads water, sugar, citric acid, sodium citrate, natural flavor, red 40. Pack Y reads water, sugar, citric acid, sodium benzoate, natural flavor, red 40. Five of the six entries are identical and in the same positions. The fourth entry differs, sodium citrate on Pack X against sodium benzoate on Pack Y. The sixth entry, red 40, is the same on both.

#### Field: The single discrepancy between the lists (`discrepancy`)

| Field | Value |
| --- | --- |
| Type | objective |
| Skills | S3 Difference Detection |
| Unconfirmed | yes |
| Key confidence | low |
| Requires human key review | yes |

Options:

- The two lists differ at the fourth entry only. **(answer)**
- The two lists are identical at every entry.
- The two lists differ at the sixth entry only.

**Answer:** The two lists differ at the fourth entry only.

**Reason:** Five of the six entries match in content and position and only the fourth differs, sodium citrate on Pack X against sodium benzoate on Pack Y. The heavy overlap lures a reader toward calling the lists identical, and the sixth entry red 40 is the same on both, so the single conflict is the fourth entry.

---

### Item 15

| Field | Value |
| --- | --- |
| Project | entity-reference-verification |
| Skills | S1 Instruction Reading |
| Is trap | no |
| Cognitive level | analyze |
| Flag for review | no |
| Difficulty | Provisional moderate, to be overwritten by observed p-value. |

**Provisional MCC estimate:** A minimally competent worker parses the instruction and lists every condition with none added or dropped. Provisional and non-load-bearing.

**Prompt**

Read the following contest rule, then identify which list correctly captures every separate condition an entry must satisfy to be valid. Rule: An entry is valid only if it is submitted by a resident of the state, only if the entrant is at least eighteen years old, only if it is received before the closing date, and only if it includes a proof of purchase. Choose the option that lists the distinct conditions without adding or dropping any.

#### Field: The complete set of stated conditions (`condition_set`)

| Field | Value |
| --- | --- |
| Type | objective |
| Skills | S1 Instruction Reading |
| Unconfirmed | yes |
| Key confidence | high |
| Requires human key review | no |

Options:

- Submitted by a state resident, entrant at least eighteen years old, received before the closing date, and includes a proof of purchase. **(answer)**
- Submitted by a state resident, entrant at least eighteen years old, and received before the closing date.
- Submitted by a state resident, received before the closing date, includes a proof of purchase, and limited to one entry per day.

**Answer:** Submitted by a state resident, entrant at least eighteen years old, received before the closing date, and includes a proof of purchase.

**Reason:** The rule states four distinct conditions, state residency, age at least eighteen, received before the closing date, and a proof of purchase. The second option drops the proof-of-purchase condition and the third omits the age condition while inventing a one-entry-per-day limit the rule never states.

---

### Item 16

| Field | Value |
| --- | --- |
| Project | entity-reference-verification |
| Skills | S4 Objectivity |
| Is trap | yes |
| Cognitive level | evaluate |
| Flag for review | no |
| Difficulty | Provisional hard, to be overwritten by observed p-value. |

**Provisional MCC estimate:** A minimally competent worker keys on the identifying evidence and ignores surface resemblance. Provisional and non-load-bearing.

**Prompt**

A reference storefront and a candidate storefront are shown. Decide whether the candidate is the same specific location as the reference, using only the evidence that identifies a specific location.

**Media**

- `q16-stimulus` (image status: pending, key confidence: medium, human key review: yes)
  - placeholder: The reference storefront shows a coffee chain sign in the chain distinctive green script, with the street address 88 Harlow Street on the door. The candidate storefront shows the same coffee chain sign in the same green script, with the street address 88 Harlowe Street on the door. The chain branding is identical between the two. The door addresses differ, 88 Harlow Street against 88 Harlowe Street.

#### Field: Same specific location or not (`same_location_verdict`)

| Field | Value |
| --- | --- |
| Type | objective |
| Skills | S4 Objectivity |
| Unconfirmed | yes |
| Key confidence | medium |
| Requires human key review | yes |

Options:

- The candidate is a different location, because the door addresses differ. **(answer)**
- The candidate is the same location, because the chain branding is identical.
- The candidate is the same location, because both signs use the green script.

**Answer:** The candidate is a different location, because the door addresses differ.

**Reason:** Only the door address identifies a specific location, and the two differ, 88 Harlow Street against 88 Harlowe Street. The identical green-script branding is shared by every branch of the chain and is the surface resemblance that lures a same-location verdict, so resting on it rather than on the address is the objectivity failure.

---

### Item 17

| Field | Value |
| --- | --- |
| Project | entity-reference-verification |
| Skills | S5 Calibrated Judgment |
| Is trap | no |
| Cognitive level | evaluate |
| Flag for review | no |
| Difficulty | Provisional moderate, to be overwritten by observed p-value. |

**Provisional MCC estimate:** A minimally competent worker selects the defensible confidence band for the stated evidence. Provisional and non-load-bearing.

**Prompt**

A worker must decide whether two shipment records refer to the same shipment. Both records list the same tracking number 1Z-9920-4471, the same origin depot, the same weight, and the same dispatch date, and the tracking number is agreed to be globally unique. Choose the conclusion the available evidence defensibly supports.

#### Field: The defensible conclusion (`confidence_band`)

| Field | Value |
| --- | --- |
| Type | objective |
| Skills | S5 Calibrated Judgment |
| Unconfirmed | yes |
| Key confidence | medium |
| Requires human key review | no |

Options:

- The records refer to the same shipment, because the unique tracking number matches along with every other field. **(answer)**
- The evidence is insufficient to determine whether the records refer to the same shipment.
- The records refer to different shipments, because two separate records exist.

**Answer:** The records refer to the same shipment, because the unique tracking number matches along with every other field.

**Reason:** A globally unique tracking number matches across both records, and origin, weight, and dispatch date all agree, so the evidence defensibly confirms one shipment. Calling this insufficient ignores the matching unique identifier, and the mere existence of two records is not evidence of two shipments.

---

### Item 18

| Field | Value |
| --- | --- |
| Project | entity-reference-verification |
| Skills | S6 Source Validity Judgment |
| Is trap | no |
| Cognitive level | evaluate |
| Flag for review | no |
| Difficulty | Provisional moderate, to be overwritten by observed p-value. |

**Provisional MCC estimate:** A minimally competent worker judges whether the source can support the intended check. Provisional and non-load-bearing.

**Prompt**

A worker is asked to verify the wing markings of a specific aircraft whose tail number is the registered subject. Decide whether the provided photo is a fit source for that verification.

**Media**

- `q18-stimulus` (image status: pending, key confidence: medium, human key review: no)
  - placeholder: The task names the subject as the aircraft with tail number G-7714, described as a twin-engine propeller plane. The provided photo is sharp, well lit, and fully legible. It shows a single-engine jet whose painted tail number reads G-1147. The aircraft in the photo is plainly not the subject, it carries a different tail number and a different airframe type.

#### Field: Fit source for the verification or not (`source_fitness`)

| Field | Value |
| --- | --- |
| Type | objective |
| Skills | S6 Source Validity Judgment |
| Unconfirmed | yes |
| Key confidence | medium |
| Requires human key review | no |

Options:

- The photo is unfit for the task, because it shows a different aircraft than the subject. **(answer)**
- The photo is fit, and the wing markings can be verified from it.
- The photo is unfit, because it is too blurred to read the tail number.

**Answer:** The photo is unfit for the task, because it shows a different aircraft than the subject.

**Reason:** The photo is fully legible but shows an aircraft with tail number G-1147 and a single-engine jet airframe, not the subject G-7714 twin-engine propeller plane, so it cannot verify the subject markings. The image is stated to be sharp and legible, so the defect is the wrong subject and not blur, and a wrong-subject source cannot verify the subject.

---

### Item 19

| Field | Value |
| --- | --- |
| Project | entity-reference-verification |
| Skills | S2 Attention to Detail |
| Is trap | no |
| Cognitive level | analyze |
| Flag for review | no |
| Difficulty | Provisional moderate, to be overwritten by observed p-value. |

**Provisional MCC estimate:** A minimally competent worker isolates the small deciding feature past the salient decoy and selects it. Provisional and non-load-bearing.

**Prompt**

A single mounted electronic component is shown. Decide which statement about the component is correct based only on what is visible.

**Media**

- `q19-stimulus` (image status: pending, key confidence: low, human key review: yes)
  - placeholder: A square integrated-circuit chip soldered to a green board. A large white silkscreen label beside the chip reads U7 in bold and is the most prominent nearby text. On the chip body itself, one corner carries a small printed dot marking pin one. The small pin-one dot is at the top-left corner of the chip body.

#### Field: Correct statement about the component (`label_feature`)

| Field | Value |
| --- | --- |
| Type | objective |
| Skills | S2 Attention to Detail |
| Unconfirmed | yes |
| Key confidence | low |
| Requires human key review | yes |

Options:

- The chip pin-one dot is at the top-left corner of its body. **(answer)**
- The chip pin-one dot is at the bottom-right corner of its body.
- The chip body carries no pin-one dot at all.

**Answer:** The chip pin-one dot is at the top-left corner of its body.

**Reason:** A small printed dot on the chip body marks pin one and sits at the top-left corner. The bold U7 silkscreen label is a salient decoy that does not indicate pin one, and placing the dot at the opposite corner or missing it entirely are the attention failures the distractors capture.

---

### Item 20

| Field | Value |
| --- | --- |
| Project | entity-reference-verification |
| Skills | S3 Difference Detection |
| Is trap | no |
| Cognitive level | analyze |
| Flag for review | no |
| Difficulty | Provisional moderate, to be overwritten by observed p-value. |

**Provisional MCC estimate:** A minimally competent worker scans both observations and names the single conflicting field. Provisional and non-load-bearing.

**Prompt**

Two copies of a building floor plan are shown. Identify the one specific discrepancy between them.

**Media**

- `q20-stimulus` (image status: pending, key confidence: low, human key review: yes)
  - placeholder: Two floor plans labeled Issue 1 and Issue 2, each labeling four rooms. Both label them Lobby, Server Room, Break Room, Records. The room areas on both read 220, 95, 140, and 60 square feet. The door swing on the Records room is drawn inward on Issue 1 and outward on Issue 2. Every label and area matches, and only the Records door swing direction differs, inward against outward.

#### Field: The single discrepancy between the plans (`discrepancy`)

| Field | Value |
| --- | --- |
| Type | objective |
| Skills | S3 Difference Detection |
| Unconfirmed | yes |
| Key confidence | low |
| Requires human key review | yes |

Options:

- The plans differ in the door swing direction of the Records room. **(answer)**
- The plans differ in the labeled area of the Break Room.
- The plans differ in the name of the second room.

**Answer:** The plans differ in the door swing direction of the Records room.

**Reason:** Every room label and printed area matches across the two plans, and the only conflict is the Records room door swing, drawn inward on Issue 1 and outward on Issue 2. The Break Room area reads 140 on both and the second room is Server Room on both, so neither distractor names a real difference.

---

### Item 21

| Field | Value |
| --- | --- |
| Project | entity-reference-verification |
| Skills | S1 Instruction Reading |
| Is trap | no |
| Cognitive level | analyze |
| Flag for review | no |
| Difficulty | Provisional moderate, to be overwritten by observed p-value. |

**Provisional MCC estimate:** A minimally competent worker parses the instruction and lists every condition with none added or dropped. Provisional and non-load-bearing.

**Prompt**

Read the following loan policy, then identify which list correctly captures every separate condition under which an item may be borrowed. Policy: An item may be borrowed only by a member in good standing, only if the member has fewer than ten items currently out, and only if the item is not marked reference-only. Choose the option that lists the distinct conditions without adding or dropping any.

#### Field: The complete set of stated conditions (`condition_set`)

| Field | Value |
| --- | --- |
| Type | objective |
| Skills | S1 Instruction Reading |
| Unconfirmed | yes |
| Key confidence | high |
| Requires human key review | no |

Options:

- The borrower is a member in good standing, the member has fewer than ten items currently out, and the item is not marked reference-only. **(answer)**
- The borrower is a member in good standing, and the item is not marked reference-only.
- The borrower is a member in good standing, the member has fewer than ten items currently out, and the item is returned within fourteen days.

**Answer:** The borrower is a member in good standing, the member has fewer than ten items currently out, and the item is not marked reference-only.

**Reason:** The policy states three distinct conditions, membership in good standing, fewer than ten items currently out, and the item not marked reference-only. The second option drops the fewer-than-ten condition and the third replaces the reference-only condition with a fourteen-day return term the policy never states for borrowing.

---

### Item 22

| Field | Value |
| --- | --- |
| Project | entity-reference-verification |
| Skills | S4 Objectivity |
| Is trap | no |
| Cognitive level | evaluate |
| Flag for review | no |
| Difficulty | Provisional moderate, to be overwritten by observed p-value. |

**Provisional MCC estimate:** A minimally competent worker keys on the identifying evidence and ignores surface resemblance. Provisional and non-load-bearing.

**Prompt**

A reference painting and a candidate painting are shown. Decide whether the candidate is the same individual work as the reference, using only the evidence that identifies a specific work.

**Media**

- `q22-stimulus` (image status: pending, key confidence: medium, human key review: yes)
  - placeholder: The reference is a small landscape in a loose impressionist style, with the inventory mark INV-3120 on its back label. The candidate is a small landscape in the same loose impressionist style, with the inventory mark INV-3210 on its back label. Both share the impressionist style and a similar palette. The back-label inventory mark is the only work-specific identifier, and the two differ, INV-3120 against INV-3210.

#### Field: Same individual work or not (`same_work_verdict`)

| Field | Value |
| --- | --- |
| Type | objective |
| Skills | S4 Objectivity |
| Unconfirmed | yes |
| Key confidence | medium |
| Requires human key review | yes |

Options:

- The candidate is a different work, because the back-label inventory marks differ. **(answer)**
- The candidate is the same work, because both share the impressionist style.
- The candidate is the same work, because the palettes are similar.

**Answer:** The candidate is a different work, because the back-label inventory marks differ.

**Reason:** Only the back-label inventory mark identifies a specific work, and the two differ, INV-3120 against INV-3210. Shared impressionist style and a similar palette are surface resemblances common to many works, so resting the verdict on them rather than on the inventory mark is the objectivity failure the distractors capture.

---

### Item 23

| Field | Value |
| --- | --- |
| Project | entity-reference-verification |
| Skills | S5 Calibrated Judgment |
| Is trap | no |
| Cognitive level | evaluate |
| Flag for review | no |
| Difficulty | Provisional moderate, to be overwritten by observed p-value. |

**Provisional MCC estimate:** A minimally competent worker selects the defensible confidence band for the stated evidence. Provisional and non-load-bearing.

**Prompt**

A worker must decide whether two badge records describe the same employee. Both records share the department Logistics, but the agreed unique identifier, the employee number, is present on both and differs, reading EMP-5567 on one record and EMP-8841 on the other. No other fields are available. Choose the conclusion the available evidence defensibly supports.

#### Field: The defensible conclusion (`confidence_band`)

| Field | Value |
| --- | --- |
| Type | objective |
| Skills | S5 Calibrated Judgment |
| Unconfirmed | yes |
| Key confidence | medium |
| Requires human key review | no |

Options:

- The records describe different employees, because the unique employee numbers differ. **(answer)**
- The records describe the same employee, because the department matches.
- The evidence is insufficient to determine whether the records describe the same employee.

**Answer:** The records describe different employees, because the unique employee numbers differ.

**Reason:** The employee number is the agreed unique identifier and it is present on both records and differs, EMP-5567 against EMP-8841, which defensibly rules out the same employee. A shared department is common to many employees and does not establish identity, and a conflict in a present unique identifier is decisive rather than insufficient.

---

### Item 24

| Field | Value |
| --- | --- |
| Project | entity-reference-verification |
| Skills | S2 Attention to Detail |
| Is trap | no |
| Cognitive level | analyze |
| Flag for review | no |
| Difficulty | Provisional moderate, to be overwritten by observed p-value. |

**Provisional MCC estimate:** A minimally competent worker isolates the small deciding feature past the salient decoy and selects it. Provisional and non-load-bearing.

**Prompt**

A single medication blister-pack backing is shown. Decide which statement about the backing is correct based only on what it displays.

**Media**

- `q24-stimulus` (image status: pending, key confidence: low, human key review: yes)
  - placeholder: A foil blister-pack backing printed with a large bold brand name OXACALM and a prominent strength 500 mg as its most visible elements. Near the crimped edge, in small embossed type, the lot code is printed as L4471K. The final character of the small lot code is the letter K.

#### Field: Correct statement about the backing (`label_feature`)

| Field | Value |
| --- | --- |
| Type | objective |
| Skills | S2 Attention to Detail |
| Unconfirmed | yes |
| Key confidence | low |
| Requires human key review | yes |

Options:

- The small lot code near the edge ends in the letter K. **(answer)**
- The small lot code near the edge ends in the letter R.
- The backing shows no lot code at all.

**Answer:** The small lot code near the edge ends in the letter K.

**Reason:** The lot code is embossed in small type near the crimped edge as L4471K and ends in the letter K. The bold brand name OXACALM and the 500 mg strength are salient decoys that are not the lot code, and reading the final character as the similar letter R or missing the lot code entirely are the attention failures the distractors capture.

---

### Item 25

| Field | Value |
| --- | --- |
| Project | entity-reference-verification |
| Skills | S3 Difference Detection |
| Is trap | no |
| Cognitive level | analyze |
| Flag for review | no |
| Difficulty | Provisional moderate, to be overwritten by observed p-value. |

**Provisional MCC estimate:** A minimally competent worker scans both observations and names the single conflicting field. Provisional and non-load-bearing.

**Prompt**

Two catalog rows for what is claimed to be the same part are shown. Identify the one specific discrepancy between them.

**Media**

- `q25-stimulus` (image status: pending, key confidence: low, human key review: yes)
  - placeholder: Two rows labeled Listing A and Listing B for a bearing. Listing A shows part number BR-6204, bore 20 mm, outer diameter 47 mm, width 14 mm. Listing B shows part number BR-6204, bore 20 mm, outer diameter 47 mm, width 14 mm. The seal type is 2RS on Listing A and ZZ on Listing B. Every numeric field and the part number match, and only the seal type differs, 2RS against ZZ.

#### Field: The single discrepancy between the listings (`discrepancy`)

| Field | Value |
| --- | --- |
| Type | objective |
| Skills | S3 Difference Detection |
| Unconfirmed | yes |
| Key confidence | low |
| Requires human key review | yes |

Options:

- The two listings differ in their seal type. **(answer)**
- The two listings differ in their bore dimension.
- The two listings differ in their part number.

**Answer:** The two listings differ in their seal type.

**Reason:** The part number and every numeric dimension match across the two listings, and the only conflict is the seal type, 2RS on Listing A against ZZ on Listing B. The bore reads 20 mm on both and the part number is BR-6204 on both, so neither distractor names a real difference.

---

## Worker grading rubric

| Field type | Skill ID | Correct response looks like | Common errors |
| --- | --- | --- | --- |
| objective | S1 | The worker selects the option that lists every stated condition with none added and none dropped. | Dropping a stated condition or importing a condition the instruction never states. |
| objective | S2 | The worker selects the option naming the small deciding feature and ignores the salient decoy. | Following the salient element or misreading a near-identical character. |
| objective | S3 | The worker selects the option naming the single conflicting field across the two observations. | Declaring no difference under heavy overlap or naming a field that actually matches. |
| objective | S4 | The worker selects the verdict the unit-specific identifying evidence supports. | Resting on shared category, brand, or style resemblance instead of the identifying evidence. |
| objective | S5 | The worker selects the conclusion band the stated evidence defensibly supports, including insufficient when a unique identifier is missing. | Overconfidence from a weak partial match or false exclusion from a missing datum. |
| objective | S6 | The worker selects whether the source is fit for the intended check and names the fitness defect when it is not. | Proceeding on a structurally unfit source or confusing a wrong-subject defect with an illegibility defect. |

**Stated pass target**

Stated as a target only and never applied here. The aspiration is that a minimally competent worker keys the deciding detail on most items within each skill and is separated from a guesser by the trap items, while the platform owns any actual cutoff.

## Validity argument

### Bank level

**claim:** A worker who passes this bank can perform high-quality work on entity-reference-verification, the kind of work its required skills demand.

**construct sampled:** The in-scope and objective-assessable skills S1 Instruction Reading, S2 Attention to Detail, S3 Difference Detection, S4 Objectivity, S5 Calibrated Judgment, and S6 Source Validity Judgment, sampled in proportion to the entity-reference-verification weight column.

**scoring inference:** Each objective field is keyed by code to one correct option, field scores roll up per frozen skill into a skill profile, and the profile aggregates into a composite, with no cutoff applied here.

**generalization warrant:** Blueprint coverage of every in-scope objective-assessable skill, with every weight four or five skill measured across more than one item, supports generalization from these items to the skill domain.

**extrapolation warrant:** OPEN pending a criterion study. Generic scenarios were chosen over reproductions of the real task, which lowers fidelity and leaves the link to on-the-job performance a hypothesis to be tested against downstream job-performance data.

### Per high-weight skill

#### S1

- **claim:** A capable worker can decompose a stated requirement into its distinct governing conditions before judging.
- **evidence warranted:** Correctly enumerates every separate condition embedded in a compound instruction, neither merging nor dropping one.
- **evidence excluded by boundary:** Excludes applying the conditions to any evidence and judging the underlying content, the item is decided by parsing the instruction alone.
- **task format chosen:** Objective extraction with one correct condition set and distractors that drop a stated condition or add an unstated one.
- **format validity rationale:** An instruction-comprehension construct has a single defensible parse, so a single-keyed extraction item measures it without forcing arbitrariness.

#### S2

- **claim:** A capable worker can detect the small but consequential feature that decides a verdict.
- **evidence warranted:** Identifies the single small deciding feature in one field while a salient element competes for attention.
- **evidence excluded by boundary:** Excludes cross-comparing two observations and weighing confidence, the item turns on one feature in one field.
- **task format chosen:** Objective single-keyed decision with a salient decoy and a near-miss misread distractor.
- **format validity rationale:** A perceptual verdict on visible detail has one defensible answer, so a single-keyed item with diagnostic distractors fits.

#### S3

- **claim:** A capable worker can identify the specific correspondences and conflicts between two observations.
- **evidence warranted:** Names the one field that conflicts across two otherwise matching observations.
- **evidence excluded by boundary:** Excludes noticing a feature in a single field and ranking by overall quality, the item turns on a two-field correspondence.
- **task format chosen:** Objective single-keyed decision naming the conflicting field, with non-conflicting fields as distractors.
- **format validity rationale:** A pairwise difference has one defensible answer provable from the two fields, so a single-keyed item fits.

#### S4

- **claim:** A capable worker can base the verdict only on genuinely relevant identifying evidence.
- **evidence warranted:** Reaches the verdict the unit-specific evidence supports while resisting a surface-resemblance or category-similarity lure.
- **evidence excluded by boundary:** Excludes confidence calibration, the relevant evidence is present and decisive and only its proper use is at issue.
- **task format chosen:** Objective single-keyed decision with surface-resemblance and category-similarity distractors.
- **format validity rationale:** With decisive relevant evidence present, one verdict is defensible, so a single-keyed item isolates whether the worker uses it.

#### S5

- **claim:** A capable worker can match confidence to the completeness of the evidence, including recognizing when it is too thin to decide.
- **evidence warranted:** Selects the one defensible conclusion band given the stated evidence, whether confirm, rule out, or insufficient.
- **evidence excluded by boundary:** Excludes relevance judgment and source-fitness judgment, the source is fit and the evidence relevant and only its sufficiency is at issue.
- **task format chosen:** Objective band-selection item built only where one band is clearly defensible.
- **format validity rationale:** A calibration is keyed objectively only when one band is unambiguous, which avoids forcing a key onto a genuine judgment, otherwise it would need a subjective field.

## Question bank quality

**Total items:** 25

### Per skill

| Skill ID | Count | Deciding | Exercised | Meets floor | SEM warning |
| --- | --- | --- | --- | --- | --- |
| S1 | 4 | 4 | yes | yes | Fewer than six items measure this deciding skill, so the per-skill score carries a wide standard error and is a provisional profile signal most reliable at the composite level, to be replaced by observed item statistics after piloting. |
| S2 | 5 | 5 | yes | yes | Fewer than six items measure this deciding skill, so the per-skill score carries a wide standard error and is a provisional profile signal most reliable at the composite level, to be replaced by observed item statistics after piloting. |
| S3 | 5 | 5 | yes | yes | Fewer than six items measure this deciding skill, so the per-skill score carries a wide standard error and is a provisional profile signal most reliable at the composite level, to be replaced by observed item statistics after piloting. |
| S4 | 4 | 4 | yes | yes | Fewer than six items measure this deciding skill, so the per-skill score carries a wide standard error and is a provisional profile signal most reliable at the composite level, to be replaced by observed item statistics after piloting. |
| S5 | 4 | 4 | yes | yes | Fewer than six items measure this deciding skill, so the per-skill score carries a wide standard error and is a provisional profile signal most reliable at the composite level, to be replaced by observed item statistics after piloting. |
| S6 | 3 | 2 | yes | yes | Only three items with a deciding count of two measure this skill, the thinnest coverage in the bank, so the per-skill score carries the widest standard error and is a provisional profile signal, to be replaced by observed item statistics after piloting. |

### Skills out of scope

- S8 Specification Conformance, weight 0 for entity-reference-verification
- S9 Spatial Alignment, weight 0 for entity-reference-verification
- S10 Plausibility Assessment, weight 0 for entity-reference-verification
- S11 Systematic Coverage, weight 0 for entity-reference-verification

### Skills not covered under type

- S7 Clear Writing, in scope at weight 4, has no valid single-keyed objective form because it is an open-justification competency graded against the quality of the writing, so it is not assessable under the Objective type and is excluded from this bank.

### Reliability risk notes

- Short bank of 25 items with per-skill counts of two to five, so per-skill decision consistency is limited and the composite is the more reliable signal.
- S6 Source Validity Judgment has the thinnest coverage at three items with a deciding count of two, the widest per-skill standard error in the bank.
- Single served form at pool factor one, which gives no parallel-form equating and no exposure control at scale.

### Coverage gaps

- S7 Clear Writing, weight 4 for entity-reference-verification, is not represented because the Objective type admits no valid single-keyed form for an open-justification skill. Recorded here rather than padded over. It is assessable under the Subjective or Both type.

### Flags

- Every field is marked unconfirmed and all wording is provisional pending human key review.
- Perceptual items on S2, S3, and S4 and the obscured-source item on S6 carry low or medium key confidence and require human key review once the assets are rendered.
- S7 Clear Writing is omitted under the Objective type as a logged coverage gap, not a silent drop.
- Each covered skill is measured by fewer than six items, so per-skill standard error is wide and item statistics are provisional.
- The extrapolation warrant is OPEN because no criterion data is collected here.
- Pool factor is one, a single served form with no exposure-control variants.

### Blueprint realized vs target

Target raw quotas over 25 items were S1 3.70, S2 4.63, S3 4.63, S4 4.63, S5 4.63, and S6 2.78. Realized allocation after the representation floor and largest-remainder distribution is S1 4, S2 5, S3 5, S4 4, S5 4, and S6 3, summing to 25. Of the four leftover items beyond the floored quotas, the first two went to S6 and S1 by largest fractional remainder and the next two went to S2 and S3 by the higher-weight then lower-skill-id tie-break.

### Reading load scan

Scenarios use short plain sentences and concrete nouns, avoid culture-bound and idiomatic content, and keep the deciding detail short to read, so reading load is not a source of construct-irrelevant difficulty.

### Item writing defect check

Each objective field states the full problem in the stem, offers three mutually exclusive options parallel in grammar and length, avoids all-of-the-above, none-of-the-above, and combination options, builds each distractor from a named error mode of the probed skill, and lets no item clue another.

### Stimulus status

Pending. Every media entry is a placeholder brief with an empty url and image_status pending, and the pipeline fills each url by media_id. No verdict rests on a generated or instruction-conditioned image.

### Global checks

Items are unambiguous with one defensible answer each, every field carries a frozen registry skill tag, no near-duplicate shares both scenario type and probed skill, the mixed arrangement places no two consecutive items on the same skill, and house style is clean throughout.

### Result

The bank covers every in-scope objective-assessable skill for entity-reference-verification in proportion to the weight column, meets the representation floor on all six covered skills, and isolates each item to one construct with diagnostic distractors. S7 Clear Writing is in scope at weight four but is not assessable by a single-keyed item and is recorded as a coverage gap under the Objective type rather than forced or hidden. Per-skill scores carry wide standard errors because each skill is measured by fewer than six items, so the bank is most reliable at the composite and as a profile signal, and all item statistics are provisional pending piloting. No pass, fail, or cutoff is asserted.
