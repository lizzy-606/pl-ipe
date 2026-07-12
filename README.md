
# PL-IPE — Polish Inflectional-Paradigm Evaluation

**Author:** Elżbieta Dawidek · ORCID 0009-0000-0433-6095  
**Version:** 0.1.0 · July 2026  
**Status:** closed research benchmark · items gated under a DUA  
**Licenses:** documentation — CC BY 4.0 · interface — Apache-2.0 · items — DUA

---

## Why

Inflectional languages — not only Polish, but any language with a rich case, gender, number, person, mood, and aspect system — require models to produce the correct form, not merely recognize, classify, or tag it.

Tagging and production are different competences.

PL-IPE measures whether a model can realize the correct member of an inflectional paradigm from an explicit morphosyntactic specification. It isolates paradigm realization from broader sentence and discourse generation.

This isolation is the point. PL-IPE is designed to be read against PL-GGE, which measures the same morphology from the opposite side — see below.

## What it measures

PL-IPE measures whether a model produces the correct inflectional form for a specified combination of:

- lemma,
- case,
- number,
- gender,
- person,
- mood,
- aspect,
- and other relevant morphosyntactic features.

The task is direct production from a feature specification, not classification and not multiple-choice selection. The model is told which form is required and must generate it, without selecting from a supplied answer set.

Item taxonomy, item construction, the set of acceptance criteria, and the error-classification procedure are not publicly disclosed, in order to preserve benchmark validity.

## Relation to PL-GGE

PL-IPE and PL-GGE measure different levels of generative competence.

PL-IPE evaluates the realization of an individual inflectional form from an explicit morphosyntactic specification. It does not evaluate whether the model can independently infer that specification from context, maintain grammatical relations across an utterance, or generate globally well-formed text.

Those abilities are evaluated separately in PL-GGE: https://github.com/lizzy-606/pl-gge

In practical terms:

- **PL-IPE:** specified features → target inflectional form;
- **PL-GGE:** linguistic context → grammatically well-formed generated text.

The separation makes it possible to distinguish a failure of paradigm realization from a failure of contextual grammatical inference.

**PL-IPE asks whether the model can produce a specified form. PL-GGE asks whether the model knows which forms and relations the context requires.**

### Why the two are run together

Neither benchmark alone identifies what a model is missing when it fails. Run as a pair, they separate a missing resource from a missing control over it:

| | **PL-IPE passed** | **PL-IPE failed** |
|---|---|---|
| **PL-GGE passed** | grammatical competence | anomaly: contextual success without reliable paradigm realization — worth investigating in its own right |
| **PL-GGE failed** | the paradigms are there; the model cannot infer from context which form the structure requires | the paradigms are not there |

A single aggregate score cannot make this distinction. The two benchmarks are separate instruments, and each is usable on its own; together they yield a diagnosis that neither yields alone.

## Two measurement layers

**Measurement layer (anchor).** A fixed core of items, identical on every run. It provides comparability across models and measurement of gain over time — gain is only visible against a ruler that does not move. It rests on explicit, once-fixed evaluation assumptions.

**Diagnostic layer.** Growing and tuned to a specific model and its training base. It shows not only that a model fails, but on which morphosyntactic features, paradigm classes, and form patterns it breaks. It also yields material for correcting data and training. Tuning the diagnosis to a model requires jointly fixed evaluation assumptions held stable over time, which is why this layer is offered as long-term collaboration on defined terms.

## Status and access

PL-IPE is a research-grade evaluation instrument for Polish.

- **Test items** are released only under a Data Use Agreement (`DATA-USE-AGREEMENT.md`). This protects the set from leaking into training corpora — a model that has seen the test stops measuring it.
- **The scoring engine** is closed and offered as a service (eval-as-a-service, in preparation).
- **This repository is a public shell:** documentation, licensing, and citation metadata. It is enough to cite the benchmark and to understand what is measured and how.

## How it works

1. Items share a uniform JSONL format. Each item contains a lemma, a target morphosyntactic specification, and a set of acceptable target forms.
2. The model receives the specification and produces a form.
3. The generated form passes through the scoring engine.
4. The engine checks whether the form correctly realizes the requested paradigm position.
5. Results are reported per feature and paradigm class, so the output shows where a model fails, not only that it fails.

The diagnostic layer adds a report showing which paradigm classes and feature combinations break down, at a resolution that can support corrections to data and training methods.

## What you can do with it

- measure your own model via eval-as-a-service, once released;
- compare models on a single, controlled scale of inflectional production;
- run developmental diagnostics of a model in long-term collaboration;
- identify whether errors cluster by case, number, gender, person, aspect, mood, or paradigm class;
- adapt the evaluation frame to another language with comparable morphological parameters.

Adaptation means re-instantiating the construct using native linguistic material and language-specific paradigm structure. It does not mean translating Polish items. A translated Polish inflectional item may measure a different construct, or none at all.

Items, target forms, and examples are in Polish because they measure Polish; they are not translated.

## Contact

Access requests, evaluation enquiries, and collaboration proposals: **plgram.benchmarks@proton.me**

Please do not open public Issues for access requests.

---

*Citation: see `CITATION.cff`. Dataset description: `DATASHEET.md`. Licensing: `LICENSING.md`.*
