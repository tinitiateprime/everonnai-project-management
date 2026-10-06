# EVN-VOX-006 - English and Spanish

Project: EverOnnAI. Module: [Telephone numbers, voice service and bilingual calls](../README.md). Source business requirement [BR-006](../../../requirements/BR.md#br-006).

| Tracking dimension | Disposition |
| --- | --- |
| Engineering | Planned |
| QA | Existing checks are evidence for current slices; full ticket criteria remain pending |
| Deployment | Current local snapshot; verify ticket-specific hosted rollout and configuration |
| Business acceptance | Pending client review; no signed acceptance recorded |
| Owner | Voice/Media Lead + SRE (proposed role; named person unassigned) |
| Priority / phase | Must / P1 |
| Estimate | TBD after scope/architecture agreement; no delivery date committed |
| Dependencies | [EVN-VOX-101](EVN-VOX-101.md), [EVN-KNW-102](../../02-knowledge-agent-configuration/tickets/EVN-KNW-102.md) |

## Business deliverable

English and Spanish. The service works in English and Spanish and can switch language mid-call, including when a human takes over.

The client accepts the demonstrated outcome and evidence, rather than the existence of a route, table or screen. This ticket does not certify the whole source requirement as complete.

## Current implemented slice

- [ ] The current voice context explicitly selects English.

The current statement describes prerequisites or context; this business deliverable has not been demonstrated.

## Remaining delivery checklist

- [ ] Add English/Spanish detection, mid-call switching, bilingual read-back, skilled operator routing and audio evaluations.

## Technical component

- [ ] Implement the module boundary and contracts for: Language resolver, speech provider selection, bilingual routing.
- [ ] Maintain tenant boundaries, explicit state transitions, access policy and failure handling for the delivered workflow.
- [ ] Resolve applicable architecture decisions before committing to a new provider or infrastructure baseline.

## DB

Existing module persistence: conversations, conversation_messages, contacts, leads; browser voice usage sessions.

The following records/contracts are proposed or require extension; their names are planning terms, not assertions that production tables exist.

- [ ] language_preferences, voice_profiles, operator_skills.
- [ ] Review scope keys, uniqueness, indexes, retention and migration compatibility; backfill safely and preserve existing tenant records.

## UI

- [ ] Language selection, caller-language badge and bilingual transcripts.
- [ ] Provide loading, empty, validation, permission-denied and recoverable failure states with keyboard and mobile access.
- [ ] Show observed facts and pending states accurately; do not present estimates, configured flags or mock results as confirmed business actions.

## Translate - business-to-technical mapping

| Business rule / outcome | Technical responsibility | Evidence needed |
| --- | --- | --- |
| English and Spanish. The service works in English and Spanish and can switch language mid-call, including when a human takes over. | Language resolver, speech provider selection, bilingual routing | Tenant-scoped end-to-end demonstration of the outcome |
| Add English/Spanish detection, mid-call switching, bilingual read-back, skilled operator routing and audio evaluations. | language_preferences, voice_profiles, operator_skills; Language selection, caller-language badge and bilingual transcripts | Migration/contracts, visible state and failure-path evidence |
| Safe, truthful AI behaviour where applicable | EN/ES prompts, speech models and native-speaker evaluation | Approved context, verified side-effect receipts and evaluation results or justified N/A |
| Client can approve delivery | QA report, rollout evidence and named acceptance owner | Evidence links and dated client sign-off |

This section means requirements-to-implementation mapping. It does not mean language translation; source language obligations are tracked in their own requirements.

## Backend services

- [ ] Language resolver, speech provider selection, bilingual routing.
- [ ] Define request/response/event schemas, authorisation and input validation for each affected operation.
- [ ] For writes and provider effects, define idempotency, retry/timeout, receipts and reconciliation; document N/A where no side effects exist.
- [ ] Expose actionable status and scoped logs without secrets; distinguish completed, failed and uncertain outcomes.

## AI component

- [ ] EN/ES prompts, speech models and native-speaker evaluation.
- [ ] Record instruction/knowledge/tool versions, measured quality, tenant scope, cost and safe fallback; a Markdown standard alone is not a passed evaluation.

## Testing / QA

- [ ] Exercise the intended user journey with real tenant-scoped state; cover forbidden role and cross-tenant requests.
- [ ] Test malformed inputs, provider failure, retries/replays and cancellation as applicable; keep deterministic mocks separate from live-provider evidence.
- [ ] Review desktop/mobile accessibility, factual copy and failure recovery in the delivered UI.
- [ ] Attach test environment, code/config/instruction versions, results and remaining defects to the acceptance report.

| Source test | Scenario | Required pass criteria | Current disposition |
| --- | --- | --- | --- |
| [AT-17](../../../requirements/AT.md#at-17) | Caller speaks Spanish or switches mid-call | Agent switches language; the caller's language is recorded; a Spanish-skilled operator is routed when escalated | Full source scenario not evidenced; client acceptance pending |

Source stories: [US-012](../../../requirements/US.md#us-012).

## Deployment

- [ ] Confirm approved hosting/database/provider architecture and required credentials in the deployment environment.
- [ ] Apply compatible migrations/configuration in staging, rehearse rollback, then promote the reviewed artifact.
- [ ] Verify the actual hosted workflow, monitoring, fallback and customer-visible errors after release.
- [ ] Update CODE_PROFILE.md, PROJECT_DATA_FLOW.md and CLIENT_TECHNICAL_QA.md in the application when behaviour or architecture changes.
- [ ] Record deployment identity, operator, timestamp and rollback evidence; document-only tickets instead record the reviewed Git commit.

## Source traceability

| Source ID | Mapping basis | Source section |
| --- | --- | --- |
| [AT-17](../../../requirements/AT.md#at-17) | Source-linked | 25.2 Acceptance tests |
| [BO-1](../../../requirements/BO.md#bo-1) | Source-linked | 3.1 Business objectives |
| [BR-006](../../../requirements/BR.md#br-006) | Source-linked | 7.1 Answering calls |
| [DSK-017](../../../requirements/DSK.md#dsk-017) | Source-linked | 16.4.4 Handling the interaction |
| [SCF-019](../../../requirements/SCF.md#scf-019) | Plan allocation / source cross-reference | 22.3 Scaffolding checklist |
| [US-012](../../../requirements/US.md#us-012) | Source-linked | EP-03 AI voice front desk |
| [VOX-008](../../../requirements/VOX.md#vox-008) | Source-linked | 14.4 Requirements: real-time conversation quality |
| [VOX-012](../../../requirements/VOX.md#vox-012) | Plan allocation / source cross-reference | 14.4 Requirements: real-time conversation quality |
| [WEB-015](../../../requirements/WEB.md#web-015) | Plan allocation / source cross-reference | 18.3 Requirements |

Read every allocated record, including its continuation bullets and source variants. Source-linked rows preserve explicit document relationships; plan allocations are implementation responsibility assignments created during this review.

## Allocated specification checklist

The unchecked source obligations below require requirement-level evidence. They are deliberately separate from checked statements about current implemented slices. Read linked continuation bullets and additional source wording before accepting a record.

- [ ] [DSK-017](../../../requirements/DSK.md#dsk-017): DSK-017 [P1] MUST handle language: the offer shows the caller's language; routing prefers operators skilled in it (English and Spanish at P1); the operator can switch language mid-conversation; an interpreter path is P3.
- [ ] [SCF-019](../../../requirements/SCF.md#scf-019): 19 | i18n keys and locale-aware formatting in all UIs, prompts and templates | New languages and markets without refactor.
- [ ] [VOX-008](../../../requirements/VOX.md#vox-008): VOX-008 [P1] MUST support English and Spanish at P1 (auto-detect and switch mid-call; caller-preferred language stored), with an extensible language framework (P3: more languages).
- [ ] [VOX-012](../../../requirements/VOX.md#vox-012): VOX-012 [P1] MUST provide voice selection: a curated set of natural voices per language (with cloning of the owner's voice explicitly out of scope for P1, and only with documented consent in P3). Pronunciation dictionaries per tenant (business names, streets, terms).
- [ ] [WEB-015](../../../requirements/WEB.md#web-015): WEB-015 [P2] SHOULD support i18n (English and Spanish first) at the Site Spec level.

## Existing code / check evidence

- `app/api/voice/session/route.ts` - inspected current application working tree; see [snapshot evidence](../../../EVIDENCE.md).
- `app/api/site-assistant/session/route.ts` - inspected current application working tree; see [snapshot evidence](../../../EVIDENCE.md).
- `features/voice-agent/session-context.ts` - inspected current application working tree; see [snapshot evidence](../../../EVIDENCE.md).
- `features/voice-agent/session-prompt.ts` - inspected current application working tree; see [snapshot evidence](../../../EVIDENCE.md).
- `features/voice-agent/engine.ts` - inspected current application working tree; see [snapshot evidence](../../../EVIDENCE.md).
- `components/preview/website-assistant.tsx` - inspected current application working tree; see [snapshot evidence](../../../EVIDENCE.md).
- Relevant automated checks: `tests/lead-automation.test.ts`, `tests/product-core.test.ts`. Their scope is bounded by [current validation](../../../CURRENT_STATE.md).

## Blockers and boundaries

Module risk: Browser ElevenLabs sessions do not establish real PSTN numbers, two carriers, warm transfers, Spanish coverage or 24/7 answering.

Dependencies: [EVN-VOX-101](EVN-VOX-101.md), [EVN-KNW-102](../../02-knowledge-agent-configuration/tickets/EVN-KNW-102.md). A blocked prerequisite can be prototyped independently, but its contract and deployment must be approved before claiming this ticket delivered. Service limits, third-party approvals and staffing are evidence requirements, not assumptions that they are available.

## Handover and client acceptance

- [ ] Attach the business demonstration, technical evidence and operating/recovery instructions.
- [ ] Assign a named acceptance owner and agree any deferred criteria with the client in writing.
- [ ] Resolve launch-blocking defects and document accepted residual risks.
- [ ] Client records dated acceptance against the deployed/documented version.

Use [the acceptance protocol](../../../ACCEPTANCE.md) and [the ticket update rules](../../../TICKET_TEMPLATE.md) when changing status.
