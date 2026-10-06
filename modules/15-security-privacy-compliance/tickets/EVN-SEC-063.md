# EVN-SEC-063 - Client data isolation

Project: EverOnnAI. Module: [Security, consent, privacy, legal terms and assurance](../README.md). Source business requirement [BR-063](../../../requirements/BR.md#br-063).

| Tracking dimension | Disposition |
| --- | --- |
| Engineering | Partial |
| QA | Existing checks are evidence for current slices; full ticket criteria remain pending |
| Deployment | Current local snapshot; verify ticket-specific hosted rollout and configuration |
| Business acceptance | Pending client review; no signed acceptance recorded |
| Owner | Security Lead + Counsel + Product Owner (proposed role; named person unassigned) |
| Priority / phase | Must / P1 |
| Estimate | TBD after scope/architecture agreement; no delivery date committed |
| Dependencies | [EVN-SEC-101](EVN-SEC-101.md), [EVN-SEC-102](EVN-SEC-102.md) |

## Business deliverable

Client data isolation. One client's data is never visible to, or used for, another client.

The client accepts the demonstrated outcome and evidence, rather than the existence of a route, table or screen. This ticket does not certify the whole source requirement as complete.

## Current implemented slice

- [x] Server workspace scope, RBAC, private SQL and isolation tests exist.

## Remaining delivery checklist

- [ ] Complete brand/cell/operator/storage boundaries and independent assurance; resolve the DB baseline deviation.

## Technical component

- [ ] Implement the module boundary and contracts for: Tenant repositories, policy and isolation tests.
- [ ] Maintain tenant boundaries, explicit state transitions, access policy and failure handling for the delivered workflow.
- [ ] Resolve applicable architecture decisions before committing to a new provider or infrastructure baseline.

## DB

Existing module persistence: Private entity tables, scoped auth, encrypted provider payloads and invoker write functions.

The following records/contracts are proposed or require extension; their names are planning terms, not assertions that production tables exist.

- [ ] workspaces, scoped_entities, routing_map.
- [ ] Review scope keys, uniqueness, indexes, retention and migration compatibility; backfill safely and preserve existing tenant records.

## UI

- [ ] Role-scoped UI and tenant denial states.
- [ ] Provide loading, empty, validation, permission-denied and recoverable failure states with keyboard and mobile access.
- [ ] Show observed facts and pending states accurately; do not present estimates, configured flags or mock results as confirmed business actions.

## Translate - business-to-technical mapping

| Business rule / outcome | Technical responsibility | Evidence needed |
| --- | --- | --- |
| Client data isolation. One client's data is never visible to, or used for, another client. | Tenant repositories, policy and isolation tests | Tenant-scoped end-to-end demonstration of the outcome |
| Complete brand/cell/operator/storage boundaries and independent assurance; resolve the DB baseline deviation. | workspaces, scoped_entities, routing_map; Role-scoped UI and tenant denial states | Migration/contracts, visible state and failure-path evidence |
| Safe, truthful AI behaviour where applicable | Tenant-filter knowledge, tool tokens and model context | Approved context, verified side-effect receipts and evaluation results or justified N/A |
| Client can approve delivery | QA report, rollout evidence and named acceptance owner | Evidence links and dated client sign-off |

This section means requirements-to-implementation mapping. It does not mean language translation; source language obligations are tracked in their own requirements.

## Backend services

- [ ] Tenant repositories, policy and isolation tests.
- [ ] Define request/response/event schemas, authorisation and input validation for each affected operation.
- [ ] For writes and provider effects, define idempotency, retry/timeout, receipts and reconciliation; document N/A where no side effects exist.
- [ ] Expose actionable status and scoped logs without secrets; distinguish completed, failed and uncertain outcomes.

## AI component

- [ ] Tenant-filter knowledge, tool tokens and model context.
- [ ] Record instruction/knowledge/tool versions, measured quality, tenant scope, cost and safe fallback; a Markdown standard alone is not a passed evaluation.

## Testing / QA

- [ ] Exercise the intended user journey with real tenant-scoped state; cover forbidden role and cross-tenant requests.
- [ ] Test malformed inputs, provider failure, retries/replays and cancellation as applicable; keep deterministic mocks separate from live-provider evidence.
- [ ] Review desktop/mobile accessibility, factual copy and failure recovery in the delivered UI.
- [ ] Attach test environment, code/config/instruction versions, results and remaining defects to the acceptance report.

| Source test | Scenario | Required pass criteria | Current disposition |
| --- | --- | --- | --- |
| [AT-32](../../../requirements/AT.md#at-32) | Client isolation on the desk | An operator without a grant sees nothing for that client; simultaneous chats are separately labeled; attaching data across clients is rejected; a revoked grant removes access within 5 seconds; the wrong-client control logs and re-routes | Full source scenario not evidenced; client acceptance pending |
| [AT-47](../../../requirements/AT.md#at-47) | Cross-client isolation suite | Zero leaks across API routes, jobs and retrieval | Full source scenario not evidenced; client acceptance pending |

Source stories: [US-023](../../../requirements/US.md#us-023), [US-050](../../../requirements/US.md#us-050).

## Deployment

- [ ] Confirm approved hosting/database/provider architecture and required credentials in the deployment environment.
- [ ] Apply compatible migrations/configuration in staging, rehearse rollback, then promote the reviewed artifact.
- [ ] Verify the actual hosted workflow, monitoring, fallback and customer-visible errors after release.
- [ ] Update CODE_PROFILE.md, PROJECT_DATA_FLOW.md and CLIENT_TECHNICAL_QA.md in the application when behaviour or architecture changes.
- [ ] Record deployment identity, operator, timestamp and rollback evidence; document-only tickets instead record the reviewed Git commit.

## Source traceability

| Source ID | Mapping basis | Source section |
| --- | --- | --- |
| [AT-32](../../../requirements/AT.md#at-32) | Source-linked | 25.2 Acceptance tests |
| [AT-47](../../../requirements/AT.md#at-47) | Source-linked | 25.2 Acceptance tests |
| [BO-7](../../../requirements/BO.md#bo-7) | Source-linked | 3.1 Business objectives |
| [BR-063](../../../requirements/BR.md#br-063) | Source-linked | 7.11 Platform, security, compliance and reliability |
| [BRL-010](../../../requirements/BRL.md#brl-010) | Plan allocation / source cross-reference | 8. Business rules |
| [BRL-015](../../../requirements/BRL.md#brl-015) | Plan allocation / source cross-reference | 8. Business rules |
| [SCF-006](../../../requirements/SCF.md#scf-006) | Plan allocation / source cross-reference | 22.3 Scaffolding checklist |
| [SEC-014](../../../requirements/SEC.md#sec-014) | Source-linked | 22.2 Security requirements |
| [TEN-001](../../../requirements/TEN.md#ten-001) | Source-linked | 12.3 Tenancy model requirements |
| [TEN-004](../../../requirements/TEN.md#ten-004) | Source-linked | 12.3 Tenancy model requirements |
| [US-023](../../../requirements/US.md#us-023) | Source-linked | EP-05 Human operations and the Live Agent Desk |
| [US-050](../../../requirements/US.md#us-050) | Source-linked | EP-10 Compliance, security and privacy |

Read every allocated record, including its continuation bullets and source variants. Source-linked rows preserve explicit document relationships; plan allocations are implementation responsibility assignments created during this review.

## Allocated specification checklist

The unchecked source obligations below require requirement-level evidence. They are deliberately separate from checked statements about current implemented slices. Read linked continuation bullets and additional source wording before accepting a record.

- [ ] [BRL-010](../../../requirements/BRL.md#brl-010): BRL-010 | An operator sees and uses only the data of the client for the interaction being handled, one client context at a time per interaction. | Operators | DSK-009, DSK-010, TEN-001.
- [ ] [BRL-015](../../../requirements/BRL.md#brl-015): BRL-015 | One client's data is never used to answer another client's callers or to build another client's site. | Platform | TEN-001, TEN-004, KNW-004.
- [ ] [SCF-006](../../../requirements/SCF.md#scf-006): 6 | Consent ledger and fail-closed sending guard | Marketing and outbound campaigns; HIPAA mode; regulatory audits.
- [ ] [SEC-014](../../../requirements/SEC.md#sec-014): SEC-014 [P1] MUST test isolation continuously (TEN-001) and include tenant-isolation cases in the pen-test scope.
- [ ] [TEN-001](../../../requirements/TEN.md#ten-001): TEN-001 [P0] MUST use a shared-schema, tenant_id-keyed model in MariaDB for P1 and P2, with these guarantees:.
- [ ] [TEN-004](../../../requirements/TEN.md#ten-004): TEN-004 [P1] MUST namespace all cache keys, queue names, object-storage paths and search indexes by tenant (t/{tenant_id}/...). Recordings and exports MUST be encrypted with keys derived per tenant (envelope encryption, SEC-005).

## Existing code / check evidence

- `features/auth/request-origin.ts` - inspected current application working tree; see [snapshot evidence](../../../EVIDENCE.md).
- `features/auth/session.ts` - inspected current application working tree; see [snapshot evidence](../../../EVIDENCE.md).
- `features/auth/rbac.ts` - inspected current application working tree; see [snapshot evidence](../../../EVIDENCE.md).
- `lib/provider-credentials.ts` - inspected current application working tree; see [snapshot evidence](../../../EVIDENCE.md).
- `lib/app-records.ts` - inspected current application working tree; see [snapshot evidence](../../../EVIDENCE.md).
- `supabase/migrations/202610040003_everonn_relational.sql` - inspected current application working tree; see [snapshot evidence](../../../EVIDENCE.md).
- `supabase/migrations/202610060004_project_repositories.sql` - inspected current application working tree; see [snapshot evidence](../../../EVIDENCE.md).
- Relevant automated checks: `tests/workspace-security.test.ts`, `tests/request-origin.test.ts`, `tests/provider-credentials.test.ts`, `tests/everonn-relational.test.ts`, `tests/project-workspace.test.ts`. Their scope is bounded by [current validation](../../../CURRENT_STATE.md).

## Blockers and boundaries

Module risk: Private PostgreSQL and AES-GCM tokens are not a consent ledger, per-tenant KMS keys, audit/WORM chain, privacy operations, pen-test pass or SOC 2 certification.

Dependencies: [EVN-SEC-101](EVN-SEC-101.md), [EVN-SEC-102](EVN-SEC-102.md). A blocked prerequisite can be prototyped independently, but its contract and deployment must be approved before claiming this ticket delivered. Service limits, third-party approvals and staffing are evidence requirements, not assumptions that they are available.

## Handover and client acceptance

- [ ] Attach the business demonstration, technical evidence and operating/recovery instructions.
- [ ] Assign a named acceptance owner and agree any deferred criteria with the client in writing.
- [ ] Resolve launch-blocking defects and document accepted residual risks.
- [ ] Client records dated acceptance against the deployed/documented version.

Use [the acceptance protocol](../../../ACCEPTANCE.md) and [the ticket update rules](../../../TICKET_TEMPLATE.md) when changing status.
