# EVN-HIL-036 - Desk reliability

Project: EverOnnAI. Module: [Human escalation and the multi-client Live Agent Desk](../README.md). Source business requirement [BR-036](../../../requirements/BR.md#br-036).

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

Desk reliability. The desk stays reliable: reloads and network drops do not lose calls, and no two operators take the same interaction.

The client accepts the demonstrated outcome and evidence, rather than the existence of a route, table or screen. This ticket does not certify the whole source requirement as complete.

## Current implemented slice

- [ ] Desk state, offer races and media reconnection are absent.

The current statement describes prerequisites or context; this business deliverable has not been demonstrated.

## Remaining delivery checklist

- [ ] Prove first acceptance wins, single operator session, three-second restore and five-second disconnect detection.

## Technical component

- [ ] Implement the module boundary and contracts for: Atomic assignment, resume protocol, heartbeat and media lifecycle.
- [ ] Maintain tenant boundaries, explicit state transitions, access policy and failure handling for the delivered workflow.
- [ ] Resolve applicable architecture decisions before committing to a new provider or infrastructure baseline.

## DB

Existing module persistence: Basic tenant conversation handoff status and transfer-number facts only; no managed desk domain.

The following records/contracts are proposed or require extension; their names are planning terms, not assertions that production tables exist.

- [ ] offers, assignments, desk_sessions, command_receipts.
- [ ] Review scope keys, uniqueness, indexes, retention and migration compatibility; backfill safely and preserve existing tenant records.

## UI

- [ ] Reconnect/state restoration and call continuity.
- [ ] Provide loading, empty, validation, permission-denied and recoverable failure states with keyboard and mobile access.
- [ ] Show observed facts and pending states accurately; do not present estimates, configured flags or mock results as confirmed business actions.

## Translate - business-to-technical mapping

| Business rule / outcome | Technical responsibility | Evidence needed |
| --- | --- | --- |
| Desk reliability. The desk stays reliable: reloads and network drops do not lose calls, and no two operators take the same interaction. | Atomic assignment, resume protocol, heartbeat and media lifecycle | Tenant-scoped end-to-end demonstration of the outcome |
| Prove first acceptance wins, single operator session, three-second restore and five-second disconnect detection. | offers, assignments, desk_sessions, command_receipts; Reconnect/state restoration and call continuity | Migration/contracts, visible state and failure-path evidence |
| Safe, truthful AI behaviour where applicable | Fallback only after authoritative rerouting | Approved context, verified side-effect receipts and evaluation results or justified N/A |
| Client can approve delivery | QA report, rollout evidence and named acceptance owner | Evidence links and dated client sign-off |

This section means requirements-to-implementation mapping. It does not mean language translation; source language obligations are tracked in their own requirements.

## Backend services

- [ ] Atomic assignment, resume protocol, heartbeat and media lifecycle.
- [ ] Define request/response/event schemas, authorisation and input validation for each affected operation.
- [ ] For writes and provider effects, define idempotency, retry/timeout, receipts and reconciliation; document N/A where no side effects exist.
- [ ] Expose actionable status and scoped logs without secrets; distinguish completed, failed and uncertain outcomes.

## AI component

- [ ] Fallback only after authoritative rerouting.
- [ ] Record instruction/knowledge/tool versions, measured quality, tenant scope, cost and safe fallback; a Markdown standard alone is not a passed evaluation.

## Testing / QA

- [ ] Exercise the intended user journey with real tenant-scoped state; cover forbidden role and cross-tenant requests.
- [ ] Test malformed inputs, provider failure, retries/replays and cancellation as applicable; keep deterministic mocks separate from live-provider evidence.
- [ ] Review desktop/mobile accessibility, factual copy and failure recovery in the delivered UI.
- [ ] Attach test environment, code/config/instruction versions, results and remaining defects to the acceptance report.

| Source test | Scenario | Required pass criteria | Current disposition |
| --- | --- | --- | --- |
| [AT-34](../../../requirements/AT.md#at-34) | No operator accepts in time, and simultaneous acceptance | Cascade proceeds (next operator, then owner, then message capture with a promised callback); two simultaneous acceptances result in exactly one assignment | Full source scenario not evidenced; client acceptance pending |
| [AT-37](../../../requirements/AT.md#at-37) | Desk reload, network loss and a second browser tab | State restored within 3 seconds with no dropped call; disconnect detected within 5 seconds and handled per policy; a second session supersedes the first; telephone fallback works | Full source scenario not evidenced; client acceptance pending |

Source stories: [US-034](../../../requirements/US.md#us-034).

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
| [AT-34](../../../requirements/AT.md#at-34) | Source-linked | 25.2 Acceptance tests |
| [AT-37](../../../requirements/AT.md#at-37) | Source-linked | 25.2 Acceptance tests |
| [BO-4](../../../requirements/BO.md#bo-4) | Source-linked | 3.1 Business objectives |
| [BR-036](../../../requirements/BR.md#br-036) | Source-linked | 7.5 Human operations and the Live Agent Desk |
| [DSK-011](../../../requirements/DSK.md#dsk-011) | Source-linked | 16.4.4 Handling the interaction |
| [DSK-018](../../../requirements/DSK.md#dsk-018) | Source-linked | 16.4.5 Offers, routing behavior and wrap-up |
| [DSK-026](../../../requirements/DSK.md#dsk-026) | Source-linked | 16.4.7 Ergonomics and resilience |
| [HIL-016](../../../requirements/HIL.md#hil-016) | Plan allocation / source cross-reference | 16.3 Escalation, routing and service levels (HIL) |
| [SCF-025](../../../requirements/SCF.md#scf-025) | Plan allocation / source cross-reference | 22.3 Scaffolding checklist |
| [US-034](../../../requirements/US.md#us-034) | Source-linked | EP-05 Human operations and the Live Agent Desk |

Read every allocated record, including its continuation bullets and source variants. Source-linked rows preserve explicit document relationships; plan allocations are implementation responsibility assignments created during this review.

## Allocated specification checklist

The unchecked source obligations below require requirement-level evidence. They are deliberately separate from checked statements about current implemented slices. Read linked continuation bullets and additional source wording before accepting a record.

- [ ] [API-006](../../../requirements/API.md#api-006): API-006 [P1] MUST provide realtime channels for the dashboard (WebSocket or SSE) for live call status, inbox updates and escalation alerts.
- [ ] [DSK-011](../../../requirements/DSK.md#dsk-011): DSK-011 [P1] MUST provide a browser softphone: WebRTC audio through the media layer, device selection and test, echo cancellation and noise suppression, a network quality indicator, pre-shift diagnostics, automatic reconnection, and a telephone fallback (the platform calls the operator's registered number) if browser audio fails. USB headset call-control buttons via WebHID are P2.
- [ ] [DSK-018](../../../requirements/DSK.md#dsk-018): DSK-018 [P1] MUST implement offer, ring and cascade behavior: offers expire after a configurable time (default 15 seconds); strategies include longest-idle and skills-first (ring-all-eligible at P2); the first acceptance wins through an atomic assignment; a decline or timeout moves to the next operator per the cascade; when no operator accepts within the service level the cascade continues (overflow pool, then the client's owner, then message capture with a promised callback and repeated alerts for emergencies). While the caller waits they hear branded hold messages, an offer to leave a message, and periodic updates. Every step is logged with timestamps.
- [ ] [DSK-026](../../../requirements/DSK.md#dsk-026): DSK-026 [P1] MUST be resilient: the server is authoritative for interaction state. A desk reload or reconnect restores the exact state within three seconds and never drops a live call. Heartbeats detect operator disconnection within five seconds (the call returns to the queue or the AI resumes, per policy). A single active desk session per operator is enforced.
- [ ] [HIL-016](../../../requirements/HIL.md#hil-016): HIL-016 [P1] SHOULD provide degraded-operator mode: if no human is available within SLA, the system falls back to the safest path (take detailed message, callback task, and clear promise to the caller), and alerts the on-call lead.
- [ ] [SCF-025](../../../requirements/SCF.md#scf-025): 25 | Client desk profile, authority matrix and operator grants as data; line-based routing key | Dedicated operator teams per client, partner operator pools, premium human-service tiers.

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
