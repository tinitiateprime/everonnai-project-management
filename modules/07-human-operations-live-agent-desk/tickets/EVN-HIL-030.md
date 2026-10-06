# EVN-HIL-030 - Operator call and chat controls

Project: EverOnnAI. Module: [Human escalation and the multi-client Live Agent Desk](../README.md). Source business requirement [BR-030](../../../requirements/BR.md#br-030).

| Tracking dimension | Disposition |
| --- | --- |
| Engineering | Planned |
| QA | Existing checks are evidence for current slices; full ticket criteria remain pending |
| Deployment | Current local snapshot; verify ticket-specific hosted rollout and configuration |
| Business acceptance | Pending client review; no signed acceptance recorded |
| Owner | Operations Lead + Voice/Media Lead + Backend Lead (proposed role; named person unassigned) |
| Priority / phase | Must / P1 |
| Estimate | TBD after scope/architecture agreement; no delivery date committed |
| Dependencies | [EVN-VOX-101](../../04-telephone-voice-language/tickets/EVN-VOX-101.md), [EVN-ONB-101](../../01-onboarding-tenancy-identity/tickets/EVN-ONB-101.md), [EVN-ONB-102](../../01-onboarding-tenancy-identity/tickets/EVN-ONB-102.md), [EVN-AIQ-102](../../03-ai-governance-evaluation/tickets/EVN-AIQ-102.md) |

## Business deliverable

Operator call and chat controls. Operators can hold, transfer to the client's owner or technician with a briefing, schedule a callback, take chats and texts, or hand the caller back to the AI.

The client accepts the demonstrated outcome and evidence, rather than the existence of a route, table or screen. This ticket does not certify the whole source requirement as complete.

## Current implemented slice

- [ ] Browser AI voice testing is not an operator softphone.

The current statement describes prerequisites or context; this business deliverable has not been demonstrated.

## Remaining delivery checklist

- [ ] Build accept/hold/mute/transfer/conference/callback/chat, contextual briefing and telephone fallback.

## Technical component

- [ ] Implement the module boundary and contracts for: MediaBridge, DeskCommandService and chat takeover.
- [ ] Maintain tenant boundaries, explicit state transitions, access policy and failure handling for the delivered workflow.
- [ ] Resolve applicable architecture decisions before committing to a new provider or infrastructure baseline.

## DB

Existing module persistence: Basic tenant conversation handoff status and transfer-number facts only; no managed desk domain.

The following records/contracts are proposed or require extension; their names are planning terms, not assertions that production tables exist.

- [ ] media_sessions, desk_commands, transfers.
- [ ] Review scope keys, uniqueness, indexes, retention and migration compatibility; backfill safely and preserve existing tenant records.

## UI

- [ ] WebRTC softphone, devices, keypad and shared chat.
- [ ] Provide loading, empty, validation, permission-denied and recoverable failure states with keyboard and mobile access.
- [ ] Show observed facts and pending states accurately; do not present estimates, configured flags or mock results as confirmed business actions.

## Translate - business-to-technical mapping

| Business rule / outcome | Technical responsibility | Evidence needed |
| --- | --- | --- |
| Operator call and chat controls. Operators can hold, transfer to the client's owner or technician with a briefing, schedule a callback, take chats and texts, or hand the caller back to the AI. | MediaBridge, DeskCommandService and chat takeover | Tenant-scoped end-to-end demonstration of the outcome |
| Build accept/hold/mute/transfer/conference/callback/chat, contextual briefing and telephone fallback. | media_sessions, desk_commands, transfers; WebRTC softphone, devices, keypad and shared chat | Migration/contracts, visible state and failure-path evidence |
| Safe, truthful AI behaviour where applicable | AI resumes only on explicit handback; label copilot drafts | Approved context, verified side-effect receipts and evaluation results or justified N/A |
| Client can approve delivery | QA report, rollout evidence and named acceptance owner | Evidence links and dated client sign-off |

This section means requirements-to-implementation mapping. It does not mean language translation; source language obligations are tracked in their own requirements.

## Backend services

- [ ] MediaBridge, DeskCommandService and chat takeover.
- [ ] Define request/response/event schemas, authorisation and input validation for each affected operation.
- [ ] For writes and provider effects, define idempotency, retry/timeout, receipts and reconciliation; document N/A where no side effects exist.
- [ ] Expose actionable status and scoped logs without secrets; distinguish completed, failed and uncertain outcomes.

## AI component

- [ ] AI resumes only on explicit handback.
- [ ] label copilot drafts.
- [ ] Record instruction/knowledge/tool versions, measured quality, tenant scope, cost and safe fallback; a Markdown standard alone is not a passed evaluation.

## Testing / QA

- [ ] Exercise the intended user journey with real tenant-scoped state; cover forbidden role and cross-tenant requests.
- [ ] Test malformed inputs, provider failure, retries/replays and cancellation as applicable; keep deterministic mocks separate from live-provider evidence.
- [ ] Review desktop/mobile accessibility, factual copy and failure recovery in the delivered UI.
- [ ] Attach test environment, code/config/instruction versions, results and remaining defects to the acceptance report.

| Source test | Scenario | Required pass criteria | Current disposition |
| --- | --- | --- | --- |
| [AT-33](../../../requirements/AT.md#at-33) | Operator call and chat controls | Hold with the client's audio; warm transfer with a briefing to the owner; conference a technician; callback showing the client's number; hand back to the AI; chats parked while on a call | Full source scenario not evidenced; client acceptance pending |
| [AT-35](../../../requirements/AT.md#at-35) | Wrap-up, handling record and quality sampling | Disposition and notes recorded; handling timestamps stored; operator minutes metered; the interaction enters the sampling queue by risk | Full source scenario not evidenced; client acceptance pending |

Source stories: [US-025](../../../requirements/US.md#us-025), [US-026](../../../requirements/US.md#us-026), [US-027](../../../requirements/US.md#us-027).

## Deployment

- [ ] Confirm approved hosting/database/provider architecture and required credentials in the deployment environment.
- [ ] Apply compatible migrations/configuration in staging, rehearse rollback, then promote the reviewed artifact.
- [ ] Verify the actual hosted workflow, monitoring, fallback and customer-visible errors after release.
- [ ] Update CODE_PROFILE.md, PROJECT_DATA_FLOW.md and CLIENT_TECHNICAL_QA.md in the application when behaviour or architecture changes.
- [ ] Record deployment identity, operator, timestamp and rollback evidence; document-only tickets instead record the reviewed Git commit.

## Source traceability

| Source ID | Mapping basis | Source section |
| --- | --- | --- |
| [AT-33](../../../requirements/AT.md#at-33) | Source-linked | 25.2 Acceptance tests |
| [AT-35](../../../requirements/AT.md#at-35) | Source-linked | 25.2 Acceptance tests |
| [BO-4](../../../requirements/BO.md#bo-4) | Source-linked | 3.1 Business objectives |
| [BR-030](../../../requirements/BR.md#br-030) | Source-linked | 7.5 Human operations and the Live Agent Desk |
| [BRL-020](../../../requirements/BRL.md#brl-020) | Plan allocation / source cross-reference | 8. Business rules |
| [CHT-008](../../../requirements/CHT.md#cht-008) | Plan allocation / source cross-reference | 15.2 Requirements |
| [DSK-011](../../../requirements/DSK.md#dsk-011) | Source-linked | 16.4.4 Handling the interaction |
| [DSK-012](../../../requirements/DSK.md#dsk-012) | Source-linked | 16.4.4 Handling the interaction |
| [DSK-013](../../../requirements/DSK.md#dsk-013) | Source-linked | 16.4.4 Handling the interaction |
| [DSK-015](../../../requirements/DSK.md#dsk-015) | Plan allocation / source cross-reference | 16.4.4 Handling the interaction |
| [DSK-016](../../../requirements/DSK.md#dsk-016) | Source-linked | 16.4.4 Handling the interaction |
| [DSK-019](../../../requirements/DSK.md#dsk-019) | Source-linked | 16.4.5 Offers, routing behavior and wrap-up |
| [US-025](../../../requirements/US.md#us-025) | Source-linked | EP-05 Human operations and the Live Agent Desk |
| [US-026](../../../requirements/US.md#us-026) | Source-linked | EP-05 Human operations and the Live Agent Desk |
| [US-027](../../../requirements/US.md#us-027) | Source-linked | EP-05 Human operations and the Live Agent Desk |
| [VOX-010](../../../requirements/VOX.md#vox-010) | Plan allocation / source cross-reference | 14.4 Requirements: real-time conversation quality |
| [VOX-019](../../../requirements/VOX.md#vox-019) | Plan allocation / source cross-reference | 14.5 Requirements: business behavior |

Read every allocated record, including its continuation bullets and source variants. Source-linked rows preserve explicit document relationships; plan allocations are implementation responsibility assignments created during this review.

## Allocated specification checklist

The unchecked source obligations below require requirement-level evidence. They are deliberately separate from checked statements about current implemented slices. Read linked continuation bullets and additional source wording before accepting a record.

- [ ] [BRL-020](../../../requirements/BRL.md#brl-020): BRL-020 | Callbacks show the client's business number as caller ID, never an operator's personal number. | Operators | DSK-016.
- [ ] [CHT-008](../../../requirements/CHT.md#cht-008): CHT-008 [P1] MUST support human takeover in chat (HIL-004): the operator or owner joins the same thread; the widget shows a subtle "a team member has joined" state.
- [ ] [DSK-011](../../../requirements/DSK.md#dsk-011): DSK-011 [P1] MUST provide a browser softphone: WebRTC audio through the media layer, device selection and test, echo cancellation and noise suppression, a network quality indicator, pre-shift diagnostics, automatic reconnection, and a telephone fallback (the platform calls the operator's registered number) if browser audio fails. USB headset call-control buttons via WebHID are P2.
- [ ] [DSK-012](../../../requirements/DSK.md#dsk-012): DSK-012 [P1] MUST provide voice call controls: accept; decline with a reason (returns to the queue); hold and resume with the client's hold audio; mute; warm transfer to the client's contacts with a whispered briefing; cold transfer; add a third party (the owner or a technician); hand back to the AI with an instruction; end; keypad; schedule a callback; send an SMS from client-approved templates; recording and consent indicator. Keyboard shortcuts for the common actions.
- [ ] [DSK-013](../../../requirements/DSK.md#dsk-013): DSK-013 [P1] MUST handle chat and SMS threads in the same queue and workspace: takeover and release, typing indicators, AI-drafted replies to approve, edit or send, client-specific canned replies, an attachment viewer for photos, and per-operator concurrency (default one voice interaction and up to three chat or SMS threads, configurable; chats are parked automatically when a voice interaction is accepted).
- [ ] [DSK-015](../../../requirements/DSK.md#dsk-015): DSK-015 [P2] SHOULD offer an operator copilot: live suggested questions, knowledge answers, summaries and draft messages under the same guardrails, clearly marked, never executed automatically, with operator feedback and measured effect on handling time and quality scores.
- [ ] [DSK-016](../../../requirements/DSK.md#dsk-016): DSK-016 [P1] MUST support callbacks and outbound calls from the desk only for interactions the caller or the client initiated: click-to-call showing the client's business number as caller ID, an outbound greeting script ("calling on behalf of {client_name}"), calling-hour and consent checks, and full logging. No cold outbound calling (COM-012).
- [ ] [DSK-019](../../../requirements/DSK.md#dsk-019): DSK-019 [P1] MUST require wrap-up: after the interaction the operator selects a disposition (resolved, message taken, transferred to owner, callback scheduled, spam, wrong number, other), corrects the structured request, adds notes visible to the client, sets a follow-up task and sends the client summary. Wrap-up has a timer (default 60 seconds, configurable) with automatic release; fields required per client are enforced; the operator cannot accept another voice offer until wrap-up is complete or the timer expires.
- [ ] [VOX-010](../../../requirements/VOX.md#vox-010): VOX-010 [P1] MUST detect voicemail/answering-machine and IVR situations on any outbound leg (transfers, callbacks) and behave appropriately (leave message or abort).
- [ ] [VOX-019](../../../requirements/VOX.md#vox-019): VOX-019 [P1] MUST support live transfer: warm transfer with a whispered context summary to the receiving party ("Caller Maria, lockout at 12 Oak St, urgent"), cold transfer, and transfer failure fallback (no answer → return to AI → capture message and schedule callback). Transfer targets and priority order are configured per hours mode. Targets are the client's own contacts and, in operator mode, EverOnn operators on the Live Agent Desk (§16.4).

## Existing code / check evidence

- `features/voice-agent/engine.ts` - inspected current application working tree; see [snapshot evidence](../../../EVIDENCE.md).
- `features/auth/rbac.ts` - inspected current application working tree; see [snapshot evidence](../../../EVIDENCE.md).
- `components/dashboard/everonn-dashboard.tsx` - inspected current application working tree; see [snapshot evidence](../../../EVIDENCE.md).
- Relevant automated checks: `tests/workspace-security.test.ts`, `tests/agent-runtime.test.ts`. Their scope is bounded by [current validation](../../../CURRENT_STATE.md).

## Blockers and boundaries

Module risk: No operator grants/queue/softphone, private briefing, authoritative offers, supervised human SLA or staffing evidence exists.

Dependencies: [EVN-VOX-101](../../04-telephone-voice-language/tickets/EVN-VOX-101.md), [EVN-ONB-101](../../01-onboarding-tenancy-identity/tickets/EVN-ONB-101.md), [EVN-ONB-102](../../01-onboarding-tenancy-identity/tickets/EVN-ONB-102.md), [EVN-AIQ-102](../../03-ai-governance-evaluation/tickets/EVN-AIQ-102.md). A blocked prerequisite can be prototyped independently, but its contract and deployment must be approved before claiming this ticket delivered. Service limits, third-party approvals and staffing are evidence requirements, not assumptions that they are available.

## Handover and client acceptance

- [ ] Attach the business demonstration, technical evidence and operating/recovery instructions.
- [ ] Assign a named acceptance owner and agree any deferred criteria with the client in writing.
- [ ] Resolve launch-blocking defects and document accepted residual risks.
- [ ] Client records dated acceptance against the deployed/documented version.

Use [the acceptance protocol](../../../ACCEPTANCE.md) and [the ticket update rules](../../../TICKET_TEMPLATE.md) when changing status.
