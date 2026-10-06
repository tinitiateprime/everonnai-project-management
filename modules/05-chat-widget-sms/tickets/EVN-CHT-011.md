# EVN-CHT-011 - Website chat

Project: EverOnnAI. Module: [Customer chat, external widget and SMS](../README.md). Source business requirement [BR-011](../../../requirements/BR.md#br-011).

| Tracking dimension | Disposition |
| --- | --- |
| Engineering | Partial |
| QA | Existing checks are evidence for current slices; full ticket criteria remain pending |
| Deployment | Current local snapshot; verify ticket-specific hosted rollout and configuration |
| Business acceptance | Pending client review; no signed acceptance recorded |
| Owner | Frontend Lead + Channel Integration Lead (proposed role; named person unassigned) |
| Priority / phase | Must / P1 |
| Estimate | TBD after scope/architecture agreement; no delivery date committed |
| Dependencies | [EVN-CHT-101](EVN-CHT-101.md), [EVN-AIQ-102](../../03-ai-governance-evaluation/tickets/EVN-AIQ-102.md) |

## Business deliverable

Website chat. Website visitors can chat with the same AI around the clock and become structured leads, with photos where useful.

The client accepts the demonstrated outcome and evidence, rather than the existence of a route, table or screen. This ticket does not certify the whole source requirement as complete.

## Current implemented slice

- [x] Generated sites have approved-facts assistance with ElevenLabs text and Gemini fallback.

## Remaining delivery checklist

- [ ] Deliver an external widget, streaming, photo capture, consent, visitor continuity and full structured requests.

## Technical component

- [ ] Implement the module boundary and contracts for: Widget API, identity continuity, upload scanning, channel adapters.
- [ ] Maintain tenant boundaries, explicit state transitions, access policy and failure handling for the delivered workflow.
- [ ] Resolve applicable architecture decisions before committing to a new provider or infrastructure baseline.

## DB

Existing module persistence: conversations, messages, contacts, leads and scoped visitor/provider sessions.

The following records/contracts are proposed or require extension; their names are planning terms, not assertions that production tables exist.

- [ ] visitor_sessions, threads, messages, attachments.
- [ ] Review scope keys, uniqueness, indexes, retention and migration compatibility; backfill safely and preserve existing tenant records.

## UI

- [ ] Accessible widget, quick replies and upload flow.
- [ ] Provide loading, empty, validation, permission-denied and recoverable failure states with keyboard and mobile access.
- [ ] Show observed facts and pending states accurately; do not present estimates, configured flags or mock results as confirmed business actions.

## Translate - business-to-technical mapping

| Business rule / outcome | Technical responsibility | Evidence needed |
| --- | --- | --- |
| Website chat. Website visitors can chat with the same AI around the clock and become structured leads, with photos where useful. | Widget API, identity continuity, upload scanning, channel adapters | Tenant-scoped end-to-end demonstration of the outcome |
| Deliver an external widget, streaming, photo capture, consent, visitor continuity and full structured requests. | visitor_sessions, threads, messages, attachments; Accessible widget, quick replies and upload flow | Migration/contracts, visible state and failure-path evidence |
| Safe, truthful AI behaviour where applicable | Shared approved brain with chat-specific response style | Approved context, verified side-effect receipts and evaluation results or justified N/A |
| Client can approve delivery | QA report, rollout evidence and named acceptance owner | Evidence links and dated client sign-off |

This section means requirements-to-implementation mapping. It does not mean language translation; source language obligations are tracked in their own requirements.

## Backend services

- [ ] Widget API, identity continuity, upload scanning, channel adapters.
- [ ] Define request/response/event schemas, authorisation and input validation for each affected operation.
- [ ] For writes and provider effects, define idempotency, retry/timeout, receipts and reconciliation; document N/A where no side effects exist.
- [ ] Expose actionable status and scoped logs without secrets; distinguish completed, failed and uncertain outcomes.

## AI component

- [ ] Shared approved brain with chat-specific response style.
- [ ] Record instruction/knowledge/tool versions, measured quality, tenant scope, cost and safe fallback; a Markdown standard alone is not a passed evaluation.

## Testing / QA

- [ ] Exercise the intended user journey with real tenant-scoped state; cover forbidden role and cross-tenant requests.
- [ ] Test malformed inputs, provider failure, retries/replays and cancellation as applicable; keep deterministic mocks separate from live-provider evidence.
- [ ] Review desktop/mobile accessibility, factual copy and failure recovery in the delivered UI.
- [ ] Attach test environment, code/config/instruction versions, results and remaining defects to the acceptance report.

| Source test | Scenario | Required pass criteria | Current disposition |
| --- | --- | --- | --- |
| [AT-19](../../../requirements/AT.md#at-19) | Website chat with photo upload and lead capture | Structured request created; consent recorded; owner notified; widget under 40 KB | Full source scenario not evidenced; client acceptance pending |

Source stories: [US-017](../../../requirements/US.md#us-017).

## Deployment

- [ ] Confirm approved hosting/database/provider architecture and required credentials in the deployment environment.
- [ ] Apply compatible migrations/configuration in staging, rehearse rollback, then promote the reviewed artifact.
- [ ] Verify the actual hosted workflow, monitoring, fallback and customer-visible errors after release.
- [ ] Update CODE_PROFILE.md, PROJECT_DATA_FLOW.md and CLIENT_TECHNICAL_QA.md in the application when behaviour or architecture changes.
- [ ] Record deployment identity, operator, timestamp and rollback evidence; document-only tickets instead record the reviewed Git commit.

## Source traceability

| Source ID | Mapping basis | Source section |
| --- | --- | --- |
| [AT-19](../../../requirements/AT.md#at-19) | Source-linked | 25.2 Acceptance tests |
| [BO-1](../../../requirements/BO.md#bo-1) | Source-linked | 3.1 Business objectives |
| [BR-011](../../../requirements/BR.md#br-011) | Source-linked | 7.2 Chat and messaging |
| [CHT-001](../../../requirements/CHT.md#cht-001) | Source-linked | 15.2 Requirements |
| [CHT-003](../../../requirements/CHT.md#cht-003) | Source-linked | 15.2 Requirements |
| [CHT-004](../../../requirements/CHT.md#cht-004) | Source-linked | 15.2 Requirements |
| [CHT-008](../../../requirements/CHT.md#cht-008) | Plan allocation / source cross-reference | 15.2 Requirements |
| [CHT-011](../../../requirements/CHT.md#cht-011) | Source-linked | 15.2 Requirements |
| [SL-04](../../../requirements/SL.md#sl-04) | Plan allocation / source cross-reference | 10.1 Service levels |
| [US-017](../../../requirements/US.md#us-017) | Source-linked | EP-04 Chat and messaging |

Read every allocated record, including its continuation bullets and source variants. Source-linked rows preserve explicit document relationships; plan allocations are implementation responsibility assignments created during this review.

## Allocated specification checklist

The unchecked source obligations below require requirement-level evidence. They are deliberately separate from checked statements about current implemented slices. Read linked continuation bullets and additional source wording before accepting a record.

- [ ] [CHT-001](../../../requirements/CHT.md#cht-001): CHT-001 [P1] MUST ship an embeddable widget (single script, under 40 KB gzipped, no third-party cookies, accessible WCAG 2.1 AA, keyboard and screen-reader friendly) with theming from the tenant's brand, mobile-first layout, and lazy loading so it never harms Core Web Vitals.
- [ ] [CHT-003](../../../requirements/CHT.md#cht-003): CHT-003 [P1] MUST use the same agent brain, KB, playbook, tools and guardrails as voice (AGT-001), with channel-specific style (shorter, links, buttons).
- [ ] [CHT-004](../../../requirements/CHT.md#cht-004): CHT-004 [P1] MUST support rich responses: quick-reply buttons, "Call us", "Text me", location capture (with permission), photo upload (for example a photo of a lock or a leak; virus-scanned, size-limited, stored per tenant), and a contact card.
- [ ] [CHT-008](../../../requirements/CHT.md#cht-008): CHT-008 [P1] MUST support human takeover in chat (HIL-004): the operator or owner joins the same thread; the widget shows a subtle "a team member has joined" state.
- [ ] [CHT-011](../../../requirements/CHT.md#cht-011): CHT-011 [P1] MUST provide transcript and summary delivery with the same structured Request output as voice (AGT-008).
- [ ] [SL-04](../../../requirements/SL.md#sl-04): SL-04 | First words of a chat reply | Median under 1.5 s.

## Existing code / check evidence

- `app/api/assistant/message/route.ts` - inspected current application working tree; see [snapshot evidence](../../../EVIDENCE.md).
- `app/api/site-assistant/session/route.ts` - inspected current application working tree; see [snapshot evidence](../../../EVIDENCE.md).
- `app/api/site-assistant/lead/route.ts` - inspected current application working tree; see [snapshot evidence](../../../EVIDENCE.md).
- `components/preview/website-assistant.tsx` - inspected current application working tree; see [snapshot evidence](../../../EVIDENCE.md).
- `features/voice-agent/capture-client.ts` - inspected current application working tree; see [snapshot evidence](../../../EVIDENCE.md).
- Relevant automated checks: `tests/lead-automation.test.ts`, `tests/product-core.test.ts`, `scripts/smoke-hvac.ts`. Their scope is bounded by [current validation](../../../CURRENT_STATE.md).

## Blockers and boundaries

Module risk: Current in-site chat is not a standalone sub-40 KB widget, two-way SMS, consent ledger or human takeover.

Dependencies: [EVN-CHT-101](EVN-CHT-101.md), [EVN-AIQ-102](../../03-ai-governance-evaluation/tickets/EVN-AIQ-102.md). A blocked prerequisite can be prototyped independently, but its contract and deployment must be approved before claiming this ticket delivered. Service limits, third-party approvals and staffing are evidence requirements, not assumptions that they are available.

## Handover and client acceptance

- [ ] Attach the business demonstration, technical evidence and operating/recovery instructions.
- [ ] Assign a named acceptance owner and agree any deferred criteria with the client in writing.
- [ ] Resolve launch-blocking defects and document accepted residual risks.
- [ ] Client records dated acceptance against the deployed/documented version.

Use [the acceptance protocol](../../../ACCEPTANCE.md) and [the ticket update rules](../../../TICKET_TEMPLATE.md) when changing status.
