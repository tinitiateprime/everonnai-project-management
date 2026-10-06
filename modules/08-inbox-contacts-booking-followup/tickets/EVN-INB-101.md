# EVN-INB-101 - Turn each conversation into an auditable business request

Project: EverOnnAI. Module: [Unified inbox, contacts, booking and follow-up](../README.md). Technical delivery enabler allocated by this plan; source references below.

| Tracking dimension | Disposition |
| --- | --- |
| Engineering | Partial |
| QA | Existing checks are evidence for current slices; full ticket criteria remain pending |
| Deployment | Current local snapshot; verify ticket-specific hosted rollout and configuration |
| Business acceptance | Pending client review; no signed acceptance recorded |
| Owner | Backend Lead + Frontend Lead (proposed role; named person unassigned) |
| Priority / phase | Delivery enabler / P1 |
| Estimate | TBD after scope/architecture agreement; no delivery date committed |
| Dependencies | [EVN-ONB-102](../../01-onboarding-tenancy-identity/tickets/EVN-ONB-102.md), [EVN-AIQ-102](../../03-ai-governance-evaluation/tickets/EVN-AIQ-102.md) |

## Business deliverable

Turn each conversation into an auditable business request.

The client accepts the demonstrated outcome and evidence, rather than the existence of a route, table or screen. This ticket does not certify the whole source requirement as complete.

## Current implemented slice

- [x] Lead/contact/appointment records and selected transcript extraction work.

## Remaining delivery checklist

- [ ] Publish Request JSON Schema with confidence/evidence, tags/assignment and event contracts; retain actual customer corrections.

## Technical component

- [ ] Implement the module boundary and contracts for: Extraction validator, contact merge and request domain events.
- [ ] Maintain tenant boundaries, explicit state transitions, access policy and failure handling for the delivered workflow.
- [ ] Resolve applicable architecture decisions before committing to a new provider or infrastructure baseline.

## DB

Existing module persistence: contacts, leads, conversations, conversation_messages, appointments, encrypted Google provider connections.

The following records/contracts are proposed or require extension; their names are planning terms, not assertions that production tables exist.

- [ ] requests, fields, confidence/evidence, assignments.
- [ ] Review scope keys, uniqueness, indexes, retention and migration compatibility; backfill safely and preserve existing tenant records.

## UI

- [ ] Request correction, assignment and source evidence.
- [ ] Provide loading, empty, validation, permission-denied and recoverable failure states with keyboard and mobile access.
- [ ] Show observed facts and pending states accurately; do not present estimates, configured flags or mock results as confirmed business actions.

## Translate - business-to-technical mapping

| Business rule / outcome | Technical responsibility | Evidence needed |
| --- | --- | --- |
| Turn each conversation into an auditable business request. | Extraction validator, contact merge and request domain events | Tenant-scoped end-to-end demonstration of the outcome |
| Publish Request JSON Schema with confidence/evidence, tags/assignment and event contracts; retain actual customer corrections. | requests, fields, confidence/evidence, assignments; Request correction, assignment and source evidence | Migration/contracts, visible state and failure-path evidence |
| Safe, truthful AI behaviour where applicable | Extraction proposes evidence-backed fields; ambiguity stays unconfirmed | Approved context, verified side-effect receipts and evaluation results or justified N/A |
| Client can approve delivery | QA report, rollout evidence and named acceptance owner | Evidence links and dated client sign-off |

This section means requirements-to-implementation mapping. It does not mean language translation; source language obligations are tracked in their own requirements.

## Backend services

- [ ] Extraction validator, contact merge and request domain events.
- [ ] Define request/response/event schemas, authorisation and input validation for each affected operation.
- [ ] For writes and provider effects, define idempotency, retry/timeout, receipts and reconciliation; document N/A where no side effects exist.
- [ ] Expose actionable status and scoped logs without secrets; distinguish completed, failed and uncertain outcomes.

## AI component

- [ ] Extraction proposes evidence-backed fields.
- [ ] ambiguity stays unconfirmed.
- [ ] Record instruction/knowledge/tool versions, measured quality, tenant scope, cost and safe fallback; a Markdown standard alone is not a passed evaluation.

## Testing / QA

- [ ] Exercise the intended user journey with real tenant-scoped state; cover forbidden role and cross-tenant requests.
- [ ] Test malformed inputs, provider failure, retries/replays and cancellation as applicable; keep deterministic mocks separate from live-provider evidence.
- [ ] Review desktop/mobile accessibility, factual copy and failure recovery in the delivered UI.
- [ ] Attach test environment, code/config/instruction versions, results and remaining defects to the acceptance report.

No dedicated source AT is assigned to this enabling/extension ticket. Define a ticket-specific acceptance report before closing it; the module and release gates still apply.

Source stories: No dedicated source story; business/enabling outcome above is the acceptance brief.

## Deployment

- [ ] Confirm approved hosting/database/provider architecture and required credentials in the deployment environment.
- [ ] Apply compatible migrations/configuration in staging, rehearse rollback, then promote the reviewed artifact.
- [ ] Verify the actual hosted workflow, monitoring, fallback and customer-visible errors after release.
- [ ] Update CODE_PROFILE.md, PROJECT_DATA_FLOW.md and CLIENT_TECHNICAL_QA.md in the application when behaviour or architecture changes.
- [ ] Record deployment identity, operator, timestamp and rollback evidence; document-only tickets instead record the reviewed Git commit.

## Source traceability

| Source ID | Mapping basis | Source section |
| --- | --- | --- |
| [AGT-008](../../../requirements/AGT.md#agt-008) | Source-linked | 13.3 Agent configuration |
| [INB-002](../../../requirements/INB.md#inb-002) | Source-linked | 17.2 Requirements |
| [INB-004](../../../requirements/INB.md#inb-004) | Source-linked | 17.2 Requirements |
| [INB-005](../../../requirements/INB.md#inb-005) | Source-linked | 17.2 Requirements |
| [INB-007](../../../requirements/INB.md#inb-007) | Source-linked | 17.2 Requirements |
| [VOX-023](../../../requirements/VOX.md#vox-023) | Plan allocation / source cross-reference | 14.5 Requirements: business behavior |

Read every allocated record, including its continuation bullets and source variants. Source-linked rows preserve explicit document relationships; plan allocations are implementation responsibility assignments created during this review.

## Allocated specification checklist

The unchecked source obligations below require requirement-level evidence. They are deliberately separate from checked statements about current implemented slices. Read linked continuation bullets and additional source wording before accepting a record.

- [ ] [AGT-008](../../../requirements/AGT.md#agt-008): AGT-008 [P1] MUST implement structured extraction: at the end of every conversation, produce a schema-validated Request object (Appendix D) from the transcript and tool results, with per-field confidence and evidence spans. Downstream systems consume the structured object, never free text.
- [ ] [INB-002](../../../requirements/INB.md#inb-002): INB-002 [P1] MUST show each conversation with transcript, audio player with waveform and transcript sync, AI summary, extracted fields with confidence indicators, tool log, and "why the AI said this" (KNW-009).
- [ ] [INB-004](../../../requirements/INB.md#inb-004): INB-004 [P1] MUST support assignment, notes, status changes, tags, and one-tap "call back" (click-to-call bridging via provider so the business's caller ID is shown to the customer).
- [ ] [INB-005](../../../requirements/INB.md#inb-005): INB-005 [P1] MUST de-duplicate and merge contacts (verified phone/email keys), with merge preview and audit.
- [ ] [INB-007](../../../requirements/INB.md#inb-007): INB-007 [P1] SHOULD provide export (CSV) and Zapier/webhook triggers for new requests (API-004).
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

Dependencies: [EVN-ONB-102](../../01-onboarding-tenancy-identity/tickets/EVN-ONB-102.md), [EVN-AIQ-102](../../03-ai-governance-evaluation/tickets/EVN-AIQ-102.md). A blocked prerequisite can be prototyped independently, but its contract and deployment must be approved before claiming this ticket delivered. Service limits, third-party approvals and staffing are evidence requirements, not assumptions that they are available.

## Handover and client acceptance

- [ ] Attach the business demonstration, technical evidence and operating/recovery instructions.
- [ ] Assign a named acceptance owner and agree any deferred criteria with the client in writing.
- [ ] Resolve launch-blocking defects and document accepted residual risks.
- [ ] Client records dated acceptance against the deployed/documented version.

Use [the acceptance protocol](../../../ACCEPTANCE.md) and [the ticket update rules](../../../TICKET_TEMPLATE.md) when changing status.
