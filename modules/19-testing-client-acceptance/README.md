# 19. Testing, accessibility, UAT and release acceptance

Project: [EverOnnAI client delivery plan](../../README.md). Module code: `QA`. Proposed accountable roles: QA Lead + Client Product Owner; named owners await assignment.

## Business outcomes and tickets

| Ticket | Business deliverable | Engineering status | Planning phase |
| --- | --- | --- | --- |
| [EVN-QA-074](tickets/EVN-QA-074.md) | Accessibility | Partial | P1 |
| [EVN-QA-101](tickets/EVN-QA-101.md) | Accept the product against repeatable functional, accessibility and release gates | Partial | P1 |

## Current project capability

**EVN-QA-074:** Responsive controls, semantic generated HTML and mobile smoke checks exist.

**EVN-QA-101:** 127 tests and desktop/mobile fixture smoke checks have passed.

Current persistence: No signed client AT-result repository in the application. These are working-tree capabilities. Hosted availability and full client acceptance must be checked separately.

## Planned technical delivery

Each ticket contains DB, UI, business-to-technical mapping, backend, AI, QA and deployment checklists. Proposed schema/provider terms are labelled as plans rather than existing components. 8 source records are assigned across this module; see [the requirement matrix](../../TRACEABILITY.md) for record-by-record ownership.

Dependencies outside this module: [EVN-AIQ-103](../03-ai-governance-evaluation/tickets/EVN-AIQ-103.md), [EVN-OPS-104](../18-reliability-deployment-scale/tickets/EVN-OPS-104.md).

## Existing code and verification

- `tests/` - inspected current application working tree; see [snapshot evidence](../../EVIDENCE.md).
- `scripts/smoke-hvac.ts` - inspected current application working tree; see [snapshot evidence](../../EVIDENCE.md).
- `scripts/smoke-booking.ts` - inspected current application working tree; see [snapshot evidence](../../EVIDENCE.md).
- `scripts/smoke-usage.ts` - inspected current application working tree; see [snapshot evidence](../../EVIDENCE.md).
- `scripts/smoke-project-workspace.ts` - inspected current application working tree; see [snapshot evidence](../../EVIDENCE.md).
- Relevant automated checks: `tests/agent-runtime.test.ts`, `tests/website-code.test.ts`, `tests/lead-automation.test.ts`, `tests/project-workspace.test.ts`. Their scope is bounded by [current validation](../../CURRENT_STATE.md).

## Main delivery risk

127 automated tests and fixture smoke passes do not establish all 60 source acceptance scenarios, real model/audio outcomes, WCAG conformance or client sign-off.

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
