# EVN-WEB-019 - Prevent fake or abusive sites

Project: EverOnnAI. Module: [AI website generation, editing, publishing and domains](../README.md). Source business requirement [BR-019](../../../requirements/BR.md#br-019).

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

Prevent fake or abusive sites. Fake, impersonating or abusive sites cannot go public, and generated content contains no unverified claims.

The client accepts the demonstrated outcome and evidence, rather than the existence of a route, table or screen. This ticket does not certify the whole source requirement as complete.

## Current implemented slice

- [x] Validation rejects unsafe execution, unsupported routes/assets and invented business claims.

## Remaining delivery checklist

- [ ] Add independent ownership proof, prohibited-category rules, impersonation detection, abuse reports and takedown.

## Technical component

- [ ] Implement the module boundary and contracts for: Eligibility, publication checks and takedown service.
- [ ] Maintain tenant boundaries, explicit state transitions, access policy and failure handling for the delivered workflow.
- [ ] Resolve applicable architecture decisions before committing to a new provider or infrastructure baseline.

## DB

Existing module persistence: website_projects and immutable draft/live release snapshots in scoped workspace records.

The following records/contracts are proposed or require extension; their names are planning terms, not assertions that production tables exist.

- [ ] abuse_reports, claims_provenance, takedowns.
- [ ] Review scope keys, uniqueness, indexes, retention and migration compatibility; backfill safely and preserve existing tenant records.

## UI

- [ ] Unverified-claim highlights and abuse review.
- [ ] Provide loading, empty, validation, permission-denied and recoverable failure states with keyboard and mobile access.
- [ ] Show observed facts and pending states accurately; do not present estimates, configured flags or mock results as confirmed business actions.

## Translate - business-to-technical mapping

| Business rule / outcome | Technical responsibility | Evidence needed |
| --- | --- | --- |
| Prevent fake or abusive sites. Fake, impersonating or abusive sites cannot go public, and generated content contains no unverified claims. | Eligibility, publication checks and takedown service | Tenant-scoped end-to-end demonstration of the outcome |
| Add independent ownership proof, prohibited-category rules, impersonation detection, abuse reports and takedown. | abuse_reports, claims_provenance, takedowns; Unverified-claim highlights and abuse review | Migration/contracts, visible state and failure-path evidence |
| Safe, truthful AI behaviour where applicable | Claim source tracing and reviewed unsafe-output rejection | Approved context, verified side-effect receipts and evaluation results or justified N/A |
| Client can approve delivery | QA report, rollout evidence and named acceptance owner | Evidence links and dated client sign-off |

This section means requirements-to-implementation mapping. It does not mean language translation; source language obligations are tracked in their own requirements.

## Backend services

- [ ] Eligibility, publication checks and takedown service.
- [ ] Define request/response/event schemas, authorisation and input validation for each affected operation.
- [ ] For writes and provider effects, define idempotency, retry/timeout, receipts and reconciliation; document N/A where no side effects exist.
- [ ] Expose actionable status and scoped logs without secrets; distinguish completed, failed and uncertain outcomes.

## AI component

- [ ] Claim source tracing and reviewed unsafe-output rejection.
- [ ] Record instruction/knowledge/tool versions, measured quality, tenant scope, cost and safe fallback; a Markdown standard alone is not a passed evaluation.

## Testing / QA

- [ ] Exercise the intended user journey with real tenant-scoped state; cover forbidden role and cross-tenant requests.
- [ ] Test malformed inputs, provider failure, retries/replays and cancellation as applicable; keep deterministic mocks separate from live-provider evidence.
- [ ] Review desktop/mobile accessibility, factual copy and failure recovery in the delivered UI.
- [ ] Attach test environment, code/config/instruction versions, results and remaining defects to the acceptance report.

| Source test | Scenario | Required pass criteria | Current disposition |
| --- | --- | --- | --- |
| [AT-01](../../../requirements/AT.md#at-01) | Owner claims a business from a Google listing | Private preview and draft profile in under 2 minutes; page is not indexable; no real phone number shown; unverified claims are highlighted for the owner | Full source scenario not evidenced; client acceptance pending |
| [AT-05](../../../requirements/AT.md#at-05) | Bulk generation at 1,000 sites per day with bursts of 300 per hour | Throughput met; per-site cost tracked; prohibited categories blocked | Full source scenario not evidenced; client acceptance pending |

Source stories: [US-002](../../../requirements/US.md#us-002), [US-039](../../../requirements/US.md#us-039).

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
| [AT-05](../../../requirements/AT.md#at-05) | Source-linked | 25.2 Acceptance tests |
| [BO-7](../../../requirements/BO.md#bo-7) | Source-linked | 3.1 Business objectives |
| [BR-019](../../../requirements/BR.md#br-019) | Source-linked | 7.3 Websites |
| [BRL-006](../../../requirements/BRL.md#brl-006) | Plan allocation / source cross-reference | 8. Business rules |
| [BRL-017](../../../requirements/BRL.md#brl-017) | Plan allocation / source cross-reference | 8. Business rules |
| [BRL-021](../../../requirements/BRL.md#brl-021) | Plan allocation / source cross-reference | 8. Business rules |
| [ONB-002](../../../requirements/ONB.md#onb-002) | Source-linked | 12.2 Requirements |
| [US-002](../../../requirements/US.md#us-002) | Source-linked | EP-01 Onboarding and claim |
| [US-039](../../../requirements/US.md#us-039) | Source-linked | EP-07 Websites |
| [WEB-002](../../../requirements/WEB.md#web-002) | Source-linked | 18.3 Requirements |
| [WEB-005](../../../requirements/WEB.md#web-005) | Source-linked | 18.3 Requirements |
| [WEB-013](../../../requirements/WEB.md#web-013) | Source-linked | 18.3 Requirements |

Read every allocated record, including its continuation bullets and source variants. Source-linked rows preserve explicit document relationships; plan allocations are implementation responsibility assignments created during this review.

## Allocated specification checklist

The unchecked source obligations below require requirement-level evidence. They are deliberately separate from checked statements about current implemented slices. Read linked continuation bullets and additional source wording before accepting a record.

- [ ] [BRL-006](../../../requirements/BRL.md#brl-006): BRL-006 | A preview site stays private, and shows no real phone number, until ownership is verified and the owner approves. | Website engine | ONB-002, WEB-003.
- [ ] [BRL-017](../../../requirements/BRL.md#brl-017): BRL-017 | EverOnn provides technology, not the client's trade services; terms and site copy say so. | Legal, websites | COM-006, WEB-002.
- [ ] [BRL-021](../../../requirements/BRL.md#brl-021): BRL-021 | Generated website content contains no unverified claims (reviews, licenses, awards, prices). | Website engine | WEB-002.
- [ ] [ONB-002](../../../requirements/ONB.md#onb-002): ONB-002 [P1] MUST prevent impersonation: a preview MUST NOT go public, receive real calls, or display the business's real phone number until ownership is verified (phone OTP to the number on the listing, or Google Business Profile ownership, or a document/manual review path handled by support). Verification method and result are stored.
- [ ] [WEB-002](../../../requirements/WEB.md#web-002): WEB-002 [P1] MUST ensure content claim safety: the generator MUST NOT fabricate reviews, certifications, years in business, service guarantees, or prices. Any claim must trace to a source field or be flagged for owner confirmation. Preview shows "unverified claims" highlights the owner must resolve.
- [ ] [WEB-005](../../../requirements/WEB.md#web-005): WEB-005 [P1] MUST serve tenant sites on a separate registrable domain from EverOnn's own application and marketing domains (for example everonn.site), so cookies, XSS blast radius, email reputation and SEO reputation are isolated.
- [ ] [WEB-013](../../../requirements/WEB.md#web-013): WEB-013 [P1] MUST implement abuse controls: block generation for prohibited business categories, prevent phishing/impersonation sites (brand and domain similarity checks), takedown workflow (admin action within minutes), and a report-abuse link on every site.

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
