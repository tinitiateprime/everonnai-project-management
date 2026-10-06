# EVN-BIL-042 - Cost and margin visibility

Project: EverOnnAI. Module: [Plans, subscriptions, metering, budgets and margin](../README.md). Source business requirement [BR-042](../../../requirements/BR.md#br-042).

| Tracking dimension | Disposition |
| --- | --- |
| Engineering | Partial |
| QA | Existing checks are evidence for current slices; full ticket criteria remain pending |
| Deployment | Current local snapshot; verify ticket-specific hosted rollout and configuration |
| Business acceptance | Pending client review; no signed acceptance recorded |
| Owner | Finance/Product Owner + Backend Lead (proposed role; named person unassigned) |
| Priority / phase | Must / P1 |
| Estimate | TBD after scope/architecture agreement; no delivery date committed |
| Dependencies | [EVN-BIL-101](EVN-BIL-101.md), [EVN-ONB-102](../../01-onboarding-tenancy-identity/tickets/EVN-ONB-102.md) |

## Business deliverable

Cost and margin visibility. EverOnn sees cost and margin per client, plan and vendor (including operator minutes), with automatic cost circuit breakers.

The client accepts the demonstrated outcome and evidence, rather than the existence of a route, table or screen. This ticket does not certify the whole source requirement as complete.

## Current implemented slice

- [x] Reported costs and dated Gemini token estimates stay distinct.

## Remaining delivery checklist

- [ ] Add carrier/STT/TTS/SMS/storage/operator costs, margins, budgets and automatic breakers.

## Technical component

- [ ] Implement the module boundary and contracts for: Cost attribution, anomaly detection and circuit breakers.
- [ ] Maintain tenant boundaries, explicit state transitions, access policy and failure handling for the delivered workflow.
- [ ] Resolve applicable architecture decisions before committing to a new provider or infrastructure baseline.

## DB

Existing module persistence: usage_events, usage_sessions, usage_outbox, usage_claims, billing_reports, worker state/nonces/receipts.

The following records/contracts are proposed or require extension; their names are planning terms, not assertions that production tables exist.

- [ ] provider_costs, operator_minutes, margin_rollups.
- [ ] Review scope keys, uniqueness, indexes, retention and migration compatibility; backfill safely and preserve existing tenant records.

## UI

- [ ] Tenant/plan/vendor margin dashboard.
- [ ] Provide loading, empty, validation, permission-denied and recoverable failure states with keyboard and mobile access.
- [ ] Show observed facts and pending states accurately; do not present estimates, configured flags or mock results as confirmed business actions.

## Translate - business-to-technical mapping

| Business rule / outcome | Technical responsibility | Evidence needed |
| --- | --- | --- |
| Cost and margin visibility. EverOnn sees cost and margin per client, plan and vendor (including operator minutes), with automatic cost circuit breakers. | Cost attribution, anomaly detection and circuit breakers | Tenant-scoped end-to-end demonstration of the outcome |
| Add carrier/STT/TTS/SMS/storage/operator costs, margins, budgets and automatic breakers. | provider_costs, operator_minutes, margin_rollups; Tenant/plan/vendor margin dashboard | Migration/contracts, visible state and failure-path evidence |
| Safe, truthful AI behaviour where applicable | Task budgets/tier routing; estimates are not invoices | Approved context, verified side-effect receipts and evaluation results or justified N/A |
| Client can approve delivery | QA report, rollout evidence and named acceptance owner | Evidence links and dated client sign-off |

This section means requirements-to-implementation mapping. It does not mean language translation; source language obligations are tracked in their own requirements.

## Backend services

- [ ] Cost attribution, anomaly detection and circuit breakers.
- [ ] Define request/response/event schemas, authorisation and input validation for each affected operation.
- [ ] For writes and provider effects, define idempotency, retry/timeout, receipts and reconciliation; document N/A where no side effects exist.
- [ ] Expose actionable status and scoped logs without secrets; distinguish completed, failed and uncertain outcomes.

## AI component

- [ ] Task budgets/tier routing.
- [ ] estimates are not invoices.
- [ ] Record instruction/knowledge/tool versions, measured quality, tenant scope, cost and safe fallback; a Markdown standard alone is not a passed evaluation.

## Testing / QA

- [ ] Exercise the intended user journey with real tenant-scoped state; cover forbidden role and cross-tenant requests.
- [ ] Test malformed inputs, provider failure, retries/replays and cancellation as applicable; keep deterministic mocks separate from live-provider evidence.
- [ ] Review desktop/mobile accessibility, factual copy and failure recovery in the delivered UI.
- [ ] Attach test environment, code/config/instruction versions, results and remaining defects to the acceptance report.

| Source test | Scenario | Required pass criteria | Current disposition |
| --- | --- | --- | --- |
| [AT-56](../../../requirements/AT.md#at-56) | Subscription, entitlements and margin | A plan change reaches entitlements without a deployment; Stripe reconciliation is clean; margin per client including operator minutes is visible | Full source scenario not evidenced; client acceptance pending |

Source stories: [US-043](../../../requirements/US.md#us-043).

## Deployment

- [ ] Confirm approved hosting/database/provider architecture and required credentials in the deployment environment.
- [ ] Apply compatible migrations/configuration in staging, rehearse rollback, then promote the reviewed artifact.
- [ ] Verify the actual hosted workflow, monitoring, fallback and customer-visible errors after release.
- [ ] Update CODE_PROFILE.md, PROJECT_DATA_FLOW.md and CLIENT_TECHNICAL_QA.md in the application when behaviour or architecture changes.
- [ ] Record deployment identity, operator, timestamp and rollback evidence; document-only tickets instead record the reviewed Git commit.

## Source traceability

| Source ID | Mapping basis | Source section |
| --- | --- | --- |
| [ADM-004](../../../requirements/ADM.md#adm-004) | Source-linked | 19.3 Admin back-office (ADM) |
| [AT-56](../../../requirements/AT.md#at-56) | Source-linked | 25.2 Acceptance tests |
| [BIL-007](../../../requirements/BIL.md#bil-007) | Source-linked | 19.1 Billing, plans, entitlements and metering (BIL) |
| [BO-5](../../../requirements/BO.md#bo-5) | Source-linked | 3.1 Business objectives |
| [BR-042](../../../requirements/BR.md#br-042) | Source-linked | 7.7 Commercial model |
| [CST-001](../../../requirements/CST.md#cst-001) | Source-linked | 23.6 Unit economics and cost controls |
| [CST-002](../../../requirements/CST.md#cst-002) | Source-linked | 23.6 Unit economics and cost controls |
| [CST-007](../../../requirements/CST.md#cst-007) | Source-linked | 23.6 Unit economics and cost controls |
| [US-043](../../../requirements/US.md#us-043) | Source-linked | EP-08 Billing, plans and cost |

Read every allocated record, including its continuation bullets and source variants. Source-linked rows preserve explicit document relationships; plan allocations are implementation responsibility assignments created during this review.

## Allocated specification checklist

The unchecked source obligations below require requirement-level evidence. They are deliberately separate from checked statements about current implemented slices. Read linked continuation bullets and additional source wording before accepting a record.

- [ ] [ADM-004](../../../requirements/ADM.md#adm-004): ADM-004 [P1] MUST provide cost and margin dashboards per tenant, per plan and per vendor, with alerting on abnormal spend.
- [ ] [BIL-007](../../../requirements/BIL.md#bil-007): BIL-007 [P1] MUST compute and store per-tenant cost of service (telephony, STT, LLM tokens, TTS characters, SMS, storage) to power margin dashboards (ADM-004) and cost circuit breakers (VOX-026).
- [ ] [CST-001](../../../requirements/CST.md#cst-001): CST-001 [P0] MUST produce a cost model and measured per-minute cost in the P0 spike for at least three vendor combinations, and recommend the default stack by cost and quality.
- [ ] [CST-002](../../../requirements/CST.md#cst-002): CST-002 [P1] MUST implement per-call, per-tenant and global cost budgets with alerts and circuit breakers (VOX-026), and dashboards for margin by tenant (ADM-004).
- [ ] [CST-007](../../../requirements/CST.md#cst-007): CST-007 [P2] MUST model, meter and report the cost of operator-handled time per client, vertical and escalation reason (§16.7.5), so that operator add-on pricing (D-1) covers it and escalation rate can be managed as a margin lever.

## Existing code / check evidence

- `features/usage/gemini.ts` - inspected current application working tree; see [snapshot evidence](../../../EVIDENCE.md).
- `features/usage/elevenlabs.ts` - inspected current application working tree; see [snapshot evidence](../../../EVIDENCE.md).
- `features/usage/worker.ts` - inspected current application working tree; see [snapshot evidence](../../../EVIDENCE.md).
- `features/usage/summary.ts` - inspected current application working tree; see [snapshot evidence](../../../EVIDENCE.md).
- `features/usage/pricing.ts` - inspected current application working tree; see [snapshot evidence](../../../EVIDENCE.md).
- `features/usage/billing.ts` - inspected current application working tree; see [snapshot evidence](../../../EVIDENCE.md).
- `features/usage/job-auth.ts` - inspected current application working tree; see [snapshot evidence](../../../EVIDENCE.md).
- `features/usage/webhook.ts` - inspected current application working tree; see [snapshot evidence](../../../EVIDENCE.md).
- `components/dashboard/usage-section.tsx` - inspected current application working tree; see [snapshot evidence](../../../EVIDENCE.md).
- `lib/usage-postgres.ts` - inspected current application working tree; see [snapshot evidence](../../../EVIDENCE.md).
- `lib/usage-scheduler.ts` - inspected current application working tree; see [snapshot evidence](../../../EVIDENCE.md).
- Relevant automated checks: `tests/usage.test.ts`, `tests/usage-reliability.test.ts`, `tests/usage-scheduler.test.ts`, `tests/usage-supabase.test.ts`, `scripts/smoke-usage.ts`. Their scope is bounded by [current validation](../../../CURRENT_STATE.md).

## Blockers and boundaries

Module risk: Observed usage/estimated provider costs are not subscriptions, Stripe invoices, plan enforcement, all-channel costs or measured margins.

Dependencies: [EVN-BIL-101](EVN-BIL-101.md), [EVN-ONB-102](../../01-onboarding-tenancy-identity/tickets/EVN-ONB-102.md). A blocked prerequisite can be prototyped independently, but its contract and deployment must be approved before claiming this ticket delivered. Service limits, third-party approvals and staffing are evidence requirements, not assumptions that they are available.

## Handover and client acceptance

- [ ] Attach the business demonstration, technical evidence and operating/recovery instructions.
- [ ] Assign a named acceptance owner and agree any deferred criteria with the client in writing.
- [ ] Resolve launch-blocking defects and document accepted residual risks.
- [ ] Client records dated acceptance against the deployed/documented version.

Use [the acceptance protocol](../../../ACCEPTANCE.md) and [the ticket update rules](../../../TICKET_TEMPLATE.md) when changing status.
