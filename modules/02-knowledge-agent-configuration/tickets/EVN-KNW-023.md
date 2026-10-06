# EVN-KNW-023 - Explain and correct

Project: EverOnnAI. Module: [Knowledge, agent configuration and approved business memory](../README.md). Source business requirement [BR-023](../../../requirements/BR.md#br-023).

| Tracking dimension | Disposition |
| --- | --- |
| Engineering | Partial |
| QA | Existing checks are evidence for current slices; full ticket criteria remain pending |
| Deployment | Current local snapshot; verify ticket-specific hosted rollout and configuration |
| Business acceptance | Pending client review; no signed acceptance recorded |
| Owner | AI Lead + Backend Lead (proposed role; named person unassigned) |
| Priority / phase | Should / P1 |
| Estimate | TBD after scope/architecture agreement; no delivery date committed |
| Dependencies | [EVN-KNW-101](EVN-KNW-101.md), [EVN-KNW-102](EVN-KNW-102.md) |

## Business deliverable

Explain and correct. Clients see why the AI said something and can correct it.

The client accepts the demonstrated outcome and evidence, rather than the existence of a route, table or screen. This ticket does not certify the whole source requirement as complete.

## Current implemented slice

- [x] Generation records skill versions and approved website change requests.

## Remaining delivery checklist

- [ ] Add per-message field/chunk/tool/policy provenance, knowledge gaps and approved correction workflows.

## Technical component

- [ ] Implement the module boundary and contracts for: Trace/provenance service and review queue.
- [ ] Maintain tenant boundaries, explicit state transitions, access policy and failure handling for the delivered workflow.
- [ ] Resolve applicable architecture decisions before committing to a new provider or infrastructure baseline.

## DB

Existing module persistence: business_profiles, business_services, knowledge_items; scoped website aiMemory in workspace payload.

The following records/contracts are proposed or require extension; their names are planning terms, not assertions that production tables exist.

- [ ] message_provenance, corrections, knowledge_gaps.
- [ ] Review scope keys, uniqueness, indexes, retention and migration compatibility; backfill safely and preserve existing tenant records.

## UI

- [ ] Why-this-answer, correction and add-to-knowledge.
- [ ] Provide loading, empty, validation, permission-denied and recoverable failure states with keyboard and mobile access.
- [ ] Show observed facts and pending states accurately; do not present estimates, configured flags or mock results as confirmed business actions.

## Translate - business-to-technical mapping

| Business rule / outcome | Technical responsibility | Evidence needed |
| --- | --- | --- |
| Explain and correct. Clients see why the AI said something and can correct it. | Trace/provenance service and review queue | Tenant-scoped end-to-end demonstration of the outcome |
| Add per-message field/chunk/tool/policy provenance, knowledge gaps and approved correction workflows. | message_provenance, corrections, knowledge_gaps; Why-this-answer, correction and add-to-knowledge | Migration/contracts, visible state and failure-path evidence |
| Safe, truthful AI behaviour where applicable | Suggestions cannot silently change published prompts or knowledge | Approved context, verified side-effect receipts and evaluation results or justified N/A |
| Client can approve delivery | QA report, rollout evidence and named acceptance owner | Evidence links and dated client sign-off |

This section means requirements-to-implementation mapping. It does not mean language translation; source language obligations are tracked in their own requirements.

## Backend services

- [ ] Trace/provenance service and review queue.
- [ ] Define request/response/event schemas, authorisation and input validation for each affected operation.
- [ ] For writes and provider effects, define idempotency, retry/timeout, receipts and reconciliation; document N/A where no side effects exist.
- [ ] Expose actionable status and scoped logs without secrets; distinguish completed, failed and uncertain outcomes.

## AI component

- [ ] Suggestions cannot silently change published prompts or knowledge.
- [ ] Record instruction/knowledge/tool versions, measured quality, tenant scope, cost and safe fallback; a Markdown standard alone is not a passed evaluation.

## Testing / QA

- [ ] Exercise the intended user journey with real tenant-scoped state; cover forbidden role and cross-tenant requests.
- [ ] Test malformed inputs, provider failure, retries/replays and cancellation as applicable; keep deterministic mocks separate from live-provider evidence.
- [ ] Review desktop/mobile accessibility, factual copy and failure recovery in the delivered UI.
- [ ] Attach test environment, code/config/instruction versions, results and remaining defects to the acceptance report.

| Source test | Scenario | Required pass criteria | Current disposition |
| --- | --- | --- | --- |
| [AT-39](../../../requirements/AT.md#at-39) | Explainability and correction | The owner opens a call, sees the knowledge sources, tools and rules used, flags a wrong answer, and a knowledge proposal and an evaluation case are created | Full source scenario not evidenced; client acceptance pending |

Source stories: [US-007](../../../requirements/US.md#us-007), [US-044](../../../requirements/US.md#us-044).

## Deployment

- [ ] Confirm approved hosting/database/provider architecture and required credentials in the deployment environment.
- [ ] Apply compatible migrations/configuration in staging, rehearse rollback, then promote the reviewed artifact.
- [ ] Verify the actual hosted workflow, monitoring, fallback and customer-visible errors after release.
- [ ] Update CODE_PROFILE.md, PROJECT_DATA_FLOW.md and CLIENT_TECHNICAL_QA.md in the application when behaviour or architecture changes.
- [ ] Record deployment identity, operator, timestamp and rollback evidence; document-only tickets instead record the reviewed Git commit.

## Source traceability

| Source ID | Mapping basis | Source section |
| --- | --- | --- |
| [AT-39](../../../requirements/AT.md#at-39) | Source-linked | 25.2 Acceptance tests |
| [BO-3](../../../requirements/BO.md#bo-3) | Source-linked | 3.1 Business objectives |
| [BO-8](../../../requirements/BO.md#bo-8) | Source-linked | 3.1 Business objectives |
| [BR-023](../../../requirements/BR.md#br-023) | Source-linked | 7.4 Knowledge and client control |
| [BRL-001](../../../requirements/BRL.md#brl-001) | Plan allocation / source cross-reference | 8. Business rules |
| [HIL-008](../../../requirements/HIL.md#hil-008) | Source-linked | 16.5 Quality, learning and control of the human layer |
| [KNW-007](../../../requirements/KNW.md#knw-007) | Source-linked | 13.2 Unstructured knowledge (RAG) |
| [KNW-009](../../../requirements/KNW.md#knw-009) | Source-linked | 13.2 Unstructured knowledge (RAG) |
| [US-007](../../../requirements/US.md#us-007) | Source-linked | EP-02 Knowledge and agent control |
| [US-044](../../../requirements/US.md#us-044) | Source-linked | EP-09 Administration and operations |

Read every allocated record, including its continuation bullets and source variants. Source-linked rows preserve explicit document relationships; plan allocations are implementation responsibility assignments created during this review.

## Allocated specification checklist

The unchecked source obligations below require requirement-level evidence. They are deliberately separate from checked statements about current implemented slices. Read linked continuation bullets and additional source wording before accepting a record.

- [ ] [BRL-001](../../../requirements/BRL.md#brl-001): BRL-001 | The AI answers only from the client's approved knowledge. When it does not know, it says so and captures a callback. | AI agents | KNW-005, KNW-007, POL-001.
- [ ] [HIL-008](../../../requirements/HIL.md#hil-008): HIL-008 [P1] MUST support post-conversation review by the owner: thumbs up/down, "correct this answer", "add to knowledge", "never say this". Owner corrections create KB proposals (KNW-005) and eval cases (§24.5).
- [ ] [KNW-007](../../../requirements/KNW.md#knw-007): KNW-007 [P1] MUST implement the "I don't know" contract: when retrieval fails or confidence is low, the agent states it will have someone follow up, captures the question and contact details, and creates a knowledge_gap item shown to the owner ("Your AI was asked this and didn't know. Add an answer?"). Answering it updates the KB after approval.
- [ ] [KNW-009](../../../requirements/KNW.md#knw-009): KNW-009 [P1] MUST provide explainability: for any AI message, the dashboard shows which profile fields and KB chunks were used, which tools were called, and which policy rules fired.

## Existing code / check evidence

- `features/everonn/types.ts` - inspected current application working tree; see [snapshot evidence](../../../EVIDENCE.md).
- `features/agent-runtime/prompt-composer.ts` - inspected current application working tree; see [snapshot evidence](../../../EVIDENCE.md).
- `features/agent-runtime/memory.ts` - inspected current application working tree; see [snapshot evidence](../../../EVIDENCE.md).
- `features/agent-runtime/skill-loader.ts` - inspected current application working tree; see [snapshot evidence](../../../EVIDENCE.md).
- `app/api/agent-runtime/memory/route.ts` - inspected current application working tree; see [snapshot evidence](../../../EVIDENCE.md).
- `components/dashboard/website-design-editor.tsx` - inspected current application working tree; see [snapshot evidence](../../../EVIDENCE.md).
- Relevant automated checks: `tests/agent-runtime.test.ts`, `tests/json-workspace.test.ts`. Their scope is bounded by [current validation](../../../CURRENT_STATE.md).

## Blockers and boundaries

Module risk: Structured FAQs and website memory are not document RAG, immutable published KB/agent versions or assistant long-term memory.

Dependencies: [EVN-KNW-101](EVN-KNW-101.md), [EVN-KNW-102](EVN-KNW-102.md). A blocked prerequisite can be prototyped independently, but its contract and deployment must be approved before claiming this ticket delivered. Service limits, third-party approvals and staffing are evidence requirements, not assumptions that they are available.

## Handover and client acceptance

- [ ] Attach the business demonstration, technical evidence and operating/recovery instructions.
- [ ] Assign a named acceptance owner and agree any deferred criteria with the client in writing.
- [ ] Resolve launch-blocking defects and document accepted residual risks.
- [ ] Client records dated acceptance against the deployed/documented version.

Use [the acceptance protocol](../../../ACCEPTANCE.md) and [the ticket update rules](../../../TICKET_TEMPLATE.md) when changing status.
