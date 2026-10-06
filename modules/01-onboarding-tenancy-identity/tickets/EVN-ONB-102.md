# EVN-ONB-102 - Preserve tenant data while preparing brands, locations and cells

Project: EverOnnAI. Module: [Onboarding, identity and tenant lifecycle](../README.md). Technical delivery enabler allocated by this plan; source references below.

| Tracking dimension | Disposition |
| --- | --- |
| Engineering | Partial |
| QA | Existing checks are evidence for current slices; full ticket criteria remain pending |
| Deployment | Current local snapshot; verify ticket-specific hosted rollout and configuration |
| Business acceptance | Pending client review; no signed acceptance recorded |
| Owner | Backend Lead + Frontend Lead (proposed role; named person unassigned) |
| Priority / phase | Delivery enabler / P0 schema decision / P1 completion |
| Estimate | TBD after scope/architecture agreement; no delivery date committed |
| Dependencies | [EVN-FND-101](../../00-foundations-governance/tickets/EVN-FND-101.md) |

## Business deliverable

Preserve tenant data while preparing brands, locations and cells.

The client accepts the demonstrated outcome and evidence, rather than the existence of a route, table or screen. This ticket does not certify the whole source requirement as complete.

## Current implemented slice

- [x] Scoped relational stores and optimistic revisions are implemented.

## Remaining delivery checklist

- [ ] Define brand/location/cell/region/residency/tier schema and an expand-contract migration compatible with current workspaces.

## Technical component

- [ ] Implement the module boundary and contracts for: TenantRepository, routing map and migration validator.
- [ ] Maintain tenant boundaries, explicit state transitions, access policy and failure handling for the delivered workflow.
- [ ] Resolve applicable architecture decisions before committing to a new provider or infrastructure baseline.

## DB

Existing module persistence: workspaces, business_profiles, users, auth_sessions, invitations, team_members, record_revisions.

The following records/contracts are proposed or require extension; their names are planning terms, not assertions that production tables exist.

- [ ] tenant placement, brand/location references and published JSON schemas.
- [ ] Review scope keys, uniqueness, indexes, retention and migration compatibility; backfill safely and preserve existing tenant records.

## UI

- [ ] Tenant/location settings and safe placement diagnostics.
- [ ] Provide loading, empty, validation, permission-denied and recoverable failure states with keyboard and mobile access.
- [ ] Show observed facts and pending states accurately; do not present estimates, configured flags or mock results as confirmed business actions.

## Translate - business-to-technical mapping

| Business rule / outcome | Technical responsibility | Evidence needed |
| --- | --- | --- |
| Preserve tenant data while preparing brands, locations and cells. | TenantRepository, routing map and migration validator | Tenant-scoped end-to-end demonstration of the outcome |
| Define brand/location/cell/region/residency/tier schema and an expand-contract migration compatible with current workspaces. | tenant placement, brand/location references and published JSON schemas; Tenant/location settings and safe placement diagnostics | Migration/contracts, visible state and failure-path evidence |
| Safe, truthful AI behaviour where applicable | Tenant scope and published-version bindings on every AI request | Approved context, verified side-effect receipts and evaluation results or justified N/A |
| Client can approve delivery | QA report, rollout evidence and named acceptance owner | Evidence links and dated client sign-off |

This section means requirements-to-implementation mapping. It does not mean language translation; source language obligations are tracked in their own requirements.

## Backend services

- [ ] TenantRepository, routing map and migration validator.
- [ ] Define request/response/event schemas, authorisation and input validation for each affected operation.
- [ ] For writes and provider effects, define idempotency, retry/timeout, receipts and reconciliation; document N/A where no side effects exist.
- [ ] Expose actionable status and scoped logs without secrets; distinguish completed, failed and uncertain outcomes.

## AI component

- [ ] Tenant scope and published-version bindings on every AI request.
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
| [BRL-010](../../../requirements/BRL.md#brl-010) | Plan allocation / source cross-reference | 8. Business rules |
| [BRL-015](../../../requirements/BRL.md#brl-015) | Plan allocation / source cross-reference | 8. Business rules |
| [HIL-014](../../../requirements/HIL.md#hil-014) | Plan allocation / source cross-reference | 16.5 Quality, learning and control of the human layer |
| [ONB-006](../../../requirements/ONB.md#onb-006) | Source-linked | 12.2 Requirements |
| [ONB-008](../../../requirements/ONB.md#onb-008) | Source-linked | 12.2 Requirements |
| [ONB-010](../../../requirements/ONB.md#onb-010) | Plan allocation / source cross-reference | 12.2 Requirements |
| [ONB-011](../../../requirements/ONB.md#onb-011) | Plan allocation / source cross-reference | 12.2 Requirements |
| [SCF-001](../../../requirements/SCF.md#scf-001) | Plan allocation / source cross-reference | 22.3 Scaffolding checklist |
| [SCF-002](../../../requirements/SCF.md#scf-002) | Plan allocation / source cross-reference | 22.3 Scaffolding checklist |
| [TEN-001](../../../requirements/TEN.md#ten-001) | Source-linked | 12.3 Tenancy model requirements |
| [TEN-002](../../../requirements/TEN.md#ten-002) | Source-linked | 12.3 Tenancy model requirements |
| [TEN-003](../../../requirements/TEN.md#ten-003) | Source-linked | 12.3 Tenancy model requirements |
| [TEN-004](../../../requirements/TEN.md#ten-004) | Source-linked | 12.3 Tenancy model requirements |
| [TEN-005](../../../requirements/TEN.md#ten-005) | Source-linked | 12.3 Tenancy model requirements |
| [TEN-007](../../../requirements/TEN.md#ten-007) | Source-linked | 12.3 Tenancy model requirements |

Read every allocated record, including its continuation bullets and source variants. Source-linked rows preserve explicit document relationships; plan allocations are implementation responsibility assignments created during this review.

## Allocated specification checklist

The unchecked source obligations below require requirement-level evidence. They are deliberately separate from checked statements about current implemented slices. Read linked continuation bullets and additional source wording before accepting a record.

- [ ] [BRL-010](../../../requirements/BRL.md#brl-010): BRL-010 | An operator sees and uses only the data of the client for the interaction being handled, one client context at a time per interaction. | Operators | DSK-009, DSK-010, TEN-001.
- [ ] [BRL-015](../../../requirements/BRL.md#brl-015): BRL-015 | One client's data is never used to answer another client's callers or to build another client's site. | Platform | TEN-001, TEN-004, KNW-004.
- [ ] [HIL-014](../../../requirements/HIL.md#hil-014): HIL-014 [P2] SHOULD support partner/BPO operator pools as external tenants of the console with strict data segmentation, SLAs and per-partner reporting (scaffold identity model for external operator orgs in P1).
- [ ] [ONB-006](../../../requirements/ONB.md#onb-006): ONB-006 [P1] MUST capture business-hours, time zone, service area, languages, emergency policy, and preferred notification channels at onboarding.
- [ ] [ONB-008](../../../requirements/ONB.md#onb-008): ONB-008 [P2] SHOULD support multi-location tenants (one tenant, many locations, each with its own number, hours and agent variant).
- [ ] [ONB-010](../../../requirements/ONB.md#onb-010): ONB-010 [P1] MUST be resumable and idempotent: repeated claim submissions for the same business MUST NOT create duplicate tenants (dedupe on normalized phone, domain and Place ID).
- [ ] [ONB-011](../../../requirements/ONB.md#onb-011): ONB-011 [P1] MUST make the claim flow brand-aware: each brand has its own landing and claim pages, forms, emails and consent texts, and creates the tenant under that brand and its vertical pack.
- [ ] [SCF-001](../../../requirements/SCF.md#scf-001): 1 | tenant_id first in every key + tenant-scoped repository layer + isolation tests | Dedicated schema or database per tenant; regulated and enterprise tenants.
- [ ] [SCF-002](../../../requirements/SCF.md#scf-002): 2 | cell_id, region, data_residency columns and a routing map; scripted cell creation | Multiple cells for capacity; EU or regional data residency; blast-radius reduction.
- [ ] [TEN-001](../../../requirements/TEN.md#ten-001): TEN-001 [P0] MUST use a shared-schema, tenant_id-keyed model in MariaDB for P1 and P2, with these guarantees:.
- [ ] [TEN-002](../../../requirements/TEN.md#ten-002): TEN-002 [P1] MUST include tenants.cell_id, tenants.region, tenants.data_residency and tenants.tier columns and a routing map from day one (scaffolding for cells, regional residency and dedicated-schema enterprise tenants).
- [ ] [TEN-003](../../../requirements/TEN.md#ten-003): TEN-003 [P2] SHOULD support schema-per-tenant or database-per-tenant placement for large or regulated tenants without code changes (the repository layer resolves the connection from the routing map).
- [ ] [TEN-004](../../../requirements/TEN.md#ten-004): TEN-004 [P1] MUST namespace all cache keys, queue names, object-storage paths and search indexes by tenant (t/{tenant_id}/...). Recordings and exports MUST be encrypted with keys derived per tenant (envelope encryption, SEC-005).
- [ ] [TEN-005](../../../requirements/TEN.md#ten-005): TEN-005 [P1] MUST enforce per-tenant quotas and rate limits (API, calls per minute, concurrent calls, SMS per hour, generation jobs) with a noisy-neighbor policy: one tenant MUST NOT be able to starve others (fair queuing in workers).
- [ ] [TEN-007](../../../requirements/TEN.md#ten-007): TEN-007 [P1] MUST record brand_id and vertical_pack_id on every tenant, and run brand isolation tests alongside the tenant isolation tests (TEN-001): users, APIs, emails and pages of one brand MUST NOT expose another brand's data.

## Existing code / check evidence

- `features/auth/rbac.ts` - inspected current application working tree; see [snapshot evidence](../../../EVIDENCE.md).
- `features/auth/session.ts` - inspected current application working tree; see [snapshot evidence](../../../EVIDENCE.md).
- `features/auth/password.ts` - inspected current application working tree; see [snapshot evidence](../../../EVIDENCE.md).
- `lib/auth-store.ts` - inspected current application working tree; see [snapshot evidence](../../../EVIDENCE.md).
- `lib/json-workspace-store.ts` - inspected current application working tree; see [snapshot evidence](../../../EVIDENCE.md).
- `features/everonn/starter-workspace.ts` - inspected current application working tree; see [snapshot evidence](../../../EVIDENCE.md).
- `app/api/auth/register/route.ts` - inspected current application working tree; see [snapshot evidence](../../../EVIDENCE.md).
- Relevant automated checks: `tests/auth.test.ts`, `tests/workspace-security.test.ts`, `tests/app-records.test.ts`, `tests/everonn-relational.test.ts`, `scripts/smoke-auth-database.ts`. Their scope is bounded by [current validation](../../../CURRENT_STATE.md).

## Blockers and boundaries

Module risk: A boolean verified state does not establish independent business ownership; MFA/recovery and operator/brand identities remain incomplete.

Dependencies: [EVN-FND-101](../../00-foundations-governance/tickets/EVN-FND-101.md). A blocked prerequisite can be prototyped independently, but its contract and deployment must be approved before claiming this ticket delivered. Service limits, third-party approvals and staffing are evidence requirements, not assumptions that they are available.

## Handover and client acceptance

- [ ] Attach the business demonstration, technical evidence and operating/recovery instructions.
- [ ] Assign a named acceptance owner and agree any deferred criteria with the client in writing.
- [ ] Resolve launch-blocking defects and document accepted residual risks.
- [ ] Client records dated acceptance against the deployed/documented version.

Use [the acceptance protocol](../../../ACCEPTANCE.md) and [the ticket update rules](../../../TICKET_TEMPLATE.md) when changing status.
