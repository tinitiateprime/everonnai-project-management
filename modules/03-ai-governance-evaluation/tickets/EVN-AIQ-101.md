# EVN-AIQ-101 - Make provider selection portable and measurable

Project: EverOnnAI. Module: [AI runtime, skills, provider portability and evaluation](../README.md). Technical delivery enabler allocated by this plan; source references below.

| Tracking dimension | Disposition |
| --- | --- |
| Engineering | Partial |
| QA | Existing checks are evidence for current slices; full ticket criteria remain pending |
| Deployment | Current local snapshot; verify ticket-specific hosted rollout and configuration |
| Business acceptance | Pending client review; no signed acceptance recorded |
| Owner | AI Lead + QA Lead (proposed role; named person unassigned) |
| Priority / phase | Delivery enabler / P0 |
| Estimate | TBD after scope/architecture agreement; no delivery date committed |
| Dependencies | [EVN-FND-101](../../00-foundations-governance/tickets/EVN-FND-101.md) |

## Business deliverable

Make provider selection portable and measurable.

The client accepts the demonstrated outcome and evidence, rather than the existence of a route, table or screen. This ticket does not certify the whole source requirement as complete.

## Current implemented slice

- [x] Gemini generation and ElevenLabs sessions use scoped application services.

## Remaining delivery checklist

- [ ] Define provider contracts, alternatives/contract tests, task tiers, safe failover, privacy hooks and per-call budgets.

## Technical component

- [ ] Implement the module boundary and contracts for: Llm/Stt/Tts/Telephony/Sms/Email/Payment/Calendar provider interfaces.
- [ ] Maintain tenant boundaries, explicit state transitions, access policy and failure handling for the delivered workflow.
- [ ] Resolve applicable architecture decisions before committing to a new provider or infrastructure baseline.

## DB

Existing module persistence: Skill version/digest traces, generation metadata, scoped preferences and usage records.

The following records/contracts are proposed or require extension; their names are planning terms, not assertions that production tables exist.

- [ ] provider_config, task_routes, provider_health, budget records.
- [ ] Review scope keys, uniqueness, indexes, retention and migration compatibility; backfill safely and preserve existing tenant records.

## UI

- [ ] Admin provider-health and approved tier configuration.
- [ ] Provide loading, empty, validation, permission-denied and recoverable failure states with keyboard and mobile access.
- [ ] Show observed facts and pending states accurately; do not present estimates, configured flags or mock results as confirmed business actions.

## Translate - business-to-technical mapping

| Business rule / outcome | Technical responsibility | Evidence needed |
| --- | --- | --- |
| Make provider selection portable and measurable. | Llm/Stt/Tts/Telephony/Sms/Email/Payment/Calendar provider interfaces | Tenant-scoped end-to-end demonstration of the outcome |
| Define provider contracts, alternatives/contract tests, task tiers, safe failover, privacy hooks and per-call budgets. | provider_config, task_routes, provider_health, budget records; Admin provider-health and approved tier configuration | Migration/contracts, visible state and failure-path evidence |
| Safe, truthful AI behaviour where applicable | No raw model selection by tenants; measure quality/cost before switching | Approved context, verified side-effect receipts and evaluation results or justified N/A |
| Client can approve delivery | QA report, rollout evidence and named acceptance owner | Evidence links and dated client sign-off |

This section means requirements-to-implementation mapping. It does not mean language translation; source language obligations are tracked in their own requirements.

## Backend services

- [ ] Llm/Stt/Tts/Telephony/Sms/Email/Payment/Calendar provider interfaces.
- [ ] Define request/response/event schemas, authorisation and input validation for each affected operation.
- [ ] For writes and provider effects, define idempotency, retry/timeout, receipts and reconciliation; document N/A where no side effects exist.
- [ ] Expose actionable status and scoped logs without secrets; distinguish completed, failed and uncertain outcomes.

## AI component

- [ ] No raw model selection by tenants.
- [ ] measure quality/cost before switching.
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
| [AGT-006](../../../requirements/AGT.md#agt-006) | Source-linked | 13.3 Agent configuration |
| [AR-002](../../../requirements/AR.md#ar-002) | Source-linked | 11.7 Architecture requirements |
| [CST-001](../../../requirements/CST.md#cst-001) | Source-linked | 23.6 Unit economics and cost controls |
| [CST-003](../../../requirements/CST.md#cst-003) | Source-linked | 23.6 Unit economics and cost controls |
| [SCF-004](../../../requirements/SCF.md#scf-004) | Plan allocation / source cross-reference | 22.3 Scaffolding checklist |
| [SCF-024](../../../requirements/SCF.md#scf-024) | Plan allocation / source cross-reference | 22.3 Scaffolding checklist |

Read every allocated record, including its continuation bullets and source variants. Source-linked rows preserve explicit document relationships; plan allocations are implementation responsibility assignments created during this review.

## Allocated specification checklist

The unchecked source obligations below require requirement-level evidence. They are deliberately separate from checked statements about current implemented slices. Read linked continuation bullets and additional source wording before accepting a record.

- [ ] [AGT-006](../../../requirements/AGT.md#agt-006): AGT-006 [P1] MUST include model routing configuration per agent and per task (voice turn, chat turn, summarization, extraction, QA judge) resolved through the model gateway (§20.3); tenants never choose raw model names, only quality tiers.
- [ ] [AR-002](../../../requirements/AR.md#ar-002): AR-002 [P0] MUST expose every external vendor behind an internal interface: TelephonyProvider, SttProvider, TtsProvider, LlmProvider, SmsProvider, EmailProvider, PaymentProvider, CalendarProvider, GeocodingProvider. Each MUST have at least one alternative implementation stubbed or contract-tested by end of P1 for telephony and LLM, by P2 for the rest.
- [ ] [CST-001](../../../requirements/CST.md#cst-001): CST-001 [P0] MUST produce a cost model and measured per-minute cost in the P0 spike for at least three vendor combinations, and recommend the default stack by cost and quality.
- [ ] [CST-003](../../../requirements/CST.md#cst-003): CST-003 [P1] MUST use prompt caching, compact prompts, retrieval limits, and short-turn design to minimize tokens; record tokens and cost per turn.
- [ ] [SCF-004](../../../requirements/SCF.md#scf-004): 4 | Provider interfaces (Telephony, Stt, Tts, Llm, Sms, Email, Payment, Calendar, Geocoding, Fsm) with contract tests and a second implementation | Vendor swaps for cost/quality/outage; multi-carrier routing; on-prem models.
- [ ] [SCF-024](../../../requirements/SCF.md#scf-024): 24 | Vendor health checks and circuit breakers with per-tenant fallback modes | Automated failover, graceful degradation at scale.

## Existing code / check evidence

- `ai/SYSTEM.md` - inspected current application working tree; see [snapshot evidence](../../../EVIDENCE.md).
- `ai/GUARDRAILS.md` - inspected current application working tree; see [snapshot evidence](../../../EVIDENCE.md).
- `ai/domains/hvac/SKILL.md` - inspected current application working tree; see [snapshot evidence](../../../EVIDENCE.md).
- `ai/domains/hvac/GUARDRAILS.md` - inspected current application working tree; see [snapshot evidence](../../../EVIDENCE.md).
- `ai/capabilities/website-building/SKILL.md` - inspected current application working tree; see [snapshot evidence](../../../EVIDENCE.md).
- `features/agent-runtime/tool-registry.ts` - inspected current application working tree; see [snapshot evidence](../../../EVIDENCE.md).
- `features/agent-runtime/safety.ts` - inspected current application working tree; see [snapshot evidence](../../../EVIDENCE.md).
- `features/voice-agent/gemini.ts` - inspected current application working tree; see [snapshot evidence](../../../EVIDENCE.md).
- `lib/provider-config.ts` - inspected current application working tree; see [snapshot evidence](../../../EVIDENCE.md).
- Relevant automated checks: `tests/agent-runtime.test.ts`, `tests/website-ai.test.ts`, `tests/website-code.test.ts`, `tests/provider-config.test.ts`. Their scope is bounded by [current validation](../../../CURRENT_STATE.md).

## Blockers and boundaries

Module risk: Deterministic mocks and EVALS Markdown do not prove live-model accuracy, audio latency or the required 150/500 scenario launch datasets.

Dependencies: [EVN-FND-101](../../00-foundations-governance/tickets/EVN-FND-101.md). A blocked prerequisite can be prototyped independently, but its contract and deployment must be approved before claiming this ticket delivered. Service limits, third-party approvals and staffing are evidence requirements, not assumptions that they are available.

## Handover and client acceptance

- [ ] Attach the business demonstration, technical evidence and operating/recovery instructions.
- [ ] Assign a named acceptance owner and agree any deferred criteria with the client in writing.
- [ ] Resolve launch-blocking defects and document accepted residual risks.
- [ ] Client records dated acceptance against the deployed/documented version.

Use [the acceptance protocol](../../../ACCEPTANCE.md) and [the ticket update rules](../../../TICKET_TEMPLATE.md) when changing status.
