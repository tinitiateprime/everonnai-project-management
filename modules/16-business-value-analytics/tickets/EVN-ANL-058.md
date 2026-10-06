# EVN-ANL-058 - Acquisition analytics

Project: EverOnnAI. Module: [Customer value, funnel and acquisition analytics](../README.md). Source business requirement [BR-058](../../../requirements/BR.md#br-058).

| Tracking dimension | Disposition |
| --- | --- |
| Engineering | Planned |
| QA | Existing checks are evidence for current slices; full ticket criteria remain pending |
| Deployment | Current local snapshot; verify ticket-specific hosted rollout and configuration |
| Business acceptance | Pending client review; no signed acceptance recorded |
| Owner | Product Analyst + Data/Backend Lead (proposed role; named person unassigned) |
| Priority / phase | Should / P2 |
| Estimate | TBD after scope/architecture agreement; no delivery date committed |
| Dependencies | [EVN-INB-101](../../08-inbox-contacts-booking-followup/tickets/EVN-INB-101.md), [EVN-BIL-101](../../09-plans-billing-usage-margin/tickets/EVN-BIL-101.md), [EVN-OPS-101](../../18-reliability-deployment-scale/tickets/EVN-OPS-101.md) |

## Business deliverable

Acquisition analytics. EverOnn can see, by target, vertical, brand and channel, the prospects, contacts, previews, demonstrations, conversions, time to switch, savings delivered, retention and acquisition cost.

The client accepts the demonstrated outcome and evidence, rather than the existence of a route, table or screen. This ticket does not certify the whole source requirement as complete.

## Current implemented slice

- [ ] Provider usage is not acquisition cohort analytics.

The current statement describes prerequisites or context; this business deliverable has not been demonstrated.

## Remaining delivery checklist

- [ ] Report target/vertical/brand/channel funnel, conversion, savings, migration time, retention and acquisition cost.

## Technical component

- [ ] Implement the module boundary and contracts for: Attribution and funnel aggregation.
- [ ] Maintain tenant boundaries, explicit state transitions, access policy and failure handling for the delivered workflow.
- [ ] Resolve applicable architecture decisions before committing to a new provider or infrastructure baseline.

## DB

Existing module persistence: Operational lead/conversation/appointment counters and metering summaries.

The following records/contracts are proposed or require extension; their names are planning terms, not assertions that production tables exist.

- [ ] acquisition_events, cohort_rollups.
- [ ] Review scope keys, uniqueness, indexes, retention and migration compatibility; backfill safely and preserve existing tenant records.

## UI

- [ ] Acquisition/migration analytics.
- [ ] Provide loading, empty, validation, permission-denied and recoverable failure states with keyboard and mobile access.
- [ ] Show observed facts and pending states accurately; do not present estimates, configured flags or mock results as confirmed business actions.

## Translate - business-to-technical mapping

| Business rule / outcome | Technical responsibility | Evidence needed |
| --- | --- | --- |
| Acquisition analytics. EverOnn can see, by target, vertical, brand and channel, the prospects, contacts, previews, demonstrations, conversions, time to switch, savings delivered, retention and acquisition cost. | Attribution and funnel aggregation | Tenant-scoped end-to-end demonstration of the outcome |
| Report target/vertical/brand/channel funnel, conversion, savings, migration time, retention and acquisition cost. | acquisition_events, cohort_rollups; Acquisition/migration analytics | Migration/contracts, visible state and failure-path evidence |
| Safe, truthful AI behaviour where applicable | Preserve measured versus estimated results | Approved context, verified side-effect receipts and evaluation results or justified N/A |
| Client can approve delivery | QA report, rollout evidence and named acceptance owner | Evidence links and dated client sign-off |

This section means requirements-to-implementation mapping. It does not mean language translation; source language obligations are tracked in their own requirements.

## Backend services

- [ ] Attribution and funnel aggregation.
- [ ] Define request/response/event schemas, authorisation and input validation for each affected operation.
- [ ] For writes and provider effects, define idempotency, retry/timeout, receipts and reconciliation; document N/A where no side effects exist.
- [ ] Expose actionable status and scoped logs without secrets; distinguish completed, failed and uncertain outcomes.

## AI component

- [ ] Preserve measured versus estimated results.
- [ ] Record instruction/knowledge/tool versions, measured quality, tenant scope, cost and safe fallback; a Markdown standard alone is not a passed evaluation.

## Testing / QA

- [ ] Exercise the intended user journey with real tenant-scoped state; cover forbidden role and cross-tenant requests.
- [ ] Test malformed inputs, provider failure, retries/replays and cancellation as applicable; keep deterministic mocks separate from live-provider evidence.
- [ ] Review desktop/mobile accessibility, factual copy and failure recovery in the delivered UI.
- [ ] Attach test environment, code/config/instruction versions, results and remaining defects to the acceptance report.

| Source test | Scenario | Required pass criteria | Current disposition |
| --- | --- | --- | --- |
| [AT-27](../../../requirements/AT.md#at-27) | Acquisition analytics | Funnel, cost per acquired client, time to switch, savings delivered and retention are reported by target, vertical, brand and channel | Full source scenario not evidenced; client acceptance pending |

Source stories: [US-068](../../../requirements/US.md#us-068).

## Deployment

- [ ] Confirm approved hosting/database/provider architecture and required credentials in the deployment environment.
- [ ] Apply compatible migrations/configuration in staging, rehearse rollback, then promote the reviewed artifact.
- [ ] Verify the actual hosted workflow, monitoring, fallback and customer-visible errors after release.
- [ ] Update CODE_PROFILE.md, PROJECT_DATA_FLOW.md and CLIENT_TECHNICAL_QA.md in the application when behaviour or architecture changes.
- [ ] Record deployment identity, operator, timestamp and rollback evidence; document-only tickets instead record the reviewed Git commit.

## Source traceability

| Source ID | Mapping basis | Source section |
| --- | --- | --- |
| [ACQ-012](../../../requirements/ACQ.md#acq-012) | Source-linked | 19.7 Customer acquisition (ACQ) |
| [ANL-004](../../../requirements/ANL.md#anl-004) | Plan allocation / source cross-reference | 19.2 Analytics and reporting (ANL) |
| [AT-27](../../../requirements/AT.md#at-27) | Source-linked | 25.2 Acceptance tests |
| [BO-10](../../../requirements/BO.md#bo-10) | Source-linked | 3.1 Business objectives |
| [BR-058](../../../requirements/BR.md#br-058) | Source-linked | 7.9 Customer acquisition and migration |
| [MIG-009](../../../requirements/MIG.md#mig-009) | Source-linked | 19.8 Migration (MIG) |
| [US-068](../../../requirements/US.md#us-068) | Source-linked | EP-13 Customer acquisition and migration |
| [VRT-007](../../../requirements/VRT.md#vrt-007) | Plan allocation / source cross-reference | 19.6 Brands and vertical packs (VRT) |

Read every allocated record, including its continuation bullets and source variants. Source-linked rows preserve explicit document relationships; plan allocations are implementation responsibility assignments created during this review.

## Allocated specification checklist

The unchecked source obligations below require requirement-level evidence. They are deliberately separate from checked statements about current implemented slices. Read linked continuation bullets and additional source wording before accepting a record.

- [ ] [ACQ-012](../../../requirements/ACQ.md#acq-012): ACQ-012 [P2] SHOULD provide acquisition analytics: funnel by target, vertical, brand and channel; cost per acquired client; time from first contact to live; savings delivered; retention after switching; and the accuracy of each source list measured by sampling.
- [ ] [ANL-004](../../../requirements/ANL.md#anl-004): ANL-004 [P2] SHOULD provide cohort and funnel analysis for onboarding (claim → verified → live → first call → first booked job → paid).
- [ ] [MIG-009](../../../requirements/MIG.md#mig-009): MIG-009 [P2] SHOULD report migration metrics (time to cut-over, defects, rollbacks, support contacts in the first 30 days) by target and feed them back into the playbooks.
- [ ] [VRT-007](../../../requirements/VRT.md#vrt-007): VRT-007 [P2] SHOULD provide brand-level defaults for operators (greeting and desk-profile templates, notices) and cross-brand analytics for EverOnn with a brand and vertical filter.

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
