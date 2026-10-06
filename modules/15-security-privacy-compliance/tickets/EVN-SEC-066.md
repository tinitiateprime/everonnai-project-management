# EVN-SEC-066 - Clear client terms

Project: EverOnnAI. Module: [Security, consent, privacy, legal terms and assurance](../README.md). Source business requirement [BR-066](../../../requirements/BR.md#br-066).

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

Clear client terms. Clients accept clear service terms that define EverOnn as a technology provider, the client's responsibility for its own services and communications, data-processing roles, and call-recording and AI-disclosure responsibilities.

The client accepts the demonstrated outcome and evidence, rather than the existence of a route, table or screen. This ticket does not certify the whole source requirement as complete.

## Current implemented slice

- [ ] Marketing legal pages are not recorded client/DPA acceptance.

The current statement describes prerequisites or context; this business deliverable has not been demonstrated.

## Remaining delivery checklist

- [ ] Publish counsel-approved brand/client terms, version notices and require acceptance before activation.

## Technical component

- [ ] Implement the module boundary and contracts for: LegalDocumentService and activation gates.
- [ ] Maintain tenant boundaries, explicit state transitions, access policy and failure handling for the delivered workflow.
- [ ] Resolve applicable architecture decisions before committing to a new provider or infrastructure baseline.

## DB

Existing module persistence: Private entity tables, scoped auth, encrypted provider payloads and invoker write functions.

The following records/contracts are proposed or require extension; their names are planning terms, not assertions that production tables exist.

- [ ] legal_documents, acceptances, dp_roles.
- [ ] Review scope keys, uniqueness, indexes, retention and migration compatibility; backfill safely and preserve existing tenant records.

## UI

- [ ] Agreement/legal-version review.
- [ ] Provide loading, empty, validation, permission-denied and recoverable failure states with keyboard and mobile access.
- [ ] Show observed facts and pending states accurately; do not present estimates, configured flags or mock results as confirmed business actions.

## Translate - business-to-technical mapping

| Business rule / outcome | Technical responsibility | Evidence needed |
| --- | --- | --- |
| Clear client terms. Clients accept clear service terms that define EverOnn as a technology provider, the client's responsibility for its own services and communications, data-processing roles, and call-recording and AI-disclosure responsibilities. | LegalDocumentService and activation gates | Tenant-scoped end-to-end demonstration of the outcome |
| Publish counsel-approved brand/client terms, version notices and require acceptance before activation. | legal_documents, acceptances, dp_roles; Agreement/legal-version review | Migration/contracts, visible state and failure-path evidence |
| Safe, truthful AI behaviour where applicable | N/A; counsel approves legal wording/responsibilities | Approved context, verified side-effect receipts and evaluation results or justified N/A |
| Client can approve delivery | QA report, rollout evidence and named acceptance owner | Evidence links and dated client sign-off |

This section means requirements-to-implementation mapping. It does not mean language translation; source language obligations are tracked in their own requirements.

## Backend services

- [ ] LegalDocumentService and activation gates.
- [ ] Define request/response/event schemas, authorisation and input validation for each affected operation.
- [ ] For writes and provider effects, define idempotency, retry/timeout, receipts and reconciliation; document N/A where no side effects exist.
- [ ] Expose actionable status and scoped logs without secrets; distinguish completed, failed and uncertain outcomes.

## AI component

N/A; counsel approves legal wording/responsibilities. AI is outside this ticket's runtime scope.

## Testing / QA

- [ ] Exercise the intended user journey with real tenant-scoped state; cover forbidden role and cross-tenant requests.
- [ ] Test malformed inputs, provider failure, retries/replays and cancellation as applicable; keep deterministic mocks separate from live-provider evidence.
- [ ] Review desktop/mobile accessibility, factual copy and failure recovery in the delivered UI.
- [ ] Attach test environment, code/config/instruction versions, results and remaining defects to the acceptance report.

| Source test | Scenario | Required pass criteria | Current disposition |
| --- | --- | --- | --- |
| [AT-45](../../../requirements/AT.md#at-45) | Client terms and disclosures at onboarding | A new client cannot go live without accepting the terms; recording and AI-disclosure settings are explained and recorded; the data-processing terms are available to the client | Full source scenario not evidenced; client acceptance pending |

Source stories: [US-047](../../../requirements/US.md#us-047).

## Deployment

- [ ] Confirm approved hosting/database/provider architecture and required credentials in the deployment environment.
- [ ] Apply compatible migrations/configuration in staging, rehearse rollback, then promote the reviewed artifact.
- [ ] Verify the actual hosted workflow, monitoring, fallback and customer-visible errors after release.
- [ ] Update CODE_PROFILE.md, PROJECT_DATA_FLOW.md and CLIENT_TECHNICAL_QA.md in the application when behaviour or architecture changes.
- [ ] Record deployment identity, operator, timestamp and rollback evidence; document-only tickets instead record the reviewed Git commit.

## Source traceability

| Source ID | Mapping basis | Source section |
| --- | --- | --- |
| [AT-45](../../../requirements/AT.md#at-45) | Source-linked | 25.2 Acceptance tests |
| [BO-7](../../../requirements/BO.md#bo-7) | Source-linked | 3.1 Business objectives |
| [BR-066](../../../requirements/BR.md#br-066) | Source-linked | 7.11 Platform, security, compliance and reliability |
| [BRL-008](../../../requirements/BRL.md#brl-008) | Plan allocation / source cross-reference | 8. Business rules |
| [BRL-017](../../../requirements/BRL.md#brl-017) | Plan allocation / source cross-reference | 8. Business rules |
| [BRL-023](../../../requirements/BRL.md#brl-023) | Plan allocation / source cross-reference | 8. Business rules |
| [COM-003](../../../requirements/COM.md#com-003) | Source-linked | 19.5 Compliance and legal-by-design (COM) |
| [COM-004](../../../requirements/COM.md#com-004) | Source-linked | 19.5 Compliance and legal-by-design (COM) |
| [COM-006](../../../requirements/COM.md#com-006) | Source-linked | 19.5 Compliance and legal-by-design (COM) |
| [COM-009](../../../requirements/COM.md#com-009) | Source-linked | 19.5 Compliance and legal-by-design (COM) |
| [COM-011](../../../requirements/COM.md#com-011) | Plan allocation / source cross-reference | 19.5 Compliance and legal-by-design (COM) |
| [US-047](../../../requirements/US.md#us-047) | Source-linked | EP-10 Compliance, security and privacy |

Read every allocated record, including its continuation bullets and source variants. Source-linked rows preserve explicit document relationships; plan allocations are implementation responsibility assignments created during this review.

## Allocated specification checklist

The unchecked source obligations below require requirement-level evidence. They are deliberately separate from checked statements about current implemented slices. Read linked continuation bullets and additional source wording before accepting a record.

- [ ] [BRL-008](../../../requirements/BRL.md#brl-008): BRL-008 | Call-recording announcements and consent follow the applicable jurisdiction; refusal stops recording. | Voice | COM-004.
- [ ] [BRL-017](../../../requirements/BRL.md#brl-017): BRL-017 | EverOnn provides technology, not the client's trade services; terms and site copy say so. | Legal, websites | COM-006, WEB-002.
- [ ] [BRL-023](../../../requirements/BRL.md#brl-023): BRL-023 | The AI identifies itself as an AI where required and whenever sincerely asked. | AI agents | COM-003.
- [ ] [COM-003](../../../requirements/COM.md#com-003): COM-003 [P1] MUST implement AI disclosure: voice and chat identify as AI where required or when sincerely asked, in a configurable but policy-bounded manner (state and jurisdiction rules table maintained by EverOnn).
- [ ] [COM-004](../../../requirements/COM.md#com-004): COM-004 [P1] MUST implement call recording consent logic by jurisdiction (one-party vs all-party regimes, determined from the caller's and business's locations): play an announcement where needed; if consent is refused, stop recording and continue with transcript-only or per policy. The jurisdiction rules table is data, versioned, and reviewed by counsel.
- [ ] [COM-006](../../../requirements/COM.md#com-006): COM-006 [P1] MUST publish accurate Privacy Policy, Terms, Messaging Terms templates rendered per tenant on their sites, with tenant-specific data controller information.
- [ ] [COM-009](../../../requirements/COM.md#com-009): COM-009 [P1] MUST support data subject rights (access, deletion, correction, opt-out of sale/sharing where applicable) for tenants' customers via tenant-initiated tooling and an EverOnn intake process, with SLAs.
- [ ] [COM-011](../../../requirements/COM.md#com-011): COM-011 [P2] SHOULD maintain a subprocessor register and vendor DPA/BAA tracking; expose it publicly.

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
