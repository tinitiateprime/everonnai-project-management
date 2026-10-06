# EVN-VOX-101 - Prove a real telephone call can meet quality, latency and cost targets

Project: EverOnnAI. Module: [Telephone numbers, voice service and bilingual calls](../README.md). Technical delivery enabler allocated by this plan; source references below.

| Tracking dimension | Disposition |
| --- | --- |
| Engineering | Planned |
| QA | Existing checks are evidence for current slices; full ticket criteria remain pending |
| Deployment | Current local snapshot; verify ticket-specific hosted rollout and configuration |
| Business acceptance | Pending client review; no signed acceptance recorded |
| Owner | Voice/Media Lead + SRE (proposed role; named person unassigned) |
| Priority / phase | Delivery enabler / P0 |
| Estimate | TBD after scope/architecture agreement; no delivery date committed |
| Dependencies | [EVN-FND-101](../../00-foundations-governance/tickets/EVN-FND-101.md), [EVN-AIQ-101](../../03-ai-governance-evaluation/tickets/EVN-AIQ-101.md) |

## Business deliverable

Prove a real telephone call can meet quality, latency and cost targets.

The client accepts the demonstrated outcome and evidence, rather than the existence of a route, table or screen. This ticket does not certify the whole source requirement as complete.

## Current implemented slice

- [ ] Browser voice is available; no source-compliant SIP/PSTN spike evidence exists.

The current statement describes prerequisites or context; this business deliverable has not been demonstrated.

## Remaining delivery checklist

- [ ] Place controlled sandbox calls on both carriers, compare speech/model combinations and operator audio topology, then publish traces and costs.

## Technical component

- [ ] Implement the module boundary and contracts for: SIP carrier/media bridge and synthetic caller harness.
- [ ] Maintain tenant boundaries, explicit state transitions, access policy and failure handling for the delivered workflow.
- [ ] Resolve applicable architecture decisions before committing to a new provider or infrastructure baseline.

## DB

Existing module persistence: conversations, conversation_messages, contacts, leads; browser voice usage sessions.

The following records/contracts are proposed or require extension; their names are planning terms, not assertions that production tables exist.

- [ ] call_spike_runs, latency/cost results, topology evidence.
- [ ] Review scope keys, uniqueness, indexes, retention and migration compatibility; backfill safely and preserve existing tenant records.

## UI

- [ ] Call-spike diagnostics and recordings approved for test use.
- [ ] Provide loading, empty, validation, permission-denied and recoverable failure states with keyboard and mobile access.
- [ ] Show observed facts and pending states accurately; do not present estimates, configured flags or mock results as confirmed business actions.

## Translate - business-to-technical mapping

| Business rule / outcome | Technical responsibility | Evidence needed |
| --- | --- | --- |
| Prove a real telephone call can meet quality, latency and cost targets. | SIP carrier/media bridge and synthetic caller harness | Tenant-scoped end-to-end demonstration of the outcome |
| Place controlled sandbox calls on both carriers, compare speech/model combinations and operator audio topology, then publish traces and costs. | call_spike_runs, latency/cost results, topology evidence; Call-spike diagnostics and recordings approved for test use | Migration/contracts, visible state and failure-path evidence |
| Safe, truthful AI behaviour where applicable | No new production vendor commitment without the ADR and measured evidence | Approved context, verified side-effect receipts and evaluation results or justified N/A |
| Client can approve delivery | QA report, rollout evidence and named acceptance owner | Evidence links and dated client sign-off |

This section means requirements-to-implementation mapping. It does not mean language translation; source language obligations are tracked in their own requirements.

## Backend services

- [ ] SIP carrier/media bridge and synthetic caller harness.
- [ ] Define request/response/event schemas, authorisation and input validation for each affected operation.
- [ ] For writes and provider effects, define idempotency, retry/timeout, receipts and reconciliation; document N/A where no side effects exist.
- [ ] Expose actionable status and scoped logs without secrets; distinguish completed, failed and uncertain outcomes.

## AI component

- [ ] No new production vendor commitment without the ADR and measured evidence.
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
| [CST-001](../../../requirements/CST.md#cst-001) | Source-linked | 23.6 Unit economics and cost controls |
| [VOX-002](../../../requirements/VOX.md#vox-002) | Source-linked | 14.4 Requirements: real-time conversation quality |
| [VOX-003](../../../requirements/VOX.md#vox-003) | Source-linked | 14.4 Requirements: real-time conversation quality |
| [VOX-040](../../../requirements/VOX.md#vox-040) | Source-linked | 14.6 Voice runtime deployment requirements |
| [VOX-041](../../../requirements/VOX.md#vox-041) | Source-linked | 14.6 Voice runtime deployment requirements |
| [VOX-042](../../../requirements/VOX.md#vox-042) | Source-linked | 14.6 Voice runtime deployment requirements |
| [VOX-043](../../../requirements/VOX.md#vox-043) | Source-linked | 14.6 Voice runtime deployment requirements |
| [VOX-044](../../../requirements/VOX.md#vox-044) | Source-linked | 14.6 Voice runtime deployment requirements |

Read every allocated record, including its continuation bullets and source variants. Source-linked rows preserve explicit document relationships; plan allocations are implementation responsibility assignments created during this review.

## Allocated specification checklist

The unchecked source obligations below require requirement-level evidence. They are deliberately separate from checked statements about current implemented slices. Read linked continuation bullets and additional source wording before accepting a record.

- [ ] [CST-001](../../../requirements/CST.md#cst-001): CST-001 [P0] MUST produce a cost model and measured per-minute cost in the P0 spike for at least three vendor combinations, and recommend the default stack by cost and quality.
- [ ] [VOX-002](../../../requirements/VOX.md#vox-002): VOX-002 [P0] MUST implement a cascaded real-time pipeline (streaming STT → LLM → streaming TTS) behind provider interfaces, with the ability to swap in a speech-to-speech model as an alternative implementation later. P0 spike compares at least: two STT vendors, two TTS vendors, two LLM tiers, on real PSTN audio (8 kHz, noisy, accents) and reports latency, accuracy and cost.
- [ ] [VOX-003](../../../requirements/VOX.md#vox-003): VOX-003 [P0] MUST meet the latency budget (planning targets, measured end-to-end as caller-perceived silence between end of caller speech and first agent audio):.
- [ ] [VOX-040](../../../requirements/VOX.md#vox-040): VOX-040 [P1] MUST run voice workers as horizontally scalable, stateless containers that pull tenant configuration from a cache keyed by version, with graceful draining (AR-009).
- [ ] [VOX-041](../../../requirements/VOX.md#vox-041): VOX-041 [P1] MUST be latency-aware in placement: media and voice workers deployed in the same region as the carrier edge; multi-region capable by config (P2).
- [ ] [VOX-042](../../../requirements/VOX.md#vox-042): VOX-042 [P1] MUST emit per-turn traces (OpenTelemetry) covering endpointing, STT, retrieval, LLM, tool, TTS spans, plus per-call cost attribution.
- [ ] [VOX-043](../../../requirements/VOX.md#vox-043): VOX-043 [P1] MUST support call replay in staging from recorded audio and transcripts for debugging and regression (with redaction, COM-007).
- [ ] [VOX-044](../../../requirements/VOX.md#vox-044): VOX-044 [P2] SHOULD support warm pools of pre-initialized agent sessions for common tenants to cut first-turn latency.

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

Dependencies: [EVN-FND-101](../../00-foundations-governance/tickets/EVN-FND-101.md), [EVN-AIQ-101](../../03-ai-governance-evaluation/tickets/EVN-AIQ-101.md). A blocked prerequisite can be prototyped independently, but its contract and deployment must be approved before claiming this ticket delivered. Service limits, third-party approvals and staffing are evidence requirements, not assumptions that they are available.

## Handover and client acceptance

- [ ] Attach the business demonstration, technical evidence and operating/recovery instructions.
- [ ] Assign a named acceptance owner and agree any deferred criteria with the client in writing.
- [ ] Resolve launch-blocking defects and document accepted residual risks.
- [ ] Client records dated acceptance against the deployed/documented version.

Use [the acceptance protocol](../../../ACCEPTANCE.md) and [the ticket update rules](../../../TICKET_TEMPLATE.md) when changing status.
