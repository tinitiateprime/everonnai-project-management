# EVN-VRT-048 - Match what customers already rely on

Project: EverOnnAI. Module: [Vertical brands, packs, readiness and capability parity](../README.md). Source business requirement [BR-048](../../../requirements/BR.md#br-048).

| Tracking dimension | Disposition |
| --- | --- |
| Engineering | Planned |
| QA | Existing checks are evidence for current slices; full ticket criteria remain pending |
| Deployment | Current local snapshot; verify ticket-specific hosted rollout and configuration |
| Business acceptance | Pending client review; no signed acceptance recorded |
| Owner | Vertical Manager + Product Owner + Counsel (proposed role; named person unassigned) |
| Priority / phase | Must / P1 first packs; later by wave |
| Estimate | TBD after scope/architecture agreement; no delivery date committed |
| Dependencies | [EVN-ONB-102](../../01-onboarding-tenancy-identity/tickets/EVN-ONB-102.md), [EVN-AIQ-104](../../03-ai-governance-evaluation/tickets/EVN-AIQ-104.md) |

## Business deliverable

Match what customers already rely on. Each vertical offers the capabilities its customers already rely on from their current provider (for example service pages, reviews and local marketing for auto repair; a secure client portal and newsletters for accountants; online ordering for restaurants) by building, embedding or connecting them.

The client accepts the demonstrated outcome and evidence, rather than the existence of a route, table or screen. This ticket does not certify the whole source requirement as complete.

## Current implemented slice

- [ ] Service pages exist; complete vertical parity products/connectors do not.

The current statement describes prerequisites or context; this business deliverable has not been demonstrated.

## Remaining delivery checklist

- [ ] Approve parity matrices; demonstrate every built/embedded/connected capability.

## Technical component

- [ ] Implement the module boundary and contracts for: Parity verification and governed connectors.
- [ ] Maintain tenant boundaries, explicit state transitions, access policy and failure handling for the delivered workflow.
- [ ] Resolve applicable architecture decisions before committing to a new provider or infrastructure baseline.

## DB

Existing module persistence: Explicit skillId/domain selection and generation skill traces; no first-class brand/pack governance tables.

The following records/contracts are proposed or require extension; their names are planning terms, not assertions that production tables exist.

- [ ] parity_requirements, connector_capabilities.
- [ ] Review scope keys, uniqueness, indexes, retention and migration compatibility; backfill safely and preserve existing tenant records.

## UI

- [ ] Vertical capability/readiness views.
- [ ] Provide loading, empty, validation, permission-denied and recoverable failure states with keyboard and mobile access.
- [ ] Show observed facts and pending states accurately; do not present estimates, configured flags or mock results as confirmed business actions.

## Translate - business-to-technical mapping

| Business rule / outcome | Technical responsibility | Evidence needed |
| --- | --- | --- |
| Match what customers already rely on. Each vertical offers the capabilities its customers already rely on from their current provider (for example service pages, reviews and local marketing for auto repair; a secure client portal and newsletters for accountants; online ordering for restaurants) by building, embedding or connecting them. | Parity verification and governed connectors | Tenant-scoped end-to-end demonstration of the outcome |
| Approve parity matrices; demonstrate every built/embedded/connected capability. | parity_requirements, connector_capabilities; Vertical capability/readiness views | Migration/contracts, visible state and failure-path evidence |
| Safe, truthful AI behaviour where applicable | Evaluate vertical content; never claim unbuilt integrations | Approved context, verified side-effect receipts and evaluation results or justified N/A |
| Client can approve delivery | QA report, rollout evidence and named acceptance owner | Evidence links and dated client sign-off |

This section means requirements-to-implementation mapping. It does not mean language translation; source language obligations are tracked in their own requirements.

## Backend services

- [ ] Parity verification and governed connectors.
- [ ] Define request/response/event schemas, authorisation and input validation for each affected operation.
- [ ] For writes and provider effects, define idempotency, retry/timeout, receipts and reconciliation; document N/A where no side effects exist.
- [ ] Expose actionable status and scoped logs without secrets; distinguish completed, failed and uncertain outcomes.

## AI component

- [ ] Evaluate vertical content.
- [ ] never claim unbuilt integrations.
- [ ] Record instruction/knowledge/tool versions, measured quality, tenant scope, cost and safe fallback; a Markdown standard alone is not a passed evaluation.

## Testing / QA

- [ ] Exercise the intended user journey with real tenant-scoped state; cover forbidden role and cross-tenant requests.
- [ ] Test malformed inputs, provider failure, retries/replays and cancellation as applicable; keep deterministic mocks separate from live-provider evidence.
- [ ] Review desktop/mobile accessibility, factual copy and failure recovery in the delivered UI.
- [ ] Attach test environment, code/config/instruction versions, results and remaining defects to the acceptance report.

| Source test | Scenario | Required pass criteria | Current disposition |
| --- | --- | --- | --- |
| [AT-09](../../../requirements/AT.md#at-09) | Parity capabilities for the first packs | Each capability on the pack's parity list is present, embedded or connected and demonstrated with test data | Full source scenario not evidenced; client acceptance pending |

Source stories: [US-058](../../../requirements/US.md#us-058).

## Deployment

- [ ] Confirm approved hosting/database/provider architecture and required credentials in the deployment environment.
- [ ] Apply compatible migrations/configuration in staging, rehearse rollback, then promote the reviewed artifact.
- [ ] Verify the actual hosted workflow, monitoring, fallback and customer-visible errors after release.
- [ ] Update CODE_PROFILE.md, PROJECT_DATA_FLOW.md and CLIENT_TECHNICAL_QA.md in the application when behaviour or architecture changes.
- [ ] Record deployment identity, operator, timestamp and rollback evidence; document-only tickets instead record the reviewed Git commit.

## Source traceability

| Source ID | Mapping basis | Source section |
| --- | --- | --- |
| [AT-09](../../../requirements/AT.md#at-09) | Source-linked | 25.2 Acceptance tests |
| [BO-8](../../../requirements/BO.md#bo-8) | Source-linked | 3.1 Business objectives |
| [BO-10](../../../requirements/BO.md#bo-10) | Source-linked | 3.1 Business objectives |
| [BR-048](../../../requirements/BR.md#br-048) | Source-linked | 7.8 Suite, verticals and brands |
| [INT-002](../../../requirements/INT.md#int-002) | Source-linked | 19.10 Integration framework and vertical connectors (INT) |
| [US-058](../../../requirements/US.md#us-058) | Source-linked | EP-12 Verticals and brands |
| [VRT-003](../../../requirements/VRT.md#vrt-003) | Source-linked | 19.6 Brands and vertical packs (VRT) |
| [WEB-018](../../../requirements/WEB.md#web-018) | Source-linked | 18.3 Requirements |

Read every allocated record, including its continuation bullets and source variants. Source-linked rows preserve explicit document relationships; plan allocations are implementation responsibility assignments created during this review.

## Allocated specification checklist

The unchecked source obligations below require requirement-level evidence. They are deliberately separate from checked statements about current implemented slices. Read linked continuation bullets and additional source wording before accepting a record.

- [ ] [INT-002](../../../requirements/INT.md#int-002): INT-002 [P1] SHOULD maintain a connector catalog by vertical, in priority tiers with status (planned, beta, generally available). Candidates, each subject to confirmed access and terms before anything is promised to a client: auto repair (Tekmetric, Shop-Ware, Mitchell1, Shopmonkey and similar); home and urgent services (ServiceTitan, Housecall Pro, Jobber, FieldEdge); accounting (TaxDome, Canopy, Karbon, QuickBooks, Xero, SmartVault); law (Clio, MyCase, Lawmatics, Filevine); insurance (Applied Epic, EZLynx, HawkSoft, AMS360, AgencyZoom); dental (Dentrix, Eaglesoft, Open Dental); chiropractic (ChiroTouch); veterinary (Cornerstone, ezyVet, Shepherd, Neo); medical and med spa (Nextech, Zenoti, Boulevard); restaurants (Square, Toast, Clover). A connector appears in client-facing material only when it is generally available.
- [ ] [VRT-003](../../../requirements/VRT.md#vrt-003): VRT-003 [P1] MUST define a Vertical pack as a versioned data bundle containing: website templates and section variants; content library (service pages, FAQs, industry explanations); vocabulary and labels; intake playbooks and slot definitions; urgency, escalation and authority defaults; starter knowledge; greeting templates; the vertical's structured request schema (VRT-006); the compliance profile it requires (COM-014); the connector set it uses (INT-002); plans, entitlements and default terms; dashboard and report definitions; the onboarding checklist; and the migration playbooks for its conquest targets (MIG-010). Pack changes are versioned, staged, evaluated (EVL-005) and reversible.
- [ ] [WEB-018](../../../requirements/WEB.md#web-018): WEB-018 [P2] SHOULD provide vertical parity components per pack, delivered by building, embedding or connecting: accounting (secure client portal through a connector first; newsletters and tax-content library), auto repair (service pages, offers, review display), dental and medical (patient forms, scheduling embed), law (practice-area pages, intake forms), insurance (coverage pages, quote request), restaurants (ordering pages).

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
