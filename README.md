
# PL-IPE — Polish Inflectional-Paradigm Evaluation

**Author:** Elżbieta Dawidek · ORCID 0009-0000-0433-6095
**Status:** closed research benchmark · items gated under a DUA
**Licenses:** documentation — CC BY 4.0 · interface — Apache-2.0 · items — DUA

---

## Why

Inflectional languages — not only Polish, but any language with a rich case, gender, and aspect system — demand that a model *produce* the right form, not merely recognize or tag one. Tagging and production are two different competences, and existing Polish benchmarks reach the first, not the second.

PL-IPE measures the second: whether a model realizes the correct paradigm form when it has to generate it.

## What it measures

Whether a model, when generating, produces the **correct inflectional form** — that is, whether it realizes the right paradigm pattern for a requested set of morphosyntactic features: case, number, gender, aspect, mood, person.

The task is production, not classification. Not "does the model recognize this form", but "does the model produce it" — from a feature specification, in free generation.

## Two measurement layers

**Measurement layer (anchor).** A fixed core of items, identical on every run. It provides comparability across models and measurement of gain over time — gain is only visible against a ruler that does not move. It rests on explicit, once-fixed evaluation assumptions. Available via eval-as-a-service.

**Diagnostic layer.** Growing, tuned to a specific model and its training base. It shows not only that a model fails, but on which features and paradigm classes it breaks — and yields material for correcting the data and the training. Tuning the diagnosis to a model requires jointly fixed evaluation assumptions held stable over time, which is why this layer is offered as long-term collaboration on defined terms.

## Status and access

PL-IPE is a research-grade evaluation instrument for Polish.

- **Test items** are released only under a Data Use Agreement (`DATA-USE-AGREEMENT.md`). This protects the set from leaking into training corpora — a model that has "seen" the test stops measuring it.
- **The scoring engine** is closed and offered as a service (eval-as-a-service, in preparation).
- This repository is a public shell: documentation, interface, schemas, an illustrative example. It is enough to cite the benchmark and to understand what is measured and how.

## How it works, and what comes next

1. Items share a uniform JSONL format (schema in `schema/`). Each item: a feature specification (lemma + target morphosyntactic features) + the set of acceptable target forms.
2. The model receives the specification and produces the form.
3. The generated form passes through the scoring engine, which checks paradigm correctness and returns a result.
4. Results are reported per feature and paradigm class — you see where a model fails, not only that it fails.

The diagnostic layer adds a report showing which paradigm classes break down — at a resolution that lets you design the correction to the material and the training method.

**What you can do with it:**

- measure your own model via eval-as-a-service (once released),
- compare models on a single, controlled scale of inflectional production,
- run developmental diagnostics of a model in long-term collaboration (diagnostic layer),
- adapt the frame to another inflectional or agglutinative language with comparable parameters — this is re-instantiation of the construct on native material, not translation of items. A Polish inflectional item translated into another language measures something else, or nothing.

Items, target forms, and examples are in Polish, because they measure Polish; they are not translated.

---

*Citation: see `CITATION.cff`. Full dataset description: `DATASHEET.md`.*
