# 08. Unified inbox, contacts, booking and follow-up

Project: [EverOnnAI client delivery plan](../../README.md). Module code: `INB`. Proposed accountable roles: Backend Lead + Frontend Lead; named owners await assignment.

## Business outcomes and tickets

| Ticket | Business deliverable | Engineering status | Planning phase |
| --- | --- | --- | --- |
| [EVN-INB-007](tickets/EVN-INB-007.md) | Owner summary within 30 seconds | Partial | P1 |
| [EVN-INB-008](tickets/EVN-INB-008.md) | Calendar booking | Partial | P1 |
| [EVN-INB-035](tickets/EVN-INB-035.md) | Owner sees human handling | Planned | P1 |
| [EVN-INB-037](tickets/EVN-INB-037.md) | Unified inbox | Partial | P1 |
| [EVN-INB-038](tickets/EVN-INB-038.md) | Automated follow-up | Planned | P2 |
| [EVN-INB-101](tickets/EVN-INB-101.md) | Turn each conversation into an auditable business request | Partial | P1 |

## Current project capability

**EVN-INB-007:** Lead automation can send Gmail owner summaries with duplicate-send protection.

**EVN-INB-008:** Google OAuth, timezone validation, free/busy checks, event recovery and a workspace lease exist.

**EVN-INB-035:** Conversations have no managed-operator attribution/disposition records.

**EVN-INB-037:** Tenant inbox, contacts, conversations, lead filters/statuses and request capture exist.

**EVN-INB-038:** Gmail lead notification is not a follow-up sequence engine.

**EVN-INB-101:** Lead/contact/appointment records and selected transcript extraction work.

Current persistence: contacts, leads, conversations, conversation_messages, appointments, encrypted Google provider connections. These are working-tree capabilities. Hosted availability and full client acceptance must be checked separately.

## Planned technical delivery

Each ticket contains DB, UI, business-to-technical mapping, backend, AI, QA and deployment checklists. Proposed schema/provider terms are labelled as plans rather than existing components. 42 source records are assigned across this module; see [the requirement matrix](../../TRACEABILITY.md) for record-by-record ownership.

Dependencies outside this module: [EVN-AIQ-102](../03-ai-governance-evaluation/tickets/EVN-AIQ-102.md), [EVN-ONB-102](../01-onboarding-tenancy-identity/tickets/EVN-ONB-102.md).

## Existing code and verification

- `features/everonn/lead-capture.ts` - inspected current application working tree; see [snapshot evidence](../../EVIDENCE.md).
- `features/integrations/lead-automation-core.ts` - inspected current application working tree; see [snapshot evidence](../../EVIDENCE.md).
- `features/integrations/lead-automation.ts` - inspected current application working tree; see [snapshot evidence](../../EVIDENCE.md).
- `features/integrations/google.ts` - inspected current application working tree; see [snapshot evidence](../../EVIDENCE.md).
- `features/integrations/google-oauth.ts` - inspected current application working tree; see [snapshot evidence](../../EVIDENCE.md).
- `features/voice-agent/appointment-validation.ts` - inspected current application working tree; see [snapshot evidence](../../EVIDENCE.md).
- `features/voice-agent/appointment-time.ts` - inspected current application working tree; see [snapshot evidence](../../EVIDENCE.md).
- `components/booking/appointment-fields.tsx` - inspected current application working tree; see [snapshot evidence](../../EVIDENCE.md).
- `components/dashboard/everonn-dashboard.tsx` - inspected current application working tree; see [snapshot evidence](../../EVIDENCE.md).
- Relevant automated checks: `tests/lead-automation.test.ts`, `tests/json-workspace.test.ts`, `scripts/smoke-booking.ts`. Their scope is bounded by [current validation](../../CURRENT_STATE.md).

## Main delivery risk

Google booking is a useful slice, not full multi-calendar scheduling, SMS confirmations, assignment/notes, contact merge or follow-up sequences.

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
