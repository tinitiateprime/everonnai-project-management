# EVN-ADM-070 - Back-office administration

Project: EverOnnAI. Module: [Internal administration, support and incident operations](../README.md). Source business requirement [BR-070](../../../requirements/BR.md#br-070).

| Tracking dimension | Disposition |
| --- | --- |
| Engineering | Planned |
| QA | Existing checks are evidence for current slices; full ticket criteria remain pending |
| Deployment | Current local snapshot; verify ticket-specific hosted rollout and configuration |
| Business acceptance | Pending client review; no signed acceptance recorded |
| Owner | Operations Lead + Security Lead (proposed role; named person unassigned) |
| Priority / phase | Must / P1 |
| Estimate | TBD after scope/architecture agreement; no delivery date committed |
| Dependencies | [EVN-ONB-101](../../01-onboarding-tenancy-identity/tickets/EVN-ONB-101.md), [EVN-SEC-102](../../15-security-privacy-compliance/tickets/EVN-SEC-102.md) |

## Business deliverable

Back-office administration. EverOnn staff can administer clients, numbers, plans, prompts, flags and incidents from a back-office.

The client accepts the demonstrated outcome and evidence, rather than the existence of a route, table or screen. This ticket does not certify the whole source requirement as complete.

## Current implemented slice

- [ ] A business dashboard is not a staff back-office.

The current statement describes prerequisites or context; this business deliverable has not been demonstrated.

## Remaining delivery checklist

- [ ] Build isolated SSO/MFA admin, audited support access, numbers/plans/prompts/flags/incidents and grants.

## Technical component

- [ ] Implement the module boundary and contracts for: AdminPolicy, audited impersonation and privileged operations.
- [ ] Maintain tenant boundaries, explicit state transitions, access policy and failure handling for the delivered workflow.
- [ ] Resolve applicable architecture decisions before committing to a new provider or infrastructure baseline.

## DB

Existing module persistence: No separate staff admin, support impersonation, flag or number-inventory domain.

The following records/contracts are proposed or require extension; their names are planning terms, not assertions that production tables exist.

- [ ] staff_roles, support_sessions, incidents.
- [ ] Review scope keys, uniqueness, indexes, retention and migration compatibility; backfill safely and preserve existing tenant records.

## UI

- [ ] Tenant search, support banner and privileged consoles.
- [ ] Provide loading, empty, validation, permission-denied and recoverable failure states with keyboard and mobile access.
- [ ] Show observed facts and pending states accurately; do not present estimates, configured flags or mock results as confirmed business actions.

## Translate - business-to-technical mapping

| Business rule / outcome | Technical responsibility | Evidence needed |
| --- | --- | --- |
| Back-office administration. EverOnn staff can administer clients, numbers, plans, prompts, flags and incidents from a back-office. | AdminPolicy, audited impersonation and privileged operations | Tenant-scoped end-to-end demonstration of the outcome |
| Build isolated SSO/MFA admin, audited support access, numbers/plans/prompts/flags/incidents and grants. | staff_roles, support_sessions, incidents; Tenant search, support banner and privileged consoles | Migration/contracts, visible state and failure-path evidence |
| Safe, truthful AI behaviour where applicable | Prompt changes need review/evals; prevent cross-customer context | Approved context, verified side-effect receipts and evaluation results or justified N/A |
| Client can approve delivery | QA report, rollout evidence and named acceptance owner | Evidence links and dated client sign-off |

This section means requirements-to-implementation mapping. It does not mean language translation; source language obligations are tracked in their own requirements.

## Backend services

- [ ] AdminPolicy, audited impersonation and privileged operations.
- [ ] Define request/response/event schemas, authorisation and input validation for each affected operation.
- [ ] For writes and provider effects, define idempotency, retry/timeout, receipts and reconciliation; document N/A where no side effects exist.
- [ ] Expose actionable status and scoped logs without secrets; distinguish completed, failed and uncertain outcomes.

## AI component

- [ ] Prompt changes need review/evals.
- [ ] prevent cross-customer context.
- [ ] Record instruction/knowledge/tool versions, measured quality, tenant scope, cost and safe fallback; a Markdown standard alone is not a passed evaluation.

## Testing / QA

- [ ] Exercise the intended user journey with real tenant-scoped state; cover forbidden role and cross-tenant requests.
- [ ] Test malformed inputs, provider failure, retries/replays and cancellation as applicable; keep deterministic mocks separate from live-provider evidence.
- [ ] Review desktop/mobile accessibility, factual copy and failure recovery in the delivered UI.
- [ ] Attach test environment, code/config/instruction versions, results and remaining defects to the acceptance report.

| Source test | Scenario | Required pass criteria | Current disposition |
| --- | --- | --- | --- |
| [AT-58](../../../requirements/AT.md#at-58) | Administration and incident controls | Support finds a client, replays a call and impersonates with a visible banner; kill switch and vendor failover work | Full source scenario not evidenced; client acceptance pending |

Source stories: [US-044](../../../requirements/US.md#us-044), [US-045](../../../requirements/US.md#us-045).

## Deployment

- [ ] Confirm approved hosting/database/provider architecture and required credentials in the deployment environment.
- [ ] Apply compatible migrations/configuration in staging, rehearse rollback, then promote the reviewed artifact.
- [ ] Verify the actual hosted workflow, monitoring, fallback and customer-visible errors after release.
- [ ] Update CODE_PROFILE.md, PROJECT_DATA_FLOW.md and CLIENT_TECHNICAL_QA.md in the application when behaviour or architecture changes.
- [ ] Record deployment identity, operator, timestamp and rollback evidence; document-only tickets instead record the reviewed Git commit.

## Source traceability

| Source ID | Mapping basis | Source section |
| --- | --- | --- |
| [ADM-001](../../../requirements/ADM.md#adm-001) | Source-linked | 19.3 Admin back-office (ADM) |
| [ADM-002](../../../requirements/ADM.md#adm-002) | Source-linked | 19.3 Admin back-office (ADM) |
| [ADM-003](../../../requirements/ADM.md#adm-003) | Source-linked | 19.3 Admin back-office (ADM) |
| [ADM-005](../../../requirements/ADM.md#adm-005) | Source-linked | 19.3 Admin back-office (ADM) |
| [ADM-006](../../../requirements/ADM.md#adm-006) | Plan allocation / source cross-reference | 19.3 Admin back-office (ADM) |
| [ADM-007](../../../requirements/ADM.md#adm-007) | Source-linked | 19.3 Admin back-office (ADM) |
| [ADM-008](../../../requirements/ADM.md#adm-008) | Plan allocation / source cross-reference | 19.3 Admin back-office (ADM) |
| [AT-58](../../../requirements/AT.md#at-58) | Source-linked | 25.2 Acceptance tests |
| [BO-6](../../../requirements/BO.md#bo-6) | Source-linked | 3.1 Business objectives |
| [BR-070](../../../requirements/BR.md#br-070) | Source-linked | 7.11 Platform, security, compliance and reliability |
| [BRL-018](../../../requirements/BRL.md#brl-018) | Plan allocation / source cross-reference | 8. Business rules |
| [BRL-025](../../../requirements/BRL.md#brl-025) | Plan allocation / source cross-reference | 8. Business rules |
| [SL-09](../../../requirements/SL.md#sl-09) | Plan allocation / source cross-reference | 10.1 Service levels |
| [US-044](../../../requirements/US.md#us-044) | Source-linked | EP-09 Administration and operations |
| [US-045](../../../requirements/US.md#us-045) | Source-linked | EP-09 Administration and operations |

Read every allocated record, including its continuation bullets and source variants. Source-linked rows preserve explicit document relationships; plan allocations are implementation responsibility assignments created during this review.

## Allocated specification checklist

The unchecked source obligations below require requirement-level evidence. They are deliberately separate from checked statements about current implemented slices. Read linked continuation bullets and additional source wording before accepting a record.

- [ ] [ADM-001](../../../requirements/ADM.md#adm-001): ADM-001 [P1] MUST provide an internal admin app (separate deployment and hostname, SSO plus MFA, IP-restricted) to search tenants; view state, config versions, numbers, usage and cost; replay and inspect conversations with reasons; manage plans and entitlements; suspend, unsuspend and close tenants; run support impersonation (ACC-002).
- [ ] [ADM-002](../../../requirements/ADM.md#adm-002): ADM-002 [P1] MUST provide feature flags and staged rollouts (per tenant, per plan, percentage), a kill switch per capability and per vendor, and audit of flag changes. Flags are evaluated via an OpenFeature-compatible interface.
- [ ] [ADM-003](../../../requirements/ADM.md#adm-003): ADM-003 [P1] MUST provide prompt and policy management: versioned platform policy and vertical templates with diff, review and approval, staged rollout with canary tenants, automated eval gate (§24.5), and instant rollback.
- [ ] [ADM-005](../../../requirements/ADM.md#adm-005): ADM-005 [P1] MUST provide number inventory management (search, buy, assign, release, port status), and compliance registration status (A2P 10DLC, toll-free verification).
- [ ] [ADM-006](../../../requirements/ADM.md#adm-006): ADM-006 [P2] SHOULD provide bulk tenant operations with dry-run and audit.
- [ ] [ADM-007](../../../requirements/ADM.md#adm-007): ADM-007 [P1] MUST provide an incident toolkit: broadcast banner to tenants, per-tenant fallback switch (route all calls to owner or to message-capture), and vendor failover controls.
- [ ] [ADM-008](../../../requirements/ADM.md#adm-008): ADM-008 [P1] MUST provide administration for brands, vertical packs, targets and prospects: create and configure brands and packs; manage the target registry and the claims register; view the pipeline and migration boards; roles limited to acquisition and vertical staff (ACC-006).
- [ ] [BRL-018](../../../requirements/BRL.md#brl-018): BRL-018 | When a client leaves, numbers are released or ported per policy and data is retained and deleted on a fixed schedule. | Offboarding | COM-008, ADM-005, TEN-006.
- [ ] [BRL-025](../../../requirements/BRL.md#brl-025): BRL-025 | Public descriptions of what a plan includes come from the same entitlement data the platform enforces, so a published plan never promises what the platform does not deliver. | Pricing and marketing | BIL-001, API-001, ADM-002.
- [ ] [SL-09](../../../requirements/SL.md#sl-09): SL-09 | Client support response times and hours | To be defined by EverOnn before the pilot.

## Existing code / check evidence



## Blockers and boundaries

Module risk: A tenant owner dashboard cannot substitute for a separate SSO/MFA/IP-restricted internal admin and audited staff access.

Dependencies: [EVN-ONB-101](../../01-onboarding-tenancy-identity/tickets/EVN-ONB-101.md), [EVN-SEC-102](../../15-security-privacy-compliance/tickets/EVN-SEC-102.md). A blocked prerequisite can be prototyped independently, but its contract and deployment must be approved before claiming this ticket delivered. Service limits, third-party approvals and staffing are evidence requirements, not assumptions that they are available.

## Handover and client acceptance

- [ ] Attach the business demonstration, technical evidence and operating/recovery instructions.
- [ ] Assign a named acceptance owner and agree any deferred criteria with the client in writing.
- [ ] Resolve launch-blocking defects and document accepted residual risks.
- [ ] Client records dated acceptance against the deployed/documented version.

Use [the acceptance protocol](../../../ACCEPTANCE.md) and [the ticket update rules](../../../TICKET_TEMPLATE.md) when changing status.
