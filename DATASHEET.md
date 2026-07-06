# Datasheet — `PL-IPE`

> Structure after: Gebru et al., *Datasheets for Datasets*, CACM 2021.
> Fill in at the level you are comfortable with. A scholarly gesture that stakes a claim **without leakage**: you state *what* and *why*, not *exactly how*.

## Motivation
- **Why was the dataset created?** To measure inflectional-paradigm production in Polish — whether a model realizes the correct paradigm form for a requested feature set — a construct that existing Polish benchmarks (tagging, MCQ, LLM-judge) do not measure.
- **Who created it?** Elżbieta Dawidek.

## Composition
- **What does one item represent?** `[unit type — a feature specification + acceptable target forms, without revealing distribution]`
- **How many items?** `[order of magnitude, e.g. "several hundred"]` — you need not give an exact count.
- **Which morphosyntactic dimensions does it cover?** `[e.g. case, number, gender, aspect, mood, person — a list of axes, not a distribution]`
- **Any sensitive / personal data?** `[no / description]`

## Collection process
- **How were the items built?** `[description at the level of principle, e.g. "expert construction", without the decomposition procedure]`
- **Who built them?** `[Author / collaboration]`
- **Period:** `[ ]`

## Preprocessing
- `[general description; the correctness adjudication procedure is not part of this datasheet; it belongs to the closed scoring engine]`

## Uses
- **What is the dataset for?** Model evaluation.
- **What must it NOT be used for?** Training, fine-tuning, RAG, redistribution (see DUA).

## Distribution
- **How is it released?** Gated (Hugging Face) after signing the DUA. Not public.
- **License:** documentation CC BY 4.0; items — DUA (non-OSS).

## Maintenance
- **Maintainer / contact:** Elżbieta Dawidek, `[contact]`.
- **Versioning:** `[policy]`.
- **Canary:** present; do not remove.
