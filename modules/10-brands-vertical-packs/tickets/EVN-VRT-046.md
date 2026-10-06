# EVN-VRT-046 - Launch a vertical by configuration

Project: EverOnnAI. Module: [Vertical brands, packs, readiness and capability parity](../README.md). Source business requirement [BR-046](../../../requirements/BR.md#br-046).

| Tracking dimension | Disposition |
| --- | --- |
| Engineering | Partial |
| QA | Existing checks are evidence for current slices; full ticket criteria remain pending |
| Deployment | Current local snapshot; verify ticket-specific hosted rollout and configuration |
| Business acceptance | Pending client review; no signed acceptance recorded |
| Owner | Vertical Manager + Product Owner + Counsel (proposed role; named person unassigned) |
| Priority / phase | Must / P1 |
| Estimate | TBD after scope/architecture agreement; no delivery date committed |
| Dependencies | [EVN-ONB-102](../../01-onboarding-tenancy-identity/tickets/EVN-ONB-102.md), [EVN-AIQ-104](../../03-ai-governance-evaluation/tickets/EVN-AIQ-104.md) |

## Business deliverable

Launch a vertical by configuration. A new industry can be launched from a configuration bundle (site templates, content, intake playbooks, starter knowledge, compliance profile, integrations, plans and terms) without new platform development for standard cases.

The client accepts the demonstrated outcome and evidence, rather than the existence of a route, table or screen. This ticket does not certify the whole source requirement as complete.

## Current implemented slice

- [x] Versioned shared/capability/HVAC Markdown uses an allowlisted registry.

## Remaining delivery checklist

- [ ] Extend to data packs with schemas, playbooks, knowledge, compliance, plans/legal content and config-only rollout.

## Technical component

- [ ] Implement the module boundary and contracts for: Pack loader/validator and versioned rollout.
- [ ] Maintain tenant boundaries, explicit state transitions, access policy and failure handling for the delivered workflow.
- [ ] Resolve applicable architecture decisions before committing to a new provider or infrastructure baseline.

## DB

Existing module persistence: Explicit skillId/domain selection and generation skill traces; no first-class brand/pack governance tables.

The following records/contracts are proposed or require extension; their names are planning terms, not assertions that production tables exist.

- [ ] vertical_packs, pack_versions, pack_bindings.
- [ ] Review scope keys, uniqueness, indexes, retention and migration compatibility; backfill safely and preserve existing tenant records.

## UI

- [ ] Pack configuration and preview.
- [ ] Provide loading, empty, validation, permission-denied and recoverable failure states with keyboard and mobile access.
- [ ] Show observed facts and pending states accurately; do not present estimates, configured flags or mock results as confirmed business actions.

## Translate - business-to-technical mapping

| Business rule / outcome | Technical responsibility | Evidence needed |
| --- | --- | --- |
| Launch a vertical by configuration. A new industry can be launched from a configuration bundle (site templates, content, intake playbooks, starter knowledge, compliance profile, integrations, plans and terms) without new platform development for standard cases. | Pack loader/validator and versioned rollout | Tenant-scoped end-to-end demonstration of the outcome |
| Extend to data packs with schemas, playbooks, knowledge, compliance, plans/legal content and config-only rollout. | vertical_packs, pack_versions, pack_bindings; Pack configuration and preview | Migration/contracts, visible state and failure-path evidence |
| Safe, truthful AI behaviour where applicable | Service-specific skills/intake; repository docs are not executable packs | Approved context, verified side-effect receipts and evaluation results or justified N/A |
| Client can approve delivery | QA report, rollout evidence and named acceptance owner | Evidence links and dated client sign-off |

This section means requirements-to-implementation mapping. It does not mean language translation; source language obligations are tracked in their own requirements.

## Backend services

- [ ] Pack loader/validator and versioned rollout.
- [ ] Define request/response/event schemas, authorisation and input validation for each affected operation.
- [ ] For writes and provider effects, define idempotency, retry/timeout, receipts and reconciliation; document N/A where no side effects exist.
- [ ] Expose actionable status and scoped logs without secrets; distinguish completed, failed and uncertain outcomes.

## AI component

- [ ] Service-specific skills/intake.
- [ ] repository docs are not executable packs.
- [ ] Record instruction/knowledge/tool versions, measured quality, tenant scope, cost and safe fallback; a Markdown standard alone is not a passed evaluation.

## Testing / QA

- [ ] Exercise the intended user journey with real tenant-scoped state; cover forbidden role and cross-tenant requests.
- [ ] Test malformed inputs, provider failure, retries/replays and cancellation as applicable; keep deterministic mocks separate from live-provider evidence.
- [ ] Review desktop/mobile accessibility, factual copy and failure recovery in the delivered UI.
- [ ] Attach test environment, code/config/instruction versions, results and remaining defects to the acceptance report.

| Source test | Scenario | Required pass criteria | Current disposition |
| --- | --- | --- | --- |
| [AT-07](../../../requirements/AT.md#at-07) | Configure a new vertical pack from the template | A test vertical is created from the pack template (site, playbooks, knowledge, plans, terms) and reaches the readiness gate without platform code changes; elapsed time is recorded | Full source scenario not evidenced; client acceptance pending |

Source stories: [US-055](../../../requirements/US.md#us-055).

## Deployment

- [ ] Confirm approved hosting/database/provider architecture and required credentials in the deployment environment.
- [ ] Apply compatible migrations/configuration in staging, rehearse rollback, then promote the reviewed artifact.
- [ ] Verify the actual hosted workflow, monitoring, fallback and customer-visible errors after release.
- [ ] Update CODE_PROFILE.md, PROJECT_DATA_FLOW.md and CLIENT_TECHNICAL_QA.md in the application when behaviour or architecture changes.
- [ ] Record deployment identity, operator, timestamp and rollback evidence; document-only tickets instead record the reviewed Git commit.

## Source traceability

| Source ID | Mapping basis | Source section |
| --- | --- | --- |
| [AT-07](../../../requirements/AT.md#at-07) | Source-linked | 25.2 Acceptance tests |
| [BO-11](../../../requirements/BO.md#bo-11) | Source-linked | 3.1 Business objectives |
| [BR-046](../../../requirements/BR.md#br-046) | Source-linked | 7.8 Suite, verticals and brands |
| [US-055](../../../requirements/US.md#us-055) | Source-linked | EP-12 Verticals and brands |
| [VRT-003](../../../requirements/VRT.md#vrt-003) | Source-linked | 19.6 Brands and vertical packs (VRT) |
| [VRT-004](../../../requirements/VRT.md#vrt-004) | Source-linked | 19.6 Brands and vertical packs (VRT) |
| [VRT-006](../../../requirements/VRT.md#vrt-006) | Source-linked | 19.6 Brands and vertical packs (VRT) |
| [VRT-010](../../../requirements/VRT.md#vrt-010) | Plan allocation / source cross-reference | 19.6 Brands and vertical packs (VRT) |
| [WEB-016](../../../requirements/WEB.md#web-016) | Source-linked | 18.3 Requirements |

Read every allocated record, including its continuation bullets and source variants. Source-linked rows preserve explicit document relationships; plan allocations are implementation responsibility assignments created during this review.

## Allocated specification checklist

The unchecked source obligations below require requirement-level evidence. They are deliberately separate from checked statements about current implemented slices. Read linked continuation bullets and additional source wording before accepting a record.

- [ ] [VRT-003](../../../requirements/VRT.md#vrt-003): VRT-003 [P1] MUST define a Vertical pack as a versioned data bundle containing: website templates and section variants; content library (service pages, FAQs, industry explanations); vocabulary and labels; intake playbooks and slot definitions; urgency, escalation and authority defaults; starter knowledge; greeting templates; the vertical's structured request schema (VRT-006); the compliance profile it requires (COM-014); the connector set it uses (INT-002); plans, entitlements and default terms; dashboard and report definitions; the onboarding checklist; and the migration playbooks for its conquest targets (MIG-010). Pack changes are versioned, staged, evaluated (EVL-005) and reversible.
- [ ] [VRT-004](../../../requirements/VRT.md#vrt-004): VRT-004 [P1] MUST support at least two brands and two packs live on one platform at the pilot, and MUST allow a new brand or pack to be added by configuration and content alone for standard cases, without changes to platform code. The elapsed time to create a new standard pack is measured and reported.
- [ ] [VRT-006](../../../requirements/VRT.md#vrt-006): VRT-006 [P1] MUST support vertical-specific structured data without schema changes: each pack declares the fields of its request object (for example vehicle details for auto repair, entity type and tax years for accounting, an order for a restaurant) in a JSON Schema; the platform validates, stores, displays, searches and reports on them.
- [ ] [VRT-010](../../../requirements/VRT.md#vrt-010): VRT-010 [P1] MUST support pack governance: an owner (vertical manager) per pack, a change log, a review calendar for time-sensitive content (market prices, regulatory notes), and metrics per pack (time to launch, activation, retention, cost to serve, escalation rate).
- [ ] [WEB-016](../../../requirements/WEB.md#web-016): WEB-016 [P1] MUST provide vertical site templates and content libraries per pack (section variants, vocabulary, trust elements, service pages); the generation pipeline uses the pack's knowledge, and every generated claim remains subject to WEB-002.

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
