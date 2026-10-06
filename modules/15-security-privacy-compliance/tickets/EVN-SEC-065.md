# EVN-SEC-065 - Compliance profile for each vertical

Project: EverOnnAI. Module: [Security, consent, privacy, legal terms and assurance](../README.md). Source business requirement [BR-065](../../../requirements/BR.md#br-065).

| Tracking dimension | Disposition |
| --- | --- |
| Engineering | Planned |
| QA | Existing checks are evidence for current slices; full ticket criteria remain pending |
| Deployment | Current local snapshot; verify ticket-specific hosted rollout and configuration |
| Business acceptance | Pending client review; no signed acceptance recorded |
| Owner | Security Lead + Counsel + Product Owner (proposed role; named person unassigned) |
| Priority / phase | Must / P1 framework, P3 health care |
| Estimate | TBD after scope/architecture agreement; no delivery date committed |
| Dependencies | [EVN-SEC-101](EVN-SEC-101.md), [EVN-SEC-102](EVN-SEC-102.md) |

## Business deliverable

Compliance profile for each vertical. Regulated verticals run under enforced compliance profiles (health-care privacy, legal, insurance, tax and accounting, food ordering, veterinary) that control disclosures, data handling, permitted subprocessors, prohibited advice and human gating.

The client accepts the demonstrated outcome and evidence, rather than the existence of a route, table or screen. This ticket does not certify the whole source requirement as complete.

## Current implemented slice

- [ ] HVAC guardrails are not a compliance-profile engine.

The current statement describes prerequisites or context; this business deliverable has not been demonstrated.

## Remaining delivery checklist

- [ ] Enforce providers, data classes, advice limits, retention and human gates by vertical.

## Technical component

- [ ] Implement the module boundary and contracts for: Compliance resolver and deployment eligibility.
- [ ] Maintain tenant boundaries, explicit state transitions, access policy and failure handling for the delivered workflow.
- [ ] Resolve applicable architecture decisions before committing to a new provider or infrastructure baseline.

## DB

Existing module persistence: Private entity tables, scoped auth, encrypted provider payloads and invoker write functions.

The following records/contracts are proposed or require extension; their names are planning terms, not assertions that production tables exist.

- [ ] compliance_profiles, subprocessor_approvals.
- [ ] Review scope keys, uniqueness, indexes, retention and migration compatibility; backfill safely and preserve existing tenant records.

## UI

- [ ] Profile/readiness/exception review.
- [ ] Provide loading, empty, validation, permission-denied and recoverable failure states with keyboard and mobile access.
- [ ] Show observed facts and pending states accurately; do not present estimates, configured flags or mock results as confirmed business actions.

## Translate - business-to-technical mapping

| Business rule / outcome | Technical responsibility | Evidence needed |
| --- | --- | --- |
| Compliance profile for each vertical. Regulated verticals run under enforced compliance profiles (health-care privacy, legal, insurance, tax and accounting, food ordering, veterinary) that control disclosures, data handling, permitted subprocessors, prohibited advice and human gating. | Compliance resolver and deployment eligibility | Tenant-scoped end-to-end demonstration of the outcome |
| Enforce providers, data classes, advice limits, retention and human gates by vertical. | compliance_profiles, subprocessor_approvals; Profile/readiness/exception review | Migration/contracts, visible state and failure-path evidence |
| Safe, truthful AI behaviour where applicable | Profile-specific scripts, redaction and restricted tools | Approved context, verified side-effect receipts and evaluation results or justified N/A |
| Client can approve delivery | QA report, rollout evidence and named acceptance owner | Evidence links and dated client sign-off |

This section means requirements-to-implementation mapping. It does not mean language translation; source language obligations are tracked in their own requirements.

## Backend services

- [ ] Compliance resolver and deployment eligibility.
- [ ] Define request/response/event schemas, authorisation and input validation for each affected operation.
- [ ] For writes and provider effects, define idempotency, retry/timeout, receipts and reconciliation; document N/A where no side effects exist.
- [ ] Expose actionable status and scoped logs without secrets; distinguish completed, failed and uncertain outcomes.

## AI component

- [ ] Profile-specific scripts, redaction and restricted tools.
- [ ] Record instruction/knowledge/tool versions, measured quality, tenant scope, cost and safe fallback; a Markdown standard alone is not a passed evaluation.

## Testing / QA

- [ ] Exercise the intended user journey with real tenant-scoped state; cover forbidden role and cross-tenant requests.
- [ ] Test malformed inputs, provider failure, retries/replays and cancellation as applicable; keep deterministic mocks separate from live-provider evidence.
- [ ] Review desktop/mobile accessibility, factual copy and failure recovery in the delivered UI.
- [ ] Attach test environment, code/config/instruction versions, results and remaining defects to the acceptance report.

| Source test | Scenario | Required pass criteria | Current disposition |
| --- | --- | --- | --- |
| [AT-11](../../../requirements/AT.md#at-11) | Compliance profile enforcement | A pack under the health-care profile cannot go live unless every provider in the call path is on the agreement-covered list; legal and insurance profiles block advice and quoting; the tax profile prevents collection of return details; profile changes are audited | Full source scenario not evidenced; client acceptance pending |

Source stories: [US-060](../../../requirements/US.md#us-060).

## Deployment

- [ ] Confirm approved hosting/database/provider architecture and required credentials in the deployment environment.
- [ ] Apply compatible migrations/configuration in staging, rehearse rollback, then promote the reviewed artifact.
- [ ] Verify the actual hosted workflow, monitoring, fallback and customer-visible errors after release.
- [ ] Update CODE_PROFILE.md, PROJECT_DATA_FLOW.md and CLIENT_TECHNICAL_QA.md in the application when behaviour or architecture changes.
- [ ] Record deployment identity, operator, timestamp and rollback evidence; document-only tickets instead record the reviewed Git commit.

## Source traceability

| Source ID | Mapping basis | Source section |
| --- | --- | --- |
| [AT-11](../../../requirements/AT.md#at-11) | Source-linked | 25.2 Acceptance tests |
| [BO-7](../../../requirements/BO.md#bo-7) | Source-linked | 3.1 Business objectives |
| [BR-065](../../../requirements/BR.md#br-065) | Source-linked | 7.11 Platform, security, compliance and reliability |
| [BRL-034](../../../requirements/BRL.md#brl-034) | Plan allocation / source cross-reference | 8. Business rules |
| [BRL-035](../../../requirements/BRL.md#brl-035) | Plan allocation / source cross-reference | 8. Business rules |
| [COM-010](../../../requirements/COM.md#com-010) | Plan allocation / source cross-reference | 19.5 Compliance and legal-by-design (COM) |
| [COM-014](../../../requirements/COM.md#com-014) | Source-linked | 19.5 Compliance and legal-by-design (COM) |
| [COM-015](../../../requirements/COM.md#com-015) | Source-linked | 19.5 Compliance and legal-by-design (COM) |
| [COM-016](../../../requirements/COM.md#com-016) | Source-linked | 19.5 Compliance and legal-by-design (COM) |
| [COM-017](../../../requirements/COM.md#com-017) | Source-linked | 19.5 Compliance and legal-by-design (COM) |
| [COM-018](../../../requirements/COM.md#com-018) | Source-linked | 19.5 Compliance and legal-by-design (COM) |
| [INT-005](../../../requirements/INT.md#int-005) | Plan allocation / source cross-reference | 19.10 Integration framework and vertical connectors (INT) |
| [SCF-009](../../../requirements/SCF.md#scf-009) | Plan allocation / source cross-reference | 22.3 Scaffolding checklist |
| [US-060](../../../requirements/US.md#us-060) | Source-linked | EP-12 Verticals and brands |

Read every allocated record, including its continuation bullets and source variants. Source-linked rows preserve explicit document relationships; plan allocations are implementation responsibility assignments created during this review.

## Allocated specification checklist

The unchecked source obligations below require requirement-level evidence. They are deliberately separate from checked statements about current implemented slices. Read linked continuation bullets and additional source wording before accepting a record.

- [ ] [BRL-034](../../../requirements/BRL.md#brl-034): BRL-034 | For HIPAA-covered practices, EverOnn handles patient information only under a signed business associate agreement, only with subprocessors covered by such agreements for the specific product used, and only as much as the conversation needs. | Health-care verticals | COM-015, INT-005.
- [ ] [BRL-035](../../../requirements/BRL.md#brl-035): BRL-035 | The AI gives no clinical, legal, tax or insurance advice. In licensed professions, binding actions and coverage or claims answers are reserved to licensed staff. | AI agents, operators | COM-016, COM-017, POL-001.
- [ ] [COM-010](../../../requirements/COM.md#com-010): COM-010 [P2] SHOULD provide a HIPAA-ready mode (BAA-eligible vendors only, restricted logging, encryption, audit) for health-adjacent verticals in P3; scaffold the compliance_profile field on tenants at P1.
- [ ] [COM-014](../../../requirements/COM.md#com-014): COM-014 [P1] MUST implement a compliance profile framework. Each tenant has a compliance profile (default, hipaa_covered, legal, insurance, tax_accounting, food_ordering, veterinary) that the vertical pack requires and that drives enforced behavior: disclosure texts, recording rules, retention, redaction level, permitted subprocessors, capabilities allowed (for example quoting), prohibited topics, escalation triggers and human gating. Profile changes are audited and cannot be made by the client alone.
- [ ] [COM-015](../../../requirements/COM.md#com-015): COM-015 [P3] MUST provide a health-care privacy mode for HIPAA-covered practices: a workflow for the client to sign the business associate agreement; a subprocessor register that records, per provider and per product or tier, whether an agreement covers it; a patient-information pipeline with no model training, zero-retention or equivalent settings where required, encrypted recordings and transcripts, redacted logs, traces and evaluation data, minimum-necessary capture, short default retention with purge, access logging and a breach-notification workflow. A health-care pack MUST be blocked from going live unless every provider in the call path is covered.
- [ ] [COM-016](../../../requirements/COM.md#com-016): COM-016 [P2] MUST apply professional-services guardrails: for law, disclose the AI, state that no attorney-client relationship exists yet, gather party names for conflict checks without advising, never train on client data, and keep transcripts retrievable; for insurance, gate quotes, coverage explanations, claims-status answers and binding to licensed staff; for accounting and tax, give no tax advice or return-specific answers, never collect Social Security numbers or return details by voice or chat, provide secure-upload instructions, and default to not ingesting return data.
- [ ] [COM-017](../../../requirements/COM.md#com-017): COM-017 [P1] MUST enforce advice limits and safe scripts in every vertical: emergency guidance and routing, no diagnosis or interpretation of results or medication advice, no titles that imply licensure, AI disclosure at the start of every call and chat, and a route to a person.
- [ ] [COM-018](../../../requirements/COM.md#com-018): COM-018 [P2] MUST hold state and vertical rule tables as data, reviewed by counsel: AI-disclosure and recording rules by state and vertical, and outreach rules (calling hours, frequency limits, registration) used by the acquisition console (ACQ-008).
- [ ] [INT-005](../../../requirements/INT.md#int-005): INT-005 [P2] MUST apply data minimization and the vertical's compliance profile to connectors, and for health-care connectors permit only subprocessors covered by business associate agreements (COM-015).
- [ ] [SCF-009](../../../requirements/SCF.md#scf-009): 9 | compliance_profile on tenants and jurisdiction tables as data | HIPAA, state-specific rules, new countries.

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
