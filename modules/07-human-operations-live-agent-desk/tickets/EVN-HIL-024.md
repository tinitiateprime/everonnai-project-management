# EVN-HIL-024 - Always able to reach a human

Project: EverOnnAI. Module: [Human escalation and the multi-client Live Agent Desk](../README.md). Source business requirement [BR-024](../../../requirements/BR.md#br-024).

| Tracking dimension | Disposition |
| --- | --- |
| Engineering | Partial |
| QA | Existing checks are evidence for current slices; full ticket criteria remain pending |
| Deployment | Current local snapshot; verify ticket-specific hosted rollout and configuration |
| Business acceptance | Pending client review; no signed acceptance recorded |
| Owner | Operations Lead + Voice/Media Lead + Backend Lead (proposed role; named person unassigned) |
| Priority / phase | Must / P1 |
| Estimate | TBD after scope/architecture agreement; no delivery date committed |
| Dependencies | [EVN-VOX-101](../../04-telephone-voice-language/tickets/EVN-VOX-101.md), [EVN-ONB-101](../../01-onboarding-tenancy-identity/tickets/EVN-ONB-101.md), [EVN-ONB-102](../../01-onboarding-tenancy-identity/tickets/EVN-ONB-102.md), [EVN-AIQ-102](../../03-ai-governance-evaluation/tickets/EVN-AIQ-102.md) |

## Business deliverable

Always able to reach a human. A caller can always reach a human or is guaranteed a callback; no caller is trapped with the AI.

The client accepts the demonstrated outcome and evidence, rather than the existence of a route, table or screen. This ticket does not certify the whole source requirement as complete.

## Current implemented slice

- [x] Safety text can recommend emergency services or a human; guaranteed takeover is absent.

## Remaining delivery checklist

- [ ] Guarantee transfer or an acknowledged callback within one turn, including no-answer/no-operator cases.

## Technical component

- [ ] Implement the module boundary and contracts for: EscalationRouter, warm transfer and safe message capture.
- [ ] Maintain tenant boundaries, explicit state transitions, access policy and failure handling for the delivered workflow.
- [ ] Resolve applicable architecture decisions before committing to a new provider or infrastructure baseline.

## DB

Existing module persistence: Basic tenant conversation handoff status and transfer-number facts only; no managed desk domain.

The following records/contracts are proposed or require extension; their names are planning terms, not assertions that production tables exist.

- [ ] escalations, callback_tasks, routing_attempts.
- [ ] Review scope keys, uniqueness, indexes, retention and migration compatibility; backfill safely and preserve existing tenant records.

## UI

- [ ] Reach-a-person, callback SLA and outcome.
- [ ] Provide loading, empty, validation, permission-denied and recoverable failure states with keyboard and mobile access.
- [ ] Show observed facts and pending states accurately; do not present estimates, configured flags or mock results as confirmed business actions.

## Translate - business-to-technical mapping

| Business rule / outcome | Technical responsibility | Evidence needed |
| --- | --- | --- |
| Always able to reach a human. A caller can always reach a human or is guaranteed a callback; no caller is trapped with the AI. | EscalationRouter, warm transfer and safe message capture | Tenant-scoped end-to-end demonstration of the outcome |
| Guarantee transfer or an acknowledged callback within one turn, including no-answer/no-operator cases. | escalations, callback_tasks, routing_attempts; Reach-a-person, callback SLA and outcome | Migration/contracts, visible state and failure-path evidence |
| Safe, truthful AI behaviour where applicable | Person requests override ordinary conversation; no loops or false promises | Approved context, verified side-effect receipts and evaluation results or justified N/A |
| Client can approve delivery | QA report, rollout evidence and named acceptance owner | Evidence links and dated client sign-off |

This section means requirements-to-implementation mapping. It does not mean language translation; source language obligations are tracked in their own requirements.

## Backend services

- [ ] EscalationRouter, warm transfer and safe message capture.
- [ ] Define request/response/event schemas, authorisation and input validation for each affected operation.
- [ ] For writes and provider effects, define idempotency, retry/timeout, receipts and reconciliation; document N/A where no side effects exist.
- [ ] Expose actionable status and scoped logs without secrets; distinguish completed, failed and uncertain outcomes.

## AI component

- [ ] Person requests override ordinary conversation.
- [ ] no loops or false promises.
- [ ] Record instruction/knowledge/tool versions, measured quality, tenant scope, cost and safe fallback; a Markdown standard alone is not a passed evaluation.

## Testing / QA

- [ ] Exercise the intended user journey with real tenant-scoped state; cover forbidden role and cross-tenant requests.
- [ ] Test malformed inputs, provider failure, retries/replays and cancellation as applicable; keep deterministic mocks separate from live-provider evidence.
- [ ] Review desktop/mobile accessibility, factual copy and failure recovery in the delivered UI.
- [ ] Attach test environment, code/config/instruction versions, results and remaining defects to the acceptance report.

| Source test | Scenario | Required pass criteria | Current disposition |
| --- | --- | --- | --- |
| [AT-28](../../../requirements/AT.md#at-28) | Caller says "let me talk to a person" | Live transfer to an available human, or a promise and a scheduled callback within one turn; the caller is never trapped | Full source scenario not evidenced; client acceptance pending |
| [AT-34](../../../requirements/AT.md#at-34) | No operator accepts in time, and simultaneous acceptance | Cascade proceeds (next operator, then owner, then message capture with a promised callback); two simultaneous acceptances result in exactly one assignment | Full source scenario not evidenced; client acceptance pending |

Source stories: [US-020](../../../requirements/US.md#us-020).

## Deployment

- [ ] Confirm approved hosting/database/provider architecture and required credentials in the deployment environment.
- [ ] Apply compatible migrations/configuration in staging, rehearse rollback, then promote the reviewed artifact.
- [ ] Verify the actual hosted workflow, monitoring, fallback and customer-visible errors after release.
- [ ] Update CODE_PROFILE.md, PROJECT_DATA_FLOW.md and CLIENT_TECHNICAL_QA.md in the application when behaviour or architecture changes.
- [ ] Record deployment identity, operator, timestamp and rollback evidence; document-only tickets instead record the reviewed Git commit.

## Source traceability

| Source ID | Mapping basis | Source section |
| --- | --- | --- |
| [AT-28](../../../requirements/AT.md#at-28) | Source-linked | 25.2 Acceptance tests |
| [AT-34](../../../requirements/AT.md#at-34) | Source-linked | 25.2 Acceptance tests |
| [BO-3](../../../requirements/BO.md#bo-3) | Source-linked | 3.1 Business objectives |
| [BR-024](../../../requirements/BR.md#br-024) | Source-linked | 7.5 Human operations and the Live Agent Desk |
| [BRL-005](../../../requirements/BRL.md#brl-005) | Plan allocation / source cross-reference | 8. Business rules |
| [HIL-003](../../../requirements/HIL.md#hil-003) | Source-linked | 16.3 Escalation, routing and service levels (HIL) |
| [HIL-004](../../../requirements/HIL.md#hil-004) | Source-linked | 16.3 Escalation, routing and service levels (HIL) |
| [HIL-016](../../../requirements/HIL.md#hil-016) | Plan allocation / source cross-reference | 16.3 Escalation, routing and service levels (HIL) |
| [SCF-010](../../../requirements/SCF.md#scf-010) | Plan allocation / source cross-reference | 22.3 Scaffolding checklist |
| [SCF-011](../../../requirements/SCF.md#scf-011) | Plan allocation / source cross-reference | 22.3 Scaffolding checklist |
| [SL-05](../../../requirements/SL.md#sl-05) | Plan allocation / source cross-reference | 10.1 Service levels |
| [US-020](../../../requirements/US.md#us-020) | Source-linked | EP-05 Human operations and the Live Agent Desk |
| [VOX-009](../../../requirements/VOX.md#vox-009) | Source-linked | 14.4 Requirements: real-time conversation quality |
| [VOX-019](../../../requirements/VOX.md#vox-019) | Plan allocation / source cross-reference | 14.5 Requirements: business behavior |

Read every allocated record, including its continuation bullets and source variants. Source-linked rows preserve explicit document relationships; plan allocations are implementation responsibility assignments created during this review.

## Allocated specification checklist

The unchecked source obligations below require requirement-level evidence. They are deliberately separate from checked statements about current implemented slices. Read linked continuation bullets and additional source wording before accepting a record.

- [ ] [BRL-005](../../../requirements/BRL.md#brl-005): BRL-005 | A caller can always reach a human or is guaranteed a callback. | Platform | HIL-003, HIL-016, VOX-009.
- [ ] [HIL-003](../../../requirements/HIL.md#hil-003): HIL-003 [P1] MUST guarantee that "I want a person" always produces an outcome: a live transfer if a human is reachable, otherwise a promise-and-capture with a scheduled callback task and SLA. The caller MUST never be trapped in an AI loop.
- [ ] [HIL-004](../../../requirements/HIL.md#hil-004): HIL-004 [P1] MUST support live takeover: a human can join or take over an active chat immediately; for voice, via warm transfer or conference join (listen, whisper to AI, or take over). The AI receives the human's instruction as a privileged context message ("operator whisper") and can continue under supervision.
- [ ] [HIL-016](../../../requirements/HIL.md#hil-016): HIL-016 [P1] SHOULD provide degraded-operator mode: if no human is available within SLA, the system falls back to the safest path (take detailed message, callback task, and clear promise to the caller), and alerts the on-call lead.
- [ ] [SCF-010](../../../requirements/SCF.md#scf-010): 10 | Operator org and identity model (internal and external orgs) | BPO/partner operator pools; follow-the-sun coverage.
- [ ] [SCF-011](../../../requirements/SCF.md#scf-011): 11 | EscalationRouter, OperatorDirectory, ShiftCalendar interfaces with a simple P1 implementation | Skills-based routing, workforce management, overflow pools.
- [ ] [SL-05](../../../requirements/SL.md#sl-05): SL-05 | Escalations to a human | Emergencies: immediate. Urgent: under 60 seconds. Routine requests: within 15 minutes in business hours.
- [ ] [VOX-009](../../../requirements/VOX.md#vox-009): VOX-009 [P1] MUST support DTMF input and output (for example "press 1 to speak to a person") and a universal "I want a person" intent that triggers HIL-003 within one turn.
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
