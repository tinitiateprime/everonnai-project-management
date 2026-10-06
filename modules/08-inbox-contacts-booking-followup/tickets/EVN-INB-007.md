# EVN-INB-007 - Owner summary within 30 seconds

Project: EverOnnAI. Module: [Unified inbox, contacts, booking and follow-up](../README.md). Source business requirement [BR-007](../../../requirements/BR.md#br-007).

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

Owner summary within 30 seconds. The owner receives a clear summary within 30 seconds of every call.

The client accepts the demonstrated outcome and evidence, rather than the existence of a route, table or screen. This ticket does not certify the whole source requirement as complete.

## Current implemented slice

- [x] Lead automation can send Gmail owner summaries with duplicate-send protection.

## Remaining delivery checklist

- [ ] Deliver post-call summaries on configured channels within the source 30-second target; add retries, receipts and preferences.

## Technical component

- [ ] Implement the module boundary and contracts for: Conversation-completion worker, channel adapters, deadline monitoring.
- [ ] Maintain tenant boundaries, explicit state transitions, access policy and failure handling for the delivered workflow.
- [ ] Resolve applicable architecture decisions before committing to a new provider or infrastructure baseline.

## DB

Existing module persistence: contacts, leads, conversations, conversation_messages, appointments, encrypted Google provider connections.

The following records/contracts are proposed or require extension; their names are planning terms, not assertions that production tables exist.

- [ ] notification_preferences, delivery_receipts, summary_jobs.
- [ ] Review scope keys, uniqueness, indexes, retention and migration compatibility; backfill safely and preserve existing tenant records.

## UI

- [ ] Notification settings and delivery status.
- [ ] Provide loading, empty, validation, permission-denied and recoverable failure states with keyboard and mobile access.
- [ ] Show observed facts and pending states accurately; do not present estimates, configured flags or mock results as confirmed business actions.

## Translate - business-to-technical mapping

| Business rule / outcome | Technical responsibility | Evidence needed |
| --- | --- | --- |
| Owner summary within 30 seconds. The owner receives a clear summary within 30 seconds of every call. | Conversation-completion worker, channel adapters, deadline monitoring | Tenant-scoped end-to-end demonstration of the outcome |
| Deliver post-call summaries on configured channels within the source 30-second target; add retries, receipts and preferences. | notification_preferences, delivery_receipts, summary_jobs; Notification settings and delivery status | Migration/contracts, visible state and failure-path evidence |
| Safe, truthful AI behaviour where applicable | Grounded summary with transcript references | Approved context, verified side-effect receipts and evaluation results or justified N/A |
| Client can approve delivery | QA report, rollout evidence and named acceptance owner | Evidence links and dated client sign-off |

This section means requirements-to-implementation mapping. It does not mean language translation; source language obligations are tracked in their own requirements.

## Backend services

- [ ] Conversation-completion worker, channel adapters, deadline monitoring.
- [ ] Define request/response/event schemas, authorisation and input validation for each affected operation.
- [ ] For writes and provider effects, define idempotency, retry/timeout, receipts and reconciliation; document N/A where no side effects exist.
- [ ] Expose actionable status and scoped logs without secrets; distinguish completed, failed and uncertain outcomes.

## AI component

- [ ] Grounded summary with transcript references.
- [ ] Record instruction/knowledge/tool versions, measured quality, tenant scope, cost and safe fallback; a Markdown standard alone is not a passed evaluation.

## Testing / QA

- [ ] Exercise the intended user journey with real tenant-scoped state; cover forbidden role and cross-tenant requests.
- [ ] Test malformed inputs, provider failure, retries/replays and cancellation as applicable; keep deterministic mocks separate from live-provider evidence.
- [ ] Review desktop/mobile accessibility, factual copy and failure recovery in the delivered UI.
- [ ] Attach test environment, code/config/instruction versions, results and remaining defects to the acceptance report.

| Source test | Scenario | Required pass criteria | Current disposition |
| --- | --- | --- | --- |
| [AT-12](../../../requirements/AT.md#at-12) | After-hours locksmith lockout call | Details captured with read-back; urgency classified; owner text within 30 seconds; request, transcript and audio present | Full source scenario not evidenced; client acceptance pending |

Source stories: [US-015](../../../requirements/US.md#us-015).

## Deployment

- [ ] Confirm approved hosting/database/provider architecture and required credentials in the deployment environment.
- [ ] Apply compatible migrations/configuration in staging, rehearse rollback, then promote the reviewed artifact.
- [ ] Verify the actual hosted workflow, monitoring, fallback and customer-visible errors after release.
- [ ] Update CODE_PROFILE.md, PROJECT_DATA_FLOW.md and CLIENT_TECHNICAL_QA.md in the application when behaviour or architecture changes.
- [ ] Record deployment identity, operator, timestamp and rollback evidence; document-only tickets instead record the reviewed Git commit.

## Source traceability

| Source ID | Mapping basis | Source section |
| --- | --- | --- |
| [AT-12](../../../requirements/AT.md#at-12) | Source-linked | 25.2 Acceptance tests |
| [BO-1](../../../requirements/BO.md#bo-1) | Source-linked | 3.1 Business objectives |
| [BO-8](../../../requirements/BO.md#bo-8) | Source-linked | 3.1 Business objectives |
| [BR-007](../../../requirements/BR.md#br-007) | Source-linked | 7.1 Answering calls |
| [INB-006](../../../requirements/INB.md#inb-006) | Source-linked | 17.2 Requirements |
| [SL-03](../../../requirements/SL.md#sl-03) | Plan allocation / source cross-reference | 10.1 Service levels |
| [US-015](../../../requirements/US.md#us-015) | Source-linked | EP-03 AI voice front desk |
| [VOX-011](../../../requirements/VOX.md#vox-011) | Plan allocation / source cross-reference | 14.4 Requirements: real-time conversation quality |
| [VOX-021](../../../requirements/VOX.md#vox-021) | Source-linked | 14.5 Requirements: business behavior |
| [VOX-023](../../../requirements/VOX.md#vox-023) | Plan allocation / source cross-reference | 14.5 Requirements: business behavior |

Read every allocated record, including its continuation bullets and source variants. Source-linked rows preserve explicit document relationships; plan allocations are implementation responsibility assignments created during this review.

## Allocated specification checklist

The unchecked source obligations below require requirement-level evidence. They are deliberately separate from checked statements about current implemented slices. Read linked continuation bullets and additional source wording before accepting a record.

- [ ] [INB-006](../../../requirements/INB.md#inb-006): INB-006 [P1] MUST give owners notifications with per-channel, per-severity preferences and quiet hours; P1 severity bypasses quiet hours.
- [ ] [SL-03](../../../requirements/SL.md#sl-03): SL-03 | Owner summary after a call | 99% within 30 seconds.
- [ ] [VOX-011](../../../requirements/VOX.md#vox-011): VOX-011 [P1] MUST manage silence, hold and dropped calls: prompts after configurable silence, hang-up after N prompts, graceful handling of caller hang-up mid-turn, and full post-call processing even on abrupt termination.
- [ ] [VOX-021](../../../requirements/VOX.md#vox-021): VOX-021 [P1] MUST send the owner summary within 30 seconds of call end via the tenant's preferred channels (SMS, push, email): who, what, where, urgency, next action, link to transcript and audio.
- [ ] [VOX-023](../../../requirements/VOX.md#vox-023): VOX-023 [P1] MUST produce the post-call package: transcript with timestamps and speaker labels, audio recording (if permitted), summary, structured Request, sentiment, outcome code, tool-call log, cost breakdown, guardrail events, latency per turn.

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
