# EVN-VRT-045 - Brands are kept apart

Project: EverOnnAI. Module: [Vertical brands, packs, readiness and capability parity](../README.md). Source business requirement [BR-045](../../../requirements/BR.md#br-045).

| Tracking dimension | Disposition |
| --- | --- |
| Engineering | Planned |
| QA | Existing checks are evidence for current slices; full ticket criteria remain pending |
| Deployment | Current local snapshot; verify ticket-specific hosted rollout and configuration |
| Business acceptance | Pending client review; no signed acceptance recorded |
| Owner | Vertical Manager + Product Owner + Counsel (proposed role; named person unassigned) |
| Priority / phase | Must / P1 |
| Estimate | TBD after scope/architecture agreement; no delivery date committed |
| Dependencies | [EVN-ONB-102](../../01-onboarding-tenancy-identity/tickets/EVN-ONB-102.md), [EVN-AIQ-104](../../03-ai-governance-evaluation/tickets/EVN-AIQ-104.md) |

## Business deliverable

Brands are kept apart. A client sees and is served only under its own brand, and the contracting entity, privacy terms and sender identity are always correct for that brand.

The client accepts the demonstrated outcome and evidence, rather than the existence of a route, table or screen. This ticket does not certify the whole source requirement as complete.

## Current implemented slice

- [ ] Tenant isolation exists; brand context and legal/sender separation do not.

The current statement describes prerequisites or context; this business deliverable has not been demonstrated.

## Remaining delivery checklist

- [ ] Enforce brand context across login, APIs, email, invoices, sites/legal pages; test cross-brand denial.

## Technical component

- [ ] Implement the module boundary and contracts for: Brand policy, sender routing and boundary tests.
- [ ] Maintain tenant boundaries, explicit state transitions, access policy and failure handling for the delivered workflow.
- [ ] Resolve applicable architecture decisions before committing to a new provider or infrastructure baseline.

## DB

Existing module persistence: Explicit skillId/domain selection and generation skill traces; no first-class brand/pack governance tables.

The following records/contracts are proposed or require extension; their names are planning terms, not assertions that production tables exist.

- [ ] brand_grants, tenant_brand_links, legal_versions.
- [ ] Review scope keys, uniqueness, indexes, retention and migration compatibility; backfill safely and preserve existing tenant records.

## UI

- [ ] Brand shell and contracting-entity notices.
- [ ] Provide loading, empty, validation, permission-denied and recoverable failure states with keyboard and mobile access.
- [ ] Show observed facts and pending states accurately; do not present estimates, configured flags or mock results as confirmed business actions.

## Translate - business-to-technical mapping

| Business rule / outcome | Technical responsibility | Evidence needed |
| --- | --- | --- |
| Brands are kept apart. A client sees and is served only under its own brand, and the contracting entity, privacy terms and sender identity are always correct for that brand. | Brand policy, sender routing and boundary tests | Tenant-scoped end-to-end demonstration of the outcome |
| Enforce brand context across login, APIs, email, invoices, sites/legal pages; test cross-brand denial. | brand_grants, tenant_brand_links, legal_versions; Brand shell and contracting-entity notices | Migration/contracts, visible state and failure-path evidence |
| Safe, truthful AI behaviour where applicable | No cross-brand context or misleading provider identity | Approved context, verified side-effect receipts and evaluation results or justified N/A |
| Client can approve delivery | QA report, rollout evidence and named acceptance owner | Evidence links and dated client sign-off |

This section means requirements-to-implementation mapping. It does not mean language translation; source language obligations are tracked in their own requirements.

## Backend services

- [ ] Brand policy, sender routing and boundary tests.
- [ ] Define request/response/event schemas, authorisation and input validation for each affected operation.
- [ ] For writes and provider effects, define idempotency, retry/timeout, receipts and reconciliation; document N/A where no side effects exist.
- [ ] Expose actionable status and scoped logs without secrets; distinguish completed, failed and uncertain outcomes.

## AI component

- [ ] No cross-brand context or misleading provider identity.
- [ ] Record instruction/knowledge/tool versions, measured quality, tenant scope, cost and safe fallback; a Markdown standard alone is not a passed evaluation.

## Testing / QA

- [ ] Exercise the intended user journey with real tenant-scoped state; cover forbidden role and cross-tenant requests.
- [ ] Test malformed inputs, provider failure, retries/replays and cancellation as applicable; keep deterministic mocks separate from live-provider evidence.
- [ ] Review desktop/mobile accessibility, factual copy and failure recovery in the delivered UI.
- [ ] Attach test environment, code/config/instruction versions, results and remaining defects to the acceptance report.

| Source test | Scenario | Required pass criteria | Current disposition |
| --- | --- | --- | --- |
| [AT-06](../../../requirements/AT.md#at-06) | Two brands and two vertical packs live on one platform | Each brand shows its own name, domain, theme, emails, texts and legal pages; a client cannot see another brand; one operator can serve clients of both brands; every brand's terms name the contracting entity | Full source scenario not evidenced; client acceptance pending |

Source stories: [US-056](../../../requirements/US.md#us-056), [US-057](../../../requirements/US.md#us-057).

## Deployment

- [ ] Confirm approved hosting/database/provider architecture and required credentials in the deployment environment.
- [ ] Apply compatible migrations/configuration in staging, rehearse rollback, then promote the reviewed artifact.
- [ ] Verify the actual hosted workflow, monitoring, fallback and customer-visible errors after release.
- [ ] Update CODE_PROFILE.md, PROJECT_DATA_FLOW.md and CLIENT_TECHNICAL_QA.md in the application when behaviour or architecture changes.
- [ ] Record deployment identity, operator, timestamp and rollback evidence; document-only tickets instead record the reviewed Git commit.

## Source traceability

| Source ID | Mapping basis | Source section |
| --- | --- | --- |
| [AT-06](../../../requirements/AT.md#at-06) | Source-linked | 25.2 Acceptance tests |
| [BO-7](../../../requirements/BO.md#bo-7) | Source-linked | 3.1 Business objectives |
| [BO-10](../../../requirements/BO.md#bo-10) | Source-linked | 3.1 Business objectives |
| [BR-045](../../../requirements/BR.md#br-045) | Source-linked | 7.8 Suite, verticals and brands |
| [BRL-017](../../../requirements/BRL.md#brl-017) | Plan allocation / source cross-reference | 8. Business rules |
| [BRL-032](../../../requirements/BRL.md#brl-032) | Plan allocation / source cross-reference | 8. Business rules |
| [COM-006](../../../requirements/COM.md#com-006) | Source-linked | 19.5 Compliance and legal-by-design (COM) |
| [TEN-007](../../../requirements/TEN.md#ten-007) | Source-linked | 12.3 Tenancy model requirements |
| [US-056](../../../requirements/US.md#us-056) | Source-linked | EP-12 Verticals and brands |
| [US-057](../../../requirements/US.md#us-057) | Source-linked | EP-12 Verticals and brands |
| [VRT-002](../../../requirements/VRT.md#vrt-002) | Source-linked | 19.6 Brands and vertical packs (VRT) |
| [VRT-009](../../../requirements/VRT.md#vrt-009) | Source-linked | 19.6 Brands and vertical packs (VRT) |

Read every allocated record, including its continuation bullets and source variants. Source-linked rows preserve explicit document relationships; plan allocations are implementation responsibility assignments created during this review.

## Allocated specification checklist

The unchecked source obligations below require requirement-level evidence. They are deliberately separate from checked statements about current implemented slices. Read linked continuation bullets and additional source wording before accepting a record.

- [ ] [BRL-017](../../../requirements/BRL.md#brl-017): BRL-017 | EverOnn provides technology, not the client's trade services; terms and site copy say so. | Legal, websites | COM-006, WEB-002.
- [ ] [BRL-032](../../../requirements/BRL.md#brl-032): BRL-032 | Vertical brands are presentation brands of one company. The contracting entity, privacy terms and client agreement always name EverOnn; no brand suggests independence it does not have; every claim, review or testimonial shown on a brand is true for that brand; trademarks are cleared before a brand launches. | Brands | VRT-001, VRT-009, ACQ-010.
- [ ] [COM-006](../../../requirements/COM.md#com-006): COM-006 [P1] MUST publish accurate Privacy Policy, Terms, Messaging Terms templates rendered per tenant on their sites, with tenant-specific data controller information.
- [ ] [TEN-007](../../../requirements/TEN.md#ten-007): TEN-007 [P1] MUST record brand_id and vertical_pack_id on every tenant, and run brand isolation tests alongside the tenant isolation tests (TEN-001): users, APIs, emails and pages of one brand MUST NOT expose another brand's data.
- [ ] [VRT-002](../../../requirements/VRT.md#vrt-002): VRT-002 [P1] MUST apply the brand to everything a client or a client's customer sees: the client application and its login address, emails, texts, invoices, help content, generated websites' preview host, demonstration pages and notices. A user of one brand MUST NOT be able to discover or see another brand's clients, pricing or content.
- [ ] [VRT-009](../../../requirements/VRT.md#vrt-009): VRT-009 [P1] MUST name the contracting entity in every brand's legal documents, footers and client agreement, apply one consistent set of terms, privacy and refund policies across brands, and share a single suppression list across all brands (ACQ-008).

## Existing code / check evidence

- `features/agent-runtime/skill-registry.ts` - inspected current application working tree; see [snapshot evidence](../../../EVIDENCE.md).
- `features/agent-runtime/skill-loader.ts` - inspected current application working tree; see [snapshot evidence](../../../EVIDENCE.md).
- `ai/domains/hvac/SKILL.md` - inspected current application working tree; see [snapshot evidence](../../../EVIDENCE.md).
- `ai/domains/hvac/EVALS.md` - inspected current application working tree; see [snapshot evidence](../../../EVIDENCE.md).
- `ai/domains/hvac/SOURCES.md` - inspected current application working tree; see [snapshot evidence](../../../EVIDENCE.md).
- Relevant automated checks: `tests/agent-runtime.test.ts`, `scripts/smoke-hvac.ts`. Their scope is bounded by [current validation](../../../CURRENT_STATE.md).

## Blockers and boundaries

Module risk: One HVAC pack is not two live brands/packs, configuration-only launch, vertical parity or legal/expert/operator readiness approval.

Dependencies: [EVN-ONB-102](../../01-onboarding-tenancy-identity/tickets/EVN-ONB-102.md), [EVN-AIQ-104](../../03-ai-governance-evaluation/tickets/EVN-AIQ-104.md). A blocked prerequisite can be prototyped independently, but its contract and deployment must be approved before claiming this ticket delivered. Service limits, third-party approvals and staffing are evidence requirements, not assumptions that they are available.

## Handover and client acceptance

- [ ] Attach the business demonstration, technical evidence and operating/recovery instructions.
- [ ] Assign a named acceptance owner and agree any deferred criteria with the client in writing.
- [ ] Resolve launch-blocking defects and document accepted residual risks.
- [ ] Client records dated acceptance against the deployed/documented version.

Use [the acceptance protocol](../../../ACCEPTANCE.md) and [the ticket update rules](../../../TICKET_TEMPLATE.md) when changing status.
