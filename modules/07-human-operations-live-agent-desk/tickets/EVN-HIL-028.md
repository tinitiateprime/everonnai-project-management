# EVN-HIL-028 - No client mix-ups

Project: EverOnnAI. Module: [Human escalation and the multi-client Live Agent Desk](../README.md). Source business requirement [BR-028](../../../requirements/BR.md#br-028).

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

No client mix-ups. Operators cannot mix up clients: one client context per interaction, always-visible client identity and no cross-client data.

The client accepts the demonstrated outcome and evidence, rather than the existence of a route, table or screen. This ticket does not certify the whole source requirement as complete.

## Current implemented slice

- [ ] Tenant API guards exist; operator grants and client locks do not.

The current statement describes prerequisites or context; this business deliverable has not been demonstrated.

## Remaining delivery checklist

- [ ] Enforce per-client grants, one context per interaction, masking and wrong-client incident reporting.

## Technical component

- [ ] Implement the module boundary and contracts for: Grant enforcement, client-bound command tokens and validation.
- [ ] Maintain tenant boundaries, explicit state transitions, access policy and failure handling for the delivered workflow.
- [ ] Resolve applicable architecture decisions before committing to a new provider or infrastructure baseline.

## DB

Existing module persistence: Basic tenant conversation handoff status and transfer-number facts only; no managed desk domain.

The following records/contracts are proposed or require extension; their names are planning terms, not assertions that production tables exist.

- [ ] client_grants, interactions, desk_audit.
- [ ] Review scope keys, uniqueness, indexes, retention and migration compatibility; backfill safely and preserve existing tenant records.

## UI

- [ ] Client lock, masked context and wrong-client control.
- [ ] Provide loading, empty, validation, permission-denied and recoverable failure states with keyboard and mobile access.
- [ ] Show observed facts and pending states accurately; do not present estimates, configured flags or mock results as confirmed business actions.

## Translate - business-to-technical mapping

| Business rule / outcome | Technical responsibility | Evidence needed |
| --- | --- | --- |
| No client mix-ups. Operators cannot mix up clients: one client context per interaction, always-visible client identity and no cross-client data. | Grant enforcement, client-bound command tokens and validation | Tenant-scoped end-to-end demonstration of the outcome |
| Enforce per-client grants, one context per interaction, masking and wrong-client incident reporting. | client_grants, interactions, desk_audit; Client lock, masked context and wrong-client control | Migration/contracts, visible state and failure-path evidence |
| Safe, truthful AI behaviour where applicable | Bind model/tool context to one client and conversation | Approved context, verified side-effect receipts and evaluation results or justified N/A |
| Client can approve delivery | QA report, rollout evidence and named acceptance owner | Evidence links and dated client sign-off |

This section means requirements-to-implementation mapping. It does not mean language translation; source language obligations are tracked in their own requirements.

## Backend services

- [ ] Grant enforcement, client-bound command tokens and validation.
- [ ] Define request/response/event schemas, authorisation and input validation for each affected operation.
- [ ] For writes and provider effects, define idempotency, retry/timeout, receipts and reconciliation; document N/A where no side effects exist.
- [ ] Expose actionable status and scoped logs without secrets; distinguish completed, failed and uncertain outcomes.

## AI component

- [ ] Bind model/tool context to one client and conversation.
- [ ] Record instruction/knowledge/tool versions, measured quality, tenant scope, cost and safe fallback; a Markdown standard alone is not a passed evaluation.

## Testing / QA

- [ ] Exercise the intended user journey with real tenant-scoped state; cover forbidden role and cross-tenant requests.
- [ ] Test malformed inputs, provider failure, retries/replays and cancellation as applicable; keep deterministic mocks separate from live-provider evidence.
- [ ] Review desktop/mobile accessibility, factual copy and failure recovery in the delivered UI.
- [ ] Attach test environment, code/config/instruction versions, results and remaining defects to the acceptance report.

| Source test | Scenario | Required pass criteria | Current disposition |
| --- | --- | --- | --- |
| [AT-30](../../../requirements/AT.md#at-30) | Call arrives on a line that cannot be resolved | Desk shows UNKNOWN LINE, no client data and only the neutral greeting; a support incident is opened; the router did not guess | Full source scenario not evidenced; client acceptance pending |
| [AT-32](../../../requirements/AT.md#at-32) | Client isolation on the desk | An operator without a grant sees nothing for that client; simultaneous chats are separately labeled; attaching data across clients is rejected; a revoked grant removes access within 5 seconds; the wrong-client control logs and re-routes | Full source scenario not evidenced; client acceptance pending |

Source stories: [US-022](../../../requirements/US.md#us-022), [US-023](../../../requirements/US.md#us-023), [US-026](../../../requirements/US.md#us-026), [US-029](../../../requirements/US.md#us-029).

## Deployment

- [ ] Confirm approved hosting/database/provider architecture and required credentials in the deployment environment.
- [ ] Apply compatible migrations/configuration in staging, rehearse rollback, then promote the reviewed artifact.
- [ ] Verify the actual hosted workflow, monitoring, fallback and customer-visible errors after release.
- [ ] Update CODE_PROFILE.md, PROJECT_DATA_FLOW.md and CLIENT_TECHNICAL_QA.md in the application when behaviour or architecture changes.
- [ ] Record deployment identity, operator, timestamp and rollback evidence; document-only tickets instead record the reviewed Git commit.

## Source traceability

| Source ID | Mapping basis | Source section |
| --- | --- | --- |
| [AT-30](../../../requirements/AT.md#at-30) | Source-linked | 25.2 Acceptance tests |
| [AT-32](../../../requirements/AT.md#at-32) | Source-linked | 25.2 Acceptance tests |
| [BO-4](../../../requirements/BO.md#bo-4) | Source-linked | 3.1 Business objectives |
| [BO-7](../../../requirements/BO.md#bo-7) | Source-linked | 3.1 Business objectives |
| [BR-028](../../../requirements/BR.md#br-028) | Source-linked | 7.5 Human operations and the Live Agent Desk |
| [BRL-009](../../../requirements/BRL.md#brl-009) | Plan allocation / source cross-reference | 8. Business rules |
| [BRL-010](../../../requirements/BRL.md#brl-010) | Plan allocation / source cross-reference | 8. Business rules |
| [BRL-015](../../../requirements/BRL.md#brl-015) | Plan allocation / source cross-reference | 8. Business rules |
| [DSK-003](../../../requirements/DSK.md#dsk-003) | Source-linked | 16.4.1 Multi-client operations |
| [DSK-009](../../../requirements/DSK.md#dsk-009) | Source-linked | 16.4.3 Client context and authority |
| [DSK-010](../../../requirements/DSK.md#dsk-010) | Source-linked | 16.4.3 Client context and authority |
| [HIL-013](../../../requirements/HIL.md#hil-013) | Plan allocation / source cross-reference | 16.5 Quality, learning and control of the human layer |
| [TEN-001](../../../requirements/TEN.md#ten-001) | Source-linked | 12.3 Tenancy model requirements |
| [US-022](../../../requirements/US.md#us-022) | Source-linked | EP-05 Human operations and the Live Agent Desk |
| [US-023](../../../requirements/US.md#us-023) | Source-linked | EP-05 Human operations and the Live Agent Desk |
| [US-026](../../../requirements/US.md#us-026) | Source-linked | EP-05 Human operations and the Live Agent Desk |
| [US-029](../../../requirements/US.md#us-029) | Source-linked | EP-05 Human operations and the Live Agent Desk |

Read every allocated record, including its continuation bullets and source variants. Source-linked rows preserve explicit document relationships; plan allocations are implementation responsibility assignments created during this review.

## Allocated specification checklist

The unchecked source obligations below require requirement-level evidence. They are deliberately separate from checked statements about current implemented slices. Read linked continuation bullets and additional source wording before accepting a record.

- [ ] [BRL-009](../../../requirements/BRL.md#brl-009): BRL-009 | An operator greets a caller only in the name of the client identified by the dialed line. If the line is unknown, only a neutral greeting is used. | Operators | DSK-003, DSK-004, DSK-006.
- [ ] [BRL-010](../../../requirements/BRL.md#brl-010): BRL-010 | An operator sees and uses only the data of the client for the interaction being handled, one client context at a time per interaction. | Operators | DSK-009, DSK-010, TEN-001.
- [ ] [BRL-015](../../../requirements/BRL.md#brl-015): BRL-015 | One client's data is never used to answer another client's callers or to build another client's site. | Platform | TEN-001, TEN-004, KNW-004.
- [ ] [DSK-003](../../../requirements/DSK.md#dsk-003): DSK-003 [P1] MUST perform line identification: each inbound leg is resolved to tenant_id and line_id from the dialed number and the carrier's signaling (the To, Diversion and History-Info headers and provider metadata), cross-checked against the number registry. The resolved line label (for example "Acme Locksmith, after-hours emergency line") travels with the escalation. If the line cannot be resolved with confidence (unknown number, ambiguous forwarding chain, inconsistent headers), the desk MUST show a prominent UNKNOWN LINE state, hide all client data, offer only a neutral greeting ("Thank you for calling, how can I help?"), and open a support incident. The system MUST NOT guess the client.
- [ ] [DSK-009](../../../requirements/DSK.md#dsk-009): DSK-009 [P1] MUST prevent client mix-ups through a client lock: each active interaction has exactly one client context, shown persistently in the header, in every panel, in the browser tab title and, for voice, in the operator-only announcement. When an operator has several interactions open, each is color- and name-coded, and switching shows a visible client-change confirmation. The desk never displays data of two clients in one panel, and the server rejects any action that would attach data from one client to another client's interaction. A one-tap "wrong client" control logs the event and re-routes. Wrong-client incidents (from the operator control, quality findings, or a caller correcting the greeting) are counted and alerted; the target is under 0.1% of interactions.
- [ ] [DSK-010](../../../requirements/DSK.md#dsk-010): DSK-010 [P1] MUST apply data minimization and masking: the operator sees only fields the client has made visible to operators; sensitive tokens (card numbers, government identifiers) are masked; revealing a masked value requires a reason and is logged; bulk export or listing of contacts is not possible from the desk. A session watermark showing the operator id is a P2 option.
- [ ] [HIL-013](../../../requirements/HIL.md#hil-013): HIL-013 [P1] MUST apply operator security controls (minimum set at P1, full set at P2): least-privilege access (only assigned tenants and only the fields needed), MFA, device posture checks, session recording of console actions (not customer audio beyond policy), NDA/training attestation tracking, IP allow-listing for pooled operators, and automatic access expiry at shift end. Operators MUST NOT be able to export bulk data.
- [ ] [TEN-001](../../../requirements/TEN.md#ten-001): TEN-001 [P0] MUST use a shared-schema, tenant_id-keyed model in MariaDB for P1 and P2, with these guarantees:.

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
