# Licensing

PL-IPE releases three kinds of artifact, each under different terms. A single license across all of them would either expose what is meant to stay closed, or block what is meant to be citable.

## 1. Documentation — CC BY 4.0

`README.md`, `DATASHEET.md`, `LICENSING.md`, and the description of the construct.

These are meant to be read, cited, quoted, and described, with attribution to the author. CC BY 4.0 permits exactly this: use is free, attribution is required.

License text: https://creativecommons.org/licenses/by/4.0/

## 2. Interface and evaluation code — Apache-2.0

The evaluation interface, the I/O contract, and the harness.

Apache-2.0 rather than MIT, for its explicit patent grant (§3): a user of the code cannot subsequently assert a patent claim against the author over what the code contains.

This code is not part of the present release. It will be published under Apache-2.0 when the evaluation service is released.

## 3. Evaluation items — Data Use Agreement

The items are not released under an open-source license. They are released under a conditional-access agreement: access is granted on the condition that the recipient does not redistribute the items and does not train on them.

Terms: `IPE_DATA-USE-AGREEMENT.md`

## Where the data lives

This repository is the public shell: documentation, licensing terms, and citation metadata. **It contains no items.**

The items are held separately, behind an access gate, and are released only under the DUA. This split — a public front, the test set behind a gate — is the standard arrangement for held-out benchmarks whose validity depends on not entering training corpora.

## References

- **Datasheets for Datasets** — Gebru et al., *Communications of the ACM* 64(12), 2021. `DATASHEET.md` follows this structure.
- **Citation File Format** — https://citation-file-format.github.io
- **Apache License 2.0** — https://www.apache.org/licenses/LICENSE-2.0
- **Creative Commons Attribution 4.0** — https://creativecommons.org/licenses/by/4.0/
- **Canary identifiers** — contamination-control practice established by BIG-bench.

This document describes licensing terms. It is not legal advice.
