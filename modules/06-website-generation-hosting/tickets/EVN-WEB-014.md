# EVN-WEB-014 - Private preview in minutes

Project: EverOnnAI. Module: [AI website generation, editing, publishing and domains](../README.md). Source business requirement [BR-014](../../../requirements/BR.md#br-014).

| Tracking dimension | Disposition |
| --- | --- |
| Engineering | Partial |
| QA | Existing checks are evidence for current slices; full ticket criteria remain pending |
| Deployment | Current local snapshot; verify ticket-specific hosted rollout and configuration |
| Business acceptance | Pending client review; no signed acceptance recorded |
| Owner | Frontend Lead + AI Lead + Platform Lead (proposed role; named person unassigned) |
| Priority / phase | Must / P1 |
| Estimate | TBD after scope/architecture agreement; no delivery date committed |
| Dependencies | [EVN-WEB-101](EVN-WEB-101.md), [EVN-WEB-102](EVN-WEB-102.md), [EVN-WEB-103](EVN-WEB-103.md) |

## Business deliverable

Private preview in minutes. Every client gets a professional, private website preview within minutes of claiming.

The client accepts the demonstrated outcome and evidence, rather than the existence of a route, table or screen. This ticket does not certify the whole source requirement as complete.

## Current implemented slice

- [x] Gemini writes multi-page HTML/CSS with private previews, bounded repairs and streamed progress.

## Remaining delivery checklist

- [ ] Add prospect claim/import, durable jobs, expiry and a measured two-minute target; review premium visual quality.

## Technical component

- [ ] Implement the module boundary and contracts for: Durable content/media/code/QA/preview workflow.
- [ ] Maintain tenant boundaries, explicit state transitions, access policy and failure handling for the delivered workflow.
- [ ] Resolve applicable architecture decisions before committing to a new provider or infrastructure baseline.

## DB

Existing module persistence: website_projects and immutable draft/live release snapshots in scoped workspace records.

The following records/contracts are proposed or require extension; their names are planning terms, not assertions that production tables exist.

- [ ] generation_jobs, draft_sites, preview_capabilities.
- [ ] Review scope keys, uniqueness, indexes, retention and migration compatibility; backfill safely and preserve existing tenant records.

## UI

- [ ] Three-field claim, progress, preview and claim highlights.
- [ ] Provide loading, empty, validation, permission-denied and recoverable failure states with keyboard and mobile access.
- [ ] Show observed facts and pending states accurately; do not present estimates, configured flags or mock results as confirmed business actions.

## Translate - business-to-technical mapping

| Business rule / outcome | Technical responsibility | Evidence needed |
| --- | --- | --- |
| Private preview in minutes. Every client gets a professional, private website preview within minutes of claiming. | Durable content/media/code/QA/preview workflow | Tenant-scoped end-to-end demonstration of the outcome |
| Add prospect claim/import, durable jobs, expiry and a measured two-minute target; review premium visual quality. | generation_jobs, draft_sites, preview_capabilities; Three-field claim, progress, preview and claim highlights | Migration/contracts, visible state and failure-path evidence |
| Safe, truthful AI behaviour where applicable | Original service-specific design guided by versioned skills and facts | Approved context, verified side-effect receipts and evaluation results or justified N/A |
| Client can approve delivery | QA report, rollout evidence and named acceptance owner | Evidence links and dated client sign-off |

This section means requirements-to-implementation mapping. It does not mean language translation; source language obligations are tracked in their own requirements.

## Backend services

- [ ] Durable content/media/code/QA/preview workflow.
- [ ] Define request/response/event schemas, authorisation and input validation for each affected operation.
- [ ] For writes and provider effects, define idempotency, retry/timeout, receipts and reconciliation; document N/A where no side effects exist.
- [ ] Expose actionable status and scoped logs without secrets; distinguish completed, failed and uncertain outcomes.

## AI component

- [ ] Original service-specific design guided by versioned skills and facts.
- [ ] Record instruction/knowledge/tool versions, measured quality, tenant scope, cost and safe fallback; a Markdown standard alone is not a passed evaluation.

## Testing / QA

- [ ] Exercise the intended user journey with real tenant-scoped state; cover forbidden role and cross-tenant requests.
- [ ] Test malformed inputs, provider failure, retries/replays and cancellation as applicable; keep deterministic mocks separate from live-provider evidence.
- [ ] Review desktop/mobile accessibility, factual copy and failure recovery in the delivered UI.
- [ ] Attach test environment, code/config/instruction versions, results and remaining defects to the acceptance report.

| Source test | Scenario | Required pass criteria | Current disposition |
| --- | --- | --- | --- |
| [AT-01](../../../requirements/AT.md#at-01) | Owner claims a business from a Google listing | Private preview and draft profile in under 2 minutes; page is not indexable; no real phone number shown; unverified claims are highlighted for the owner | Full source scenario not evidenced; client acceptance pending |

Source stories: [US-001](../../../requirements/US.md#us-001).

## Deployment

- [ ] Confirm approved hosting/database/provider architecture and required credentials in the deployment environment.
- [ ] Apply compatible migrations/configuration in staging, rehearse rollback, then promote the reviewed artifact.
- [ ] Verify the actual hosted workflow, monitoring, fallback and customer-visible errors after release.
- [ ] Update CODE_PROFILE.md, PROJECT_DATA_FLOW.md and CLIENT_TECHNICAL_QA.md in the application when behaviour or architecture changes.
- [ ] Record deployment identity, operator, timestamp and rollback evidence; document-only tickets instead record the reviewed Git commit.

## Source traceability

| Source ID | Mapping basis | Source section |
| --- | --- | --- |
| [AT-01](../../../requirements/AT.md#at-01) | Source-linked | 25.2 Acceptance tests |
| [BO-2](../../../requirements/BO.md#bo-2) | Source-linked | 3.1 Business objectives |
| [BR-014](../../../requirements/BR.md#br-014) | Source-linked | 7.3 Websites |
| [BRL-006](../../../requirements/BRL.md#brl-006) | Plan allocation / source cross-reference | 8. Business rules |
| [BRL-017](../../../requirements/BRL.md#brl-017) | Plan allocation / source cross-reference | 8. Business rules |
| [BRL-021](../../../requirements/BRL.md#brl-021) | Plan allocation / source cross-reference | 8. Business rules |
| [ONB-001](../../../requirements/ONB.md#onb-001) | Source-linked | 12.2 Requirements |
| [SL-07](../../../requirements/SL.md#sl-07) | Plan allocation / source cross-reference | 10.1 Service levels |
| [US-001](../../../requirements/US.md#us-001) | Source-linked | EP-01 Onboarding and claim |
| [WEB-001](../../../requirements/WEB.md#web-001) | Source-linked | 18.3 Requirements |
| [WEB-002](../../../requirements/WEB.md#web-002) | Source-linked | 18.3 Requirements |
| [WEB-003](../../../requirements/WEB.md#web-003) | Source-linked | 18.3 Requirements |

Read every allocated record, including its continuation bullets and source variants. Source-linked rows preserve explicit document relationships; plan allocations are implementation responsibility assignments created during this review.

## Allocated specification checklist

The unchecked source obligations below require requirement-level evidence. They are deliberately separate from checked statements about current implemented slices. Read linked continuation bullets and additional source wording before accepting a record.

- [ ] [BRL-006](../../../requirements/BRL.md#brl-006): BRL-006 | A preview site stays private, and shows no real phone number, until ownership is verified and the owner approves. | Website engine | ONB-002, WEB-003.
- [ ] [BRL-017](../../../requirements/BRL.md#brl-017): BRL-017 | EverOnn provides technology, not the client's trade services; terms and site copy say so. | Legal, websites | COM-006, WEB-002.
- [ ] [BRL-021](../../../requirements/BRL.md#brl-021): BRL-021 | Generated website content contains no unverified claims (reviews, licenses, awards, prices). | Website engine | WEB-002.
- [ ] [ONB-001](../../../requirements/ONB.md#onb-001): ONB-001 [P1] MUST implement the claim flow: input business name plus phone or website or Google listing link; system resolves the business, generates a private preview site (WEB-001) and a draft business profile within 2 minutes (target), then captures email or SMS to claim. Mobile thumb-friendly; at most 3 fields on the first screen.
- [ ] [SL-07](../../../requirements/SL.md#sl-07): SL-07 | Private website preview | Under 2 minutes (target, decision D-21).
- [ ] [WEB-001](../../../requirements/WEB.md#web-001): WEB-001 [P1] MUST implement the generation pipeline as durable jobs: (1) data collection (profile, imported content), (2) content generation with schema-constrained LLM output and brand/tone controls, (3) image selection or generation from licensed sources and the owner's photos (P1: owner photos, licensed stock; generated imagery only where licensing and disclosure rules are met), (4) Site Spec validation and safety checks (no invented licenses, awards, or claims), (5) render, (6) preview deployment. Target: under 2 minutes p50 to preview; throughput target 1,000 sites/day sustained with burst to 300 per hour (P2), with per-site LLM cost tracked and capped.
- [ ] [WEB-002](../../../requirements/WEB.md#web-002): WEB-002 [P1] MUST ensure content claim safety: the generator MUST NOT fabricate reviews, certifications, years in business, service guarantees, or prices. Any claim must trace to a source field or be flagged for owner confirmation. Preview shows "unverified claims" highlights the owner must resolve.
- [ ] [WEB-003](../../../requirements/WEB.md#web-003): WEB-003 [P1] MUST keep previews private and non-indexable (noindex, unguessable URLs, no real phone or address exposure per ONB-002) until verification and owner approval; preview TTL and cleanup jobs apply to unclaimed prospects.

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

Dependencies: [EVN-WEB-101](EVN-WEB-101.md), [EVN-WEB-102](EVN-WEB-102.md), [EVN-WEB-103](EVN-WEB-103.md). A blocked prerequisite can be prototyped independently, but its contract and deployment must be approved before claiming this ticket delivered. Service limits, third-party approvals and staffing are evidence requirements, not assumptions that they are available.

## Handover and client acceptance

- [ ] Attach the business demonstration, technical evidence and operating/recovery instructions.
- [ ] Assign a named acceptance owner and agree any deferred criteria with the client in writing.
- [ ] Resolve launch-blocking defects and document accepted residual risks.
- [ ] Client records dated acceptance against the deployed/documented version.

Use [the acceptance protocol](../../../ACCEPTANCE.md) and [the ticket update rules](../../../TICKET_TEMPLATE.md) when changing status.
