# EVN-SEC-067 - Export and deletion

Project: EverOnnAI. Module: [Security, consent, privacy, legal terms and assurance](../README.md). Source business requirement [BR-067](../../../requirements/BR.md#br-067).

| Tracking dimension | Disposition |
| --- | --- |
| Engineering | Planned |
| QA | Existing checks are evidence for current slices; full ticket criteria remain pending |
| Deployment | Current local snapshot; verify ticket-specific hosted rollout and configuration |
| Business acceptance | Pending client review; no signed acceptance recorded |
| Owner | Security Lead + Counsel + Product Owner (proposed role; named person unassigned) |
| Priority / phase | Must / P1 |
| Estimate | TBD after scope/architecture agreement; no delivery date committed |
| Dependencies | [EVN-SEC-101](EVN-SEC-101.md), [EVN-SEC-102](EVN-SEC-102.md) |

## Business deliverable

Export and deletion. Clients can export or delete their data on request.

The client accepts the demonstrated outcome and evidence, rather than the existence of a route, table or screen. This ticket does not certify the whole source requirement as complete.

## Current implemented slice

- [ ] Complete export/deletion/retention is absent.

The current statement describes prerequisites or context; this business deliverable has not been demonstrated.

## Remaining delivery checklist

- [ ] Deliver scoped exports, rights requests, legal holds, purge and crypto-erasure with receipts.

## Technical component

- [ ] Implement the module boundary and contracts for: DSR workflows, downloads, retention/key destruction.
- [ ] Maintain tenant boundaries, explicit state transitions, access policy and failure handling for the delivered workflow.
- [ ] Resolve applicable architecture decisions before committing to a new provider or infrastructure baseline.

## DB

Existing module persistence: Private entity tables, scoped auth, encrypted provider payloads and invoker write functions.

The following records/contracts are proposed or require extension; their names are planning terms, not assertions that production tables exist.

- [ ] dsr_requests, exports, retention_jobs, key_registry.
- [ ] Review scope keys, uniqueness, indexes, retention and migration compatibility; backfill safely and preserve existing tenant records.

## UI

- [ ] Export/deletion request and progress.
- [ ] Provide loading, empty, validation, permission-denied and recoverable failure states with keyboard and mobile access.
- [ ] Show observed facts and pending states accurately; do not present estimates, configured flags or mock results as confirmed business actions.

## Translate - business-to-technical mapping

| Business rule / outcome | Technical responsibility | Evidence needed |
| --- | --- | --- |
| Export and deletion. Clients can export or delete their data on request. | DSR workflows, downloads, retention/key destruction | Tenant-scoped end-to-end demonstration of the outcome |
| Deliver scoped exports, rights requests, legal holds, purge and crypto-erasure with receipts. | dsr_requests, exports, retention_jobs, key_registry; Export/deletion request and progress | Migration/contracts, visible state and failure-path evidence |
| Safe, truthful AI behaviour where applicable | Redact traces/evals; no unapproved customer-data training | Approved context, verified side-effect receipts and evaluation results or justified N/A |
| Client can approve delivery | QA report, rollout evidence and named acceptance owner | Evidence links and dated client sign-off |

This section means requirements-to-implementation mapping. It does not mean language translation; source language obligations are tracked in their own requirements.

## Backend services

- [ ] DSR workflows, downloads, retention/key destruction.
- [ ] Define request/response/event schemas, authorisation and input validation for each affected operation.
- [ ] For writes and provider effects, define idempotency, retry/timeout, receipts and reconciliation; document N/A where no side effects exist.
- [ ] Expose actionable status and scoped logs without secrets; distinguish completed, failed and uncertain outcomes.

## AI component

- [ ] Redact traces/evals.
- [ ] no unapproved customer-data training.
- [ ] Record instruction/knowledge/tool versions, measured quality, tenant scope, cost and safe fallback; a Markdown standard alone is not a passed evaluation.

## Testing / QA

- [ ] Exercise the intended user journey with real tenant-scoped state; cover forbidden role and cross-tenant requests.
- [ ] Test malformed inputs, provider failure, retries/replays and cancellation as applicable; keep deterministic mocks separate from live-provider evidence.
- [ ] Review desktop/mobile accessibility, factual copy and failure recovery in the delivered UI.
- [ ] Attach test environment, code/config/instruction versions, results and remaining defects to the acceptance report.

| Source test | Scenario | Required pass criteria | Current disposition |
| --- | --- | --- | --- |
| [AT-46](../../../requirements/AT.md#at-46) | Data export and deletion | Complete export delivered; deletion and cryptographic erasure verified | Full source scenario not evidenced; client acceptance pending |

Source stories: [US-048](../../../requirements/US.md#us-048).

## Deployment

- [ ] Confirm approved hosting/database/provider architecture and required credentials in the deployment environment.
- [ ] Apply compatible migrations/configuration in staging, rehearse rollback, then promote the reviewed artifact.
- [ ] Verify the actual hosted workflow, monitoring, fallback and customer-visible errors after release.
- [ ] Update CODE_PROFILE.md, PROJECT_DATA_FLOW.md and CLIENT_TECHNICAL_QA.md in the application when behaviour or architecture changes.
- [ ] Record deployment identity, operator, timestamp and rollback evidence; document-only tickets instead record the reviewed Git commit.

## Source traceability

| Source ID | Mapping basis | Source section |
| --- | --- | --- |
| [AT-46](../../../requirements/AT.md#at-46) | Source-linked | 25.2 Acceptance tests |
| [BO-7](../../../requirements/BO.md#bo-7) | Source-linked | 3.1 Business objectives |
| [BR-067](../../../requirements/BR.md#br-067) | Source-linked | 7.11 Platform, security, compliance and reliability |
| [BRL-018](../../../requirements/BRL.md#brl-018) | Plan allocation / source cross-reference | 8. Business rules |
| [COM-008](../../../requirements/COM.md#com-008) | Plan allocation / source cross-reference | 19.5 Compliance and legal-by-design (COM) |
| [COM-009](../../../requirements/COM.md#com-009) | Source-linked | 19.5 Compliance and legal-by-design (COM) |
| [ORD-010](../../../requirements/ORD.md#ord-010) | Plan allocation / source cross-reference | 19.9 Online ordering and restaurant workflow (ORD) |
| [TEN-006](../../../requirements/TEN.md#ten-006) | Source-linked | 12.3 Tenancy model requirements |
| [US-048](../../../requirements/US.md#us-048) | Source-linked | EP-10 Compliance, security and privacy |

Read every allocated record, including its continuation bullets and source variants. Source-linked rows preserve explicit document relationships; plan allocations are implementation responsibility assignments created during this review.

## Allocated specification checklist

The unchecked source obligations below require requirement-level evidence. They are deliberately separate from checked statements about current implemented slices. Read linked continuation bullets and additional source wording before accepting a record.

- [ ] [BRL-018](../../../requirements/BRL.md#brl-018): BRL-018 | When a client leaves, numbers are released or ported per policy and data is retained and deleted on a fixed schedule. | Offboarding | COM-008, ADM-005, TEN-006.
- [ ] [COM-008](../../../requirements/COM.md#com-008): COM-008 [P1] MUST implement data retention policies per data class (default proposals: recordings 90 days, transcripts 24 months, audit logs 7 years, billing 7 years; configurable per plan and tenant), automated deletion, legal hold support, and deletion on account closure after a grace period.
- [ ] [COM-009](../../../requirements/COM.md#com-009): COM-009 [P1] MUST support data subject rights (access, deletion, correction, opt-out of sale/sharing where applicable) for tenants' customers via tenant-initiated tooling and an EverOnn intake process, with SLAs.
- [ ] [ORD-010](../../../requirements/ORD.md#ord-010): ORD-010 [P2] MUST give the restaurant its order and customer data for export, with marketing consent recorded per customer.
- [ ] [TEN-006](../../../requirements/TEN.md#ten-006): TEN-006 [P1] MUST support tenant data export (full, machine-readable) and deletion (hard delete plus cryptographic erasure of keys) on request within statutory timelines.

## Existing code / check evidence

- `features/auth/request-origin.ts` - inspected current application working tree; see [snapshot evidence](../../../EVIDENCE.md).
- `features/auth/session.ts` - inspected current application working tree; see [snapshot evidence](../../../EVIDENCE.md).
- `features/auth/rbac.ts` - inspected current application working tree; see [snapshot evidence](../../../EVIDENCE.md).
- `lib/provider-credentials.ts` - inspected current application working tree; see [snapshot evidence](../../../EVIDENCE.md).
- `lib/app-records.ts` - inspected current application working tree; see [snapshot evidence](../../../EVIDENCE.md).
- `supabase/migrations/202610040003_everonn_relational.sql` - inspected current application working tree; see [snapshot evidence](../../../EVIDENCE.md).
- `supabase/migrations/202610060004_project_repositories.sql` - inspected current application working tree; see [snapshot evidence](../../../EVIDENCE.md).
- Relevant automated checks: `tests/workspace-security.test.ts`, `tests/request-origin.test.ts`, `tests/provider-credentials.test.ts`, `tests/everonn-relational.test.ts`, `tests/project-workspace.test.ts`. Their scope is bounded by [current validation](../../../CURRENT_STATE.md).

## Blockers and boundaries

Module risk: Private PostgreSQL and AES-GCM tokens are not a consent ledger, per-tenant KMS keys, audit/WORM chain, privacy operations, pen-test pass or SOC 2 certification.

Dependencies: [EVN-SEC-101](EVN-SEC-101.md), [EVN-SEC-102](EVN-SEC-102.md). A blocked prerequisite can be prototyped independently, but its contract and deployment must be approved before claiming this ticket delivered. Service limits, third-party approvals and staffing are evidence requirements, not assumptions that they are available.

## Handover and client acceptance

- [ ] Attach the business demonstration, technical evidence and operating/recovery instructions.
- [ ] Assign a named acceptance owner and agree any deferred criteria with the client in writing.
- [ ] Resolve launch-blocking defects and document accepted residual risks.
- [ ] Client records dated acceptance against the deployed/documented version.

Use [the acceptance protocol](../../../ACCEPTANCE.md) and [the ticket update rules](../../../TICKET_TEMPLATE.md) when changing status.
