# EVN-WEB-013 - Chat, call and forms on every site

Project: EverOnnAI. Module: [AI website generation, editing, publishing and domains](../README.md). Source business requirement [BR-013](../../../requirements/BR.md#br-013).

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

Chat, call and forms on every site. Every client website includes chat, click-to-call and lead forms out of the box.

The client accepts the demonstrated outcome and evidence, rather than the existence of a route, table or screen. This ticket does not certify the whole source requirement as complete.

## Current implemented slice

- [x] Generated pages connect request forms, assistant controls and approved telephone links.

## Remaining delivery checklist

- [ ] Add origin allowlists, bot protection, consent, tracking numbers and the reusable lightweight widget.

## Technical component

- [ ] Implement the module boundary and contracts for: Public intake endpoint, anti-abuse controls and inbox delivery.
- [ ] Maintain tenant boundaries, explicit state transitions, access policy and failure handling for the delivered workflow.
- [ ] Resolve applicable architecture decisions before committing to a new provider or infrastructure baseline.

## DB

Existing module persistence: website_projects and immutable draft/live release snapshots in scoped workspace records.

The following records/contracts are proposed or require extension; their names are planning terms, not assertions that production tables exist.

- [ ] form_submissions, widget_origins, consent_events.
- [ ] Review scope keys, uniqueness, indexes, retention and migration compatibility; backfill safely and preserve existing tenant records.

## UI

- [ ] Accessible form, chat entry and click-to-call.
- [ ] Provide loading, empty, validation, permission-denied and recoverable failure states with keyboard and mobile access.
- [ ] Show observed facts and pending states accurately; do not present estimates, configured flags or mock results as confirmed business actions.

## Translate - business-to-technical mapping

| Business rule / outcome | Technical responsibility | Evidence needed |
| --- | --- | --- |
| Chat, call and forms on every site. Every client website includes chat, click-to-call and lead forms out of the box. | Public intake endpoint, anti-abuse controls and inbox delivery | Tenant-scoped end-to-end demonstration of the outcome |
| Add origin allowlists, bot protection, consent, tracking numbers and the reusable lightweight widget. | form_submissions, widget_origins, consent_events; Accessible form, chat entry and click-to-call | Migration/contracts, visible state and failure-path evidence |
| Safe, truthful AI behaviour where applicable | Approved business facts; forms remain functional without AI | Approved context, verified side-effect receipts and evaluation results or justified N/A |
| Client can approve delivery | QA report, rollout evidence and named acceptance owner | Evidence links and dated client sign-off |

This section means requirements-to-implementation mapping. It does not mean language translation; source language obligations are tracked in their own requirements.

## Backend services

- [ ] Public intake endpoint, anti-abuse controls and inbox delivery.
- [ ] Define request/response/event schemas, authorisation and input validation for each affected operation.
- [ ] For writes and provider effects, define idempotency, retry/timeout, receipts and reconciliation; document N/A where no side effects exist.
- [ ] Expose actionable status and scoped logs without secrets; distinguish completed, failed and uncertain outcomes.

## AI component

- [ ] Approved business facts.
- [ ] forms remain functional without AI.
- [ ] Record instruction/knowledge/tool versions, measured quality, tenant scope, cost and safe fallback; a Markdown standard alone is not a passed evaluation.

## Testing / QA

- [ ] Exercise the intended user journey with real tenant-scoped state; cover forbidden role and cross-tenant requests.
- [ ] Test malformed inputs, provider failure, retries/replays and cancellation as applicable; keep deterministic mocks separate from live-provider evidence.
- [ ] Review desktop/mobile accessibility, factual copy and failure recovery in the delivered UI.
- [ ] Attach test environment, code/config/instruction versions, results and remaining defects to the acceptance report.

| Source test | Scenario | Required pass criteria | Current disposition |
| --- | --- | --- | --- |
| [AT-04](../../../requirements/AT.md#at-04) | Search and AI-search readiness on sample generated sites | Structured data validates; Lighthouse mobile 90 or more on all four categories; LCP under 2.5 s; chat, click-to-call and forms present | Full source scenario not evidenced; client acceptance pending |
| [AT-19](../../../requirements/AT.md#at-19) | Website chat with photo upload and lead capture | Structured request created; consent recorded; owner notified; widget under 40 KB | Full source scenario not evidenced; client acceptance pending |

Source stories: [US-017](../../../requirements/US.md#us-017), [US-040](../../../requirements/US.md#us-040).

## Deployment

- [ ] Confirm approved hosting/database/provider architecture and required credentials in the deployment environment.
- [ ] Apply compatible migrations/configuration in staging, rehearse rollback, then promote the reviewed artifact.
- [ ] Verify the actual hosted workflow, monitoring, fallback and customer-visible errors after release.
- [ ] Update CODE_PROFILE.md, PROJECT_DATA_FLOW.md and CLIENT_TECHNICAL_QA.md in the application when behaviour or architecture changes.
- [ ] Record deployment identity, operator, timestamp and rollback evidence; document-only tickets instead record the reviewed Git commit.

## Source traceability

| Source ID | Mapping basis | Source section |
| --- | --- | --- |
| [AT-04](../../../requirements/AT.md#at-04) | Source-linked | 25.2 Acceptance tests |
| [AT-19](../../../requirements/AT.md#at-19) | Source-linked | 25.2 Acceptance tests |
| [BO-1](../../../requirements/BO.md#bo-1) | Source-linked | 3.1 Business objectives |
| [BR-013](../../../requirements/BR.md#br-013) | Source-linked | 7.2 Chat and messaging |
| [US-017](../../../requirements/US.md#us-017) | Source-linked | EP-04 Chat and messaging |
| [US-040](../../../requirements/US.md#us-040) | Source-linked | EP-07 Websites |
| [WEB-007](../../../requirements/WEB.md#web-007) | Source-linked | 18.3 Requirements |

Read every allocated record, including its continuation bullets and source variants. Source-linked rows preserve explicit document relationships; plan allocations are implementation responsibility assignments created during this review.

## Allocated specification checklist

The unchecked source obligations below require requirement-level evidence. They are deliberately separate from checked statements about current implemented slices. Read linked continuation bullets and additional source wording before accepting a record.

- [ ] [WEB-007](../../../requirements/WEB.md#web-007): WEB-007 [P1] MUST embed the AI chat widget, click-to-call (tel: with tracking number), and lead forms by default, with spam protection (Turnstile/hCaptcha), rate limits, consent capture and delivery into the inbox.

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
