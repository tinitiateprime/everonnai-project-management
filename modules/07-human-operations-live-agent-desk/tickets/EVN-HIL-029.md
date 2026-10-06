# EVN-HIL-029 - Operator authority per client

Project: EverOnnAI. Module: [Human escalation and the multi-client Live Agent Desk](../README.md). Source business requirement [BR-029](../../../requirements/BR.md#br-029).

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

Operator authority per client. Each client defines what operators may and may not do or promise on their behalf.

The client accepts the demonstrated outcome and evidence, rather than the existence of a route, table or screen. This ticket does not certify the whole source requirement as complete.

## Current implemented slice

- [ ] No operator authority matrix is implemented.

The current statement describes prerequisites or context; this business deliverable has not been demonstrated.

## Remaining delivery checklist

- [ ] Store allowed/approval-required/prohibited actions, version approvals and enforce UI/server commands.

## Technical component

- [ ] Implement the module boundary and contracts for: Policy/ApprovalService with expiry and audit.
- [ ] Maintain tenant boundaries, explicit state transitions, access policy and failure handling for the delivered workflow.
- [ ] Resolve applicable architecture decisions before committing to a new provider or infrastructure baseline.

## DB

Existing module persistence: Basic tenant conversation handoff status and transfer-number facts only; no managed desk domain.

The following records/contracts are proposed or require extension; their names are planning terms, not assertions that production tables exist.

- [ ] authority_versions, action_approvals.
- [ ] Review scope keys, uniqueness, indexes, retention and migration compatibility; backfill safely and preserve existing tenant records.

## UI

- [ ] Authority matrix and disabled/approval-labelled controls.
- [ ] Provide loading, empty, validation, permission-denied and recoverable failure states with keyboard and mobile access.
- [ ] Show observed facts and pending states accurately; do not present estimates, configured flags or mock results as confirmed business actions.

## Translate - business-to-technical mapping

| Business rule / outcome | Technical responsibility | Evidence needed |
| --- | --- | --- |
| Operator authority per client. Each client defines what operators may and may not do or promise on their behalf. | Policy/ApprovalService with expiry and audit | Tenant-scoped end-to-end demonstration of the outcome |
| Store allowed/approval-required/prohibited actions, version approvals and enforce UI/server commands. | authority_versions, action_approvals; Authority matrix and disabled/approval-labelled controls | Migration/contracts, visible state and failure-path evidence |
| Safe, truthful AI behaviour where applicable | AI drafts sensitive actions; server authority gates execution | Approved context, verified side-effect receipts and evaluation results or justified N/A |
| Client can approve delivery | QA report, rollout evidence and named acceptance owner | Evidence links and dated client sign-off |

This section means requirements-to-implementation mapping. It does not mean language translation; source language obligations are tracked in their own requirements.

## Backend services

- [ ] Policy/ApprovalService with expiry and audit.
- [ ] Define request/response/event schemas, authorisation and input validation for each affected operation.
- [ ] For writes and provider effects, define idempotency, retry/timeout, receipts and reconciliation; document N/A where no side effects exist.
- [ ] Expose actionable status and scoped logs without secrets; distinguish completed, failed and uncertain outcomes.

## AI component

- [ ] AI drafts sensitive actions.
- [ ] server authority gates execution.
- [ ] Record instruction/knowledge/tool versions, measured quality, tenant scope, cost and safe fallback; a Markdown standard alone is not a passed evaluation.

## Testing / QA

- [ ] Exercise the intended user journey with real tenant-scoped state; cover forbidden role and cross-tenant requests.
- [ ] Test malformed inputs, provider failure, retries/replays and cancellation as applicable; keep deterministic mocks separate from live-provider evidence.
- [ ] Review desktop/mobile accessibility, factual copy and failure recovery in the delivered UI.
- [ ] Attach test environment, code/config/instruction versions, results and remaining defects to the acceptance report.

| Source test | Scenario | Required pass criteria | Current disposition |
| --- | --- | --- | --- |
| [AT-31](../../../requirements/AT.md#at-31) | Operator attempts an action outside the client's authority | Control disabled or approval requested; the server rejects a direct command; the owner's decision flows back to the desk | Full source scenario not evidenced; client acceptance pending |

Source stories: [US-008](../../../requirements/US.md#us-008), [US-009](../../../requirements/US.md#us-009), [US-024](../../../requirements/US.md#us-024).

## Deployment

- [ ] Confirm approved hosting/database/provider architecture and required credentials in the deployment environment.
- [ ] Apply compatible migrations/configuration in staging, rehearse rollback, then promote the reviewed artifact.
- [ ] Verify the actual hosted workflow, monitoring, fallback and customer-visible errors after release.
- [ ] Update CODE_PROFILE.md, PROJECT_DATA_FLOW.md and CLIENT_TECHNICAL_QA.md in the application when behaviour or architecture changes.
- [ ] Record deployment identity, operator, timestamp and rollback evidence; document-only tickets instead record the reviewed Git commit.

## Source traceability

| Source ID | Mapping basis | Source section |
| --- | --- | --- |
| [AT-31](../../../requirements/AT.md#at-31) | Source-linked | 25.2 Acceptance tests |
| [BO-3](../../../requirements/BO.md#bo-3) | Source-linked | 3.1 Business objectives |
| [BO-4](../../../requirements/BO.md#bo-4) | Source-linked | 3.1 Business objectives |
| [BR-029](../../../requirements/BR.md#br-029) | Source-linked | 7.5 Human operations and the Live Agent Desk |
| [BRL-002](../../../requirements/BRL.md#brl-002) | Plan allocation / source cross-reference | 8. Business rules |
| [BRL-003](../../../requirements/BRL.md#brl-003) | Plan allocation / source cross-reference | 8. Business rules |
| [BRL-011](../../../requirements/BRL.md#brl-011) | Plan allocation / source cross-reference | 8. Business rules |
| [DSK-008](../../../requirements/DSK.md#dsk-008) | Source-linked | 16.4.3 Client context and authority |
| [HIL-007](../../../requirements/HIL.md#hil-007) | Source-linked | 16.3 Escalation, routing and service levels (HIL) |
| [US-008](../../../requirements/US.md#us-008) | Source-linked | EP-02 Knowledge and agent control |
| [US-009](../../../requirements/US.md#us-009) | Source-linked | EP-02 Knowledge and agent control |
| [US-024](../../../requirements/US.md#us-024) | Source-linked | EP-05 Human operations and the Live Agent Desk |

Read every allocated record, including its continuation bullets and source variants. Source-linked rows preserve explicit document relationships; plan allocations are implementation responsibility assignments created during this review.

## Allocated specification checklist

The unchecked source obligations below require requirement-level evidence. They are deliberately separate from checked statements about current implemented slices. Read linked continuation bullets and additional source wording before accepting a record.

- [ ] [BRL-002](../../../requirements/BRL.md#brl-002): BRL-002 | No price is quoted unless the client's pricing policy permits it. The default is never to quote. | AI agents, operators | POL-001, DSK-008, AGT-003.
- [ ] [BRL-003](../../../requirements/BRL.md#brl-003): BRL-003 | No arrival time or availability is promised unless dispatch or calendar data supports it. | AI agents, operators | POL-001, DSK-008.
- [ ] [BRL-011](../../../requirements/BRL.md#brl-011): BRL-011 | Operators act only within the client's authority matrix; anything beyond it requires the owner's approval. | Operators | DSK-008, HIL-007.
- [ ] [DSK-008](../../../requirements/DSK.md#dsk-008): DSK-008 [P1] MUST enforce the client's authority matrix: for each capability the client sets one of allowed, requires owner approval or not allowed (quote a price, commit an arrival time, book an appointment, dispatch a technician, take payment by link, cancel or reschedule, share technician details, grant an exception). The desk disables or annotates controls accordingly, routes approvals through HIL-007, and the server enforces the same rules. Changes are versioned and audited. Defaults are conservative.
- [ ] [HIL-007](../../../requirements/HIL.md#hil-007): HIL-007 [P1] MUST implement approval workflows for sensitive actions that the AI drafts but must not execute alone (per tenant policy): sending a price, confirming a dispatch ETA, issuing a refund credit, sending a bulk message, modifying an existing appointment. Approvers can be owner, staff or operator; approvals are logged.

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
