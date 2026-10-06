# EVN-HIL-027 - Client screen-pop and correct greeting

Project: EverOnnAI. Module: [Human escalation and the multi-client Live Agent Desk](../README.md). Source business requirement [BR-027](../../../requirements/BR.md#br-027).

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

Client screen-pop and correct greeting. When a call or chat reaches a human, the operator instantly sees which client it is for, the client's details and instructions, the caller's details, why it escalated and what the AI already captured, and can greet in the client's name.

The client accepts the demonstrated outcome and evidence, rather than the existence of a route, table or screen. This ticket does not certify the whole source requirement as complete.

## Current implemented slice

- [ ] No carrier line resolver or operator screen-pop exists.

The current statement describes prerequisites or context; this business deliverable has not been demonstrated.

## Remaining delivery checklist

- [ ] Resolve line/client from trusted signaling; show context/greeting within 500 ms p95; fail closed on unknown lines.

## Technical component

- [ ] Implement the module boundary and contracts for: LineIdentityResolver, context projection and private briefing audio.
- [ ] Maintain tenant boundaries, explicit state transitions, access policy and failure handling for the delivered workflow.
- [ ] Resolve applicable architecture decisions before committing to a new provider or infrastructure baseline.

## DB

Existing module persistence: Basic tenant conversation handoff status and transfer-number facts only; no managed desk domain.

The following records/contracts are proposed or require extension; their names are planning terms, not assertions that production tables exist.

- [ ] line_registry, context_snapshots, greeting_versions.
- [ ] Review scope keys, uniqueness, indexes, retention and migration compatibility; backfill safely and preserve existing tenant records.

## UI

- [ ] Client banner, offer card and client-only panels.
- [ ] Provide loading, empty, validation, permission-denied and recoverable failure states with keyboard and mobile access.
- [ ] Show observed facts and pending states accurately; do not present estimates, configured flags or mock results as confirmed business actions.

## Translate - business-to-technical mapping

| Business rule / outcome | Technical responsibility | Evidence needed |
| --- | --- | --- |
| Client screen-pop and correct greeting. When a call or chat reaches a human, the operator instantly sees which client it is for, the client's details and instructions, the caller's details, why it escalated and what the AI already captured, and can greet in the client's name. | LineIdentityResolver, context projection and private briefing audio | Tenant-scoped end-to-end demonstration of the outcome |
| Resolve line/client from trusted signaling; show context/greeting within 500 ms p95; fail closed on unknown lines. | line_registry, context_snapshots, greeting_versions; Client banner, offer card and client-only panels | Migration/contracts, visible state and failure-path evidence |
| Safe, truthful AI behaviour where applicable | Approved summary/greeting; never guess client identity | Approved context, verified side-effect receipts and evaluation results or justified N/A |
| Client can approve delivery | QA report, rollout evidence and named acceptance owner | Evidence links and dated client sign-off |

This section means requirements-to-implementation mapping. It does not mean language translation; source language obligations are tracked in their own requirements.

## Backend services

- [ ] LineIdentityResolver, context projection and private briefing audio.
- [ ] Define request/response/event schemas, authorisation and input validation for each affected operation.
- [ ] For writes and provider effects, define idempotency, retry/timeout, receipts and reconciliation; document N/A where no side effects exist.
- [ ] Expose actionable status and scoped logs without secrets; distinguish completed, failed and uncertain outcomes.

## AI component

- [ ] Approved summary/greeting.
- [ ] never guess client identity.
- [ ] Record instruction/knowledge/tool versions, measured quality, tenant scope, cost and safe fallback; a Markdown standard alone is not a passed evaluation.

## Testing / QA

- [ ] Exercise the intended user journey with real tenant-scoped state; cover forbidden role and cross-tenant requests.
- [ ] Test malformed inputs, provider failure, retries/replays and cancellation as applicable; keep deterministic mocks separate from live-provider evidence.
- [ ] Review desktop/mobile accessibility, factual copy and failure recovery in the delivered UI.
- [ ] Attach test environment, code/config/instruction versions, results and remaining defects to the acceptance report.

| Source test | Scenario | Required pass criteria | Current disposition |
| --- | --- | --- | --- |
| [AT-29](../../../requirements/AT.md#at-29) | Multi-client screen-pop: three different clients' escalations in sequence | For each: client name, line label, greeting, caller, reason and captured details appear within 500 ms (p95); the operator greets in the right client's name; the operator hears the private announcement and the caller does not | Full source scenario not evidenced; client acceptance pending |
| [AT-30](../../../requirements/AT.md#at-30) | Call arrives on a line that cannot be resolved | Desk shows UNKNOWN LINE, no client data and only the neutral greeting; a support incident is opened; the router did not guess | Full source scenario not evidenced; client acceptance pending |

Source stories: [US-009](../../../requirements/US.md#us-009), [US-021](../../../requirements/US.md#us-021), [US-022](../../../requirements/US.md#us-022).

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
| [AT-30](../../../requirements/AT.md#at-30) | Source-linked | 25.2 Acceptance tests |
| [BO-3](../../../requirements/BO.md#bo-3) | Source-linked | 3.1 Business objectives |
| [BO-4](../../../requirements/BO.md#bo-4) | Source-linked | 3.1 Business objectives |
| [BR-027](../../../requirements/BR.md#br-027) | Source-linked | 7.5 Human operations and the Live Agent Desk |
| [BRL-009](../../../requirements/BRL.md#brl-009) | Plan allocation / source cross-reference | 8. Business rules |
| [DSK-003](../../../requirements/DSK.md#dsk-003) | Source-linked | 16.4.1 Multi-client operations |
| [DSK-004](../../../requirements/DSK.md#dsk-004) | Source-linked | 16.4.2 Incoming interaction, screen-pop and greeting |
| [DSK-005](../../../requirements/DSK.md#dsk-005) | Source-linked | 16.4.2 Incoming interaction, screen-pop and greeting |
| [DSK-006](../../../requirements/DSK.md#dsk-006) | Source-linked | 16.4.2 Incoming interaction, screen-pop and greeting |
| [DSK-007](../../../requirements/DSK.md#dsk-007) | Source-linked | 16.4.3 Client context and authority |
| [HIL-017](../../../requirements/HIL.md#hil-017) | Source-linked | 16.3 Escalation, routing and service levels (HIL) |
| [SL-06](../../../requirements/SL.md#sl-06) | Plan allocation / source cross-reference | 10.1 Service levels |
| [US-009](../../../requirements/US.md#us-009) | Source-linked | EP-02 Knowledge and agent control |
| [US-021](../../../requirements/US.md#us-021) | Source-linked | EP-05 Human operations and the Live Agent Desk |
| [US-022](../../../requirements/US.md#us-022) | Source-linked | EP-05 Human operations and the Live Agent Desk |
| [VRT-007](../../../requirements/VRT.md#vrt-007) | Plan allocation / source cross-reference | 19.6 Brands and vertical packs (VRT) |

Read every allocated record, including its continuation bullets and source variants. Source-linked rows preserve explicit document relationships; plan allocations are implementation responsibility assignments created during this review.

## Allocated specification checklist

The unchecked source obligations below require requirement-level evidence. They are deliberately separate from checked statements about current implemented slices. Read linked continuation bullets and additional source wording before accepting a record.

- [ ] [BRL-009](../../../requirements/BRL.md#brl-009): BRL-009 | An operator greets a caller only in the name of the client identified by the dialed line. If the line is unknown, only a neutral greeting is used. | Operators | DSK-003, DSK-004, DSK-006.
- [ ] [DSK-003](../../../requirements/DSK.md#dsk-003): DSK-003 [P1] MUST perform line identification: each inbound leg is resolved to tenant_id and line_id from the dialed number and the carrier's signaling (the To, Diversion and History-Info headers and provider metadata), cross-checked against the number registry. The resolved line label (for example "Acme Locksmith, after-hours emergency line") travels with the escalation. If the line cannot be resolved with confidence (unknown number, ambiguous forwarding chain, inconsistent headers), the desk MUST show a prominent UNKNOWN LINE state, hide all client data, offer only a neutral greeting ("Thank you for calling, how can I help?"), and open a support incident. The system MUST NOT guess the client.
- [ ] [DSK-004](../../../requirements/DSK.md#dsk-004): DSK-004 [P1] MUST present a screen-pop offer card at the moment an interaction is offered, with no clicks needed to see who it is for:.
- [ ] [DSK-005](../../../requirements/DSK.md#dsk-005): DSK-005 [P1] MUST support an operator-only announcement for voice: on acceptance, and before the caller is bridged, the operator hears a brief synthesized announcement naming the client and the situation ("Acme Locksmith. Car lockout. Caller Maria. Urgent."), inaudible to the caller. The caller meanwhile hears a short branded hold message ("One moment, I'm connecting you to a team member at Acme Locksmith"). The announcement is on by default for voice and configurable per operator and per client. The audio topology that keeps the announcement private is decided in the Phase 0 spike (§16.7.2).
- [ ] [DSK-006](../../../requirements/DSK.md#dsk-006): DSK-006 [P1] MUST manage greeting scripts per client: per language and per hours mode (business hours, after hours, callback), with variables {client_name}, {operator_first_name}, {line_label}, the spoken name and a phonetic hint, time-of-day variants, an outbound variant ("calling on behalf of {client_name}"), and a "do not say" list. Scripts are versioned and approved by the client (or by EverOnn operations on the client's behalf, recorded). The desk shows the script as copy-ready text with a one-key "greeting delivered" marker that is logged so greeting compliance can be measured. If no script exists, the default is a neutral greeting that includes the client name.
- [ ] [DSK-007](../../../requirements/DSK.md#dsk-007): DSK-007 [P1] MUST provide a client context panel for the active interaction, with collapsible sections that all belong to that one client:.
- [ ] [HIL-017](../../../requirements/HIL.md#hil-017): HIL-017 [P1] MUST carry client identity through every step: every escalation, offer, interaction, note and audit record holds tenant_id and line_id (or channel endpoint id), and no desk screen or API response may present interaction data without them.
- [ ] [SL-06](../../../requirements/SL.md#sl-06): SL-06 | Operator screen shows client identity and greeting | Within 500 ms for 95% of offers.
- [ ] [VRT-007](../../../requirements/VRT.md#vrt-007): VRT-007 [P2] SHOULD provide brand-level defaults for operators (greeting and desk-profile templates, notices) and cross-brand analytics for EverOnn with a brand and vertical filter.

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
