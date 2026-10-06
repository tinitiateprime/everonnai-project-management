# EVN-CHT-101 - Let any authorised customer website embed a fast accessible assistant

Project: EverOnnAI. Module: [Customer chat, external widget and SMS](../README.md). Technical delivery enabler allocated by this plan; source references below.

| Tracking dimension | Disposition |
| --- | --- |
| Engineering | Partial |
| QA | Existing checks are evidence for current slices; full ticket criteria remain pending |
| Deployment | Current local snapshot; verify ticket-specific hosted rollout and configuration |
| Business acceptance | Pending client review; no signed acceptance recorded |
| Owner | Frontend Lead + Channel Integration Lead (proposed role; named person unassigned) |
| Priority / phase | Delivery enabler / P1 |
| Estimate | TBD after scope/architecture agreement; no delivery date committed |
| Dependencies | [EVN-ONB-102](../../01-onboarding-tenancy-identity/tickets/EVN-ONB-102.md), [EVN-AIQ-102](../../03-ai-governance-evaluation/tickets/EVN-AIQ-102.md) |

## Business deliverable

Let any authorised customer website embed a fast accessible assistant.

The client accepts the demonstrated outcome and evidence, rather than the existence of a route, table or screen. This ticket does not certify the whole source requirement as complete.

## Current implemented slice

- [x] The current assistant is embedded in generated EverOnn sites.

## Remaining delivery checklist

- [ ] Provide a separately packaged origin-scoped widget under the source 40 KB gz budget, streaming, spam controls and session continuity.

## Technical component

- [ ] Implement the module boundary and contracts for: Widget packaging, public session API, SSE and upload checks.
- [ ] Maintain tenant boundaries, explicit state transitions, access policy and failure handling for the delivered workflow.
- [ ] Resolve applicable architecture decisions before committing to a new provider or infrastructure baseline.

## DB

Existing module persistence: conversations, messages, contacts, leads and scoped visitor/provider sessions.

The following records/contracts are proposed or require extension; their names are planning terms, not assertions that production tables exist.

- [ ] widget_keys, origin_grants, visitor_sessions.
- [ ] Review scope keys, uniqueness, indexes, retention and migration compatibility; backfill safely and preserve existing tenant records.

## UI

- [ ] External-host widget with disclosure, accessibility and consent.
- [ ] Provide loading, empty, validation, permission-denied and recoverable failure states with keyboard and mobile access.
- [ ] Show observed facts and pending states accurately; do not present estimates, configured flags or mock results as confirmed business actions.

## Translate - business-to-technical mapping

| Business rule / outcome | Technical responsibility | Evidence needed |
| --- | --- | --- |
| Let any authorised customer website embed a fast accessible assistant. | Widget packaging, public session API, SSE and upload checks | Tenant-scoped end-to-end demonstration of the outcome |
| Provide a separately packaged origin-scoped widget under the source 40 KB gz budget, streaming, spam controls and session continuity. | widget_keys, origin_grants, visitor_sessions; External-host widget with disclosure, accessibility and consent | Migration/contracts, visible state and failure-path evidence |
| Safe, truthful AI behaviour where applicable | Shared brain; no private owner configuration in widget payloads | Approved context, verified side-effect receipts and evaluation results or justified N/A |
| Client can approve delivery | QA report, rollout evidence and named acceptance owner | Evidence links and dated client sign-off |

This section means requirements-to-implementation mapping. It does not mean language translation; source language obligations are tracked in their own requirements.

## Backend services

- [ ] Widget packaging, public session API, SSE and upload checks.
- [ ] Define request/response/event schemas, authorisation and input validation for each affected operation.
- [ ] For writes and provider effects, define idempotency, retry/timeout, receipts and reconciliation; document N/A where no side effects exist.
- [ ] Expose actionable status and scoped logs without secrets; distinguish completed, failed and uncertain outcomes.

## AI component

- [ ] Shared brain.
- [ ] no private owner configuration in widget payloads.
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
| [CHT-001](../../../requirements/CHT.md#cht-001) | Source-linked | 15.2 Requirements |
| [CHT-002](../../../requirements/CHT.md#cht-002) | Source-linked | 15.2 Requirements |
| [CHT-005](../../../requirements/CHT.md#cht-005) | Source-linked | 15.2 Requirements |
| [CHT-006](../../../requirements/CHT.md#cht-006) | Source-linked | 15.2 Requirements |
| [CHT-007](../../../requirements/CHT.md#cht-007) | Source-linked | 15.2 Requirements |
| [CHT-010](../../../requirements/CHT.md#cht-010) | Source-linked | 15.2 Requirements |
| [CHT-012](../../../requirements/CHT.md#cht-012) | Source-linked | 15.2 Requirements |
| [CHT-013](../../../requirements/CHT.md#cht-013) | Source-linked | 15.2 Requirements |

Read every allocated record, including its continuation bullets and source variants. Source-linked rows preserve explicit document relationships; plan allocations are implementation responsibility assignments created during this review.

## Allocated specification checklist

The unchecked source obligations below require requirement-level evidence. They are deliberately separate from checked statements about current implemented slices. Read linked continuation bullets and additional source wording before accepting a record.

- [ ] [CHT-001](../../../requirements/CHT.md#cht-001): CHT-001 [P1] MUST ship an embeddable widget (single script, under 40 KB gzipped, no third-party cookies, accessible WCAG 2.1 AA, keyboard and screen-reader friendly) with theming from the tenant's brand, mobile-first layout, and lazy loading so it never harms Core Web Vitals.
- [ ] [CHT-002](../../../requirements/CHT.md#cht-002): CHT-002 [P1] MUST stream responses over SSE or WebSocket; first token within 1.5 s p50.
- [ ] [CHT-005](../../../requirements/CHT.md#cht-005): CHT-005 [P1] MUST capture consent for SMS follow-up in-widget with logged consent text, timestamp, IP and page (COM-002).
- [ ] [CHT-006](../../../requirements/CHT.md#cht-006): CHT-006 [P1] MUST support visitor identity continuity: anonymous session ID, upgraded to a contact on lead capture; the same person across voice, chat and SMS resolves to one Contact via verified identifiers (phone, email) with merge rules and merge audit.
- [ ] [CHT-007](../../../requirements/CHT.md#cht-007): CHT-007 [P1] MUST provide bot protection on the widget (Turnstile/hCaptcha or equivalent risk scoring), rate limits per IP and per session, and origin allow-listing per tenant (widget keys are public and MUST be scoped to allowed origins).
- [ ] [CHT-010](../../../requirements/CHT.md#cht-010): CHT-010 [P2] SHOULD support proactive chat triggers (for example, after 20 seconds on the emergency service page) configured per tenant.
- [ ] [CHT-012](../../../requirements/CHT.md#cht-012): CHT-012 [P2] SHOULD support multilingual chat with automatic language detection.
- [ ] [CHT-013](../../../requirements/CHT.md#cht-013): CHT-013 [P1] MUST implement an AI disclosure in chat ("You're chatting with the business's AI assistant") that is visible at the start of the conversation.

## Existing code / check evidence

- `app/api/assistant/message/route.ts` - inspected current application working tree; see [snapshot evidence](../../../EVIDENCE.md).
- `app/api/site-assistant/session/route.ts` - inspected current application working tree; see [snapshot evidence](../../../EVIDENCE.md).
- `app/api/site-assistant/lead/route.ts` - inspected current application working tree; see [snapshot evidence](../../../EVIDENCE.md).
- `components/preview/website-assistant.tsx` - inspected current application working tree; see [snapshot evidence](../../../EVIDENCE.md).
- `features/voice-agent/capture-client.ts` - inspected current application working tree; see [snapshot evidence](../../../EVIDENCE.md).
- Relevant automated checks: `tests/lead-automation.test.ts`, `tests/product-core.test.ts`, `scripts/smoke-hvac.ts`. Their scope is bounded by [current validation](../../../CURRENT_STATE.md).

## Blockers and boundaries

Module risk: Current in-site chat is not a standalone sub-40 KB widget, two-way SMS, consent ledger or human takeover.

Dependencies: [EVN-ONB-102](../../01-onboarding-tenancy-identity/tickets/EVN-ONB-102.md), [EVN-AIQ-102](../../03-ai-governance-evaluation/tickets/EVN-AIQ-102.md). A blocked prerequisite can be prototyped independently, but its contract and deployment must be approved before claiming this ticket delivered. Service limits, third-party approvals and staffing are evidence requirements, not assumptions that they are available.

## Handover and client acceptance

- [ ] Attach the business demonstration, technical evidence and operating/recovery instructions.
- [ ] Assign a named acceptance owner and agree any deferred criteria with the client in writing.
- [ ] Resolve launch-blocking defects and document accepted residual risks.
- [ ] Client records dated acceptance against the deployed/documented version.

Use [the acceptance protocol](../../../ACCEPTANCE.md) and [the ticket update rules](../../../TICKET_TEMPLATE.md) when changing status.
