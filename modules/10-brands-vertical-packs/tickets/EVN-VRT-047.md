# EVN-VRT-047 - Vertical readiness gate

Project: EverOnnAI. Module: [Vertical brands, packs, readiness and capability parity](../README.md). Source business requirement [BR-047](../../../requirements/BR.md#br-047).

| Tracking dimension | Disposition |
| --- | --- |
| Engineering | Planned |
| QA | Existing checks are evidence for current slices; full ticket criteria remain pending |
| Deployment | Current local snapshot; verify ticket-specific hosted rollout and configuration |
| Business acceptance | Pending client review; no signed acceptance recorded |
| Owner | Vertical Manager + Product Owner + Counsel (proposed role; named person unassigned) |
| Priority / phase | Must / P1 |
| Estimate | TBD after scope/architecture agreement; no delivery date committed |
| Dependencies | [EVN-ONB-102](../../01-onboarding-tenancy-identity/tickets/EVN-ONB-102.md), [EVN-AIQ-104](../../03-ai-governance-evaluation/tickets/EVN-AIQ-104.md) |

## Business deliverable

Vertical readiness gate. A vertical goes live only after its readiness checklist (legal review, compliance profile, evaluation results, expert review of playbooks, integration checks, operator training where needed) has been approved by named people.

The client accepts the demonstrated outcome and evidence, rather than the existence of a route, table or screen. This ticket does not certify the whole source requirement as complete.

## Current implemented slice

- [ ] Eval Markdown is not a named-approver launch gate.

The current statement describes prerequisites or context; this business deliverable has not been demonstrated.

## Remaining delivery checklist

- [ ] Block launches pending counsel/expert/QA/integration/pricing/operator evidence and thresholds.

## Technical component

- [ ] Implement the module boundary and contracts for: ReadinessGate and audited publication.
- [ ] Maintain tenant boundaries, explicit state transitions, access policy and failure handling for the delivered workflow.
- [ ] Resolve applicable architecture decisions before committing to a new provider or infrastructure baseline.

## DB

Existing module persistence: Explicit skillId/domain selection and generation skill traces; no first-class brand/pack governance tables.

The following records/contracts are proposed or require extension; their names are planning terms, not assertions that production tables exist.

- [ ] readiness_checks, approvals, pack_evaluations.
- [ ] Review scope keys, uniqueness, indexes, retention and migration compatibility; backfill safely and preserve existing tenant records.

## UI

- [ ] Readiness checklist and evidence approvals.
- [ ] Provide loading, empty, validation, permission-denied and recoverable failure states with keyboard and mobile access.
- [ ] Show observed facts and pending states accurately; do not present estimates, configured flags or mock results as confirmed business actions.

## Translate - business-to-technical mapping

| Business rule / outcome | Technical responsibility | Evidence needed |
| --- | --- | --- |
| Vertical readiness gate. A vertical goes live only after its readiness checklist (legal review, compliance profile, evaluation results, expert review of playbooks, integration checks, operator training where needed) has been approved by named people. | ReadinessGate and audited publication | Tenant-scoped end-to-end demonstration of the outcome |
| Block launches pending counsel/expert/QA/integration/pricing/operator evidence and thresholds. | readiness_checks, approvals, pack_evaluations; Readiness checklist and evidence approvals | Migration/contracts, visible state and failure-path evidence |
| Safe, truthful AI behaviour where applicable | Safety/quality thresholds block unready packs | Approved context, verified side-effect receipts and evaluation results or justified N/A |
| Client can approve delivery | QA report, rollout evidence and named acceptance owner | Evidence links and dated client sign-off |

This section means requirements-to-implementation mapping. It does not mean language translation; source language obligations are tracked in their own requirements.

## Backend services

- [ ] ReadinessGate and audited publication.
- [ ] Define request/response/event schemas, authorisation and input validation for each affected operation.
- [ ] For writes and provider effects, define idempotency, retry/timeout, receipts and reconciliation; document N/A where no side effects exist.
- [ ] Expose actionable status and scoped logs without secrets; distinguish completed, failed and uncertain outcomes.

## AI component

- [ ] Safety/quality thresholds block unready packs.
- [ ] Record instruction/knowledge/tool versions, measured quality, tenant scope, cost and safe fallback; a Markdown standard alone is not a passed evaluation.

## Testing / QA

- [ ] Exercise the intended user journey with real tenant-scoped state; cover forbidden role and cross-tenant requests.
- [ ] Test malformed inputs, provider failure, retries/replays and cancellation as applicable; keep deterministic mocks separate from live-provider evidence.
- [ ] Review desktop/mobile accessibility, factual copy and failure recovery in the delivered UI.
- [ ] Attach test environment, code/config/instruction versions, results and remaining defects to the acceptance report.

| Source test | Scenario | Required pass criteria | Current disposition |
| --- | --- | --- | --- |
| [AT-08](../../../requirements/AT.md#at-08) | Readiness gate blocks an unready vertical | Enabling a pack with an incomplete checklist is refused; approvals record who signed and the evidence; the evaluation threshold blocks a pack that fails safety cases | Full source scenario not evidenced; client acceptance pending |

Source stories: [US-055](../../../requirements/US.md#us-055), [US-060](../../../requirements/US.md#us-060).

## Deployment

- [ ] Confirm approved hosting/database/provider architecture and required credentials in the deployment environment.
- [ ] Apply compatible migrations/configuration in staging, rehearse rollback, then promote the reviewed artifact.
- [ ] Verify the actual hosted workflow, monitoring, fallback and customer-visible errors after release.
- [ ] Update CODE_PROFILE.md, PROJECT_DATA_FLOW.md and CLIENT_TECHNICAL_QA.md in the application when behaviour or architecture changes.
- [ ] Record deployment identity, operator, timestamp and rollback evidence; document-only tickets instead record the reviewed Git commit.

## Source traceability

| Source ID | Mapping basis | Source section |
| --- | --- | --- |
| [ADM-009](../../../requirements/ADM.md#adm-009) | Source-linked | 19.3 Admin back-office (ADM) |
| [AT-08](../../../requirements/AT.md#at-08) | Source-linked | 25.2 Acceptance tests |
| [BO-7](../../../requirements/BO.md#bo-7) | Source-linked | 3.1 Business objectives |
| [BO-11](../../../requirements/BO.md#bo-11) | Source-linked | 3.1 Business objectives |
| [BR-047](../../../requirements/BR.md#br-047) | Source-linked | 7.8 Suite, verticals and brands |
| [BRL-033](../../../requirements/BRL.md#brl-033) | Plan allocation / source cross-reference | 8. Business rules |
| [EVL-010](../../../requirements/EVL.md#evl-010) | Source-linked | 24.5 AI evaluation and safety framework |
| [INT-004](../../../requirements/INT.md#int-004) | Plan allocation / source cross-reference | 19.10 Integration framework and vertical connectors (INT) |
| [US-055](../../../requirements/US.md#us-055) | Source-linked | EP-12 Verticals and brands |
| [US-060](../../../requirements/US.md#us-060) | Source-linked | EP-12 Verticals and brands |
| [VRT-005](../../../requirements/VRT.md#vrt-005) | Source-linked | 19.6 Brands and vertical packs (VRT) |
| [VRT-010](../../../requirements/VRT.md#vrt-010) | Plan allocation / source cross-reference | 19.6 Brands and vertical packs (VRT) |

Read every allocated record, including its continuation bullets and source variants. Source-linked rows preserve explicit document relationships; plan allocations are implementation responsibility assignments created during this review.

## Allocated specification checklist

The unchecked source obligations below require requirement-level evidence. They are deliberately separate from checked statements about current implemented slices. Read linked continuation bullets and additional source wording before accepting a record.

- [ ] [ADM-009](../../../requirements/ADM.md#adm-009): ADM-009 [P1] MUST provide the readiness-gate console (VRT-005) showing checklist status, approvers and evidence.
- [ ] [BRL-033](../../../requirements/BRL.md#brl-033): BRL-033 | A vertical goes live only after its readiness gate has been passed. | Verticals | VRT-005, ADM-009.
- [ ] [EVL-010](../../../requirements/EVL.md#evl-010): EVL-010 [P1] MUST maintain an evaluation dataset per vertical pack (at least 150 scenarios at pack launch and 500 by P2), including vertical-specific safety cases: allergy and dietary questions, clinical advice requests, legal advice and conflicts, coverage and claims-status questions, tax-return details and payment-card disclosure. A pack cannot pass the readiness gate below its thresholds (VRT-005).
- [ ] [INT-004](../../../requirements/INT.md#int-004): INT-004 [P2] SHOULD track integration access as managed work: partner-program applications, terms, certification stages, commercial conditions and owners, visible to the vertical manager.
- [ ] [VRT-005](../../../requirements/VRT.md#vrt-005): VRT-005 [P1] MUST enforce a vertical readiness gate: a checklist per pack whose items (counsel review of terms and disclosures; compliance profile enabled and tested; evaluation set pass thresholds; playbook review by an industry expert; connector and fallback checks; pricing and published-claims check; operator training where the desk will serve the vertical) must each be approved by a named person before the pack can be enabled for production tenants. Approvals are recorded and versioned.
- [ ] [VRT-010](../../../requirements/VRT.md#vrt-010): VRT-010 [P1] MUST support pack governance: an owner (vertical manager) per pack, a change log, a review calendar for time-sensitive content (market prices, regulatory notes), and metrics per pack (time to launch, activation, retention, cost to serve, escalation rate).

## Existing code / check evidence

- `features/agent-runtime/skill-registry.ts` - inspected current application working tree; see [snapshot evidence](../../../EVIDENCE.md).
- `features/agent-runtime/skill-loader.ts` - inspected current application working tree; see [snapshot evidence](../../../EVIDENCE.md).
- `ai/domains/hvac/SKILL.md` - inspected current application working tree; see [snapshot evidence](../../../EVIDENCE.md).
- `ai/domains/hvac/EVALS.md` - inspected current application working tree; see [snapshot evidence](../../../EVIDENCE.md).
- `ai/domains/hvac/SOURCES.md` - inspected current application working tree; see [snapshot evidence](../../../EVIDENCE.md).
- Relevant automated checks: `tests/agent-runtime.test.ts`, `scripts/smoke-hvac.ts`. Their scope is bounded by [current validation](../../../CURRENT_STATE.md).

## Blockers and boundaries

Module risk: One HVAC pack is not two live brands/packs, configuration-only launch, vertical parity or legal/expert/operator readiness approval.

Dependencies: [EVN-ONB-102](../../01-onboarding-tenancy-identity/tickets/EVN-ONB-102.md), [EVN-AIQ-104](../../03-ai-governance-evaluation/tickets/EVN-AIQ-104.md). A blocked prerequisite can be prototyped independently, but its contract and deployment must be approved before claiming this ticket delivered. Service limits, third-party approvals and staffing are evidence requirements, not assumptions that they are available.

## Handover and client acceptance

- [ ] Attach the business demonstration, technical evidence and operating/recovery instructions.
- [ ] Assign a named acceptance owner and agree any deferred criteria with the client in writing.
- [ ] Resolve launch-blocking defects and document accepted residual risks.
- [ ] Client records dated acceptance against the deployed/documented version.

Use [the acceptance protocol](../../../ACCEPTANCE.md) and [the ticket update rules](../../../TICKET_TEMPLATE.md) when changing status.
