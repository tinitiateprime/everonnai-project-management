# EVN-INB-037 - Unified inbox

Project: EverOnnAI. Module: [Unified inbox, contacts, booking and follow-up](../README.md). Source business requirement [BR-037](../../../requirements/BR.md#br-037).

| Tracking dimension | Disposition |
| --- | --- |
| Engineering | Partial |
| QA | Existing checks are evidence for current slices; full ticket criteria remain pending |
| Deployment | Current local snapshot; verify ticket-specific hosted rollout and configuration |
| Business acceptance | Pending client review; no signed acceptance recorded |
| Owner | Backend Lead + Frontend Lead (proposed role; named person unassigned) |
| Priority / phase | Must / P1 |
| Estimate | TBD after scope/architecture agreement; no delivery date committed |
| Dependencies | [EVN-INB-101](EVN-INB-101.md), [EVN-AIQ-102](../../03-ai-governance-evaluation/tickets/EVN-AIQ-102.md) |

## Business deliverable

Unified inbox. One inbox unifies calls, chats, texts and forms as structured requests with assignment and notes.

The client accepts the demonstrated outcome and evidence, rather than the existence of a route, table or screen. This ticket does not certify the whole source requirement as complete.

## Current implemented slice

- [x] Tenant inbox, contacts, conversations, lead filters/statuses and request capture exist.

## Remaining delivery checklist

- [ ] Add SMS, assignment/notes/tags/search, confidence/audio/tool context, verified merge and PWA.

## Technical component

- [ ] Implement the module boundary and contracts for: Thread projection, search, contact merge and reply services.
- [ ] Maintain tenant boundaries, explicit state transitions, access policy and failure handling for the delivered workflow.
- [ ] Resolve applicable architecture decisions before committing to a new provider or infrastructure baseline.

## DB

Existing module persistence: contacts, leads, conversations, conversation_messages, appointments, encrypted Google provider connections.

The following records/contracts are proposed or require extension; their names are planning terms, not assertions that production tables exist.

- [ ] contacts, requests, threads, assignments, notes.
- [ ] Review scope keys, uniqueness, indexes, retention and migration compatibility; backfill safely and preserve existing tenant records.

## UI

- [ ] Unified mobile inbox, detail and merge controls.
- [ ] Provide loading, empty, validation, permission-denied and recoverable failure states with keyboard and mobile access.
- [ ] Show observed facts and pending states accurately; do not present estimates, configured flags or mock results as confirmed business actions.

## Translate - business-to-technical mapping

| Business rule / outcome | Technical responsibility | Evidence needed |
| --- | --- | --- |
| Unified inbox. One inbox unifies calls, chats, texts and forms as structured requests with assignment and notes. | Thread projection, search, contact merge and reply services | Tenant-scoped end-to-end demonstration of the outcome |
| Add SMS, assignment/notes/tags/search, confidence/audio/tool context, verified merge and PWA. | contacts, requests, threads, assignments, notes; Unified mobile inbox, detail and merge controls | Migration/contracts, visible state and failure-path evidence |
| Safe, truthful AI behaviour where applicable | Grounded summaries and structured requests; human reply approval | Approved context, verified side-effect receipts and evaluation results or justified N/A |
| Client can approve delivery | QA report, rollout evidence and named acceptance owner | Evidence links and dated client sign-off |

This section means requirements-to-implementation mapping. It does not mean language translation; source language obligations are tracked in their own requirements.

## Backend services

- [ ] Thread projection, search, contact merge and reply services.
- [ ] Define request/response/event schemas, authorisation and input validation for each affected operation.
- [ ] For writes and provider effects, define idempotency, retry/timeout, receipts and reconciliation; document N/A where no side effects exist.
- [ ] Expose actionable status and scoped logs without secrets; distinguish completed, failed and uncertain outcomes.

## AI component

- [ ] Grounded summaries and structured requests.
- [ ] human reply approval.
- [ ] Record instruction/knowledge/tool versions, measured quality, tenant scope, cost and safe fallback; a Markdown standard alone is not a passed evaluation.

## Testing / QA

- [ ] Exercise the intended user journey with real tenant-scoped state; cover forbidden role and cross-tenant requests.
- [ ] Test malformed inputs, provider failure, retries/replays and cancellation as applicable; keep deterministic mocks separate from live-provider evidence.
- [ ] Review desktop/mobile accessibility, factual copy and failure recovery in the delivered UI.
- [ ] Attach test environment, code/config/instruction versions, results and remaining defects to the acceptance report.

| Source test | Scenario | Required pass criteria | Current disposition |
| --- | --- | --- | --- |
| [AT-57](../../../requirements/AT.md#at-57) | Inbox, dashboard and follow-up | Calls, chats, texts and forms appear as requests with assignment and notes; the dashboard shows calls answered, jobs and recovered revenue; sequences respect consent and quiet hours | Full source scenario not evidenced; client acceptance pending |

Source stories: [US-035](../../../requirements/US.md#us-035).

## Deployment

- [ ] Confirm approved hosting/database/provider architecture and required credentials in the deployment environment.
- [ ] Apply compatible migrations/configuration in staging, rehearse rollback, then promote the reviewed artifact.
- [ ] Verify the actual hosted workflow, monitoring, fallback and customer-visible errors after release.
- [ ] Update CODE_PROFILE.md, PROJECT_DATA_FLOW.md and CLIENT_TECHNICAL_QA.md in the application when behaviour or architecture changes.
- [ ] Record deployment identity, operator, timestamp and rollback evidence; document-only tickets instead record the reviewed Git commit.

## Source traceability

| Source ID | Mapping basis | Source section |
| --- | --- | --- |
| [API-006](../../../requirements/API.md#api-006) | Plan allocation / source cross-reference | 19.4 Public API, webhooks and integrations (API) |
| [AT-57](../../../requirements/AT.md#at-57) | Source-linked | 25.2 Acceptance tests |
| [BO-1](../../../requirements/BO.md#bo-1) | Source-linked | 3.1 Business objectives |
| [BO-8](../../../requirements/BO.md#bo-8) | Source-linked | 3.1 Business objectives |
| [BR-037](../../../requirements/BR.md#br-037) | Source-linked | 7.6 Inbox, follow-up and value |
| [INB-001](../../../requirements/INB.md#inb-001) | Source-linked | 17.2 Requirements |
| [INB-002](../../../requirements/INB.md#inb-002) | Source-linked | 17.2 Requirements |
| [INB-003](../../../requirements/INB.md#inb-003) | Source-linked | 17.2 Requirements |
| [INB-004](../../../requirements/INB.md#inb-004) | Source-linked | 17.2 Requirements |
| [US-035](../../../requirements/US.md#us-035) | Source-linked | EP-06 Inbox, booking and follow-up |
| [VOX-024](../../../requirements/VOX.md#vox-024) | Plan allocation / source cross-reference | 14.5 Requirements: business behavior |

Read every allocated record, including its continuation bullets and source variants. Source-linked rows preserve explicit document relationships; plan allocations are implementation responsibility assignments created during this review.

## Allocated specification checklist

The unchecked source obligations below require requirement-level evidence. They are deliberately separate from checked statements about current implemented slices. Read linked continuation bullets and additional source wording before accepting a record.

- [ ] [API-006](../../../requirements/API.md#api-006): API-006 [P1] MUST provide realtime channels for the dashboard (WebSocket or SSE) for live call status, inbox updates and escalation alerts.
- [ ] [INB-001](../../../requirements/INB.md#inb-001): INB-001 [P1] MUST provide a unified inbox (responsive web, PWA-installable) listing conversations and requests with filters (status, urgency, channel, assignee, date), search (name, phone, text), and a mobile-first triage view built for one-thumb use.
- [ ] [INB-002](../../../requirements/INB.md#inb-002): INB-002 [P1] MUST show each conversation with transcript, audio player with waveform and transcript sync, AI summary, extracted fields with confidence indicators, tool log, and "why the AI said this" (KNW-009).
- [ ] [INB-003](../../../requirements/INB.md#inb-003): INB-003 [P1] MUST allow staff to reply by SMS or email from the inbox (AI-drafted replies are suggestions requiring one tap to send unless auto-send is enabled by policy).
- [ ] [INB-004](../../../requirements/INB.md#inb-004): INB-004 [P1] MUST support assignment, notes, status changes, tags, and one-tap "call back" (click-to-call bridging via provider so the business's caller ID is shown to the customer).
- [ ] [VOX-024](../../../requirements/VOX.md#vox-024): VOX-024 [P1] MUST support returning-caller recognition (matched by verified phone number and tenant contacts) to personalize ("Welcome back, Maria") without exposing history to unverified callers beyond what policy allows.

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
