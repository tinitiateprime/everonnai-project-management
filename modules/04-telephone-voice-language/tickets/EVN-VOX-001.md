# EVN-VOX-001 - Answer every call

Project: EverOnnAI. Module: [Telephone numbers, voice service and bilingual calls](../README.md). Source business requirement [BR-001](../../../requirements/BR.md#br-001).

| Tracking dimension | Disposition |
| --- | --- |
| Engineering | Planned |
| QA | Existing checks are evidence for current slices; full ticket criteria remain pending |
| Deployment | Current local snapshot; verify ticket-specific hosted rollout and configuration |
| Business acceptance | Pending client review; no signed acceptance recorded |
| Owner | Voice/Media Lead + SRE (proposed role; named person unassigned) |
| Priority / phase | Must / P1 |
| Estimate | TBD after scope/architecture agreement; no delivery date committed |
| Dependencies | [EVN-VOX-101](EVN-VOX-101.md), [EVN-KNW-102](../../02-knowledge-agent-configuration/tickets/EVN-KNW-102.md) |

## Business deliverable

Answer every call. Every inbound call to a client's business number is answered around the clock in the client's name, by the AI or, when configured, by a person.

The client accepts the demonstrated outcome and evidence, rather than the existence of a route, table or screen. This ticket does not certify the whole source requirement as complete.

## Current implemented slice

- [ ] Browser voice sessions and approved business context exist.

The current statement describes prerequisites or context; this business deliverable has not been demonstrated.

## Remaining delivery checklist

- [ ] Provide real PSTN ingress, two-carrier routing, verified forwarding, safe fallback and a measured 24/7 answering service.

## Technical component

- [ ] Implement the module boundary and contracts for: TelephonyProvider, call lifecycle, owner-first routing, safe capture.
- [ ] Maintain tenant boundaries, explicit state transitions, access policy and failure handling for the delivered workflow.
- [ ] Resolve applicable architecture decisions before committing to a new provider or infrastructure baseline.

## DB

Existing module persistence: conversations, conversation_messages, contacts, leads; browser voice usage sessions.

The following records/contracts are proposed or require extension; their names are planning terms, not assertions that production tables exist.

- [ ] calls, lines, number_routes, routing_tests.
- [ ] Review scope keys, uniqueness, indexes, retention and migration compatibility; backfill safely and preserve existing tenant records.

## UI

- [ ] Number setup wizard and live-call status.
- [ ] Provide loading, empty, validation, permission-denied and recoverable failure states with keyboard and mobile access.
- [ ] Show observed facts and pending states accurately; do not present estimates, configured flags or mock results as confirmed business actions.

## Translate - business-to-technical mapping

| Business rule / outcome | Technical responsibility | Evidence needed |
| --- | --- | --- |
| Answer every call. Every inbound call to a client's business number is answered around the clock in the client's name, by the AI or, when configured, by a person. | TelephonyProvider, call lifecycle, owner-first routing, safe capture | Tenant-scoped end-to-end demonstration of the outcome |
| Provide real PSTN ingress, two-carrier routing, verified forwarding, safe fallback and a measured 24/7 answering service. | calls, lines, number_routes, routing_tests; Number setup wizard and live-call status | Migration/contracts, visible state and failure-path evidence |
| Safe, truthful AI behaviour where applicable | Tenant-published agent greeting with fallback independent of the LLM | Approved context, verified side-effect receipts and evaluation results or justified N/A |
| Client can approve delivery | QA report, rollout evidence and named acceptance owner | Evidence links and dated client sign-off |

This section means requirements-to-implementation mapping. It does not mean language translation; source language obligations are tracked in their own requirements.

## Backend services

- [ ] TelephonyProvider, call lifecycle, owner-first routing, safe capture.
- [ ] Define request/response/event schemas, authorisation and input validation for each affected operation.
- [ ] For writes and provider effects, define idempotency, retry/timeout, receipts and reconciliation; document N/A where no side effects exist.
- [ ] Expose actionable status and scoped logs without secrets; distinguish completed, failed and uncertain outcomes.

## AI component

- [ ] Tenant-published agent greeting with fallback independent of the LLM.
- [ ] Record instruction/knowledge/tool versions, measured quality, tenant scope, cost and safe fallback; a Markdown standard alone is not a passed evaluation.

## Testing / QA

- [ ] Exercise the intended user journey with real tenant-scoped state; cover forbidden role and cross-tenant requests.
- [ ] Test malformed inputs, provider failure, retries/replays and cancellation as applicable; keep deterministic mocks separate from live-provider evidence.
- [ ] Review desktop/mobile accessibility, factual copy and failure recovery in the delivered UI.
- [ ] Attach test environment, code/config/instruction versions, results and remaining defects to the acceptance report.

| Source test | Scenario | Required pass criteria | Current disposition |
| --- | --- | --- | --- |
| [AT-12](../../../requirements/AT.md#at-12) | After-hours locksmith lockout call | Details captured with read-back; urgency classified; owner text within 30 seconds; request, transcript and audio present | Full source scenario not evidenced; client acceptance pending |

Source stories: [US-003](../../../requirements/US.md#us-003), [US-010](../../../requirements/US.md#us-010).

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
| [BR-001](../../../requirements/BR.md#br-001) | Source-linked | 7.1 Answering calls |
| [ONB-003](../../../requirements/ONB.md#onb-003) | Source-linked | 12.2 Requirements |
| [SL-01](../../../requirements/SL.md#sl-01) | Plan allocation / source cross-reference | 10.1 Service levels |
| [US-003](../../../requirements/US.md#us-003) | Source-linked | EP-01 Onboarding and claim |
| [US-010](../../../requirements/US.md#us-010) | Source-linked | EP-03 AI voice front desk |
| [VOX-001](../../../requirements/VOX.md#vox-001) | Source-linked | 14.3 Requirements: telephony and numbers |
| [VOX-010](../../../requirements/VOX.md#vox-010) | Plan allocation / source cross-reference | 14.4 Requirements: real-time conversation quality |
| [VOX-016](../../../requirements/VOX.md#vox-016) | Source-linked | 14.5 Requirements: business behavior |
| [VOX-030](../../../requirements/VOX.md#vox-030) | Source-linked | 14.3 Requirements: telephony and numbers |
| [VOX-032](../../../requirements/VOX.md#vox-032) | Source-linked | 14.3 Requirements: telephony and numbers |
| [VOX-034](../../../requirements/VOX.md#vox-034) | Plan allocation / source cross-reference | 14.3 Requirements: telephony and numbers |

Read every allocated record, including its continuation bullets and source variants. Source-linked rows preserve explicit document relationships; plan allocations are implementation responsibility assignments created during this review.

## Allocated specification checklist

The unchecked source obligations below require requirement-level evidence. They are deliberately separate from checked statements about current implemented slices. Read linked continuation bullets and additional source wording before accepting a record.

- [ ] [ONB-003](../../../requirements/ONB.md#onb-003): ONB-003 [P1] MUST guide a 5-step setup wizard: (1) confirm business facts, (2) approve or edit services and hours, (3) set escalation and handoff rules, (4) choose how calls reach EverOnn (forward, port, or new number, VOX-030 to VOX-034), (5) test call and test chat, then go live. Progress is saved; the owner can resume from any device.
- [ ] [SL-01](../../../requirements/SL.md#sl-01): SL-01 | Inbound calls answered by the AI, or safely captured, on the voice path | 99.9% availability per month.
- [ ] [VOX-001](../../../requirements/VOX.md#vox-001): VOX-001 [P1] MUST answer inbound PSTN calls via a SIP/PSTN carrier through the TelephonyProvider interface. P1 MUST support two carriers (Twilio and Telnyx) with automatic failover routing at the number or trunk level (VOX-036).
- [ ] [VOX-010](../../../requirements/VOX.md#vox-010): VOX-010 [P1] MUST detect voicemail/answering-machine and IVR situations on any outbound leg (transfers, callbacks) and behave appropriately (leave message or abort).
- [ ] [VOX-016](../../../requirements/VOX.md#vox-016): VOX-016 [P1] MUST execute the vertical playbook: required slots (for example locksmith: lockout type, vehicle or property, address, safety status, ID-at-arrival note; HVAC: system type, symptom, urgency, occupants at risk). The agent asks one question at a time, adapts to volunteered information, and never re-asks for known data.
- [ ] [VOX-030](../../../requirements/VOX.md#vox-030): VOX-030 [P1] MUST support three ways to put EverOnn in front of a business's calls:.
- [ ] [VOX-032](../../../requirements/VOX.md#vox-032): VOX-032 [P1] MUST provide a ring-owner-first option: ring the owner's phone (and staff numbers) for N seconds (default 15, configurable), then AI answers. Whisper: when the owner answers a forwarded call, no AI disclosure is played.
- [ ] [VOX-034](../../../requirements/VOX.md#vox-034): VOX-034 [P1] MUST support caller ID handling: pass caller ID into context; treat as untrusted; never assume identity from caller ID.

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
