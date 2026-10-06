# 16. Customer value, funnel and acquisition analytics

Project: [EverOnnAI client delivery plan](../../README.md). Module code: `ANL`. Proposed accountable roles: Product Analyst + Data/Backend Lead; named owners await assignment.

## Business outcomes and tickets

| Ticket | Business deliverable | Engineering status | Planning phase |
| --- | --- | --- | --- |
| [EVN-ANL-039](tickets/EVN-ANL-039.md) | Proof of value | Partial | P1 |
| [EVN-ANL-058](tickets/EVN-ANL-058.md) | Acquisition analytics | Planned | P2 |

## Current project capability

**EVN-ANL-039:** Basic lead/conversation/appointment counters and provider usage are visible.

**EVN-ANL-058:** Provider usage is not acquisition cohort analytics.

Current persistence: Operational lead/conversation/appointment counters and metering summaries. These are working-tree capabilities. Hosted availability and full client acceptance must be checked separately.

## Planned technical delivery

Each ticket contains DB, UI, business-to-technical mapping, backend, AI, QA and deployment checklists. Proposed schema/provider terms are labelled as plans rather than existing components. 17 source records are assigned across this module; see [the requirement matrix](../../TRACEABILITY.md) for record-by-record ownership.

Dependencies outside this module: [EVN-BIL-101](../09-plans-billing-usage-margin/tickets/EVN-BIL-101.md), [EVN-INB-101](../08-inbox-contacts-booking-followup/tickets/EVN-INB-101.md), [EVN-OPS-101](../18-reliability-deployment-scale/tickets/EVN-OPS-101.md).

## Existing code and verification

- `components/dashboard/everonn-dashboard.tsx` - inspected current application working tree; see [snapshot evidence](../../EVIDENCE.md).
- `features/usage/summary.ts` - inspected current application working tree; see [snapshot evidence](../../EVIDENCE.md).
- Relevant automated checks: `tests/usage.test.ts`, `tests/product-core.test.ts`. Their scope is bounded by [current validation](../../CURRENT_STATE.md).

## Main delivery risk

Counts and provider usage do not prove recovered revenue, cohort retention, operator quality or acquisition attribution.

## Module completion gate

- [ ] Ticket scope, priority and accountable people agreed.
- [ ] Business outcomes demonstrated with authorised tenant data.
- [ ] Applicable source requirements and acceptance scenarios passed with evidence.
- [ ] Database, contracts, role boundaries and failure handling reviewed.
- [ ] AI quality/safety and provider cost validated where applicable.
- [ ] UI accessibility and responsive behaviour reviewed.
- [ ] Hosted rollout, monitoring, recovery and operational ownership verified.
- [ ] Client signs the released version; deferred items have explicit written disposition.

An implemented slice or a passing unit suite does not close this module. See [current status](../../CURRENT_STATE.md) and [the phase plan](../../DELIVERY_PLAN.md).
