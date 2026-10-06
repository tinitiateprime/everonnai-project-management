# EVN-AIQ-076 - Safe AI change control

Project: EverOnnAI. Module: [AI runtime, skills, provider portability and evaluation](../README.md). Source business requirement [BR-076](../../../requirements/BR.md#br-076).

| Tracking dimension | Disposition |
| --- | --- |
| Engineering | Partial |
| QA | Existing checks are evidence for current slices; full ticket criteria remain pending |
| Deployment | Current local snapshot; verify ticket-specific hosted rollout and configuration |
| Business acceptance | Pending client review; no signed acceptance recorded |
| Owner | AI Lead + QA Lead (proposed role; named person unassigned) |
| Priority / phase | Must / P1 |
| Estimate | TBD after scope/architecture agreement; no delivery date committed |
| Dependencies | [EVN-AIQ-102](EVN-AIQ-102.md), [EVN-AIQ-103](EVN-AIQ-103.md) |

## Business deliverable

Safe AI change control. Changes to AI behavior are tested against safety and quality benchmarks before release and can be rolled back instantly.

The client accepts the demonstrated outcome and evidence, rather than the existence of a route, table or screen. This ticket does not certify the whole source requirement as complete.

## Current implemented slice

- [x] Versioned Markdown/digests, guarded tools and website rollback exist.

## Remaining delivery checklist

- [ ] Add immutable agent versions, calibrated text/audio datasets, red-team gates, shadow/canary and real kill/rollback controls.

## Technical component

- [ ] Implement the module boundary and contracts for: Evaluation pipeline, model registry and rollback.
- [ ] Maintain tenant boundaries, explicit state transitions, access policy and failure handling for the delivered workflow.
- [ ] Resolve applicable architecture decisions before committing to a new provider or infrastructure baseline.

## DB

Existing module persistence: Skill version/digest traces, generation metadata, scoped preferences and usage records.

The following records/contracts are proposed or require extension; their names are planning terms, not assertions that production tables exist.

- [ ] agent_versions, eval_runs, rollout_assignments.
- [ ] Review scope keys, uniqueness, indexes, retention and migration compatibility; backfill safely and preserve existing tenant records.

## UI

- [ ] Prompt diff, evaluation and rollout approval.
- [ ] Provide loading, empty, validation, permission-denied and recoverable failure states with keyboard and mobile access.
- [ ] Show observed facts and pending states accurately; do not present estimates, configured flags or mock results as confirmed business actions.

## Translate - business-to-technical mapping

| Business rule / outcome | Technical responsibility | Evidence needed |
| --- | --- | --- |
| Safe AI change control. Changes to AI behavior are tested against safety and quality benchmarks before release and can be rolled back instantly. | Evaluation pipeline, model registry and rollback | Tenant-scoped end-to-end demonstration of the outcome |
| Add immutable agent versions, calibrated text/audio datasets, red-team gates, shadow/canary and real kill/rollback controls. | agent_versions, eval_runs, rollout_assignments; Prompt diff, evaluation and rollout approval | Migration/contracts, visible state and failure-path evidence |
| Safe, truthful AI behaviour where applicable | Gate every prompt/model/provider change on safety/quality/cost | Approved context, verified side-effect receipts and evaluation results or justified N/A |
| Client can approve delivery | QA report, rollout evidence and named acceptance owner | Evidence links and dated client sign-off |

This section means requirements-to-implementation mapping. It does not mean language translation; source language obligations are tracked in their own requirements.

## Backend services

- [ ] Evaluation pipeline, model registry and rollback.
- [ ] Define request/response/event schemas, authorisation and input validation for each affected operation.
- [ ] For writes and provider effects, define idempotency, retry/timeout, receipts and reconciliation; document N/A where no side effects exist.
- [ ] Expose actionable status and scoped logs without secrets; distinguish completed, failed and uncertain outcomes.

## AI component

- [ ] Gate every prompt/model/provider change on safety/quality/cost.
- [ ] Record instruction/knowledge/tool versions, measured quality, tenant scope, cost and safe fallback; a Markdown standard alone is not a passed evaluation.

## Testing / QA

- [ ] Exercise the intended user journey with real tenant-scoped state; cover forbidden role and cross-tenant requests.
- [ ] Test malformed inputs, provider failure, retries/replays and cancellation as applicable; keep deterministic mocks separate from live-provider evidence.
- [ ] Review desktop/mobile accessibility, factual copy and failure recovery in the delivered UI.
- [ ] Attach test environment, code/config/instruction versions, results and remaining defects to the acceptance report.

| Source test | Scenario | Required pass criteria | Current disposition |
| --- | --- | --- | --- |
| [AT-15](../../../requirements/AT.md#at-15) | Prompt injection and social engineering on voice, chat and imported web content | Zero policy breaches across the red-team suite | Full source scenario not evidenced; client acceptance pending |
| [AT-54](../../../requirements/AT.md#at-54) | AI change blocked on regression | A prompt change that regresses safety or core metrics is blocked; a passing change can be canaried and rolled back instantly | Full source scenario not evidenced; client acceptance pending |

Source stories: [US-006](../../../requirements/US.md#us-006), [US-046](../../../requirements/US.md#us-046).

## Deployment

- [ ] Confirm approved hosting/database/provider architecture and required credentials in the deployment environment.
- [ ] Apply compatible migrations/configuration in staging, rehearse rollback, then promote the reviewed artifact.
- [ ] Verify the actual hosted workflow, monitoring, fallback and customer-visible errors after release.
- [ ] Update CODE_PROFILE.md, PROJECT_DATA_FLOW.md and CLIENT_TECHNICAL_QA.md in the application when behaviour or architecture changes.
- [ ] Record deployment identity, operator, timestamp and rollback evidence; document-only tickets instead record the reviewed Git commit.

## Source traceability

| Source ID | Mapping basis | Source section |
| --- | --- | --- |
| [ADM-003](../../../requirements/ADM.md#adm-003) | Source-linked | 19.3 Admin back-office (ADM) |
| [AGT-004](../../../requirements/AGT.md#agt-004) | Source-linked | 13.3 Agent configuration |
| [AT-15](../../../requirements/AT.md#at-15) | Source-linked | 25.2 Acceptance tests |
| [AT-54](../../../requirements/AT.md#at-54) | Source-linked | 25.2 Acceptance tests |
| [BO-3](../../../requirements/BO.md#bo-3) | Source-linked | 3.1 Business objectives |
| [BR-076](../../../requirements/BR.md#br-076) | Source-linked | 7.12 Ownership and engineering |
| [EVL-005](../../../requirements/EVL.md#evl-005) | Source-linked | 24.5 AI evaluation and safety framework |
| [US-006](../../../requirements/US.md#us-006) | Source-linked | EP-02 Knowledge and agent control |
| [US-046](../../../requirements/US.md#us-046) | Source-linked | EP-09 Administration and operations |

Read every allocated record, including its continuation bullets and source variants. Source-linked rows preserve explicit document relationships; plan allocations are implementation responsibility assignments created during this review.

## Allocated specification checklist

The unchecked source obligations below require requirement-level evidence. They are deliberately separate from checked statements about current implemented slices. Read linked continuation bullets and additional source wording before accepting a record.

- [ ] [ADM-003](../../../requirements/ADM.md#adm-003): ADM-003 [P1] MUST provide prompt and policy management: versioned platform policy and vertical templates with diff, review and approval, staged rollout with canary tenants, automated eval gate (§24.5), and instant rollback.
- [ ] [AGT-004](../../../requirements/AGT.md#agt-004): AGT-004 [P1] MUST support draft → test → publish → rollback for every agent configuration change with a version history and one-click rollback.
- [ ] [EVL-005](../../../requirements/EVL.md#evl-005): EVL-005 [P1] MUST enforce release gates: any change to models, prompts, policies, playbooks, retrieval settings or providers MUST pass (a) zero critical safety failures on the safety set, (b) no statistically significant regression on core metrics, and (c) cost and latency budgets. Gate results are attached to the change record (ADM-003).

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

Dependencies: [EVN-AIQ-102](EVN-AIQ-102.md), [EVN-AIQ-103](EVN-AIQ-103.md). A blocked prerequisite can be prototyped independently, but its contract and deployment must be approved before claiming this ticket delivered. Service limits, third-party approvals and staffing are evidence requirements, not assumptions that they are available.

## Handover and client acceptance

- [ ] Attach the business demonstration, technical evidence and operating/recovery instructions.
- [ ] Assign a named acceptance owner and agree any deferred criteria with the client in writing.
- [ ] Resolve launch-blocking defects and document accepted residual risks.
- [ ] Client records dated acceptance against the deployed/documented version.

Use [the acceptance protocol](../../../ACCEPTANCE.md) and [the ticket update rules](../../../TICKET_TEMPLATE.md) when changing status.
