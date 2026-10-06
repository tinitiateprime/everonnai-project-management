# EVN-ANL-039 - Proof of value

Project: EverOnnAI. Module: [Customer value, funnel and acquisition analytics](../README.md). Source business requirement [BR-039](../../../requirements/BR.md#br-039).

| Tracking dimension | Disposition |
| --- | --- |
| Engineering | Partial |
| QA | Existing checks are evidence for current slices; full ticket criteria remain pending |
| Deployment | Current local snapshot; verify ticket-specific hosted rollout and configuration |
| Business acceptance | Pending client review; no signed acceptance recorded |
| Owner | Product Analyst + Data/Backend Lead (proposed role; named person unassigned) |
| Priority / phase | Must / P1 |
| Estimate | TBD after scope/architecture agreement; no delivery date committed |
| Dependencies | [EVN-INB-101](../../08-inbox-contacts-booking-followup/tickets/EVN-INB-101.md), [EVN-BIL-101](../../09-plans-billing-usage-margin/tickets/EVN-BIL-101.md), [EVN-OPS-101](../../18-reliability-deployment-scale/tickets/EVN-OPS-101.md) |

## Business deliverable

Proof of value. Clients see proof of value: calls answered, jobs captured and estimated recovered revenue.

The client accepts the demonstrated outcome and evidence, rather than the existence of a route, table or screen. This ticket does not certify the whole source requirement as complete.

## Current implemented slice

- [x] Basic lead/conversation/appointment counters and provider usage are visible.

## Remaining delivery checklist

- [ ] Define measured outcomes, answered-call/job value, editable revenue assumptions and weekly digest.

## Technical component

- [ ] Implement the module boundary and contracts for: Outcome aggregation, attribution and digest service.
- [ ] Maintain tenant boundaries, explicit state transitions, access policy and failure handling for the delivered workflow.
- [ ] Resolve applicable architecture decisions before committing to a new provider or infrastructure baseline.

## DB

Existing module persistence: Operational lead/conversation/appointment counters and metering summaries.

The following records/contracts are proposed or require extension; their names are planning terms, not assertions that production tables exist.

- [ ] outcome_events, analytics_rollups, revenue_assumptions.
- [ ] Review scope keys, uniqueness, indexes, retention and migration compatibility; backfill safely and preserve existing tenant records.

## UI

- [ ] Value dashboard with estimate labels and date/source filters.
- [ ] Provide loading, empty, validation, permission-denied and recoverable failure states with keyboard and mobile access.
- [ ] Show observed facts and pending states accurately; do not present estimates, configured flags or mock results as confirmed business actions.

## Translate - business-to-technical mapping

| Business rule / outcome | Technical responsibility | Evidence needed |
| --- | --- | --- |
| Proof of value. Clients see proof of value: calls answered, jobs captured and estimated recovered revenue. | Outcome aggregation, attribution and digest service | Tenant-scoped end-to-end demonstration of the outcome |
| Define measured outcomes, answered-call/job value, editable revenue assumptions and weekly digest. | outcome_events, analytics_rollups, revenue_assumptions; Value dashboard with estimate labels and date/source filters | Migration/contracts, visible state and failure-path evidence |
| Safe, truthful AI behaviour where applicable | Never present estimated revenue as realised revenue | Approved context, verified side-effect receipts and evaluation results or justified N/A |
| Client can approve delivery | QA report, rollout evidence and named acceptance owner | Evidence links and dated client sign-off |

This section means requirements-to-implementation mapping. It does not mean language translation; source language obligations are tracked in their own requirements.

## Backend services

- [ ] Outcome aggregation, attribution and digest service.
- [ ] Define request/response/event schemas, authorisation and input validation for each affected operation.
- [ ] For writes and provider effects, define idempotency, retry/timeout, receipts and reconciliation; document N/A where no side effects exist.
- [ ] Expose actionable status and scoped logs without secrets; distinguish completed, failed and uncertain outcomes.

## AI component

- [ ] Never present estimated revenue as realised revenue.
- [ ] Record instruction/knowledge/tool versions, measured quality, tenant scope, cost and safe fallback; a Markdown standard alone is not a passed evaluation.

## Testing / QA

- [ ] Exercise the intended user journey with real tenant-scoped state; cover forbidden role and cross-tenant requests.
- [ ] Test malformed inputs, provider failure, retries/replays and cancellation as applicable; keep deterministic mocks separate from live-provider evidence.
- [ ] Review desktop/mobile accessibility, factual copy and failure recovery in the delivered UI.
- [ ] Attach test environment, code/config/instruction versions, results and remaining defects to the acceptance report.

| Source test | Scenario | Required pass criteria | Current disposition |
| --- | --- | --- | --- |
| [AT-57](../../../requirements/AT.md#at-57) | Inbox, dashboard and follow-up | Calls, chats, texts and forms appear as requests with assignment and notes; the dashboard shows calls answered, jobs and recovered revenue; sequences respect consent and quiet hours | Full source scenario not evidenced; client acceptance pending |

Source stories: [US-037](../../../requirements/US.md#us-037).

## Deployment

- [ ] Confirm approved hosting/database/provider architecture and required credentials in the deployment environment.
- [ ] Apply compatible migrations/configuration in staging, rehearse rollback, then promote the reviewed artifact.
- [ ] Verify the actual hosted workflow, monitoring, fallback and customer-visible errors after release.
- [ ] Update CODE_PROFILE.md, PROJECT_DATA_FLOW.md and CLIENT_TECHNICAL_QA.md in the application when behaviour or architecture changes.
- [ ] Record deployment identity, operator, timestamp and rollback evidence; document-only tickets instead record the reviewed Git commit.

## Source traceability

| Source ID | Mapping basis | Source section |
| --- | --- | --- |
| [ANL-001](../../../requirements/ANL.md#anl-001) | Source-linked | 19.2 Analytics and reporting (ANL) |
| [ANL-002](../../../requirements/ANL.md#anl-002) | Plan allocation / source cross-reference | 19.2 Analytics and reporting (ANL) |
| [ANL-003](../../../requirements/ANL.md#anl-003) | Plan allocation / source cross-reference | 19.2 Analytics and reporting (ANL) |
| [ANL-004](../../../requirements/ANL.md#anl-004) | Plan allocation / source cross-reference | 19.2 Analytics and reporting (ANL) |
| [AT-57](../../../requirements/AT.md#at-57) | Source-linked | 25.2 Acceptance tests |
| [BO-8](../../../requirements/BO.md#bo-8) | Source-linked | 3.1 Business objectives |
| [BR-039](../../../requirements/BR.md#br-039) | Source-linked | 7.6 Inbox, follow-up and value |
| [FUP-003](../../../requirements/FUP.md#fup-003) | Plan allocation / source cross-reference | 17.2 Requirements |
| [US-037](../../../requirements/US.md#us-037) | Source-linked | EP-06 Inbox, booking and follow-up |
| [WEB-010](../../../requirements/WEB.md#web-010) | Plan allocation / source cross-reference | 18.3 Requirements |

Read every allocated record, including its continuation bullets and source variants. Source-linked rows preserve explicit document relationships; plan allocations are implementation responsibility assignments created during this review.

## Allocated specification checklist

The unchecked source obligations below require requirement-level evidence. They are deliberately separate from checked statements about current implemented slices. Read linked continuation bullets and additional source wording before accepting a record.

- [ ] [ANL-001](../../../requirements/ANL.md#anl-001): ANL-001 [P1] MUST provide an owner dashboard: calls answered, after-hours calls captured, requests created, booked, estimated recovered revenue, average response time, top questions, knowledge gaps, missed-call rate before/after EverOnn (when baseline data exists), and a weekly emailed digest.
- [ ] [ANL-002](../../../requirements/ANL.md#anl-002): ANL-002 [P1] MUST provide a platform analytics pipeline: events (Appendix C) flow to an analytics store for internal reporting. P1 MAY use MariaDB read replicas and materialized summary tables; P2 SHOULD introduce a columnar store (for example ClickHouse or MariaDB ColumnStore, subject to the RHEL/MariaDB exception process) fed by the outbox stream.
- [ ] [ANL-003](../../../requirements/ANL.md#anl-003): ANL-003 [P1] MUST provide quality dashboards: latency per stage, guardrail hits, escalation rates and reasons, QA scores, eval pass rates by agent version, cost per call and per tenant, and vendor error rates.
- [ ] [ANL-004](../../../requirements/ANL.md#anl-004): ANL-004 [P2] SHOULD provide cohort and funnel analysis for onboarding (claim → verified → live → first call → first booked job → paid).
- [ ] [FUP-003](../../../requirements/FUP.md#fup-003): FUP-003 [P2] SHOULD provide simple pipeline metrics (calls to requests to booked to done) and estimated recovered revenue with owner-editable average job values.
- [ ] [WEB-010](../../../requirements/WEB.md#web-010): WEB-010 [P1] MUST support analytics for tenants: privacy-friendly first-party page views, click-to-call taps, form submissions, chat starts, source attribution (call tracking numbers per source at P2).

## Existing code / check evidence

- `components/dashboard/everonn-dashboard.tsx` - inspected current application working tree; see [snapshot evidence](../../../EVIDENCE.md).
- `features/usage/summary.ts` - inspected current application working tree; see [snapshot evidence](../../../EVIDENCE.md).
- Relevant automated checks: `tests/usage.test.ts`, `tests/product-core.test.ts`. Their scope is bounded by [current validation](../../../CURRENT_STATE.md).

## Blockers and boundaries

Module risk: Counts and provider usage do not prove recovered revenue, cohort retention, operator quality or acquisition attribution.

Dependencies: [EVN-INB-101](../../08-inbox-contacts-booking-followup/tickets/EVN-INB-101.md), [EVN-BIL-101](../../09-plans-billing-usage-margin/tickets/EVN-BIL-101.md), [EVN-OPS-101](../../18-reliability-deployment-scale/tickets/EVN-OPS-101.md). A blocked prerequisite can be prototyped independently, but its contract and deployment must be approved before claiming this ticket delivered. Service limits, third-party approvals and staffing are evidence requirements, not assumptions that they are available.

## Handover and client acceptance

- [ ] Attach the business demonstration, technical evidence and operating/recovery instructions.
- [ ] Assign a named acceptance owner and agree any deferred criteria with the client in writing.
- [ ] Resolve launch-blocking defects and document accepted residual risks.
- [ ] Client records dated acceptance against the deployed/documented version.

Use [the acceptance protocol](../../../ACCEPTANCE.md) and [the ticket update rules](../../../TICKET_TEMPLATE.md) when changing status.
