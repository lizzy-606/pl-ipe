
# Datasheet — PL-IPE

Structure follows Gebru et al., *Datasheets for Datasets*, CACM 2021.

PL-IPE is a closed benchmark. This datasheet states what the dataset is and why it exists. It does not state how items are constructed or how correctness is adjudicated: that information is withheld to preserve benchmark validity.

## Motivation

**Why was the dataset created?**
To measure inflectional-paradigm production in Polish — whether a model realizes the correct paradigm form for a requested set of morphosyntactic features. Existing Polish evaluation resources address tagging, multiple-choice selection, or LLM-as-a-judge scoring. None of these measures production of the form itself by a general-purpose generative model, under repeated measurement against a fixed anchor.

**Who created it?**
Elżbieta Dawidek (ORCID 0009-0000-0433-6095).

## Composition

**What does one item represent?**
A production task: a lemma together with a target morphosyntactic specification, and the set of forms admissible as its realization.

**How many items?**
Not publicly disclosed.

**Which grammatical dimensions are covered?**
Case, number, gender, person, mood, aspect, and further morphosyntactic features relevant to Polish paradigm structure. The distribution of items across these dimensions, and across paradigm classes, is not disclosed.

**Does the dataset contain sensitive or personal data?**
No. Items are constructed linguistic material. They contain no personal data and no information relating to identifiable persons.

## Collection process

**How were the items built?**
By expert construction. The construction procedure is not disclosed.

**Who built them?**
The author.

**Over what period?**
2025–2026.

## Preprocessing

Items are stored in a uniform JSONL format. The adjudication of paradigm correctness is not part of this dataset: it belongs to the closed scoring engine and is not disclosed.

## Uses

**What is the dataset for?**
Evaluation of language models.

**What must it not be used for?**
Training, fine-tuning, retrieval-augmented generation, or redistribution in any form. See `DATA-USE-AGREEMENT.md`.

## Distribution

Access is gated and granted only under a Data Use Agreement. The items are not part of this repository and are not publicly available.

**Licensing:** documentation — CC BY 4.0; items — DUA (not an open-source license). See `LICENSING.md`.

## Relation to PL-GGE

PL-IPE and PL-GGE are separate datasets with separate constructs, separate item sets, and separate canary identifiers. They are not to be merged or cited as one resource.

PL-GGE: https://github.com/lizzy-606/pl-gge

## Maintenance

**Maintainer and contact:** Elżbieta Dawidek — plgram.benchmarks@proton.me

**Versioning:** the measurement layer is fixed and versioned; changes to it are released as new versions and announced in the repository. The diagnostic layer grows and is not versioned in the same way.

**Contamination control:** the dataset carries a canary identifier, distinct from that of PL-GGE. It must not be removed or masked (see `DATA-USE-AGREEMENT.md`, §5).
