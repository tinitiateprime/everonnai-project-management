# EVN-CHT-012 - Texting and text-back

Project: EverOnnAI. Module: [Customer chat, external widget and SMS](../README.md). Source business requirement [BR-012](../../../requirements/BR.md#br-012).

| Tracking dimension | Disposition |
| --- | --- |
| Engineering | Planned |
| QA | Existing checks are evidence for current slices; full ticket criteria remain pending |
| Deployment | Current local snapshot; verify ticket-specific hosted rollout and configuration |
| Business acceptance | Pending client review; no signed acceptance recorded |
| Owner | Frontend Lead + Channel Integration Lead (proposed role; named person unassigned) |
| Priority / phase | Must / P1 |
| Estimate | TBD after scope/architecture agreement; no delivery date committed |
| Dependencies | [EVN-CHT-101](EVN-CHT-101.md), [EVN-AIQ-102](../../03-ai-governance-evaluation/tickets/EVN-AIQ-102.md) |

## Business deliverable

Texting and text-back. Two-way text messaging works, including automatic text-back after a missed call, and opt-out is honored immediately.

The client accepts the demonstrated outcome and evidence, rather than the existence of a route, table or screen. This ticket does not certify the whole source requirement as complete.

## Current implemented slice

- [ ] No two-way SMS transport or STOP ledger is implemented.

The current statement describes prerequisites or context; this business deliverable has not been demonstrated.

## Remaining delivery checklist

- [ ] Build carrier webhooks, text-back, threading, opt-out/consent checks, quiet hours and delivery tracking.

## Technical component

- [ ] Implement the module boundary and contracts for: SmsProvider, missed-call workflow and fail-closed sending guard.
- [ ] Maintain tenant boundaries, explicit state transitions, access policy and failure handling for the delivered workflow.
- [ ] Resolve applicable architecture decisions before committing to a new provider or infrastructure baseline.

## DB

Existing module persistence: conversations, messages, contacts, leads and scoped visitor/provider sessions.

The following records/contracts are proposed or require extension; their names are planning terms, not assertions that production tables exist.

- [ ] sms_threads, sms_messages, consents, suppressions.
- [ ] Review scope keys, uniqueness, indexes, retention and migration compatibility; backfill safely and preserve existing tenant records.

## UI

- [ ] Inbox texting and consent/delivery indicators.
- [ ] Provide loading, empty, validation, permission-denied and recoverable failure states with keyboard and mobile access.
- [ ] Show observed facts and pending states accurately; do not present estimates, configured flags or mock results as confirmed business actions.

## Translate - business-to-technical mapping

| Business rule / outcome | Technical responsibility | Evidence needed |
| --- | --- | --- |
| Texting and text-back. Two-way text messaging works, including automatic text-back after a missed call, and opt-out is honored immediately. | SmsProvider, missed-call workflow and fail-closed sending guard | Tenant-scoped end-to-end demonstration of the outcome |
| Build carrier webhooks, text-back, threading, opt-out/consent checks, quiet hours and delivery tracking. | sms_threads, sms_messages, consents, suppressions; Inbox texting and consent/delivery indicators | Migration/contracts, visible state and failure-path evidence |
| Safe, truthful AI behaviour where applicable | Chat-backed texting cannot override opt-out or quiet hours | Approved context, verified side-effect receipts and evaluation results or justified N/A |
| Client can approve delivery | QA report, rollout evidence and named acceptance owner | Evidence links and dated client sign-off |

This section means requirements-to-implementation mapping. It does not mean language translation; source language obligations are tracked in their own requirements.

## Backend services

- [ ] SmsProvider, missed-call workflow and fail-closed sending guard.
- [ ] Define request/response/event schemas, authorisation and input validation for each affected operation.
- [ ] For writes and provider effects, define idempotency, retry/timeout, receipts and reconciliation; document N/A where no side effects exist.
- [ ] Expose actionable status and scoped logs without secrets; distinguish completed, failed and uncertain outcomes.

## AI component

- [ ] Chat-backed texting cannot override opt-out or quiet hours.
- [ ] Record instruction/knowledge/tool versions, measured quality, tenant scope, cost and safe fallback; a Markdown standard alone is not a passed evaluation.

## Testing / QA

- [ ] Exercise the intended user journey with real tenant-scoped state; cover forbidden role and cross-tenant requests.
- [ ] Test malformed inputs, provider failure, retries/replays and cancellation as applicable; keep deterministic mocks separate from live-provider evidence.
- [ ] Review desktop/mobile accessibility, factual copy and failure recovery in the delivered UI.
- [ ] Attach test environment, code/config/instruction versions, results and remaining defects to the acceptance report.

| Source test | Scenario | Required pass criteria | Current disposition |
| --- | --- | --- | --- |
| [AT-20](../../../requirements/AT.md#at-20) | Missed-call text-back and STOP | Text-back sent only with consent; STOP ends all non-essential messages from the number; consent ledger updated; fail-closed guard verified | Full source scenario not evidenced; client acceptance pending |

Source stories: [US-018](../../../requirements/US.md#us-018), [US-019](../../../requirements/US.md#us-019), [US-049](../../../requirements/US.md#us-049).

## Deployment

- [ ] Confirm approved hosting/database/provider architecture and required credentials in the deployment environment.
- [ ] Apply compatible migrations/configuration in staging, rehearse rollback, then promote the reviewed artifact.
- [ ] Verify the actual hosted workflow, monitoring, fallback and customer-visible errors after release.
- [ ] Update CODE_PROFILE.md, PROJECT_DATA_FLOW.md and CLIENT_TECHNICAL_QA.md in the application when behaviour or architecture changes.
- [ ] Record deployment identity, operator, timestamp and rollback evidence; document-only tickets instead record the reviewed Git commit.

## Source traceability

| Source ID | Mapping basis | Source section |
| --- | --- | --- |
| [AT-20](../../../requirements/AT.md#at-20) | Source-linked | 25.2 Acceptance tests |
| [BO-1](../../../requirements/BO.md#bo-1) | Source-linked | 3.1 Business objectives |
| [BO-7](../../../requirements/BO.md#bo-7) | Source-linked | 3.1 Business objectives |
| [BR-012](../../../requirements/BR.md#br-012) | Source-linked | 7.2 Chat and messaging |
| [BRL-007](../../../requirements/BRL.md#brl-007) | Plan allocation / source cross-reference | 8. Business rules |
| [CHT-009](../../../requirements/CHT.md#cht-009) | Source-linked | 15.2 Requirements |
| [COM-002](../../../requirements/COM.md#com-002) | Source-linked | 19.5 Compliance and legal-by-design (COM) |
| [US-018](../../../requirements/US.md#us-018) | Source-linked | EP-04 Chat and messaging |
| [US-019](../../../requirements/US.md#us-019) | Source-linked | EP-04 Chat and messaging |
| [US-049](../../../requirements/US.md#us-049) | Source-linked | EP-10 Compliance, security and privacy |
| [VOX-022](../../../requirements/VOX.md#vox-022) | Plan allocation / source cross-reference | 14.5 Requirements: business behavior |
| [VOX-033](../../../requirements/VOX.md#vox-033) | Source-linked | 14.3 Requirements: telephony and numbers |
| [VOX-035](../../../requirements/VOX.md#vox-035) | Plan allocation / source cross-reference | 14.3 Requirements: telephony and numbers |

Read every allocated record, including its continuation bullets and source variants. Source-linked rows preserve explicit document relationships; plan allocations are implementation responsibility assignments created during this review.

## Allocated specification checklist

The unchecked source obligations below require requirement-level evidence. They are deliberately separate from checked statements about current implemented slices. Read linked continuation bullets and additional source wording before accepting a record.

- [ ] [BRL-007](../../../requirements/BRL.md#brl-007): BRL-007 | No text message is sent without recorded consent, and STOP is honored immediately. | All messaging | COM-001, COM-002, CHT-009.
- [ ] [CHT-009](../../../requirements/CHT.md#cht-009): CHT-009 [P1] MUST support SMS threading (one thread per contact per business number), opt-out keywords (STOP/UNSUBSCRIBE/HELP) handling at the platform level, quiet hours (default 9 pm to 8 am recipient local time unless the message is a direct reply), and delivery-status tracking.
- [ ] [COM-002](../../../requirements/COM.md#com-002): COM-002 [P1] MUST implement SMS/TCPA controls: prior express consent capture for informational and transactional messages, separate consent for marketing, STOP/HELP handling, quiet hours, sender identification, frequency caps, and a full audit trail. Marketing/outbound features are off by default.
- [ ] [VOX-022](../../../requirements/VOX.md#vox-022): VOX-022 [P1] MUST send an optional customer confirmation SMS (subject to consent, COM-002).
- [ ] [VOX-033](../../../requirements/VOX.md#vox-033): VOX-033 [P1] MUST support missed-call text-back as a fallback and supplement: if a call ends unanswered (or was answered by AI but the caller dropped), send an SMS (subject to consent rules) inviting them to continue by text (handled by the chat agent).
- [ ] [VOX-035](../../../requirements/VOX.md#vox-035): VOX-035 [P1] MUST handle A2P 10DLC registration (brand and campaign) and toll-free verification for SMS as a managed background workflow with status visible to support (COM-005).

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
