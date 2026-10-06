# EVN-AIQ-103 - Make AI changes pass a repeatable quality and safety gate

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
| Dependencies | [EVN-AIQ-101](EVN-AIQ-101.md), [EVN-AIQ-102](EVN-AIQ-102.md) |

## Business deliverable

Make AI changes pass a repeatable quality and safety gate.

The client accepts the demonstrated outcome and evidence, rather than the existence of a route, table or screen. This ticket does not certify the whole source requirement as complete.

## Current implemented slice

- [x] Unit tests, skill digests and EVALS Markdown exist.

## Remaining delivery checklist

- [ ] Build calibrated text and SIP-audio harness, golden datasets, release reports, red-team tests, canary/shadow and drift monitoring.

## Technical component

- [ ] Implement the module boundary and contracts for: Evaluation runner, report publisher and regression gate.
- [ ] Maintain tenant boundaries, explicit state transitions, access policy and failure handling for the delivered workflow.
- [ ] Resolve applicable architecture decisions before committing to a new provider or infrastructure baseline.

## DB

Existing module persistence: Skill version/digest traces, generation metadata, scoped preferences and usage records.

The following records/contracts are proposed or require extension; their names are planning terms, not assertions that production tables exist.

- [ ] eval_datasets, eval_runs, metrics, rollout gates.
- [ ] Review scope keys, uniqueness, indexes, retention and migration compatibility; backfill safely and preserve existing tenant records.

## UI

- [ ] Eval dashboard, reviewer labels and change approvals.
- [ ] Provide loading, empty, validation, permission-denied and recoverable failure states with keyboard and mobile access.
- [ ] Show observed facts and pending states accurately; do not present estimates, configured flags or mock results as confirmed business actions.

## Translate - business-to-technical mapping

| Business rule / outcome | Technical responsibility | Evidence needed |
| --- | --- | --- |
| Make AI changes pass a repeatable quality and safety gate. | Evaluation runner, report publisher and regression gate | Tenant-scoped end-to-end demonstration of the outcome |
| Build calibrated text and SIP-audio harness, golden datasets, release reports, red-team tests, canary/shadow and drift monitoring. | eval_datasets, eval_runs, metrics, rollout gates; Eval dashboard, reviewer labels and change approvals | Migration/contracts, visible state and failure-path evidence |
| Safe, truthful AI behaviour where applicable | 150 launch scenarios/500 scale scenarios per source; zero critical failures | Approved context, verified side-effect receipts and evaluation results or justified N/A |
| Client can approve delivery | QA report, rollout evidence and named acceptance owner | Evidence links and dated client sign-off |

This section means requirements-to-implementation mapping. It does not mean language translation; source language obligations are tracked in their own requirements.

## Backend services

- [ ] Evaluation runner, report publisher and regression gate.
- [ ] Define request/response/event schemas, authorisation and input validation for each affected operation.
- [ ] For writes and provider effects, define idempotency, retry/timeout, receipts and reconciliation; document N/A where no side effects exist.
- [ ] Expose actionable status and scoped logs without secrets; distinguish completed, failed and uncertain outcomes.

## AI component

- [ ] 150 launch scenarios/500 scale scenarios per source.
- [ ] zero critical failures.
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
| [BRL-016](../../../requirements/BRL.md#brl-016) | Plan allocation / source cross-reference | 8. Business rules |
| [EVL-001](../../../requirements/EVL.md#evl-001) | Source-linked | 24.5 AI evaluation and safety framework |
| [EVL-002](../../../requirements/EVL.md#evl-002) | Source-linked | 24.5 AI evaluation and safety framework |
| [EVL-003](../../../requirements/EVL.md#evl-003) | Source-linked | 24.5 AI evaluation and safety framework |
| [EVL-004](../../../requirements/EVL.md#evl-004) | Source-linked | 24.5 AI evaluation and safety framework |
| [EVL-005](../../../requirements/EVL.md#evl-005) | Source-linked | 24.5 AI evaluation and safety framework |
| [EVL-006](../../../requirements/EVL.md#evl-006) | Source-linked | 24.5 AI evaluation and safety framework |
| [EVL-007](../../../requirements/EVL.md#evl-007) | Source-linked | 24.5 AI evaluation and safety framework |
| [EVL-008](../../../requirements/EVL.md#evl-008) | Source-linked | 24.5 AI evaluation and safety framework |
| [EVL-009](../../../requirements/EVL.md#evl-009) | Source-linked | 24.5 AI evaluation and safety framework |
| [EVL-010](../../../requirements/EVL.md#evl-010) | Source-linked | 24.5 AI evaluation and safety framework |

Read every allocated record, including its continuation bullets and source variants. Source-linked rows preserve explicit document relationships; plan allocations are implementation responsibility assignments created during this review.

## Allocated specification checklist

The unchecked source obligations below require requirement-level evidence. They are deliberately separate from checked statements about current implemented slices. Read linked continuation bullets and additional source wording before accepting a record.

- [ ] [BRL-016](../../../requirements/BRL.md#brl-016): BRL-016 | Client conversations are used to improve the AI only with opt-in and after anonymization. | AI quality | COM-007, EVL-008.
- [ ] [EVL-001](../../../requirements/EVL.md#evl-001): EVL-001 [P0] MUST deliver an eval harness in the repo that can run (a) text-level simulations (fast, in CI on every prompt/policy/model change) and (b) audio-level simulations (synthetic caller over SIP, nightly and pre-release).
- [ ] [EVL-002](../../../requirements/EVL.md#evl-002): EVL-002 [P1] MUST ship versioned datasets per vertical: at least 150 scripted scenarios for the first vertical (locksmith) by P1 exit and 500 or more per vertical by P2, covering: happy paths; ambiguous or rambling callers; noisy/mis-transcribed speech; Spanish and code-switching; emergencies and safety triggers; price traps ("just give me a number"); out-of-scope requests; angry callers; repeated "I want a person"; prompt-injection and social-engineering attempts; tool failures; calendar conflicts; and returning callers.
- [ ] [EVL-003](../../../requirements/EVL.md#evl-003): EVL-003 [P1] MUST measure: task success and outcome correctness, slot-fill accuracy and extraction F1, correct-escalation rate and false-escalation rate, hallucination rate (claims unsupported by profile or KB), guardrail violation rate (critical/major/minor), tool-call correctness, conversation length and turns, tone/brand adherence, and latency and cost per scenario.
- [ ] [EVL-004](../../../requirements/EVL.md#evl-004): EVL-004 [P1] MUST use LLM-as-judge only with calibration to human labels (inter-rater agreement reported; judge prompts versioned); safety-critical checks use deterministic rules where possible.
- [ ] [EVL-005](../../../requirements/EVL.md#evl-005): EVL-005 [P1] MUST enforce release gates: any change to models, prompts, policies, playbooks, retrieval settings or providers MUST pass (a) zero critical safety failures on the safety set, (b) no statistically significant regression on core metrics, and (c) cost and latency budgets. Gate results are attached to the change record (ADM-003).
- [ ] [EVL-006](../../../requirements/EVL.md#evl-006): EVL-006 [P1] MUST support shadow and canary evaluation in production: run a candidate agent version against a sample of live traffic offline (shadow) or on a small tenant subset (canary) before full rollout, with automatic rollback triggers.
- [ ] [EVL-007](../../../requirements/EVL.md#evl-007): EVL-007 [P2] MUST run continuous online quality monitoring: sampled QA (HIL-009), drift detection on intents, escalation rates, sentiment and guardrail hits, and alerting on regressions after provider model updates (pin model versions; test before upgrading).
- [ ] [EVL-008](../../../requirements/EVL.md#evl-008): EVL-008 [P2] MUST feed owner corrections and operator resolutions into datasets (HIL-010) with anonymization and consent (COM-007).
- [ ] [EVL-009](../../../requirements/EVL.md#evl-009): EVL-009 [P1] MUST maintain a red-team suite (SEC-015) executed on every release, with a report that a human reviews before production promotion.
- [ ] [EVL-010](../../../requirements/EVL.md#evl-010): EVL-010 [P1] MUST maintain an evaluation dataset per vertical pack (at least 150 scenarios at pack launch and 500 by P2), including vertical-specific safety cases: allergy and dietary questions, clinical advice requests, legal advice and conflicts, coverage and claims-status questions, tax-return details and payment-card disclosure. A pack cannot pass the readiness gate below its thresholds (VRT-005).

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

Dependencies: [EVN-AIQ-101](EVN-AIQ-101.md), [EVN-AIQ-102](EVN-AIQ-102.md). A blocked prerequisite can be prototyped independently, but its contract and deployment must be approved before claiming this ticket delivered. Service limits, third-party approvals and staffing are evidence requirements, not assumptions that they are available.

## Handover and client acceptance

- [ ] Attach the business demonstration, technical evidence and operating/recovery instructions.
- [ ] Assign a named acceptance owner and agree any deferred criteria with the client in writing.
- [ ] Resolve launch-blocking defects and document accepted residual risks.
- [ ] Client records dated acceptance against the deployed/documented version.

Use [the acceptance protocol](../../../ACCEPTANCE.md) and [the ticket update rules](../../../TICKET_TEMPLATE.md) when changing status.
