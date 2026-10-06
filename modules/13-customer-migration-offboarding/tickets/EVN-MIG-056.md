# EVN-MIG-056 - Managed migration without service loss

Project: EverOnnAI. Module: [Authorised migration, service continuity and offboarding](../README.md). Source business requirement [BR-056](../../../requirements/BR.md#br-056).

| Tracking dimension | Disposition |
| --- | --- |
| Engineering | Planned |
| QA | Existing checks are evidence for current slices; full ticket criteria remain pending |
| Deployment | Current local snapshot; verify ticket-specific hosted rollout and configuration |
| Business acceptance | Pending client review; no signed acceptance recorded |
| Owner | Migration Specialist + Operations Lead (proposed role; named person unassigned) |
| Priority / phase | Must / P1 basic, P2 advanced |
| Estimate | TBD after scope/architecture agreement; no delivery date committed |
| Dependencies | [EVN-FND-101](../../00-foundations-governance/tickets/EVN-FND-101.md), [EVN-ONB-102](../../01-onboarding-tenancy-identity/tickets/EVN-ONB-102.md), [EVN-OPS-103](../../18-reliability-deployment-scale/tickets/EVN-OPS-103.md) |

## Business deliverable

Managed migration without service loss. A migration toolkit moves a client from an incumbent with no loss of calls, email, leads or search visibility: content import, domain ownership check and transfer or repointing, email continuity, phone forwarding, parallel run, cut-over and rollback.

The client accepts the demonstrated outcome and evidence, rather than the existence of a route, table or screen. This ticket does not certify the whole source requirement as complete.

## Current implemented slice

- [ ] Website rollback is not a business migration toolkit.

The current statement describes prerequisites or context; this business deliverable has not been demonstrated.

## Remaining delivery checklist

- [ ] Inventory/import authorised assets, preserve URLs/mail/phones, parallel-run, approve cutover and rehearse rollback.

## Technical component

- [ ] Implement the module boundary and contracts for: Import/continuity checks and reversible workflows.
- [ ] Maintain tenant boundaries, explicit state transitions, access policy and failure handling for the delivered workflow.
- [ ] Resolve applicable architecture decisions before committing to a new provider or infrastructure baseline.

## DB

Existing module persistence: Website snapshot rollback only; no whole-business migration inventory/rights/cutover model.

The following records/contracts are proposed or require extension; their names are planning terms, not assertions that production tables exist.

- [ ] migration_projects, asset_inventory, cutover_checks.
- [ ] Review scope keys, uniqueness, indexes, retention and migration compatibility; backfill safely and preserve existing tenant records.

## UI

- [ ] Migration board, checklist and approvals.
- [ ] Provide loading, empty, validation, permission-denied and recoverable failure states with keyboard and mobile access.
- [ ] Show observed facts and pending states accurately; do not present estimates, configured flags or mock results as confirmed business actions.

## Translate - business-to-technical mapping

| Business rule / outcome | Technical responsibility | Evidence needed |
| --- | --- | --- |
| Managed migration without service loss. A migration toolkit moves a client from an incumbent with no loss of calls, email, leads or search visibility: content import, domain ownership check and transfer or repointing, email continuity, phone forwarding, parallel run, cut-over and rollback. | Import/continuity checks and reversible workflows | Tenant-scoped end-to-end demonstration of the outcome |
| Inventory/import authorised assets, preserve URLs/mail/phones, parallel-run, approve cutover and rehearse rollback. | migration_projects, asset_inventory, cutover_checks; Migration board, checklist and approvals | Migration/contracts, visible state and failure-path evidence |
| Safe, truthful AI behaviour where applicable | Propose mappings for approval; no automatic cancellation/DNS change | Approved context, verified side-effect receipts and evaluation results or justified N/A |
| Client can approve delivery | QA report, rollout evidence and named acceptance owner | Evidence links and dated client sign-off |

This section means requirements-to-implementation mapping. It does not mean language translation; source language obligations are tracked in their own requirements.

## Backend services

- [ ] Import/continuity checks and reversible workflows.
- [ ] Define request/response/event schemas, authorisation and input validation for each affected operation.
- [ ] For writes and provider effects, define idempotency, retry/timeout, receipts and reconciliation; document N/A where no side effects exist.
- [ ] Expose actionable status and scoped logs without secrets; distinguish completed, failed and uncertain outcomes.

## AI component

- [ ] Propose mappings for approval.
- [ ] no automatic cancellation/DNS change.
- [ ] Record instruction/knowledge/tool versions, measured quality, tenant scope, cost and safe fallback; a Markdown standard alone is not a passed evaluation.

## Testing / QA

- [ ] Exercise the intended user journey with real tenant-scoped state; cover forbidden role and cross-tenant requests.
- [ ] Test malformed inputs, provider failure, retries/replays and cancellation as applicable; keep deterministic mocks separate from live-provider evidence.
- [ ] Review desktop/mobile accessibility, factual copy and failure recovery in the delivered UI.
- [ ] Attach test environment, code/config/instruction versions, results and remaining defects to the acceptance report.

| Source test | Scenario | Required pass criteria | Current disposition |
| --- | --- | --- | --- |
| [AT-26](../../../requirements/AT.md#at-26) | End-to-end migration without service loss | Content is imported and reviewed; domain ownership is verified and the domain transferred or repointed; email continues; forwarded numbers are verified; a parallel run and cut-over happen; rollback is exercised; no calls or form leads are lost during cut-over | Full source scenario not evidenced; client acceptance pending |

Source stories: [US-066](../../../requirements/US.md#us-066), [US-067](../../../requirements/US.md#us-067).

## Deployment

- [ ] Confirm approved hosting/database/provider architecture and required credentials in the deployment environment.
- [ ] Apply compatible migrations/configuration in staging, rehearse rollback, then promote the reviewed artifact.
- [ ] Verify the actual hosted workflow, monitoring, fallback and customer-visible errors after release.
- [ ] Update CODE_PROFILE.md, PROJECT_DATA_FLOW.md and CLIENT_TECHNICAL_QA.md in the application when behaviour or architecture changes.
- [ ] Record deployment identity, operator, timestamp and rollback evidence; document-only tickets instead record the reviewed Git commit.

## Source traceability

| Source ID | Mapping basis | Source section |
| --- | --- | --- |
| [AT-26](../../../requirements/AT.md#at-26) | Source-linked | 25.2 Acceptance tests |
| [BO-2](../../../requirements/BO.md#bo-2) | Source-linked | 3.1 Business objectives |
| [BO-10](../../../requirements/BO.md#bo-10) | Source-linked | 3.1 Business objectives |
| [BR-056](../../../requirements/BR.md#br-056) | Source-linked | 7.9 Customer acquisition and migration |
| [BRL-031](../../../requirements/BRL.md#brl-031) | Plan allocation / source cross-reference | 8. Business rules |
| [MIG-001](../../../requirements/MIG.md#mig-001) | Source-linked | 19.8 Migration (MIG) |
| [MIG-002](../../../requirements/MIG.md#mig-002) | Source-linked | 19.8 Migration (MIG) |
| [MIG-003](../../../requirements/MIG.md#mig-003) | Source-linked | 19.8 Migration (MIG) |
| [MIG-004](../../../requirements/MIG.md#mig-004) | Source-linked | 19.8 Migration (MIG) |
| [MIG-005](../../../requirements/MIG.md#mig-005) | Source-linked | 19.8 Migration (MIG) |
| [MIG-007](../../../requirements/MIG.md#mig-007) | Source-linked | 19.8 Migration (MIG) |
| [MIG-008](../../../requirements/MIG.md#mig-008) | Source-linked | 19.8 Migration (MIG) |
| [ORD-008](../../../requirements/ORD.md#ord-008) | Plan allocation / source cross-reference | 19.9 Online ordering and restaurant workflow (ORD) |
| [US-066](../../../requirements/US.md#us-066) | Source-linked | EP-13 Customer acquisition and migration |
| [US-067](../../../requirements/US.md#us-067) | Source-linked | EP-13 Customer acquisition and migration |

Read every allocated record, including its continuation bullets and source variants. Source-linked rows preserve explicit document relationships; plan allocations are implementation responsibility assignments created during this review.

## Allocated specification checklist

The unchecked source obligations below require requirement-level evidence. They are deliberately separate from checked statements about current implemented slices. Read linked continuation bullets and additional source wording before accepting a record.

- [ ] [BRL-031](../../../requirements/BRL.md#brl-031): BRL-031 | Switching respects the customer's contract and ownership: the incumbent's term, notice and fees are asked for and included in the comparison, nothing is cancelled on the customer's behalf without written authorization, and only assets the customer owns or may export are migrated. | Migration | MIG-006, MIG-003, MIG-007.
- [ ] [MIG-001](../../../requirements/MIG.md#mig-001): MIG-001 [P1] MUST create a migration project for each switching client, recording the incumbent and an inventory of assets: domain and DNS, email hosting, site content and images, forms, client portal or documents, customer lists, phone numbers and call-tracking numbers, Google Business Profile and ordering or reservation links, and integrations; the owner's authorization for each; status per asset; timeline; risks; and the rollback plan.
- [ ] [MIG-002](../../../requirements/MIG.md#mig-002): MIG-002 [P1] MUST support content import from the client's own existing public site (respecting robots directives and the incumbent's terms): pages, text, images (with a rights check), services, hours, FAQs, forms and structured data are mapped to the Site Spec, with a URL map for redirects, and reviewed by the owner. The incumbent's proprietary templates, code and licensed media are never copied.
- [ ] [MIG-003](../../../requirements/MIG.md#mig-003): MIG-003 [P1] MUST provide a domain workflow: verify who is the registrant and who controls the registrar account; guide the owner through unlocking the domain and obtaining the authorization code, or through repointing DNS where transfer is not needed; copy mail and verification records before any change; confirm that email continues; issue certificates on the new host; cut over only after the checks pass; roll back within a stated time if a check fails.
- [ ] [MIG-004](../../../requirements/MIG.md#mig-004): MIG-004 [P1] MUST support a parallel run and cut-over: the new site and front desk run on a staging address and, where safe, in shadow (calls still reach the old routing) before a scheduled cut-over window; post-cut-over checks cover forms, chat, call routing, tracking, sitemap and email; a hypercare period follows.
- [ ] [MIG-005](../../../requirements/MIG.md#mig-005): MIG-005 [P1] MUST preserve phone continuity: set up and verify forwarding so that no call is missed during the change; plan what happens to incumbent-owned call-tracking numbers (replace, forward or, from P2, port); confirm numbers and routing before the incumbent service is ended.
- [ ] [MIG-007](../../../requirements/MIG.md#mig-007): MIG-007 [P1] MUST migrate client data only through client-authorized exports (for example accountants' portal documents, patient forms, order history, customer lists), under the vertical's compliance profile, with counts and checksums verified and the source retained until the client signs off.
- [ ] [MIG-008](../../../requirements/MIG.md#mig-008): MIG-008 [P1] SHOULD preserve search and listing value: redirect map, titles and metadata, structured data, and tasks to update Google Business Profile and directory links (including ordering and reservation links).
- [ ] [ORD-008](../../../requirements/ORD.md#ord-008): ORD-008 [P2] SHOULD manage the restaurant's Google ordering and reservation links during migration, with the restaurant's authorization.

## Existing code / check evidence

- `features/website-studio/releases.ts` - inspected current application working tree; see [snapshot evidence](../../../EVIDENCE.md).
- Relevant automated checks: `tests/website-code.test.ts`. Their scope is bounded by [current validation](../../../CURRENT_STATE.md).

## Blockers and boundaries

Module risk: Website rollback does not preserve registrar/mail/phone contracts or provide authorised import, parallel run, hypercare and business offboarding.

Dependencies: [EVN-FND-101](../../00-foundations-governance/tickets/EVN-FND-101.md), [EVN-ONB-102](../../01-onboarding-tenancy-identity/tickets/EVN-ONB-102.md), [EVN-OPS-103](../../18-reliability-deployment-scale/tickets/EVN-OPS-103.md). A blocked prerequisite can be prototyped independently, but its contract and deployment must be approved before claiming this ticket delivered. Service limits, third-party approvals and staffing are evidence requirements, not assumptions that they are available.

## Handover and client acceptance

- [ ] Attach the business demonstration, technical evidence and operating/recovery instructions.
- [ ] Assign a named acceptance owner and agree any deferred criteria with the client in writing.
- [ ] Resolve launch-blocking defects and document accepted residual risks.
- [ ] Client records dated acceptance against the deployed/documented version.

Use [the acceptance protocol](../../../ACCEPTANCE.md) and [the ticket update rules](../../../TICKET_TEMPLATE.md) when changing status.
