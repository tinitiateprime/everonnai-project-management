# EVN-QA-101 - Accept the product against repeatable functional, accessibility and release gates

Project: EverOnnAI. Module: [Testing, accessibility, UAT and release acceptance](../README.md). Technical delivery enabler allocated by this plan; source references below.

| Tracking dimension | Disposition |
| --- | --- |
| Engineering | Partial |
| QA | Existing checks are evidence for current slices; full ticket criteria remain pending |
| Deployment | Current local snapshot; verify ticket-specific hosted rollout and configuration |
| Business acceptance | Pending client review; no signed acceptance recorded |
| Owner | QA Lead + Client Product Owner (proposed role; named person unassigned) |
| Priority / phase | Delivery enabler / P1 |
| Estimate | TBD after scope/architecture agreement; no delivery date committed |
| Dependencies | [EVN-AIQ-103](../../03-ai-governance-evaluation/tickets/EVN-AIQ-103.md), [EVN-OPS-104](../../18-reliability-deployment-scale/tickets/EVN-OPS-104.md) |

## Business deliverable

Accept the product against repeatable functional, accessibility and release gates.

The client accepts the demonstrated outcome and evidence, rather than the existence of a route, table or screen. This ticket does not certify the whole source requirement as complete.

## Current implemented slice

- [x] 127 tests and desktop/mobile fixture smoke checks have passed.

## Remaining delivery checklist

- [ ] Execute all source AT scenarios in staging/live pilot, manual accessibility, visual/performance audits, security and signed UAT.

## Technical component

- [ ] Implement the module boundary and contracts for: CI tests, browser journeys, accessibility/performance and acceptance reports.
- [ ] Maintain tenant boundaries, explicit state transitions, access policy and failure handling for the delivered workflow.
- [ ] Resolve applicable architecture decisions before committing to a new provider or infrastructure baseline.

## DB

Existing module persistence: No signed client AT-result repository in the application.

The following records/contracts are proposed or require extension; their names are planning terms, not assertions that production tables exist.

- [ ] acceptance_results, defects, signoffs, release_evidence.
- [ ] Version the relevant evidence/registers and keep customer secrets out of the documentation repository.

## UI

- [ ] UAT checklists and defect/evidence review.
- [ ] Provide loading, empty, validation, permission-denied and recoverable failure states with keyboard and mobile access.
- [ ] Show observed facts and pending states accurately; do not present estimates, configured flags or mock results as confirmed business actions.

## Translate - business-to-technical mapping

| Business rule / outcome | Technical responsibility | Evidence needed |
| --- | --- | --- |
| Accept the product against repeatable functional, accessibility and release gates. | CI tests, browser journeys, accessibility/performance and acceptance reports | Tenant-scoped end-to-end demonstration of the outcome |
| Execute all source AT scenarios in staging/live pilot, manual accessibility, visual/performance audits, security and signed UAT. | acceptance_results, defects, signoffs, release_evidence; UAT checklists and defect/evidence review | Migration/contracts, visible state and failure-path evidence |
| Safe, truthful AI behaviour where applicable | Real model/audio evaluation is separate from deterministic mocks | Approved context, verified side-effect receipts and evaluation results or justified N/A |
| Client can approve delivery | QA report, rollout evidence and named acceptance owner | Evidence links and dated client sign-off |

This section means requirements-to-implementation mapping. It does not mean language translation; source language obligations are tracked in their own requirements.

## Backend services

- [ ] CI tests, browser journeys, accessibility/performance and acceptance reports.
- [ ] Define request/response/event schemas, authorisation and input validation for each affected operation.
- [ ] For writes and provider effects, define idempotency, retry/timeout, receipts and reconciliation; document N/A where no side effects exist.
- [ ] Expose actionable status and scoped logs without secrets; distinguish completed, failed and uncertain outcomes.

## AI component

- [ ] Real model/audio evaluation is separate from deterministic mocks.
- [ ] Record instruction/knowledge/tool versions, measured quality, tenant scope, cost and safe fallback; a Markdown standard alone is not a passed evaluation.

## Testing / QA

- [ ] Exercise the intended user journey with real tenant-scoped state; cover forbidden role and cross-tenant requests.
- [ ] Test malformed inputs, provider failure, retries/replays and cancellation as applicable; keep deterministic mocks separate from live-provider evidence.
- [ ] Review desktop/mobile accessibility, factual copy and failure recovery in the delivered UI.
- [ ] Attach test environment, code/config/instruction versions, results and remaining defects to the acceptance report.

No dedicated source AT is assigned to this enabling/extension ticket. Define a ticket-specific acceptance report before closing it; the module and release gates still apply.

Source stories: No dedicated source story; business/enabling outcome above is the acceptance brief.

## Deployment

- [ ] Confirm approved hosting/database/provider architecture and required credentials in the deployment environment.
- [ ] Apply compatible migrations/configuration in staging, rehearse rollback, then promote the reviewed artifact.
- [ ] Verify the actual hosted workflow, monitoring, fallback and customer-visible errors after release.
- [ ] Update CODE_PROFILE.md, PROJECT_DATA_FLOW.md and CLIENT_TECHNICAL_QA.md in the application when behaviour or architecture changes.
- [ ] Record deployment identity, operator, timestamp and rollback evidence; document-only tickets instead record the reviewed Git commit.

## Source traceability

| Source ID | Mapping basis | Source section |
| --- | --- | --- |
| [COM-013](../../../requirements/COM.md#com-013) | Source-linked | 19.5 Compliance and legal-by-design (COM) |
| [SEC-014](../../../requirements/SEC.md#sec-014) | Source-linked | 22.2 Security requirements |

Read every allocated record, including its continuation bullets and source variants. Source-linked rows preserve explicit document relationships; plan allocations are implementation responsibility assignments created during this review.

## Allocated specification checklist

The unchecked source obligations below require requirement-level evidence. They are deliberately separate from checked statements about current implemented slices. Read linked continuation bullets and additional source wording before accepting a record.

- [ ] [COM-013](../../../requirements/COM.md#com-013): COM-013 [P1] MUST support accessibility compliance (WCAG 2.1 AA) for the dashboard, widget and generated sites.
- [ ] [SEC-014](../../../requirements/SEC.md#sec-014): SEC-014 [P1] MUST test isolation continuously (TEN-001) and include tenant-isolation cases in the pen-test scope.

## Existing code / check evidence

- `tests/` - inspected current application working tree; see [snapshot evidence](../../../EVIDENCE.md).
- `scripts/smoke-hvac.ts` - inspected current application working tree; see [snapshot evidence](../../../EVIDENCE.md).
- `scripts/smoke-booking.ts` - inspected current application working tree; see [snapshot evidence](../../../EVIDENCE.md).
- `scripts/smoke-usage.ts` - inspected current application working tree; see [snapshot evidence](../../../EVIDENCE.md).
- `scripts/smoke-project-workspace.ts` - inspected current application working tree; see [snapshot evidence](../../../EVIDENCE.md).
- Relevant automated checks: `tests/agent-runtime.test.ts`, `tests/website-code.test.ts`, `tests/lead-automation.test.ts`, `tests/project-workspace.test.ts`. Their scope is bounded by [current validation](../../../CURRENT_STATE.md).

## Blockers and boundaries

Module risk: 127 automated tests and fixture smoke passes do not establish all 60 source acceptance scenarios, real model/audio outcomes, WCAG conformance or client sign-off.

Dependencies: [EVN-AIQ-103](../../03-ai-governance-evaluation/tickets/EVN-AIQ-103.md), [EVN-OPS-104](../../18-reliability-deployment-scale/tickets/EVN-OPS-104.md). A blocked prerequisite can be prototyped independently, but its contract and deployment must be approved before claiming this ticket delivered. Service limits, third-party approvals and staffing are evidence requirements, not assumptions that they are available.

## Handover and client acceptance

- [ ] Attach the business demonstration, technical evidence and operating/recovery instructions.
- [ ] Assign a named acceptance owner and agree any deferred criteria with the client in writing.
- [ ] Resolve launch-blocking defects and document accepted residual risks.
- [ ] Client records dated acceptance against the deployed/documented version.

Use [the acceptance protocol](../../../ACCEPTANCE.md) and [the ticket update rules](../../../TICKET_TEMPLATE.md) when changing status.
