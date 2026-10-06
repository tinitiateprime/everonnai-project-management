# EVN-WEB-103 - Serve tenant websites with isolated domains, immutable assets and fast recovery

Project: EverOnnAI. Module: [AI website generation, editing, publishing and domains](../README.md). Technical delivery enabler allocated by this plan; source references below.

| Tracking dimension | Disposition |
| --- | --- |
| Engineering | Planned |
| QA | Existing checks are evidence for current slices; full ticket criteria remain pending |
| Deployment | Current local snapshot; verify ticket-specific hosted rollout and configuration |
| Business acceptance | Pending client review; no signed acceptance recorded |
| Owner | Frontend Lead + AI Lead + Platform Lead (proposed role; named person unassigned) |
| Priority / phase | Delivery enabler / P1 |
| Estimate | TBD after scope/architecture agreement; no delivery date committed |
| Dependencies | [EVN-FND-101](../../00-foundations-governance/tickets/EVN-FND-101.md), [EVN-WEB-101](EVN-WEB-101.md) |

## Business deliverable

Serve tenant websites with isolated domains, immutable assets and fast recovery.

The client accepts the demonstrated outcome and evidence, rather than the existence of a route, table or screen. This ticket does not certify the whole source requirement as complete.

## Current implemented slice

- [ ] Application-path publishing is implemented.

The current statement describes prerequisites or context; this business deliverable has not been demonstrated.

## Remaining delivery checklist

- [ ] Approve the edge architecture, separate registrable domain, immutable bundles, purge/rollback, malware-safe image pipeline and canary rollouts.

## Technical component

- [ ] Implement the module boundary and contracts for: Object storage, edge router, TLS, cache purge and image processing.
- [ ] Maintain tenant boundaries, explicit state transitions, access policy and failure handling for the delivered workflow.
- [ ] Resolve applicable architecture decisions before committing to a new provider or infrastructure baseline.

## DB

Existing module persistence: website_projects and immutable draft/live release snapshots in scoped workspace records.

The following records/contracts are proposed or require extension; their names are planning terms, not assertions that production tables exist.

- [ ] domain maps, bundles, asset hashes, CDN release metadata.
- [ ] Review scope keys, uniqueness, indexes, retention and migration compatibility; backfill safely and preserve existing tenant records.

## UI

- [ ] Domain/asset health and release previews.
- [ ] Provide loading, empty, validation, permission-denied and recoverable failure states with keyboard and mobile access.
- [ ] Show observed facts and pending states accurately; do not present estimates, configured flags or mock results as confirmed business actions.

## Translate - business-to-technical mapping

| Business rule / outcome | Technical responsibility | Evidence needed |
| --- | --- | --- |
| Serve tenant websites with isolated domains, immutable assets and fast recovery. | Object storage, edge router, TLS, cache purge and image processing | Tenant-scoped end-to-end demonstration of the outcome |
| Approve the edge architecture, separate registrable domain, immutable bundles, purge/rollback, malware-safe image pipeline and canary rollouts. | domain maps, bundles, asset hashes, CDN release metadata; Domain/asset health and release previews | Migration/contracts, visible state and failure-path evidence |
| Safe, truthful AI behaviour where applicable | Model output remains sanitised; no arbitrary tenant JavaScript | Approved context, verified side-effect receipts and evaluation results or justified N/A |
| Client can approve delivery | QA report, rollout evidence and named acceptance owner | Evidence links and dated client sign-off |

This section means requirements-to-implementation mapping. It does not mean language translation; source language obligations are tracked in their own requirements.

## Backend services

- [ ] Object storage, edge router, TLS, cache purge and image processing.
- [ ] Define request/response/event schemas, authorisation and input validation for each affected operation.
- [ ] For writes and provider effects, define idempotency, retry/timeout, receipts and reconciliation; document N/A where no side effects exist.
- [ ] Expose actionable status and scoped logs without secrets; distinguish completed, failed and uncertain outcomes.

## AI component

- [ ] Model output remains sanitised.
- [ ] no arbitrary tenant JavaScript.
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
| [SL-08](../../../requirements/SL.md#sl-08) | Plan allocation / source cross-reference | 10.1 Service levels |
| [WEB-005](../../../requirements/WEB.md#web-005) | Source-linked | 18.3 Requirements |
| [WEB-009](../../../requirements/WEB.md#web-009) | Source-linked | 18.3 Requirements |
| [WEB-014](../../../requirements/WEB.md#web-014) | Source-linked | 18.3 Requirements |
| [WEB-017](../../../requirements/WEB.md#web-017) | Source-linked | 18.3 Requirements |

Read every allocated record, including its continuation bullets and source variants. Source-linked rows preserve explicit document relationships; plan allocations are implementation responsibility assignments created during this review.

## Allocated specification checklist

The unchecked source obligations below require requirement-level evidence. They are deliberately separate from checked statements about current implemented slices. Read linked continuation bullets and additional source wording before accepting a record.

- [ ] [SL-08](../../../requirements/SL.md#sl-08): SL-08 | Client websites | 99.95% availability per month.
- [ ] [WEB-005](../../../requirements/WEB.md#web-005): WEB-005 [P1] MUST serve tenant sites on a separate registrable domain from EverOnn's own application and marketing domains (for example everonn.site), so cookies, XSS blast radius, email reputation and SEO reputation are isolated.
- [ ] [WEB-009](../../../requirements/WEB.md#web-009): WEB-009 [P1] MUST sanitize all tenant-supplied content and enforce a strict Content Security Policy on tenant sites; tenant scripts and arbitrary embeds are prohibited at P1 (allow-listed embeds such as Google Maps only).
- [ ] [WEB-014](../../../requirements/WEB.md#web-014): WEB-014 [P1] MUST implement CDN and cache strategy: immutable hashed assets, short HTML TTL with instant purge on publish, stale-while-revalidate, and origin shielding; the origin holds no per-request state.
- [ ] [WEB-017](../../../requirements/WEB.md#web-017): WEB-017 [P1] MUST publish sites under the client's own domain, with brand-specific preview and staging hosts and brand-specific legal pages, and a per-brand, per-plan option for a "powered by" credit; no page may give a misleading impression about the provider or its independence (BRL-032).

## Existing code / check evidence

- `features/website-studio/ai-generator.ts` - inspected current application working tree; see [snapshot evidence](../../../EVIDENCE.md).
- `features/website-studio/code-generator.ts` - inspected current application working tree; see [snapshot evidence](../../../EVIDENCE.md).
- `features/website-studio/code-validation.ts` - inspected current application working tree; see [snapshot evidence](../../../EVIDENCE.md).
- `features/website-studio/progress.ts` - inspected current application working tree; see [snapshot evidence](../../../EVIDENCE.md).
- `features/website-studio/releases.ts` - inspected current application working tree; see [snapshot evidence](../../../EVIDENCE.md).
- `features/website-studio/media.ts` - inspected current application working tree; see [snapshot evidence](../../../EVIDENCE.md).
- `app/api/website-studio/route.ts` - inspected current application working tree; see [snapshot evidence](../../../EVIDENCE.md).
- `app/api/website-studio/status/route.ts` - inspected current application working tree; see [snapshot evidence](../../../EVIDENCE.md).
- `components/preview/website-page.tsx` - inspected current application working tree; see [snapshot evidence](../../../EVIDENCE.md).
- `components/preview/legacy-website-preview.tsx` - inspected current application working tree; see [snapshot evidence](../../../EVIDENCE.md).
- Relevant automated checks: `tests/website-ai.test.ts`, `tests/website-code.test.ts`, `tests/website-media.test.ts`, `scripts/smoke-hvac.ts`, `scripts/verify-website-live.ts`. Their scope is bounded by [current validation](../../../CURRENT_STATE.md).

## Blockers and boundaries

Module risk: Synchronous generation can exceed host limits; premium visuals, ownership verification, domains/TLS and scale are not established by parser tests.

Dependencies: [EVN-FND-101](../../00-foundations-governance/tickets/EVN-FND-101.md), [EVN-WEB-101](EVN-WEB-101.md). A blocked prerequisite can be prototyped independently, but its contract and deployment must be approved before claiming this ticket delivered. Service limits, third-party approvals and staffing are evidence requirements, not assumptions that they are available.

## Handover and client acceptance

- [ ] Attach the business demonstration, technical evidence and operating/recovery instructions.
- [ ] Assign a named acceptance owner and agree any deferred criteria with the client in writing.
- [ ] Resolve launch-blocking defects and document accepted residual risks.
- [ ] Client records dated acceptance against the deployed/documented version.

Use [the acceptance protocol](../../../ACCEPTANCE.md) and [the ticket update rules](../../../TICKET_TEMPLATE.md) when changing status.
