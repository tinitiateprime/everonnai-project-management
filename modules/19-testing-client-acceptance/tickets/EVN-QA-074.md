# EVN-QA-074 - Accessibility

Project: EverOnnAI. Module: [Testing, accessibility, UAT and release acceptance](../README.md). Source business requirement [BR-074](../../../requirements/BR.md#br-074).

| Tracking dimension | Disposition |
| --- | --- |
| Engineering | Partial |
| QA | Existing checks are evidence for current slices; full ticket criteria remain pending |
| Deployment | Current local snapshot; verify ticket-specific hosted rollout and configuration |
| Business acceptance | Pending client review; no signed acceptance recorded |
| Owner | QA Lead + Client Product Owner (proposed role; named person unassigned) |
| Priority / phase | Must / P1 |
| Estimate | TBD after scope/architecture agreement; no delivery date committed |
| Dependencies | [EVN-QA-101](EVN-QA-101.md) |

## Business deliverable

Accessibility. Dashboards, the desk, the widget and generated sites are accessible (WCAG 2.1 AA).

The client accepts the demonstrated outcome and evidence, rather than the existence of a route, table or screen. This ticket does not certify the whole source requirement as complete.

## Current implemented slice

- [x] Responsive controls, semantic generated HTML and mobile smoke checks exist.

## Remaining delivery checklist

- [ ] Audit WCAG 2.1 AA keyboard/screen-reader/contrast across dashboard, widget, desk and sites.

## Technical component

- [ ] Implement the module boundary and contracts for: Automated checks plus manual review.
- [ ] Maintain tenant boundaries, explicit state transitions, access policy and failure handling for the delivered workflow.
- [ ] Resolve applicable architecture decisions before committing to a new provider or infrastructure baseline.

## DB

Existing module persistence: No signed client AT-result repository in the application.

The following records/contracts are proposed or require extension; their names are planning terms, not assertions that production tables exist.

- [ ] accessibility_findings, remediation_evidence.
- [ ] Version the relevant evidence/registers and keep customer secrets out of the documentation repository.

## UI

- [ ] Accessible focus/dialog/keyboard/assistive flows.
- [ ] Provide loading, empty, validation, permission-denied and recoverable failure states with keyboard and mobile access.
- [ ] Show observed facts and pending states accurately; do not present estimates, configured flags or mock results as confirmed business actions.

## Translate - business-to-technical mapping

| Business rule / outcome | Technical responsibility | Evidence needed |
| --- | --- | --- |
| Accessibility. Dashboards, the desk, the widget and generated sites are accessible (WCAG 2.1 AA). | Automated checks plus manual review | Tenant-scoped end-to-end demonstration of the outcome |
| Audit WCAG 2.1 AA keyboard/screen-reader/contrast across dashboard, widget, desk and sites. | accessibility_findings, remediation_evidence; Accessible focus/dialog/keyboard/assistive flows | Migration/contracts, visible state and failure-path evidence |
| Safe, truthful AI behaviour where applicable | Generated-code gate includes accessibility | Approved context, verified side-effect receipts and evaluation results or justified N/A |
| Client can approve delivery | QA report, rollout evidence and named acceptance owner | Evidence links and dated client sign-off |

This section means requirements-to-implementation mapping. It does not mean language translation; source language obligations are tracked in their own requirements.

## Backend services

- [ ] Automated checks plus manual review.
- [ ] Define request/response/event schemas, authorisation and input validation for each affected operation.
- [ ] For writes and provider effects, define idempotency, retry/timeout, receipts and reconciliation; document N/A where no side effects exist.
- [ ] Expose actionable status and scoped logs without secrets; distinguish completed, failed and uncertain outcomes.

## AI component

- [ ] Generated-code gate includes accessibility.
- [ ] Record instruction/knowledge/tool versions, measured quality, tenant scope, cost and safe fallback; a Markdown standard alone is not a passed evaluation.

## Testing / QA

- [ ] Exercise the intended user journey with real tenant-scoped state; cover forbidden role and cross-tenant requests.
- [ ] Test malformed inputs, provider failure, retries/replays and cancellation as applicable; keep deterministic mocks separate from live-provider evidence.
- [ ] Review desktop/mobile accessibility, factual copy and failure recovery in the delivered UI.
- [ ] Attach test environment, code/config/instruction versions, results and remaining defects to the acceptance report.

| Source test | Scenario | Required pass criteria | Current disposition |
| --- | --- | --- | --- |
| [AT-52](../../../requirements/AT.md#at-52) | Accessibility audit | WCAG 2.1 AA on dashboard, desk, widget and generated site templates | Full source scenario not evidenced; client acceptance pending |

Source stories: [US-053](../../../requirements/US.md#us-053).

## Deployment

- [ ] Confirm approved hosting/database/provider architecture and required credentials in the deployment environment.
- [ ] Apply compatible migrations/configuration in staging, rehearse rollback, then promote the reviewed artifact.
- [ ] Verify the actual hosted workflow, monitoring, fallback and customer-visible errors after release.
- [ ] Update CODE_PROFILE.md, PROJECT_DATA_FLOW.md and CLIENT_TECHNICAL_QA.md in the application when behaviour or architecture changes.
- [ ] Record deployment identity, operator, timestamp and rollback evidence; document-only tickets instead record the reviewed Git commit.

## Source traceability

| Source ID | Mapping basis | Source section |
| --- | --- | --- |
| [AT-52](../../../requirements/AT.md#at-52) | Source-linked | 25.2 Acceptance tests |
| [BO-7](../../../requirements/BO.md#bo-7) | Source-linked | 3.1 Business objectives |
| [BO-8](../../../requirements/BO.md#bo-8) | Source-linked | 3.1 Business objectives |
| [BR-074](../../../requirements/BR.md#br-074) | Source-linked | 7.11 Platform, security, compliance and reliability |
| [COM-013](../../../requirements/COM.md#com-013) | Source-linked | 19.5 Compliance and legal-by-design (COM) |
| [DSK-025](../../../requirements/DSK.md#dsk-025) | Source-linked | 16.4.7 Ergonomics and resilience |
| [US-053](../../../requirements/US.md#us-053) | Source-linked | EP-11 Integrations, scale and ownership |

Read every allocated record, including its continuation bullets and source variants. Source-linked rows preserve explicit document relationships; plan allocations are implementation responsibility assignments created during this review.

## Allocated specification checklist

The unchecked source obligations below require requirement-level evidence. They are deliberately separate from checked statements about current implemented slices. Read linked continuation bullets and additional source wording before accepting a record.

- [ ] [COM-013](../../../requirements/COM.md#com-013): COM-013 [P1] MUST support accessibility compliance (WCAG 2.1 AA) for the dashboard, widget and generated sites.
- [ ] [DSK-025](../../../requirements/DSK.md#dsk-025): DSK-025 [P1] SHOULD be keyboard-first and accessible: shortcuts for accept, hold, transfer and wrap-up; a large client banner; light and dark themes; pop-out panels for multiple monitors; screen-reader support; WCAG 2.1 AA; distinct audio cues by severity.

## Existing code / check evidence

- `tests/` - inspected current application working tree; see [snapshot evidence](../../../EVIDENCE.md).
- `scripts/smoke-hvac.ts` - inspected current application working tree; see [snapshot evidence](../../../EVIDENCE.md).
- `scripts/smoke-booking.ts` - inspected current application working tree; see [snapshot evidence](../../../EVIDENCE.md).
- `scripts/smoke-usage.ts` - inspected current application working tree; see [snapshot evidence](../../../EVIDENCE.md).
- `scripts/smoke-project-workspace.ts` - inspected current application working tree; see [snapshot evidence](../../../EVIDENCE.md).
- Relevant automated checks: `tests/agent-runtime.test.ts`, `tests/website-code.test.ts`, `tests/lead-automation.test.ts`, `tests/project-workspace.test.ts`. Their scope is bounded by [current validation](../../../CURRENT_STATE.md).

## Blockers and boundaries

Module risk: 127 automated tests and fixture smoke passes do not establish all 60 source acceptance scenarios, real model/audio outcomes, WCAG conformance or client sign-off.

Dependencies: [EVN-QA-101](EVN-QA-101.md). A blocked prerequisite can be prototyped independently, but its contract and deployment must be approved before claiming this ticket delivered. Service limits, third-party approvals and staffing are evidence requirements, not assumptions that they are available.

## Handover and client acceptance

- [ ] Attach the business demonstration, technical evidence and operating/recovery instructions.
- [ ] Assign a named acceptance owner and agree any deferred criteria with the client in writing.
- [ ] Resolve launch-blocking defects and document accepted residual risks.
- [ ] Client records dated acceptance against the deployed/documented version.

Use [the acceptance protocol](../../../ACCEPTANCE.md) and [the ticket update rules](../../../TICKET_TEMPLATE.md) when changing status.
