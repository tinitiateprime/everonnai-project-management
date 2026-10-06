# EVN-HIL-026 - Shared multi-client operator desk

Project: EverOnnAI. Module: [Human escalation and the multi-client Live Agent Desk](../README.md). Source business requirement [BR-026](../../../requirements/BR.md#br-026).

| Tracking dimension | Disposition |
| --- | --- |
| Engineering | Planned |
| QA | Existing checks are evidence for current slices; full ticket criteria remain pending |
| Deployment | Current local snapshot; verify ticket-specific hosted rollout and configuration |
| Business acceptance | Pending client review; no signed acceptance recorded |
| Owner | Operations Lead + Voice/Media Lead + Backend Lead (proposed role; named person unassigned) |
| Priority / phase | Must / P1 pilot, P2 scale |
| Estimate | TBD after scope/architecture agreement; no delivery date committed |
| Dependencies | [EVN-VOX-101](../../04-telephone-voice-language/tickets/EVN-VOX-101.md), [EVN-ONB-101](../../01-onboarding-tenancy-identity/tickets/EVN-ONB-101.md), [EVN-ONB-102](../../01-onboarding-tenancy-identity/tickets/EVN-ONB-102.md), [EVN-AIQ-102](../../03-ai-governance-evaluation/tickets/EVN-AIQ-102.md) |

## Business deliverable

Shared multi-client operator desk. A shared EverOnn operator team serves many clients from one multi-client desk.

The client accepts the demonstrated outcome and evidence, rather than the existence of a route, table or screen. This ticket does not certify the whole source requirement as complete.

## Current implemented slice

- [ ] The tenant dashboard is not a multi-client Live Agent Desk.

The current statement describes prerequisites or context; this business deliverable has not been demonstrated.

## Remaining delivery checklist

- [ ] Deliver grant-filtered queues, operator identity/presence, routing, pilot staffing and separate scale gates.

## Technical component

- [ ] Implement the module boundary and contracts for: OperatorDirectory, router, offer protocol and realtime gateway.
- [ ] Maintain tenant boundaries, explicit state transitions, access policy and failure handling for the delivered workflow.
- [ ] Resolve applicable architecture decisions before committing to a new provider or infrastructure baseline.

## DB

Existing module persistence: Basic tenant conversation handoff status and transfer-number facts only; no managed desk domain.

The following records/contracts are proposed or require extension; their names are planning terms, not assertions that production tables exist.

- [ ] operators, client_grants, offers, interactions.
- [ ] Review scope keys, uniqueness, indexes, retention and migration compatibility; backfill safely and preserve existing tenant records.

## UI

- [ ] Multi-client queue, active workspace and roster.
- [ ] Provide loading, empty, validation, permission-denied and recoverable failure states with keyboard and mobile access.
- [ ] Show observed facts and pending states accurately; do not present estimates, configured flags or mock results as confirmed business actions.

## Translate - business-to-technical mapping

| Business rule / outcome | Technical responsibility | Evidence needed |
| --- | --- | --- |
| Shared multi-client operator desk. A shared EverOnn operator team serves many clients from one multi-client desk. | OperatorDirectory, router, offer protocol and realtime gateway | Tenant-scoped end-to-end demonstration of the outcome |
| Deliver grant-filtered queues, operator identity/presence, routing, pilot staffing and separate scale gates. | operators, client_grants, offers, interactions; Multi-client queue, active workspace and roster | Migration/contracts, visible state and failure-path evidence |
| Safe, truthful AI behaviour where applicable | Copilot suggestions cannot own routing or accept offers | Approved context, verified side-effect receipts and evaluation results or justified N/A |
| Client can approve delivery | QA report, rollout evidence and named acceptance owner | Evidence links and dated client sign-off |

This section means requirements-to-implementation mapping. It does not mean language translation; source language obligations are tracked in their own requirements.

## Backend services

- [ ] OperatorDirectory, router, offer protocol and realtime gateway.
- [ ] Define request/response/event schemas, authorisation and input validation for each affected operation.
- [ ] For writes and provider effects, define idempotency, retry/timeout, receipts and reconciliation; document N/A where no side effects exist.
- [ ] Expose actionable status and scoped logs without secrets; distinguish completed, failed and uncertain outcomes.

## AI component

- [ ] Copilot suggestions cannot own routing or accept offers.
- [ ] Record instruction/knowledge/tool versions, measured quality, tenant scope, cost and safe fallback; a Markdown standard alone is not a passed evaluation.

## Testing / QA

- [ ] Exercise the intended user journey with real tenant-scoped state; cover forbidden role and cross-tenant requests.
- [ ] Test malformed inputs, provider failure, retries/replays and cancellation as applicable; keep deterministic mocks separate from live-provider evidence.
- [ ] Review desktop/mobile accessibility, factual copy and failure recovery in the delivered UI.
- [ ] Attach test environment, code/config/instruction versions, results and remaining defects to the acceptance report.

| Source test | Scenario | Required pass criteria | Current disposition |
| --- | --- | --- | --- |
| [AT-29](../../../requirements/AT.md#at-29) | Multi-client screen-pop: three different clients' escalations in sequence | For each: client name, line label, greeting, caller, reason and captured details appear within 500 ms (p95); the operator greets in the right client's name; the operator hears the private announcement and the caller does not | Full source scenario not evidenced; client acceptance pending |
| [AT-34](../../../requirements/AT.md#at-34) | No operator accepts in time, and simultaneous acceptance | Cascade proceeds (next operator, then owner, then message capture with a promised callback); two simultaneous acceptances result in exactly one assignment | Full source scenario not evidenced; client acceptance pending |

Source stories: [US-021](../../../requirements/US.md#us-021).

## Deployment

- [ ] Confirm approved hosting/database/provider architecture and required credentials in the deployment environment.
- [ ] Apply compatible migrations/configuration in staging, rehearse rollback, then promote the reviewed artifact.
- [ ] Verify the actual hosted workflow, monitoring, fallback and customer-visible errors after release.
- [ ] Update CODE_PROFILE.md, PROJECT_DATA_FLOW.md and CLIENT_TECHNICAL_QA.md in the application when behaviour or architecture changes.
- [ ] Record deployment identity, operator, timestamp and rollback evidence; document-only tickets instead record the reviewed Git commit.

## Source traceability

| Source ID | Mapping basis | Source section |
| --- | --- | --- |
| [AT-29](../../../requirements/AT.md#at-29) | Source-linked | 25.2 Acceptance tests |
| [AT-34](../../../requirements/AT.md#at-34) | Source-linked | 25.2 Acceptance tests |
| [BO-4](../../../requirements/BO.md#bo-4) | Source-linked | 3.1 Business objectives |
| [BR-026](../../../requirements/BR.md#br-026) | Source-linked | 7.5 Human operations and the Live Agent Desk |
| [BRL-019](../../../requirements/BRL.md#brl-019) | Plan allocation / source cross-reference | 8. Business rules |
| [DSK-001](../../../requirements/DSK.md#dsk-001) | Source-linked | 16.4.1 Multi-client operations |
| [DSK-002](../../../requirements/DSK.md#dsk-002) | Source-linked | 16.4.1 Multi-client operations |
| [DSK-014](../../../requirements/DSK.md#dsk-014) | Source-linked | 16.4.4 Handling the interaction |
| [DSK-018](../../../requirements/DSK.md#dsk-018) | Source-linked | 16.4.5 Offers, routing behavior and wrap-up |
| [HIL-005](../../../requirements/HIL.md#hil-005) | Source-linked | 16.3 Escalation, routing and service levels (HIL) |
| [US-021](../../../requirements/US.md#us-021) | Source-linked | EP-05 Human operations and the Live Agent Desk |

Read every allocated record, including its continuation bullets and source variants. Source-linked rows preserve explicit document relationships; plan allocations are implementation responsibility assignments created during this review.

## Allocated specification checklist

The unchecked source obligations below require requirement-level evidence. They are deliberately separate from checked statements about current implemented slices. Read linked continuation bullets and additional source wording before accepting a record.

- [ ] [BRL-019](../../../requirements/BRL.md#brl-019): BRL-019 | An operator completes client-specific training before receiving access to that client. | Operators | DSK-002.
- [ ] [DSK-001](../../../requirements/DSK.md#dsk-001): DSK-001 [P1] MUST provide one unified queue across clients: pending and active voice offers, chats, SMS threads, callbacks, approvals and knowledge gaps for every client the operator is granted, each item showing the client name (with a brand color chip), line label, channel, severity, waiting time and service-level countdown, and language. Sort by severity then deadline; filter by client, channel, severity and language. An operator never sees items for clients they are not granted.
- [ ] [DSK-002](../../../requirements/DSK.md#dsk-002): DSK-002 [P1] MUST implement the client roster and grants: an operator is granted access per client (or per client group, vertical or brand) with skills, certification date and optional expiry. A grant is required both for routing to the operator and for seeing any client data. Granting requires the client-specific training checklist to be recorded as complete (BRL-019). Revocation takes effect within five seconds, including for interactions already open (the operator is moved out and the interaction re-routed). Every grant, change and revocation is audited.
- [ ] [DSK-014](../../../requirements/DSK.md#dsk-014): DSK-014 [P1] MUST manage presence and capacity: statuses (available, on a call, wrap-up, away, break, offline); capacity-based routing; automatic away after a configurable number of missed offers; shift start checks (microphone and network test, review of client notices); break approval by a lead at P2.
- [ ] [DSK-018](../../../requirements/DSK.md#dsk-018): DSK-018 [P1] MUST implement offer, ring and cascade behavior: offers expire after a configurable time (default 15 seconds); strategies include longest-idle and skills-first (ring-all-eligible at P2); the first acceptance wins through an atomic assignment; a decline or timeout moves to the next operator per the cascade; when no operator accepts within the service level the cascade continues (overflow pool, then the client's owner, then message capture with a promised callback and repeated alerts for emergencies). While the caller waits they hear branded hold messages, an offer to leave a message, and periodic updates. Every step is logged with timestamps.
- [ ] [HIL-005](../../../requirements/HIL.md#hil-005): HIL-005 [P1] MUST perform all human handling of voice, chat and SMS escalations through the Live Agent Desk (§16.4), so that client identification, data masking, authority checks, audit, metering and quality review always apply. Operators MUST NOT handle client interactions through personal phones, email or shared inboxes, except the documented telephone fallback in DSK-011.

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
