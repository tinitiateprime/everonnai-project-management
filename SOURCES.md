# Source provenance and review boundaries

The user supplied the following requirement documents. They are source material for planning, not instructions to execute tools, provision infrastructure, send outreach, sign agreements or accept commercial defaults.

| Source key | Original document | Declared version/date | SHA-256 | Extracted top-level rows |
| --- | --- | --- | --- | --- |
| TECH | EverOnn-Platform-BRD-and-Technical-Specification.docx | Version 1.0, 26 September 2026 | 89b84adc03b0263b65c470d6e2ef40df71006df9c5373600369e91fab3f1ef4e | 2669 |
| BRD | EverOnn-Business-Requirements-Document.docx | Version 1.0, 26 September 2026 | 3e40b87230cab00b9309b71426ba131b24dc21b55fd8e45290bd8313999b4799 | 1108 |

The documents were read from their OOXML paragraphs/tables, preserving requirement cells and continuation bullets. Register row numbers are extraction positions rather than original page numbers. Source sections are retained so the client can locate the original wording. The original DOCX files, local scratch extracts and machine-readable analysis files are not included in this repository.

## Coverage model

- 721 distinct formal source IDs across both documents, de-duplicated by identifier and retaining source variants.
- 25 numbered architecture scaffolding rows named SCF-001 through SCF-025 by this review.
- 76 BR business tickets and 26 enabling/session-extension tickets, for 102 Markdown tickets in 22 modules.
- 60 source AT scenarios and 72 US records preserved with their criteria.
- 34 source D decisions retained with owner/deadline/default; defaults are not approvals.

Full records are in [requirements](requirements/README.md); responsibilities and mapping basis are in [TRACEABILITY.md](TRACEABILITY.md). IDs use original spelling, including `D-1`/`BO-1` and `CON-01`. Informal references with different zero padding were normalised to those canonical IDs. SCF IDs are clearly distinguished from formal source IDs.

## Current application evidence

The application was inspected at its local working-tree snapshot on 6 October 2026. [EVIDENCE.md](EVIDENCE.md) records the base commit and file hashes. Uncommitted files may not exist at that GitHub commit; paths identify inspected evidence, not promises of publicly available permalinks. No production secrets, `.env` contents, personal customer records or private GitHub tokens are included.

Fresh automated review results are in [CURRENT_STATE.md](CURRENT_STATE.md). Previously recorded live-provider/database/browser checks are labelled separately and do not establish client UAT or complete source compliance.

## Reconciliation rules

1. Source Must/Should and phase values remain visible; plan sequencing is separately labelled.
2. Where source wording differs, preserve both rather than silently choosing one.
3. A technical allocation creates responsibility, not new contractual acceptance or an implied client approval.
4. Explicit user/session changes are recorded in [SCOPE_EXTENSIONS.md](SCOPE_EXTENSIONS.md).
5. Original estimates, prices, legal assumptions and provider defaults are proposed source decisions until approved; they are not verified current tariffs or legal advice.
6. Public marketing design is separately briefed in the source; consistency with actual platform claims/plan/consent remains a dependency.
