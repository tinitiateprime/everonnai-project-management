# EVN-BIL-041 - Metering and limits

Project: EverOnnAI. Module: [Plans, subscriptions, metering, budgets and margin](../README.md). Source business requirement [BR-041](../../../requirements/BR.md#br-041).

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

Metering and limits. Usage is metered and plan allowances are enforced without ever blocking emergency handling.

The client accepts the demonstrated outcome and evidence, rather than the existence of a route, table or screen. This ticket does not certify the whole source requirement as complete.

## Current implemented slice

- [x] Gemini/ElevenLabs usage has durable records, dedupe and coverage status.

## Remaining delivery checklist

- [ ] Add all billable meters, Stripe usage, allowances, alerts and emergency-preserving enforcement.

## Technical component

- [ ] Implement the module boundary and contracts for: UsageMeter, entitlements, reconciliation and safe caps.
- [ ] Maintain tenant boundaries, explicit state transitions, access policy and failure handling for the delivered workflow.
- [ ] Resolve applicable architecture decisions before committing to a new provider or infrastructure baseline.

## DB

Existing module persistence: usage_events, usage_sessions, usage_outbox, usage_claims, billing_reports, worker state/nonces/receipts.

The following records/contracts are proposed or require extension; their names are planning terms, not assertions that production tables exist.

- [ ] usage_events, allowances, meter_rollups.
- [ ] Review scope keys, uniqueness, indexes, retention and migration compatibility; backfill safely and preserve existing tenant records.

## UI

- [ ] Usage/allowance dashboard and limit alerts.
- [ ] Provide loading, empty, validation, permission-denied and recoverable failure states with keyboard and mobile access.
- [ ] Show observed facts and pending states accurately; do not present estimates, configured flags or mock results as confirmed business actions.

## Translate - business-to-technical mapping

| Business rule / outcome | Technical responsibility | Evidence needed |
| --- | --- | --- |
| Metering and limits. Usage is metered and plan allowances are enforced without ever blocking emergency handling. | UsageMeter, entitlements, reconciliation and safe caps | Tenant-scoped end-to-end demonstration of the outcome |
| Add all billable meters, Stripe usage, allowances, alerts and emergency-preserving enforcement. | usage_events, allowances, meter_rollups; Usage/allowance dashboard and limit alerts | Migration/contracts, visible state and failure-path evidence |
| Safe, truthful AI behaviour where applicable | Meter retries/rejected output; fallback preserves emergencies | Approved context, verified side-effect receipts and evaluation results or justified N/A |
| Client can approve delivery | QA report, rollout evidence and named acceptance owner | Evidence links and dated client sign-off |

This section means requirements-to-implementation mapping. It does not mean language translation; source language obligations are tracked in their own requirements.

## Backend services

- [ ] UsageMeter, entitlements, reconciliation and safe caps.
- [ ] Define request/response/event schemas, authorisation and input validation for each affected operation.
- [ ] For writes and provider effects, define idempotency, retry/timeout, receipts and reconciliation; document N/A where no side effects exist.
- [ ] Expose actionable status and scoped logs without secrets; distinguish completed, failed and uncertain outcomes.

## AI component

- [ ] Meter retries/rejected output.
- [ ] fallback preserves emergencies.
- [ ] Record instruction/knowledge/tool versions, measured quality, tenant scope, cost and safe fallback; a Markdown standard alone is not a passed evaluation.

## Testing / QA

- [ ] Exercise the intended user journey with real tenant-scoped state; cover forbidden role and cross-tenant requests.
- [ ] Test malformed inputs, provider failure, retries/replays and cancellation as applicable; keep deterministic mocks separate from live-provider evidence.
- [ ] Review desktop/mobile accessibility, factual copy and failure recovery in the delivered UI.
- [ ] Attach test environment, code/config/instruction versions, results and remaining defects to the acceptance report.

| Source test | Scenario | Required pass criteria | Current disposition |
| --- | --- | --- | --- |
| [AT-48](../../../requirements/AT.md#at-48) | Plan limit reached mid-month, and a toll-fraud attempt | Overage or cap rule applied without dropping emergencies; alerts at 80% and 100%; caps and the kill switch stop abusive traffic | Full source scenario not evidenced; client acceptance pending |

Source stories: [US-041](../../../requirements/US.md#us-041).

## Deployment

- [ ] Confirm approved hosting/database/provider architecture and required credentials in the deployment environment.
- [ ] Apply compatible migrations/configuration in staging, rehearse rollback, then promote the reviewed artifact.
- [ ] Verify the actual hosted workflow, monitoring, fallback and customer-visible errors after release.
- [ ] Update CODE_PROFILE.md, PROJECT_DATA_FLOW.md and CLIENT_TECHNICAL_QA.md in the application when behaviour or architecture changes.
- [ ] Record deployment identity, operator, timestamp and rollback evidence; document-only tickets instead record the reviewed Git commit.

## Source traceability

| Source ID | Mapping basis | Source section |
| --- | --- | --- |
| [AT-48](../../../requirements/AT.md#at-48) | Source-linked | 25.2 Acceptance tests |
| [BIL-004](../../../requirements/BIL.md#bil-004) | Source-linked | 19.1 Billing, plans, entitlements and metering (BIL) |
| [BIL-005](../../../requirements/BIL.md#bil-005) | Source-linked | 19.1 Billing, plans, entitlements and metering (BIL) |
| [BIL-010](../../../requirements/BIL.md#bil-010) | Plan allocation / source cross-reference | 19.1 Billing, plans, entitlements and metering (BIL) |
| [BO-5](../../../requirements/BO.md#bo-5) | Source-linked | 3.1 Business objectives |
| [BR-041](../../../requirements/BR.md#br-041) | Source-linked | 7.7 Commercial model |
| [BRL-013](../../../requirements/BRL.md#brl-013) | Plan allocation / source cross-reference | 8. Business rules |
| [BRL-014](../../../requirements/BRL.md#brl-014) | Plan allocation / source cross-reference | 8. Business rules |
| [HIL-012](../../../requirements/HIL.md#hil-012) | Plan allocation / source cross-reference | 16.5 Quality, learning and control of the human layer |
| [US-041](../../../requirements/US.md#us-041) | Source-linked | EP-08 Billing, plans and cost |

Read every allocated record, including its continuation bullets and source variants. Source-linked rows preserve explicit document relationships; plan allocations are implementation responsibility assignments created during this review.

## Allocated specification checklist

The unchecked source obligations below require requirement-level evidence. They are deliberately separate from checked statements about current implemented slices. Read linked continuation bullets and additional source wording before accepting a record.

- [ ] [BIL-004](../../../requirements/BIL.md#bil-004): BIL-004 [P1] MUST implement usage metering: every billable or cost-bearing action emits an immutable usage_event (tenant_id, meter, quantity, unit, occurred_at, source_id, provider_cost_estimate). Meters: voice minutes (inbound, transfer legs), SMS segments, chat conversations or messages (per policy), HITL minutes, site generation, storage. Aggregation is exactly-once in effect (idempotent keys). Usage is pushed to Stripe metered billing where used, and shown to owners in near-real time with alerts at 80% and 100% of allowance.
- [ ] [BIL-005](../../../requirements/BIL.md#bil-005): BIL-005 [P1] MUST enforce limits without dropping emergencies: at the limit, follow the plan's rule (overage billing, soft cap with notice, or hard cap with safe fallback). P1 severity and emergency flows are never blocked by a cap; they are recorded and billed after.
- [ ] [BIL-010](../../../requirements/BIL.md#bil-010): BIL-010 [P2] SHOULD support per-order and per-handled-minute fee components alongside subscriptions, for restaurant ordering and operator handling.
- [ ] [BRL-013](../../../requirements/BRL.md#brl-013): BRL-013 | Emergency and top-priority handling is never blocked by plan limits; usage is recorded and billed afterwards. | Billing | BIL-005.
- [ ] [BRL-014](../../../requirements/BRL.md#brl-014): BRL-014 | Plans grant entitlements; usage beyond an allowance follows the plan's overage or cap rule. | Billing | BIL-001, BIL-004, BIL-005.
- [ ] [HIL-012](../../../requirements/HIL.md#hil-012): HIL-012 [P2] MUST support billing and metering of HITL: minutes of live takeover, callbacks completed, reviews performed, per plan allowances and overage (BIL-004).

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
