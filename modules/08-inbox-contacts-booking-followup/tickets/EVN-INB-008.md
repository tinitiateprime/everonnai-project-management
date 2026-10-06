# EVN-INB-008 - Calendar booking

Project: EverOnnAI. Module: [Unified inbox, contacts, booking and follow-up](../README.md). Source business requirement [BR-008](../../../requirements/BR.md#br-008).

| Tracking dimension | Disposition |
| --- | --- |
| Engineering | Partial |
| QA | Existing checks are evidence for current slices; full ticket criteria remain pending |
| Deployment | Current local snapshot; verify ticket-specific hosted rollout and configuration |
| Business acceptance | Pending client review; no signed acceptance recorded |
| Owner | Backend Lead + Frontend Lead (proposed role; named person unassigned) |
| Priority / phase | Should / P1 |
| Estimate | TBD after scope/architecture agreement; no delivery date committed |
| Dependencies | [EVN-INB-101](EVN-INB-101.md), [EVN-AIQ-102](../../03-ai-governance-evaluation/tickets/EVN-AIQ-102.md) |

## Business deliverable

Calendar booking. Appointments can be booked directly into the client's calendar without double-booking.

The client accepts the demonstrated outcome and evidence, rather than the existence of a route, table or screen. This ticket does not certify the whole source requirement as complete.

## Current implemented slice

- [x] Google OAuth, timezone validation, free/busy checks, event recovery and a workspace lease exist.

## Remaining delivery checklist

- [ ] Add Microsoft/Cal.com, buffers/hours/holidays, customer confirmations, change links and real concurrent-booking evidence.

## Technical component

- [ ] Implement the module boundary and contracts for: CalendarProvider, conflict-safe booking and recovery.
- [ ] Maintain tenant boundaries, explicit state transitions, access policy and failure handling for the delivered workflow.
- [ ] Resolve applicable architecture decisions before committing to a new provider or infrastructure baseline.

## DB

Existing module persistence: contacts, leads, conversations, conversation_messages, appointments, encrypted Google provider connections.

The following records/contracts are proposed or require extension; their names are planning terms, not assertions that production tables exist.

- [ ] appointments, booking_rules, calendar_connections.
- [ ] Review scope keys, uniqueness, indexes, retention and migration compatibility; backfill safely and preserve existing tenant records.

## UI

- [ ] Availability, appointment review and customer change links.
- [ ] Provide loading, empty, validation, permission-denied and recoverable failure states with keyboard and mobile access.
- [ ] Show observed facts and pending states accurately; do not present estimates, configured flags or mock results as confirmed business actions.

## Translate - business-to-technical mapping

| Business rule / outcome | Technical responsibility | Evidence needed |
| --- | --- | --- |
| Calendar booking. Appointments can be booked directly into the client's calendar without double-booking. | CalendarProvider, conflict-safe booking and recovery | Tenant-scoped end-to-end demonstration of the outcome |
| Add Microsoft/Cal.com, buffers/hours/holidays, customer confirmations, change links and real concurrent-booking evidence. | appointments, booking_rules, calendar_connections; Availability, appointment review and customer change links | Migration/contracts, visible state and failure-path evidence |
| Safe, truthful AI behaviour where applicable | Explicit service/time confirmation before tool execution | Approved context, verified side-effect receipts and evaluation results or justified N/A |
| Client can approve delivery | QA report, rollout evidence and named acceptance owner | Evidence links and dated client sign-off |

This section means requirements-to-implementation mapping. It does not mean language translation; source language obligations are tracked in their own requirements.

## Backend services

- [ ] CalendarProvider, conflict-safe booking and recovery.
- [ ] Define request/response/event schemas, authorisation and input validation for each affected operation.
- [ ] For writes and provider effects, define idempotency, retry/timeout, receipts and reconciliation; document N/A where no side effects exist.
- [ ] Expose actionable status and scoped logs without secrets; distinguish completed, failed and uncertain outcomes.

## AI component

- [ ] Explicit service/time confirmation before tool execution.
- [ ] Record instruction/knowledge/tool versions, measured quality, tenant scope, cost and safe fallback; a Markdown standard alone is not a passed evaluation.

## Testing / QA

- [ ] Exercise the intended user journey with real tenant-scoped state; cover forbidden role and cross-tenant requests.
- [ ] Test malformed inputs, provider failure, retries/replays and cancellation as applicable; keep deterministic mocks separate from live-provider evidence.
- [ ] Review desktop/mobile accessibility, factual copy and failure recovery in the delivered UI.
- [ ] Attach test environment, code/config/instruction versions, results and remaining defects to the acceptance report.

| Source test | Scenario | Required pass criteria | Current disposition |
| --- | --- | --- | --- |
| [AT-18](../../../requirements/AT.md#at-18) | Booking through the AI, including a conflicting slot | Appointment created and confirmed by text; a concurrent booking of the same slot is rejected and alternatives are offered | Full source scenario not evidenced; client acceptance pending |

Source stories: [US-016](../../../requirements/US.md#us-016).

## Deployment

- [ ] Confirm approved hosting/database/provider architecture and required credentials in the deployment environment.
- [ ] Apply compatible migrations/configuration in staging, rehearse rollback, then promote the reviewed artifact.
- [ ] Verify the actual hosted workflow, monitoring, fallback and customer-visible errors after release.
- [ ] Update CODE_PROFILE.md, PROJECT_DATA_FLOW.md and CLIENT_TECHNICAL_QA.md in the application when behaviour or architecture changes.
- [ ] Record deployment identity, operator, timestamp and rollback evidence; document-only tickets instead record the reviewed Git commit.

## Source traceability

| Source ID | Mapping basis | Source section |
| --- | --- | --- |
| [API-005](../../../requirements/API.md#api-005) | Plan allocation / source cross-reference | 19.4 Public API, webhooks and integrations (API) |
| [AT-18](../../../requirements/AT.md#at-18) | Source-linked | 25.2 Acceptance tests |
| [BKG-001](../../../requirements/BKG.md#bkg-001) | Source-linked | 17.2 Requirements |
| [BKG-002](../../../requirements/BKG.md#bkg-002) | Source-linked | 17.2 Requirements |
| [BKG-003](../../../requirements/BKG.md#bkg-003) | Source-linked | 17.2 Requirements |
| [BKG-004](../../../requirements/BKG.md#bkg-004) | Plan allocation / source cross-reference | 17.2 Requirements |
| [BKG-005](../../../requirements/BKG.md#bkg-005) | Plan allocation / source cross-reference | 17.2 Requirements |
| [BO-1](../../../requirements/BO.md#bo-1) | Source-linked | 3.1 Business objectives |
| [BR-008](../../../requirements/BR.md#br-008) | Source-linked | 7.1 Answering calls |
| [US-016](../../../requirements/US.md#us-016) | Source-linked | EP-03 AI voice front desk |
| [VOX-020](../../../requirements/VOX.md#vox-020) | Source-linked | 14.5 Requirements: business behavior |

Read every allocated record, including its continuation bullets and source variants. Source-linked rows preserve explicit document relationships; plan allocations are implementation responsibility assignments created during this review.

## Allocated specification checklist

The unchecked source obligations below require requirement-level evidence. They are deliberately separate from checked statements about current implemented slices. Read linked continuation bullets and additional source wording before accepting a record.

- [ ] [API-005](../../../requirements/API.md#api-005): API-005 [P2] SHOULD provide first integrations: Google Calendar and Microsoft 365 (BKG-001), Google Business Profile, QuickBooks (invoice/customer sync, P3), and one field-service system (BKG-005).
- [ ] [BKG-001](../../../requirements/BKG.md#bkg-001): BKG-001 [P1] MUST integrate calendars via OAuth (Google Calendar, Microsoft 365) and Cal.com; store only the minimum (free/busy plus created events), refresh tokens encrypted (SEC-005), and handle token revocation gracefully.
- [ ] [BKG-002](../../../requirements/BKG.md#bkg-002): BKG-002 [P1] MUST implement availability rules: business hours, service durations, buffers, travel-time estimates (P2), lead time, max per day, staff/technician assignment (P2), and holiday closures.
- [ ] [BKG-003](../../../requirements/BKG.md#bkg-003): BKG-003 [P1] MUST implement atomic booking with conflict detection (optimistic locking) so two simultaneous callers cannot book the same slot; the agent offers alternatives when a slot is taken.
- [ ] [BKG-004](../../../requirements/BKG.md#bkg-004): BKG-004 [P1] MUST send confirmations and reminders (SMS/email) with reschedule and cancel links; customer-initiated changes flow back to the calendar.
- [ ] [BKG-005](../../../requirements/BKG.md#bkg-005): BKG-005 [P3] MAY integrate field-service systems (Jobber, Housecall Pro, ServiceTitan, Workiz) via an FsmProvider interface scaffolded at P2.
- [ ] [VOX-020](../../../requirements/VOX.md#vox-020): VOX-020 [P1] MUST allow the AI to book appointments through the CalendarProvider (Google, Microsoft, Cal.com at P1; scheduling software integrations at P3) respecting buffers, service durations and territory, with confirmation SMS.

## Existing code / check evidence

- `features/everonn/lead-capture.ts` - inspected current application working tree; see [snapshot evidence](../../../EVIDENCE.md).
- `features/integrations/lead-automation-core.ts` - inspected current application working tree; see [snapshot evidence](../../../EVIDENCE.md).
- `features/integrations/lead-automation.ts` - inspected current application working tree; see [snapshot evidence](../../../EVIDENCE.md).
- `features/integrations/google.ts` - inspected current application working tree; see [snapshot evidence](../../../EVIDENCE.md).
- `features/integrations/google-oauth.ts` - inspected current application working tree; see [snapshot evidence](../../../EVIDENCE.md).
- `features/voice-agent/appointment-validation.ts` - inspected current application working tree; see [snapshot evidence](../../../EVIDENCE.md).
- `features/voice-agent/appointment-time.ts` - inspected current application working tree; see [snapshot evidence](../../../EVIDENCE.md).
- `components/booking/appointment-fields.tsx` - inspected current application working tree; see [snapshot evidence](../../../EVIDENCE.md).
- `components/dashboard/everonn-dashboard.tsx` - inspected current application working tree; see [snapshot evidence](../../../EVIDENCE.md).
- Relevant automated checks: `tests/lead-automation.test.ts`, `tests/json-workspace.test.ts`, `scripts/smoke-booking.ts`. Their scope is bounded by [current validation](../../../CURRENT_STATE.md).

## Blockers and boundaries

Module risk: Google booking is a useful slice, not full multi-calendar scheduling, SMS confirmations, assignment/notes, contact merge or follow-up sequences.

Dependencies: [EVN-INB-101](EVN-INB-101.md), [EVN-AIQ-102](../../03-ai-governance-evaluation/tickets/EVN-AIQ-102.md). A blocked prerequisite can be prototyped independently, but its contract and deployment must be approved before claiming this ticket delivered. Service limits, third-party approvals and staffing are evidence requirements, not assumptions that they are available.

## Handover and client acceptance

- [ ] Attach the business demonstration, technical evidence and operating/recovery instructions.
- [ ] Assign a named acceptance owner and agree any deferred criteria with the client in writing.
- [ ] Resolve launch-blocking defects and document accepted residual risks.
- [ ] Client records dated acceptance against the deployed/documented version.

Use [the acceptance protocol](../../../ACCEPTANCE.md) and [the ticket update rules](../../../TICKET_TEMPLATE.md) when changing status.
