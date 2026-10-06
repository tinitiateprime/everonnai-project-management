# EVN-VOX-002 - Capture the job accurately

Project: EverOnnAI. Module: [Telephone numbers, voice service and bilingual calls](../README.md). Source business requirement [BR-002](../../../requirements/BR.md#br-002).

| Tracking dimension | Disposition |
| --- | --- |
| Engineering | Partial |
| QA | Existing checks are evidence for current slices; full ticket criteria remain pending |
| Deployment | Current local snapshot; verify ticket-specific hosted rollout and configuration |
| Business acceptance | Pending client review; no signed acceptance recorded |
| Owner | Voice/Media Lead + SRE (proposed role; named person unassigned) |
| Priority / phase | Must / P1 |
| Estimate | TBD after scope/architecture agreement; no delivery date committed |
| Dependencies | [EVN-VOX-101](EVN-VOX-101.md), [EVN-KNW-102](../../02-knowledge-agent-configuration/tickets/EVN-KNW-102.md) |

## Business deliverable

Capture the job accurately. Job details (who, where, what, how urgent, callback number) are captured accurately, and critical details are confirmed by read-back.

The client accepts the demonstrated outcome and evidence, rather than the existence of a route, table or screen. This ticket does not certify the whole source requirement as complete.

## Current implemented slice

- [x] Contact extraction, progressive lead capture and deterministic service/date/time validation exist.

## Remaining delivery checklist

- [ ] Add vertical Request schemas, evidence spans, per-field confidence, address validation and spoken read-back on real audio.

## Technical component

- [ ] Implement the module boundary and contracts for: Request extraction/validation, contact resolution, event emission.
- [ ] Maintain tenant boundaries, explicit state transitions, access policy and failure handling for the delivered workflow.
- [ ] Resolve applicable architecture decisions before committing to a new provider or infrastructure baseline.

## DB

Existing module persistence: conversations, conversation_messages, contacts, leads; browser voice usage sessions.

The following records/contracts are proposed or require extension; their names are planning terms, not assertions that production tables exist.

- [ ] requests, request_fields, transcripts, contacts.
- [ ] Review scope keys, uniqueness, indexes, retention and migration compatibility; backfill safely and preserve existing tenant records.

## UI

- [ ] Captured-details review and correction panel.
- [ ] Provide loading, empty, validation, permission-denied and recoverable failure states with keyboard and mobile access.
- [ ] Show observed facts and pending states accurately; do not present estimates, configured flags or mock results as confirmed business actions.

## Translate - business-to-technical mapping

| Business rule / outcome | Technical responsibility | Evidence needed |
| --- | --- | --- |
| Capture the job accurately. Job details (who, where, what, how urgent, callback number) are captured accurately, and critical details are confirmed by read-back. | Request extraction/validation, contact resolution, event emission | Tenant-scoped end-to-end demonstration of the outcome |
| Add vertical Request schemas, evidence spans, per-field confidence, address validation and spoken read-back on real audio. | requests, request_fields, transcripts, contacts; Captured-details review and correction panel | Migration/contracts, visible state and failure-path evidence |
| Safe, truthful AI behaviour where applicable | Structured extraction with confidence and evidence; refuse invented facts | Approved context, verified side-effect receipts and evaluation results or justified N/A |
| Client can approve delivery | QA report, rollout evidence and named acceptance owner | Evidence links and dated client sign-off |

This section means requirements-to-implementation mapping. It does not mean language translation; source language obligations are tracked in their own requirements.

## Backend services

- [ ] Request extraction/validation, contact resolution, event emission.
- [ ] Define request/response/event schemas, authorisation and input validation for each affected operation.
- [ ] For writes and provider effects, define idempotency, retry/timeout, receipts and reconciliation; document N/A where no side effects exist.
- [ ] Expose actionable status and scoped logs without secrets; distinguish completed, failed and uncertain outcomes.

## AI component

- [ ] Structured extraction with confidence and evidence.
- [ ] refuse invented facts.
- [ ] Record instruction/knowledge/tool versions, measured quality, tenant scope, cost and safe fallback; a Markdown standard alone is not a passed evaluation.

## Testing / QA

- [ ] Exercise the intended user journey with real tenant-scoped state; cover forbidden role and cross-tenant requests.
- [ ] Test malformed inputs, provider failure, retries/replays and cancellation as applicable; keep deterministic mocks separate from live-provider evidence.
- [ ] Review desktop/mobile accessibility, factual copy and failure recovery in the delivered UI.
- [ ] Attach test environment, code/config/instruction versions, results and remaining defects to the acceptance report.

| Source test | Scenario | Required pass criteria | Current disposition |
| --- | --- | --- | --- |
| [AT-12](../../../requirements/AT.md#at-12) | After-hours locksmith lockout call | Details captured with read-back; urgency classified; owner text within 30 seconds; request, transcript and audio present | Full source scenario not evidenced; client acceptance pending |

Source stories: [US-010](../../../requirements/US.md#us-010).

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
| [AT-12](../../../requirements/AT.md#at-12) | Source-linked | 25.2 Acceptance tests |
| [BO-1](../../../requirements/BO.md#bo-1) | Source-linked | 3.1 Business objectives |
| [BR-002](../../../requirements/BR.md#br-002) | Source-linked | 7.1 Answering calls |
| [US-010](../../../requirements/US.md#us-010) | Source-linked | EP-03 AI voice front desk |
| [VOX-006](../../../requirements/VOX.md#vox-006) | Source-linked | 14.4 Requirements: real-time conversation quality |
| [VOX-007](../../../requirements/VOX.md#vox-007) | Source-linked | 14.4 Requirements: real-time conversation quality |
| [VOX-016](../../../requirements/VOX.md#vox-016) | Source-linked | 14.5 Requirements: business behavior |
| [VOX-017](../../../requirements/VOX.md#vox-017) | Source-linked | 14.5 Requirements: business behavior |
| [VOX-018](../../../requirements/VOX.md#vox-018) | Plan allocation / source cross-reference | 14.5 Requirements: business behavior |

Read every allocated record, including its continuation bullets and source variants. Source-linked rows preserve explicit document relationships; plan allocations are implementation responsibility assignments created during this review.

## Allocated specification checklist

The unchecked source obligations below require requirement-level evidence. They are deliberately separate from checked statements about current implemented slices. Read linked continuation bullets and additional source wording before accepting a record.

- [ ] [AGT-008](../../../requirements/AGT.md#agt-008): AGT-008 [P1] MUST implement structured extraction: at the end of every conversation, produce a schema-validated Request object (Appendix D) from the transcript and tool results, with per-field confidence and evidence spans. Downstream systems consume the structured object, never free text.
- [ ] [VOX-006](../../../requirements/VOX.md#vox-006): VOX-006 [P1] MUST handle noisy and degraded audio (car, wind, speakerphone): request repetition politely, confirm critical slots by read-back (phone number, address, name spelling), and fall back to SMS link capture ("I'll text you a link to share your location") when audio fails repeatedly.
- [ ] [VOX-007](../../../requirements/VOX.md#vox-007): VOX-007 [P1] MUST implement read-back confirmation for high-value slots: callback number, service address, name, appointment time.
- [ ] [VOX-016](../../../requirements/VOX.md#vox-016): VOX-016 [P1] MUST execute the vertical playbook: required slots (for example locksmith: lockout type, vehicle or property, address, safety status, ID-at-arrival note; HVAC: system type, symptom, urgency, occupants at risk). The agent asks one question at a time, adapts to volunteered information, and never re-asks for known data.
- [ ] [VOX-017](../../../requirements/VOX.md#vox-017): VOX-017 [P1] MUST support urgency triage producing urgency ∈ {emergency, urgent, standard, info} with reason, and route accordingly (immediate owner transfer or text with priority flag).
- [ ] [VOX-018](../../../requirements/VOX.md#vox-018): VOX-018 [P1] MUST check service area using geocoding of the captured address and politely decline or route out-of-area requests per tenant policy.

## Existing code / check evidence

- `app/api/voice/session/route.ts` - inspected current application working tree; see [snapshot evidence](../../../EVIDENCE.md).
- `app/api/site-assistant/session/route.ts` - inspected current application working tree; see [snapshot evidence](../../../EVIDENCE.md).
- `features/voice-agent/session-context.ts` - inspected current application working tree; see [snapshot evidence](../../../EVIDENCE.md).
- `features/voice-agent/session-prompt.ts` - inspected current application working tree; see [snapshot evidence](../../../EVIDENCE.md).
- `features/voice-agent/engine.ts` - inspected current application working tree; see [snapshot evidence](../../../EVIDENCE.md).
- `components/preview/website-assistant.tsx` - inspected current application working tree; see [snapshot evidence](../../../EVIDENCE.md).
- Relevant automated checks: `tests/lead-automation.test.ts`, `tests/product-core.test.ts`. Their scope is bounded by [current validation](../../../CURRENT_STATE.md).

## Blockers and boundaries

Module risk: Browser ElevenLabs sessions do not establish real PSTN numbers, two carriers, warm transfers, Spanish coverage or 24/7 answering.

Dependencies: [EVN-VOX-101](EVN-VOX-101.md), [EVN-KNW-102](../../02-knowledge-agent-configuration/tickets/EVN-KNW-102.md). A blocked prerequisite can be prototyped independently, but its contract and deployment must be approved before claiming this ticket delivered. Service limits, third-party approvals and staffing are evidence requirements, not assumptions that they are available.

## Handover and client acceptance

- [ ] Attach the business demonstration, technical evidence and operating/recovery instructions.
- [ ] Assign a named acceptance owner and agree any deferred criteria with the client in writing.
- [ ] Resolve launch-blocking defects and document accepted residual risks.
- [ ] Client records dated acceptance against the deployed/documented version.

Use [the acceptance protocol](../../../ACCEPTANCE.md) and [the ticket update rules](../../../TICKET_TEMPLATE.md) when changing status.
