# EVN-INB-035 - Owner sees human handling

Project: EverOnnAI. Module: [Unified inbox, contacts, booking and follow-up](../README.md). Source business requirement [BR-035](../../../requirements/BR.md#br-035).

| Tracking dimension | Disposition |
| --- | --- |
| Engineering | Planned |
| QA | Existing checks are evidence for current slices; full ticket criteria remain pending |
| Deployment | Current local snapshot; verify ticket-specific hosted rollout and configuration |
| Business acceptance | Pending client review; no signed acceptance recorded |
| Owner | Backend Lead + Frontend Lead (proposed role; named person unassigned) |
| Priority / phase | Must / P1 |
| Estimate | TBD after scope/architecture agreement; no delivery date committed |
| Dependencies | [EVN-INB-101](EVN-INB-101.md), [EVN-AIQ-102](../../03-ai-governance-evaluation/tickets/EVN-AIQ-102.md) |

## Business deliverable

Owner sees human handling. Clients see which interactions were handled by a human, by whom (first name), and the notes.

The client accepts the demonstrated outcome and evidence, rather than the existence of a route, table or screen. This ticket does not certify the whole source requirement as complete.

## Current implemented slice

- [ ] Conversations have no managed-operator attribution/disposition records.

The current statement describes prerequisites or context; this business deliverable has not been demonstrated.

## Remaining delivery checklist

- [ ] Expose human handler first name, duration, notes, disposition and client review under recording policy.

## Technical component

- [ ] Implement the module boundary and contracts for: Tenant-safe interaction projection and review delivery.
- [ ] Maintain tenant boundaries, explicit state transitions, access policy and failure handling for the delivered workflow.
- [ ] Resolve applicable architecture decisions before committing to a new provider or infrastructure baseline.

## DB

Existing module persistence: contacts, leads, conversations, conversation_messages, appointments, encrypted Google provider connections.

The following records/contracts are proposed or require extension; their names are planning terms, not assertions that production tables exist.

- [ ] operator_interactions, dispositions, feedback.
- [ ] Review scope keys, uniqueness, indexes, retention and migration compatibility; backfill safely and preserve existing tenant records.

## UI

- [ ] Human-handled badge and notes/review.
- [ ] Provide loading, empty, validation, permission-denied and recoverable failure states with keyboard and mobile access.
- [ ] Show observed facts and pending states accurately; do not present estimates, configured flags or mock results as confirmed business actions.

## Translate - business-to-technical mapping

| Business rule / outcome | Technical responsibility | Evidence needed |
| --- | --- | --- |
| Owner sees human handling. Clients see which interactions were handled by a human, by whom (first name), and the notes. | Tenant-safe interaction projection and review delivery | Tenant-scoped end-to-end demonstration of the outcome |
| Expose human handler first name, duration, notes, disposition and client review under recording policy. | operator_interactions, dispositions, feedback; Human-handled badge and notes/review | Migration/contracts, visible state and failure-path evidence |
| Safe, truthful AI behaviour where applicable | Summaries retain actual handling without invented actions | Approved context, verified side-effect receipts and evaluation results or justified N/A |
| Client can approve delivery | QA report, rollout evidence and named acceptance owner | Evidence links and dated client sign-off |

This section means requirements-to-implementation mapping. It does not mean language translation; source language obligations are tracked in their own requirements.

## Backend services

- [ ] Tenant-safe interaction projection and review delivery.
- [ ] Define request/response/event schemas, authorisation and input validation for each affected operation.
- [ ] For writes and provider effects, define idempotency, retry/timeout, receipts and reconciliation; document N/A where no side effects exist.
- [ ] Expose actionable status and scoped logs without secrets; distinguish completed, failed and uncertain outcomes.

## AI component

- [ ] Summaries retain actual handling without invented actions.
- [ ] Record instruction/knowledge/tool versions, measured quality, tenant scope, cost and safe fallback; a Markdown standard alone is not a passed evaluation.

## Testing / QA

- [ ] Exercise the intended user journey with real tenant-scoped state; cover forbidden role and cross-tenant requests.
- [ ] Test malformed inputs, provider failure, retries/replays and cancellation as applicable; keep deterministic mocks separate from live-provider evidence.
- [ ] Review desktop/mobile accessibility, factual copy and failure recovery in the delivered UI.
- [ ] Attach test environment, code/config/instruction versions, results and remaining defects to the acceptance report.

| Source test | Scenario | Required pass criteria | Current disposition |
| --- | --- | --- | --- |
| [AT-36](../../../requirements/AT.md#at-36) | Owner reviews a human-handled interaction | Inbox flags the interaction as handled by the EverOnn team with the operator's first name, duration, disposition and notes; recording per policy; the owner can rate it | Full source scenario not evidenced; client acceptance pending |

Source stories: [US-030](../../../requirements/US.md#us-030).

## Deployment

- [ ] Confirm approved hosting/database/provider architecture and required credentials in the deployment environment.
- [ ] Apply compatible migrations/configuration in staging, rehearse rollback, then promote the reviewed artifact.
- [ ] Verify the actual hosted workflow, monitoring, fallback and customer-visible errors after release.
- [ ] Update CODE_PROFILE.md, PROJECT_DATA_FLOW.md and CLIENT_TECHNICAL_QA.md in the application when behaviour or architecture changes.
- [ ] Record deployment identity, operator, timestamp and rollback evidence; document-only tickets instead record the reviewed Git commit.

## Source traceability

| Source ID | Mapping basis | Source section |
| --- | --- | --- |
| [AT-36](../../../requirements/AT.md#at-36) | Source-linked | 25.2 Acceptance tests |
| [BO-4](../../../requirements/BO.md#bo-4) | Source-linked | 3.1 Business objectives |
| [BO-8](../../../requirements/BO.md#bo-8) | Source-linked | 3.1 Business objectives |
| [BR-035](../../../requirements/BR.md#br-035) | Source-linked | 7.5 Human operations and the Live Agent Desk |
| [DSK-023](../../../requirements/DSK.md#dsk-023) | Source-linked | 16.4.6 Supervision, staffing and visibility |
| [INB-002](../../../requirements/INB.md#inb-002) | Source-linked | 17.2 Requirements |
| [US-030](../../../requirements/US.md#us-030) | Source-linked | EP-05 Human operations and the Live Agent Desk |

Read every allocated record, including its continuation bullets and source variants. Source-linked rows preserve explicit document relationships; plan allocations are implementation responsibility assignments created during this review.

## Allocated specification checklist

The unchecked source obligations below require requirement-level evidence. They are deliberately separate from checked statements about current implemented slices. Read linked continuation bullets and additional source wording before accepting a record.

- [ ] [DSK-023](../../../requirements/DSK.md#dsk-023): DSK-023 [P1] MUST give clients visibility of human handling: interactions handled by an operator are flagged in the client's inbox ("Handled by the EverOnn team: Sam"), with duration, disposition, notes and recording per policy. The client can rate an interaction or report a problem, which feeds quality review.
- [ ] [INB-002](../../../requirements/INB.md#inb-002): INB-002 [P1] MUST show each conversation with transcript, audio player with waveform and transcript sync, AI summary, extracted fields with confidence indicators, tool log, and "why the AI said this" (KNW-009).

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
