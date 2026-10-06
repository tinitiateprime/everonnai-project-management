# EVN-VOX-005 - Emergency handling

Project: EverOnnAI. Module: [Telephone numbers, voice service and bilingual calls](../README.md). Source business requirement [BR-005](../../../requirements/BR.md#br-005).

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

Emergency handling. Emergencies (safety, medical, threats) are recognized and handled with safe advice and immediate human escalation.

The client accepts the demonstrated outcome and evidence, rather than the existence of a route, table or screen. This ticket does not certify the whole source requirement as complete.

## Current implemented slice

- [x] Text-path gas/carbon-monoxide safety replies bypass routine generation.

## Remaining delivery checklist

- [ ] Add vertical-wide emergency recognition on real calls, immediate priority escalation, acknowledgements and no-human fallback.

## Technical component

- [ ] Implement the module boundary and contracts for: Severity router, repeated alerts and safe emergency guidance.
- [ ] Maintain tenant boundaries, explicit state transitions, access policy and failure handling for the delivered workflow.
- [ ] Resolve applicable architecture decisions before committing to a new provider or infrastructure baseline.

## DB

Existing module persistence: conversations, conversation_messages, contacts, leads; browser voice usage sessions.

The following records/contracts are proposed or require extension; their names are planning terms, not assertions that production tables exist.

- [ ] emergency_rules, escalations, acknowledgements.
- [ ] Review scope keys, uniqueness, indexes, retention and migration compatibility; backfill safely and preserve existing tenant records.

## UI

- [ ] Emergency alerts and escalation timeline.
- [ ] Provide loading, empty, validation, permission-denied and recoverable failure states with keyboard and mobile access.
- [ ] Show observed facts and pending states accurately; do not present estimates, configured flags or mock results as confirmed business actions.

## Translate - business-to-technical mapping

| Business rule / outcome | Technical responsibility | Evidence needed |
| --- | --- | --- |
| Emergency handling. Emergencies (safety, medical, threats) are recognized and handled with safe advice and immediate human escalation. | Severity router, repeated alerts and safe emergency guidance | Tenant-scoped end-to-end demonstration of the outcome |
| Add vertical-wide emergency recognition on real calls, immediate priority escalation, acknowledgements and no-human fallback. | emergency_rules, escalations, acknowledgements; Emergency alerts and escalation timeline | Migration/contracts, visible state and failure-path evidence |
| Safe, truthful AI behaviour where applicable | High-recall emergency detection with deterministic routing | Approved context, verified side-effect receipts and evaluation results or justified N/A |
| Client can approve delivery | QA report, rollout evidence and named acceptance owner | Evidence links and dated client sign-off |

This section means requirements-to-implementation mapping. It does not mean language translation; source language obligations are tracked in their own requirements.

## Backend services

- [ ] Severity router, repeated alerts and safe emergency guidance.
- [ ] Define request/response/event schemas, authorisation and input validation for each affected operation.
- [ ] For writes and provider effects, define idempotency, retry/timeout, receipts and reconciliation; document N/A where no side effects exist.
- [ ] Expose actionable status and scoped logs without secrets; distinguish completed, failed and uncertain outcomes.

## AI component

- [ ] High-recall emergency detection with deterministic routing.
- [ ] Record instruction/knowledge/tool versions, measured quality, tenant scope, cost and safe fallback; a Markdown standard alone is not a passed evaluation.

## Testing / QA

- [ ] Exercise the intended user journey with real tenant-scoped state; cover forbidden role and cross-tenant requests.
- [ ] Test malformed inputs, provider failure, retries/replays and cancellation as applicable; keep deterministic mocks separate from live-provider evidence.
- [ ] Review desktop/mobile accessibility, factual copy and failure recovery in the delivered UI.
- [ ] Attach test environment, code/config/instruction versions, results and remaining defects to the acceptance report.

| Source test | Scenario | Required pass criteria | Current disposition |
| --- | --- | --- | --- |
| [AT-16](../../../requirements/AT.md#at-16) | Caller reports a gas smell or medical emergency | Advised to call emergency services; top-priority escalation; immediate live transfer to a person; alerts repeat until acknowledged | Full source scenario not evidenced; client acceptance pending |

Source stories: [US-013](../../../requirements/US.md#us-013), [US-031](../../../requirements/US.md#us-031).

## Deployment

- [ ] Confirm approved hosting/database/provider architecture and required credentials in the deployment environment.
- [ ] Apply compatible migrations/configuration in staging, rehearse rollback, then promote the reviewed artifact.
- [ ] Verify the actual hosted workflow, monitoring, fallback and customer-visible errors after release.
- [ ] Update CODE_PROFILE.md, PROJECT_DATA_FLOW.md and CLIENT_TECHNICAL_QA.md in the application when behaviour or architecture changes.
- [ ] Record deployment identity, operator, timestamp and rollback evidence; document-only tickets instead record the reviewed Git commit.

## Source traceability

| Source ID | Mapping basis | Source section |
| --- | --- | --- |
| [AT-16](../../../requirements/AT.md#at-16) | Source-linked | 25.2 Acceptance tests |
| [BO-3](../../../requirements/BO.md#bo-3) | Source-linked | 3.1 Business objectives |
| [BR-005](../../../requirements/BR.md#br-005) | Source-linked | 7.1 Answering calls |
| [BRL-004](../../../requirements/BRL.md#brl-004) | Plan allocation / source cross-reference | 8. Business rules |
| [BRL-022](../../../requirements/BRL.md#brl-022) | Plan allocation / source cross-reference | 8. Business rules |
| [HIL-002](../../../requirements/HIL.md#hil-002) | Source-linked | 16.3 Escalation, routing and service levels (HIL) |
| [POL-002](../../../requirements/POL.md#pol-002) | Source-linked | 13.4 Guardrails and policy engine |
| [US-013](../../../requirements/US.md#us-013) | Source-linked | EP-03 AI voice front desk |
| [US-031](../../../requirements/US.md#us-031) | Source-linked | EP-05 Human operations and the Live Agent Desk |

Read every allocated record, including its continuation bullets and source variants. Source-linked rows preserve explicit document relationships; plan allocations are implementation responsibility assignments created during this review.

## Allocated specification checklist

The unchecked source obligations below require requirement-level evidence. They are deliberately separate from checked statements about current implemented slices. Read linked continuation bullets and additional source wording before accepting a record.

- [ ] [BRL-004](../../../requirements/BRL.md#brl-004): BRL-004 | An emergency (safety, medical, threat) results in advice to contact emergency services and immediate escalation at the highest priority. | AI agents, operators | POL-002, HIL-002.
- [ ] [BRL-022](../../../requirements/BRL.md#brl-022): BRL-022 | An unacknowledged emergency alert repeats until someone acknowledges it. | Escalation | HIL-002, HIL-015.
- [ ] [HIL-002](../../../requirements/HIL.md#hil-002): HIL-002 [P1] MUST implement severity-based SLAs and cascades (values configurable, defaults below):.
- [ ] [POL-002](../../../requirements/POL.md#pol-002): POL-002 [P1] MUST implement emergency and safety triage per vertical: gas smell, fire, carbon monoxide, medical emergency, child locked in car, and threats. The agent MUST advise contacting emergency services where appropriate, and immediately escalate (HIL-002) to the owner or operator with highest priority. The trigger phrases and actions are configured in vertical templates and covered by the eval set.

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
