# EVN-VOX-003 - Natural, responsive conversation

Project: EverOnnAI. Module: [Telephone numbers, voice service and bilingual calls](../README.md). Source business requirement [BR-003](../../../requirements/BR.md#br-003).

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

Natural, responsive conversation. Conversations feel natural and responsive; callers do not experience long silences and can interrupt.

The client accepts the demonstrated outcome and evidence, rather than the existence of a route, table or screen. This ticket does not certify the whole source requirement as complete.

## Current implemented slice

- [x] ElevenLabs browser voice uses signed sessions.

## Remaining delivery checklist

- [ ] Prove PSTN turn latency, interruption within 200 ms, VAD and noise tolerance; measure alternative providers.

## Technical component

- [ ] Implement the module boundary and contracts for: Streaming STT/LLM/TTS orchestration and cancellation.
- [ ] Maintain tenant boundaries, explicit state transitions, access policy and failure handling for the delivered workflow.
- [ ] Resolve applicable architecture decisions before committing to a new provider or infrastructure baseline.

## DB

Existing module persistence: conversations, conversation_messages, contacts, leads; browser voice usage sessions.

The following records/contracts are proposed or require extension; their names are planning terms, not assertions that production tables exist.

- [ ] call_turns, stage_latency, provider_health.
- [ ] Review scope keys, uniqueness, indexes, retention and migration compatibility; backfill safely and preserve existing tenant records.

## UI

- [ ] Latency diagnostics and call replay.
- [ ] Provide loading, empty, validation, permission-denied and recoverable failure states with keyboard and mobile access.
- [ ] Show observed facts and pending states accurately; do not present estimates, configured flags or mock results as confirmed business actions.

## Translate - business-to-technical mapping

| Business rule / outcome | Technical responsibility | Evidence needed |
| --- | --- | --- |
| Natural, responsive conversation. Conversations feel natural and responsive; callers do not experience long silences and can interrupt. | Streaming STT/LLM/TTS orchestration and cancellation | Tenant-scoped end-to-end demonstration of the outcome |
| Prove PSTN turn latency, interruption within 200 ms, VAD and noise tolerance; measure alternative providers. | call_turns, stage_latency, provider_health; Latency diagnostics and call replay | Migration/contracts, visible state and failure-path evidence |
| Safe, truthful AI behaviour where applicable | Task-specific voice model routing and calibrated speech evaluation | Approved context, verified side-effect receipts and evaluation results or justified N/A |
| Client can approve delivery | QA report, rollout evidence and named acceptance owner | Evidence links and dated client sign-off |

This section means requirements-to-implementation mapping. It does not mean language translation; source language obligations are tracked in their own requirements.

## Backend services

- [ ] Streaming STT/LLM/TTS orchestration and cancellation.
- [ ] Define request/response/event schemas, authorisation and input validation for each affected operation.
- [ ] For writes and provider effects, define idempotency, retry/timeout, receipts and reconciliation; document N/A where no side effects exist.
- [ ] Expose actionable status and scoped logs without secrets; distinguish completed, failed and uncertain outcomes.

## AI component

- [ ] Task-specific voice model routing and calibrated speech evaluation.
- [ ] Record instruction/knowledge/tool versions, measured quality, tenant scope, cost and safe fallback; a Markdown standard alone is not a passed evaluation.

## Testing / QA

- [ ] Exercise the intended user journey with real tenant-scoped state; cover forbidden role and cross-tenant requests.
- [ ] Test malformed inputs, provider failure, retries/replays and cancellation as applicable; keep deterministic mocks separate from live-provider evidence.
- [ ] Review desktop/mobile accessibility, factual copy and failure recovery in the delivered UI.
- [ ] Attach test environment, code/config/instruction versions, results and remaining defects to the acceptance report.

| Source test | Scenario | Required pass criteria | Current disposition |
| --- | --- | --- | --- |
| [AT-13](../../../requirements/AT.md#at-13) | Caller-perceived response time on real phone calls | Across 200 real phone calls: p50 under 1.0 s and p95 under 1.8 s; barge-in stops speech within 200 ms | Full source scenario not evidenced; client acceptance pending |

Source stories: [US-014](../../../requirements/US.md#us-014).

## Deployment

- [ ] Confirm approved hosting/database/provider architecture and required credentials in the deployment environment.
- [ ] Apply compatible migrations/configuration in staging, rehearse rollback, then promote the reviewed artifact.
- [ ] Verify the actual hosted workflow, monitoring, fallback and customer-visible errors after release.
- [ ] Update CODE_PROFILE.md, PROJECT_DATA_FLOW.md and CLIENT_TECHNICAL_QA.md in the application when behaviour or architecture changes.
- [ ] Record deployment identity, operator, timestamp and rollback evidence; document-only tickets instead record the reviewed Git commit.

## Source traceability

| Source ID | Mapping basis | Source section |
| --- | --- | --- |
| [AT-13](../../../requirements/AT.md#at-13) | Source-linked | 25.2 Acceptance tests |
| [BO-1](../../../requirements/BO.md#bo-1) | Source-linked | 3.1 Business objectives |
| [BO-3](../../../requirements/BO.md#bo-3) | Source-linked | 3.1 Business objectives |
| [BR-003](../../../requirements/BR.md#br-003) | Source-linked | 7.1 Answering calls |
| [SL-02](../../../requirements/SL.md#sl-02) | Plan allocation / source cross-reference | 10.1 Service levels |
| [US-014](../../../requirements/US.md#us-014) | Source-linked | EP-03 AI voice front desk |
| [VOX-002](../../../requirements/VOX.md#vox-002) | Source-linked | 14.4 Requirements: real-time conversation quality |
| [VOX-003](../../../requirements/VOX.md#vox-003) | Source-linked | 14.4 Requirements: real-time conversation quality |
| [VOX-004](../../../requirements/VOX.md#vox-004) | Source-linked | 14.4 Requirements: real-time conversation quality |
| [VOX-005](../../../requirements/VOX.md#vox-005) | Source-linked | 14.4 Requirements: real-time conversation quality |
| [VOX-011](../../../requirements/VOX.md#vox-011) | Plan allocation / source cross-reference | 14.4 Requirements: real-time conversation quality |
| [VOX-012](../../../requirements/VOX.md#vox-012) | Plan allocation / source cross-reference | 14.4 Requirements: real-time conversation quality |
| [VOX-013](../../../requirements/VOX.md#vox-013) | Plan allocation / source cross-reference | 14.4 Requirements: real-time conversation quality |
| [VOX-014](../../../requirements/VOX.md#vox-014) | Plan allocation / source cross-reference | 14.4 Requirements: real-time conversation quality |
| [VOX-015](../../../requirements/VOX.md#vox-015) | Plan allocation / source cross-reference | 14.4 Requirements: real-time conversation quality |

Read every allocated record, including its continuation bullets and source variants. Source-linked rows preserve explicit document relationships; plan allocations are implementation responsibility assignments created during this review.

## Allocated specification checklist

The unchecked source obligations below require requirement-level evidence. They are deliberately separate from checked statements about current implemented slices. Read linked continuation bullets and additional source wording before accepting a record.

- [ ] [SL-02](../../../requirements/SL.md#sl-02): SL-02 | Caller-perceived response gap | Median under 1.0 s; 95th percentile under 1.8 s.
- [ ] [VOX-002](../../../requirements/VOX.md#vox-002): VOX-002 [P0] MUST implement a cascaded real-time pipeline (streaming STT → LLM → streaming TTS) behind provider interfaces, with the ability to swap in a speech-to-speech model as an alternative implementation later. P0 spike compares at least: two STT vendors, two TTS vendors, two LLM tiers, on real PSTN audio (8 kHz, noisy, accents) and reports latency, accuracy and cost.
- [ ] [VOX-003](../../../requirements/VOX.md#vox-003): VOX-003 [P0] MUST meet the latency budget (planning targets, measured end-to-end as caller-perceived silence between end of caller speech and first agent audio):.
- [ ] [VOX-004](../../../requirements/VOX.md#vox-004): VOX-004 [P1] MUST support barge-in: the caller can interrupt; TTS stops within 200 ms; the agent resumes from the interrupted context and does not repeat itself.
- [ ] [VOX-005](../../../requirements/VOX.md#vox-005): VOX-005 [P1] MUST implement robust turn-taking: semantic end-of-turn detection (not silence alone), tolerance for "um/uh", handling of caller thinking pauses, and detection of the caller reading back numbers or addresses (longer pauses).
- [ ] [VOX-011](../../../requirements/VOX.md#vox-011): VOX-011 [P1] MUST manage silence, hold and dropped calls: prompts after configurable silence, hang-up after N prompts, graceful handling of caller hang-up mid-turn, and full post-call processing even on abrupt termination.
- [ ] [VOX-012](../../../requirements/VOX.md#vox-012): VOX-012 [P1] MUST provide voice selection: a curated set of natural voices per language (with cloning of the owner's voice explicitly out of scope for P1, and only with documented consent in P3). Pronunciation dictionaries per tenant (business names, streets, terms).
- [ ] [VOX-013](../../../requirements/VOX.md#vox-013): VOX-013 [P1] MUST support background-noise-safe barge-in (do not let TV/wind trigger interruption): use VAD tuned per carrier codec and echo cancellation.
- [ ] [VOX-014](../../../requirements/VOX.md#vox-014): VOX-014 [P2] SHOULD provide prosody controls (pace, warmth) and backchanneling ("mm-hm") with per-tenant toggles.
- [ ] [VOX-015](../../../requirements/VOX.md#vox-015): VOX-015 [P2] SHOULD support multi-party awareness (speakerphone with two speakers) heuristics and safe behavior (confirm who the account holder is before sharing anything).

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
