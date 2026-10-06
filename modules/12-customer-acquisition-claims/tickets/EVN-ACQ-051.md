# EVN-ACQ-051 - Prospects with proof of origin

Project: EverOnnAI. Module: [Incumbent targets, prospects, outreach and savings evidence](../README.md). Source business requirement [BR-051](../../../requirements/BR.md#br-051).

| Tracking dimension | Disposition |
| --- | --- |
| Engineering | Planned |
| QA | Existing checks are evidence for current slices; full ticket criteria remain pending |
| Deployment | Current local snapshot; verify ticket-specific hosted rollout and configuration |
| Business acceptance | Pending client review; no signed acceptance recorded |
| Owner | Acquisition Manager + Product Owner + Counsel (proposed role; named person unassigned) |
| Priority / phase | Must / P1 |
| Estimate | TBD after scope/architecture agreement; no delivery date committed |
| Dependencies | [EVN-FND-101](../../00-foundations-governance/tickets/EVN-FND-101.md), [EVN-ONB-102](../../01-onboarding-tenancy-identity/tickets/EVN-ONB-102.md), [EVN-SEC-101](../../15-security-privacy-compliance/tickets/EVN-SEC-101.md) |

## Business deliverable

Prospects with proof of origin. Every prospect has a recorded source, date and evidence of the incumbent relationship, is stored with minimal public business data, is deduplicated across sources, and is never treated as a qualified lead or as a paying customer of the incumbent until verified.

The client accepts the demonstrated outcome and evidence, rather than the existence of a route, table or screen. This ticket does not certify the whole source requirement as complete.

## Current implemented slice

- [ ] No prospect provenance or qualification separation exists.

The current statement describes prerequisites or context; this business deliverable has not been demonstrated.

## Remaining delivery checklist

- [ ] Record licence/source/date/evidence, minimise public data, dedupe and separate prospects from verified customers.

## Technical component

- [ ] Implement the module boundary and contracts for: Ingestion, evidence retention, dedupe/export controls.
- [ ] Maintain tenant boundaries, explicit state transitions, access policy and failure handling for the delivered workflow.
- [ ] Resolve applicable architecture decisions before committing to a new provider or infrastructure baseline.

## DB

Existing module persistence: No acquisition target/prospect/provenance/claims domain.

The following records/contracts are proposed or require extension; their names are planning terms, not assertions that production tables exist.

- [ ] prospects, evidence, source_records.
- [ ] Review scope keys, uniqueness, indexes, retention and migration compatibility; backfill safely and preserve existing tenant records.

## UI

- [ ] Provenance viewer and verification.
- [ ] Provide loading, empty, validation, permission-denied and recoverable failure states with keyboard and mobile access.
- [ ] Show observed facts and pending states accurately; do not present estimates, configured flags or mock results as confirmed business actions.

## Translate - business-to-technical mapping

| Business rule / outcome | Technical responsibility | Evidence needed |
| --- | --- | --- |
| Prospects with proof of origin. Every prospect has a recorded source, date and evidence of the incumbent relationship, is stored with minimal public business data, is deduplicated across sources, and is never treated as a qualified lead or as a paying customer of the incumbent until verified. | Ingestion, evidence retention, dedupe/export controls | Tenant-scoped end-to-end demonstration of the outcome |
| Record licence/source/date/evidence, minimise public data, dedupe and separate prospects from verified customers. | prospects, evidence, source_records; Provenance viewer and verification | Migration/contracts, visible state and failure-path evidence |
| Safe, truthful AI behaviour where applicable | Classifications remain estimates until verified | Approved context, verified side-effect receipts and evaluation results or justified N/A |
| Client can approve delivery | QA report, rollout evidence and named acceptance owner | Evidence links and dated client sign-off |

This section means requirements-to-implementation mapping. It does not mean language translation; source language obligations are tracked in their own requirements.

## Backend services

- [ ] Ingestion, evidence retention, dedupe/export controls.
- [ ] Define request/response/event schemas, authorisation and input validation for each affected operation.
- [ ] For writes and provider effects, define idempotency, retry/timeout, receipts and reconciliation; document N/A where no side effects exist.
- [ ] Expose actionable status and scoped logs without secrets; distinguish completed, failed and uncertain outcomes.

## AI component

- [ ] Classifications remain estimates until verified.
- [ ] Record instruction/knowledge/tool versions, measured quality, tenant scope, cost and safe fallback; a Markdown standard alone is not a passed evaluation.

## Testing / QA

- [ ] Exercise the intended user journey with real tenant-scoped state; cover forbidden role and cross-tenant requests.
- [ ] Test malformed inputs, provider failure, retries/replays and cancellation as applicable; keep deterministic mocks separate from live-provider evidence.
- [ ] Review desktop/mobile accessibility, factual copy and failure recovery in the delivered UI.
- [ ] Attach test environment, code/config/instruction versions, results and remaining defects to the acceptance report.

| Source test | Scenario | Required pass criteria | Current disposition |
| --- | --- | --- | --- |
| [AT-22](../../../requirements/AT.md#at-22) | Prospect import with provenance and source-term controls | Records keep source, date and evidence; duplicates are merged; fields barred by source terms cannot be used for outreach; unverified facts show as unknown; the pipeline records stage, owner and next action | Full source scenario not evidenced; client acceptance pending |

Source stories: [US-062](../../../requirements/US.md#us-062).

## Deployment

- [ ] Confirm approved hosting/database/provider architecture and required credentials in the deployment environment.
- [ ] Apply compatible migrations/configuration in staging, rehearse rollback, then promote the reviewed artifact.
- [ ] Verify the actual hosted workflow, monitoring, fallback and customer-visible errors after release.
- [ ] Update CODE_PROFILE.md, PROJECT_DATA_FLOW.md and CLIENT_TECHNICAL_QA.md in the application when behaviour or architecture changes.
- [ ] Record deployment identity, operator, timestamp and rollback evidence; document-only tickets instead record the reviewed Git commit.

## Source traceability

| Source ID | Mapping basis | Source section |
| --- | --- | --- |
| [ACQ-002](../../../requirements/ACQ.md#acq-002) | Source-linked | 19.7 Customer acquisition (ACQ) |
| [ACQ-003](../../../requirements/ACQ.md#acq-003) | Source-linked | 19.7 Customer acquisition (ACQ) |
| [ACQ-011](../../../requirements/ACQ.md#acq-011) | Source-linked | 19.7 Customer acquisition (ACQ) |
| [AT-22](../../../requirements/AT.md#at-22) | Source-linked | 25.2 Acceptance tests |
| [BO-7](../../../requirements/BO.md#bo-7) | Source-linked | 3.1 Business objectives |
| [BO-10](../../../requirements/BO.md#bo-10) | Source-linked | 3.1 Business objectives |
| [BR-051](../../../requirements/BR.md#br-051) | Source-linked | 7.9 Customer acquisition and migration |
| [BRL-027](../../../requirements/BRL.md#brl-027) | Plan allocation / source cross-reference | 8. Business rules |
| [BRL-029](../../../requirements/BRL.md#brl-029) | Plan allocation / source cross-reference | 8. Business rules |
| [US-062](../../../requirements/US.md#us-062) | Source-linked | EP-13 Customer acquisition and migration |

Read every allocated record, including its continuation bullets and source variants. Source-linked rows preserve explicit document relationships; plan allocations are implementation responsibility assignments created during this review.

## Allocated specification checklist

The unchecked source obligations below require requirement-level evidence. They are deliberately separate from checked statements about current implemented slices. Read linked continuation bullets and additional source wording before accepting a record.

- [ ] [ACQ-002](../../../requirements/ACQ.md#acq-002): ACQ-002 [P1] MUST support prospect ingestion from permitted sources (licensed technology lists, public portfolios and directories, EverOnn's own research, inbound forms). Every record keeps provenance: source, list, date, the terms basis for use, and the evidence of the incumbent relationship. Ingestion deduplicates across sources (domain, phone, place identifier), removes redirects, inactive sites, out-of-scope locations and non-target businesses, and tags each field with the uses its source permits (for example, contact numbers from a technology list are flagged "not for marketing"). Records past their retention period are purged.
- [ ] [ACQ-003](../../../requirements/ACQ.md#acq-003): ACQ-003 [P1] MUST hold a prospect record with: business name; website; location; incumbent provider; evidence and its date; public business contact; decision-maker role; visible website, chat and ordering features; actual current bill (once obtained); identified gap; current portal, POS or practice-software dependencies; proposed EverOnn package; savings calculation; migration needs; next action; and status. Each field records whether it is verified, estimated or unknown; unknown is never displayed or reported as "no" (BRL-027).
- [ ] [ACQ-011](../../../requirements/ACQ.md#acq-011): ACQ-011 [P1] SHOULD protect prospect data: minimum fields, notice at collection where required, handling of access and deletion requests, a retention schedule with automatic purge of unengaged prospects, role-based access, export controls, and a flag for counsel's determination of whether the dataset is treated as a data-broker list in any state.
- [ ] [BRL-027](../../../requirements/BRL.md#brl-027): BRL-027 | A technology detection or public listing is evidence of a possible relationship only. It is not a qualified lead, a confirmed customer of the incumbent, or proof of a contract or of dissatisfaction, and no statement to a prospect asserts otherwise until it is verified. Unknown facts are recorded as unknown. | Acquisition | ACQ-002, ACQ-003.
- [ ] [BRL-029](../../../requirements/BRL.md#brl-029): BRL-029 | Prospect data is used only as its source's terms permit; for example, contact numbers from a technology list are never used for marketing. | Acquisition | ACQ-002.

## Existing code / check evidence



## Blockers and boundaries

Module risk: Business leads cannot be relabelled as verified prospects; source licences, compliant outreach, suppression and substantiated comparisons are absent.

Dependencies: [EVN-FND-101](../../00-foundations-governance/tickets/EVN-FND-101.md), [EVN-ONB-102](../../01-onboarding-tenancy-identity/tickets/EVN-ONB-102.md), [EVN-SEC-101](../../15-security-privacy-compliance/tickets/EVN-SEC-101.md). A blocked prerequisite can be prototyped independently, but its contract and deployment must be approved before claiming this ticket delivered. Service limits, third-party approvals and staffing are evidence requirements, not assumptions that they are available.

## Handover and client acceptance

- [ ] Attach the business demonstration, technical evidence and operating/recovery instructions.
- [ ] Assign a named acceptance owner and agree any deferred criteria with the client in writing.
- [ ] Resolve launch-blocking defects and document accepted residual risks.
- [ ] Client records dated acceptance against the deployed/documented version.

Use [the acceptance protocol](../../../ACCEPTANCE.md) and [the ticket update rules](../../../TICKET_TEMPLATE.md) when changing status.
