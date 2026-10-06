# 14. Restaurant menus, web/phone orders and kitchen delivery

Project: [EverOnnAI client delivery plan](../../README.md). Module code: `ORD`. Proposed accountable roles: Restaurant Product Owner + Integration Lead; named owners await assignment.

## Business outcomes and tickets

| Ticket | Business deliverable | Engineering status | Planning phase |
| --- | --- | --- | --- |
| [EVN-ORD-059](tickets/EVN-ORD-059.md) | Direct online ordering | Planned | P2 |
| [EVN-ORD-060](tickets/EVN-ORD-060.md) | AI phone ordering with readback | Planned | P2 |
| [EVN-ORD-061](tickets/EVN-ORD-061.md) | Orders reach the kitchen | Planned | P2 |
| [EVN-ORD-062](tickets/EVN-ORD-062.md) | Bilingual ordering and tickets | Planned | P2 English, P3 Mandarin and Cantonese |

## Current project capability

**EVN-ORD-059:** Menu/order/payment domains are absent.

**EVN-ORD-060:** Service intake is not restaurant ordering.

**EVN-ORD-061:** Kitchen delivery/acceptance is absent.

**EVN-ORD-062:** Restaurant locale/pronunciation/bilingual printing models are absent.

Current persistence: No menu/cart/order/payment/kitchen domain. These are working-tree capabilities. Hosted availability and full client acceptance must be checked separately.

## Planned technical delivery

Each ticket contains DB, UI, business-to-technical mapping, backend, AI, QA and deployment checklists. Proposed schema/provider terms are labelled as plans rather than existing components. 28 source records are assigned across this module; see [the requirement matrix](../../TRACEABILITY.md) for record-by-record ownership.

Dependencies outside this module: [EVN-AIQ-102](../03-ai-governance-evaluation/tickets/EVN-AIQ-102.md), [EVN-INB-101](../08-inbox-contacts-booking-followup/tickets/EVN-INB-101.md).

## Existing code and verification



## Main delivery risk

A service request is not an accepted restaurant order; payments, allergy escalation, kitchen receipts and pilot accuracy gates are unbuilt.

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
