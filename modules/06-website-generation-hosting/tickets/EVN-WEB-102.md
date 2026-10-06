# EVN-WEB-102 - Approve a premium service-specific website before replacing the saved live site

Project: EverOnnAI. Module: [AI website generation, editing, publishing and domains](../README.md). Technical delivery enabler allocated by this plan; source references below.

| Tracking dimension | Disposition |
| --- | --- |
| Engineering | Partial |
| QA | Existing checks are evidence for current slices; full ticket criteria remain pending |
| Deployment | Current local snapshot; verify ticket-specific hosted rollout and configuration |
| Business acceptance | Pending client review; no signed acceptance recorded |
| Owner | Frontend Lead + AI Lead + Platform Lead (proposed role; named person unassigned) |
| Priority / phase | Delivery enabler / P1 |
| Estimate | TBD after scope/architecture agreement; no delivery date committed |
| Dependencies | [EVN-AIQ-104](../../03-ai-governance-evaluation/tickets/EVN-AIQ-104.md), [EVN-WEB-101](EVN-WEB-101.md) |

## Business deliverable

Approve a premium service-specific website before replacing the saved live site.

The client accepts the demonstrated outcome and evidence, rather than the existence of a route, table or screen. This ticket does not certify the whole source requirement as complete.

## Current implemented slice

- [x] New generation is original HTML/CSS; saved older publications retain a compatibility renderer.

## Remaining delivery checklist

- [ ] Define an art-direction brief and visual rubric; review real desktop/mobile drafts; publish only after factual/design/owner gates.

## Technical component

- [ ] Implement the module boundary and contracts for: Visual validation, release snapshots and safe rollback.
- [ ] Maintain tenant boundaries, explicit state transitions, access policy and failure handling for the delivered workflow.
- [ ] Resolve applicable architecture decisions before committing to a new provider or infrastructure baseline.

## DB

Existing module persistence: website_projects and immutable draft/live release snapshots in scoped workspace records.

The following records/contracts are proposed or require extension; their names are planning terms, not assertions that production tables exist.

- [ ] visual_reports, review_signoffs, website_releases.
- [ ] Review scope keys, uniqueness, indexes, retention and migration compatibility; backfill safely and preserve existing tenant records.

## UI

- [ ] Design review, change requests and actual draft/live comparison.
- [ ] Provide loading, empty, validation, permission-denied and recoverable failure states with keyboard and mobile access.
- [ ] Show observed facts and pending states accurately; do not present estimates, configured flags or mock results as confirmed business actions.

## Translate - business-to-technical mapping

| Business rule / outcome | Technical responsibility | Evidence needed |
| --- | --- | --- |
| Approve a premium service-specific website before replacing the saved live site. | Visual validation, release snapshots and safe rollback | Tenant-scoped end-to-end demonstration of the outcome |
| Define an art-direction brief and visual rubric; review real desktop/mobile drafts; publish only after factual/design/owner gates. | visual_reports, review_signoffs, website_releases; Design review, change requests and actual draft/live comparison | Migration/contracts, visible state and failure-path evidence |
| Safe, truthful AI behaviour where applicable | Curated imagery/typography and visual revision; no fixed layout requirement from the user | Approved context, verified side-effect receipts and evaluation results or justified N/A |
| Client can approve delivery | QA report, rollout evidence and named acceptance owner | Evidence links and dated client sign-off |

This section means requirements-to-implementation mapping. It does not mean language translation; source language obligations are tracked in their own requirements.

## Backend services

- [ ] Visual validation, release snapshots and safe rollback.
- [ ] Define request/response/event schemas, authorisation and input validation for each affected operation.
- [ ] For writes and provider effects, define idempotency, retry/timeout, receipts and reconciliation; document N/A where no side effects exist.
- [ ] Expose actionable status and scoped logs without secrets; distinguish completed, failed and uncertain outcomes.

## AI component

- [ ] Curated imagery/typography and visual revision.
- [ ] no fixed layout requirement from the user.
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
| [BRL-017](../../../requirements/BRL.md#brl-017) | Plan allocation / source cross-reference | 8. Business rules |
| [BRL-021](../../../requirements/BRL.md#brl-021) | Plan allocation / source cross-reference | 8. Business rules |
| [SCF-023](../../../requirements/SCF.md#scf-023) | Plan allocation / source cross-reference | 22.3 Scaffolding checklist |
| [WEB-002](../../../requirements/WEB.md#web-002) | Source-linked | 18.3 Requirements |
| [WEB-008](../../../requirements/WEB.md#web-008) | Source-linked | 18.3 Requirements |
| [WEB-012](../../../requirements/WEB.md#web-012) | Source-linked | 18.3 Requirements |
| [WEB-015](../../../requirements/WEB.md#web-015) | Plan allocation / source cross-reference | 18.3 Requirements |
| [WEB-016](../../../requirements/WEB.md#web-016) | Source-linked | 18.3 Requirements |

Read every allocated record, including its continuation bullets and source variants. Source-linked rows preserve explicit document relationships; plan allocations are implementation responsibility assignments created during this review.

## Allocated specification checklist

The unchecked source obligations below require requirement-level evidence. They are deliberately separate from checked statements about current implemented slices. Read linked continuation bullets and additional source wording before accepting a record.

- [ ] [BRL-017](../../../requirements/BRL.md#brl-017): BRL-017 | EverOnn provides technology, not the client's trade services; terms and site copy say so. | Legal, websites | COM-006, WEB-002.
- [ ] [BRL-021](../../../requirements/BRL.md#brl-021): BRL-021 | Generated website content contains no unverified claims (reviews, licenses, awards, prices). | Website engine | WEB-002.
- [ ] [SCF-023](../../../requirements/SCF.md#scf-023): 23 | Site Spec schema and component versioning | Bulk template upgrades, new verticals, white-label themes.
- [ ] [WEB-002](../../../requirements/WEB.md#web-002): WEB-002 [P1] MUST ensure content claim safety: the generator MUST NOT fabricate reviews, certifications, years in business, service guarantees, or prices. Any claim must trace to a source field or be flagged for owner confirmation. Preview shows "unverified claims" highlights the owner must resolve.
- [ ] [WEB-008](../../../requirements/WEB.md#web-008): WEB-008 [P1] MUST provide a simple owner editor: edit text, hours, services, photos, colors, and reorder sections in the dashboard; changes create a new version; publish and rollback. No raw HTML editing by tenants at P1 (security).
- [ ] [WEB-012](../../../requirements/WEB.md#web-012): WEB-012 [P2] SHOULD provide multi-page vertical templates (service pages, city/area pages generated from service-area data with quality thresholds to avoid thin or duplicate content; the studio MUST document a policy to avoid search-spam patterns).
- [ ] [WEB-015](../../../requirements/WEB.md#web-015): WEB-015 [P2] SHOULD support i18n (English and Spanish first) at the Site Spec level.
- [ ] [WEB-016](../../../requirements/WEB.md#web-016): WEB-016 [P1] MUST provide vertical site templates and content libraries per pack (section variants, vocabulary, trust elements, service pages); the generation pipeline uses the pack's knowledge, and every generated claim remains subject to WEB-002.

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

Dependencies: [EVN-AIQ-104](../../03-ai-governance-evaluation/tickets/EVN-AIQ-104.md), [EVN-WEB-101](EVN-WEB-101.md). A blocked prerequisite can be prototyped independently, but its contract and deployment must be approved before claiming this ticket delivered. Service limits, third-party approvals and staffing are evidence requirements, not assumptions that they are available.

## Handover and client acceptance

- [ ] Attach the business demonstration, technical evidence and operating/recovery instructions.
- [ ] Assign a named acceptance owner and agree any deferred criteria with the client in writing.
- [ ] Resolve launch-blocking defects and document accepted residual risks.
- [ ] Client records dated acceptance against the deployed/documented version.

Use [the acceptance protocol](../../../ACCEPTANCE.md) and [the ticket update rules](../../../TICKET_TEMPLATE.md) when changing status.
