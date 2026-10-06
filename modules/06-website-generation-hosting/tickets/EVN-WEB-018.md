# EVN-WEB-018 - 1,000 sites per day

Project: EverOnnAI. Module: [AI website generation, editing, publishing and domains](../README.md). Source business requirement [BR-018](../../../requirements/BR.md#br-018).

| Tracking dimension | Disposition |
| --- | --- |
| Engineering | Planned |
| QA | Existing checks are evidence for current slices; full ticket criteria remain pending |
| Deployment | Current local snapshot; verify ticket-specific hosted rollout and configuration |
| Business acceptance | Pending client review; no signed acceptance recorded |
| Owner | Frontend Lead + AI Lead + Platform Lead (proposed role; named person unassigned) |
| Priority / phase | Must / P2 |
| Estimate | TBD after scope/architecture agreement; no delivery date committed |
| Dependencies | [EVN-WEB-101](EVN-WEB-101.md), [EVN-WEB-102](EVN-WEB-102.md), [EVN-WEB-103](EVN-WEB-103.md) |

## Business deliverable

1,000 sites per day. The platform can generate and host 1,000 new sites per day.

The client accepts the demonstrated outcome and evidence, rather than the existence of a route, table or screen. This ticket does not certify the whole source requirement as complete.

## Current implemented slice

- [ ] Generation runs in one request with up to three concurrent concept calls.

The current statement describes prerequisites or context; this business deliverable has not been demonstrated.

## Remaining delivery checklist

- [ ] Prove 1,000 sites/day and 300/hour bursts using durable fair queues, quotas, storage and measured cost/load tests.

## Technical component

- [ ] Implement the module boundary and contracts for: Durable workers, fair scheduling, canary updates and artifact delivery.
- [ ] Maintain tenant boundaries, explicit state transitions, access policy and failure handling for the delivered workflow.
- [ ] Resolve applicable architecture decisions before committing to a new provider or infrastructure baseline.

## DB

Existing module persistence: website_projects and immutable draft/live release snapshots in scoped workspace records.

The following records/contracts are proposed or require extension; their names are planning terms, not assertions that production tables exist.

- [ ] generation_jobs, checkpoints, queue_metrics.
- [ ] Review scope keys, uniqueness, indexes, retention and migration compatibility; backfill safely and preserve existing tenant records.

## UI

- [ ] Bulk jobs, retry, cancellation and progress.
- [ ] Provide loading, empty, validation, permission-denied and recoverable failure states with keyboard and mobile access.
- [ ] Show observed facts and pending states accurately; do not present estimates, configured flags or mock results as confirmed business actions.

## Translate - business-to-technical mapping

| Business rule / outcome | Technical responsibility | Evidence needed |
| --- | --- | --- |
| 1,000 sites per day. The platform can generate and host 1,000 new sites per day. | Durable workers, fair scheduling, canary updates and artifact delivery | Tenant-scoped end-to-end demonstration of the outcome |
| Prove 1,000 sites/day and 300/hour bursts using durable fair queues, quotas, storage and measured cost/load tests. | generation_jobs, checkpoints, queue_metrics; Bulk jobs, retry, cancellation and progress | Migration/contracts, visible state and failure-path evidence |
| Safe, truthful AI behaviour where applicable | Rate-aware batches, checkpoints and per-site budgets | Approved context, verified side-effect receipts and evaluation results or justified N/A |
| Client can approve delivery | QA report, rollout evidence and named acceptance owner | Evidence links and dated client sign-off |

This section means requirements-to-implementation mapping. It does not mean language translation; source language obligations are tracked in their own requirements.

## Backend services

- [ ] Durable workers, fair scheduling, canary updates and artifact delivery.
- [ ] Define request/response/event schemas, authorisation and input validation for each affected operation.
- [ ] For writes and provider effects, define idempotency, retry/timeout, receipts and reconciliation; document N/A where no side effects exist.
- [ ] Expose actionable status and scoped logs without secrets; distinguish completed, failed and uncertain outcomes.

## AI component

- [ ] Rate-aware batches, checkpoints and per-site budgets.
- [ ] Record instruction/knowledge/tool versions, measured quality, tenant scope, cost and safe fallback; a Markdown standard alone is not a passed evaluation.

## Testing / QA

- [ ] Exercise the intended user journey with real tenant-scoped state; cover forbidden role and cross-tenant requests.
- [ ] Test malformed inputs, provider failure, retries/replays and cancellation as applicable; keep deterministic mocks separate from live-provider evidence.
- [ ] Review desktop/mobile accessibility, factual copy and failure recovery in the delivered UI.
- [ ] Attach test environment, code/config/instruction versions, results and remaining defects to the acceptance report.

| Source test | Scenario | Required pass criteria | Current disposition |
| --- | --- | --- | --- |
| [AT-05](../../../requirements/AT.md#at-05) | Bulk generation at 1,000 sites per day with bursts of 300 per hour | Throughput met; per-site cost tracked; prohibited categories blocked | Full source scenario not evidenced; client acceptance pending |

Source stories: [US-039](../../../requirements/US.md#us-039).

## Deployment

- [ ] Confirm approved hosting/database/provider architecture and required credentials in the deployment environment.
- [ ] Apply compatible migrations/configuration in staging, rehearse rollback, then promote the reviewed artifact.
- [ ] Verify the actual hosted workflow, monitoring, fallback and customer-visible errors after release.
- [ ] Update CODE_PROFILE.md, PROJECT_DATA_FLOW.md and CLIENT_TECHNICAL_QA.md in the application when behaviour or architecture changes.
- [ ] Record deployment identity, operator, timestamp and rollback evidence; document-only tickets instead record the reviewed Git commit.

## Source traceability

| Source ID | Mapping basis | Source section |
| --- | --- | --- |
| [AT-05](../../../requirements/AT.md#at-05) | Source-linked | 25.2 Acceptance tests |
| [BO-6](../../../requirements/BO.md#bo-6) | Source-linked | 3.1 Business objectives |
| [BR-018](../../../requirements/BR.md#br-018) | Source-linked | 7.3 Websites |
| [LT-003](../../../requirements/LT.md#lt-003) | Source-linked | 23.7 Load and soak testing requirements |
| [US-039](../../../requirements/US.md#us-039) | Source-linked | EP-07 Websites |
| [WEB-001](../../../requirements/WEB.md#web-001) | Source-linked | 18.3 Requirements |
| [WEB-011](../../../requirements/WEB.md#web-011) | Source-linked | 18.3 Requirements |

Read every allocated record, including its continuation bullets and source variants. Source-linked rows preserve explicit document relationships; plan allocations are implementation responsibility assignments created during this review.

## Allocated specification checklist

The unchecked source obligations below require requirement-level evidence. They are deliberately separate from checked statements about current implemented slices. Read linked continuation bullets and additional source wording before accepting a record.

- [ ] [LT-003](../../../requirements/LT.md#lt-003): LT-003 [P2] MUST load-test the generation pipeline at 1,000 sites/day with bursts of 300/hour, including provider rate-limit behavior and cost accounting.
- [ ] [WEB-001](../../../requirements/WEB.md#web-001): WEB-001 [P1] MUST implement the generation pipeline as durable jobs: (1) data collection (profile, imported content), (2) content generation with schema-constrained LLM output and brand/tone controls, (3) image selection or generation from licensed sources and the owner's photos (P1: owner photos, licensed stock; generated imagery only where licensing and disclosure rules are met), (4) Site Spec validation and safety checks (no invented licenses, awards, or claims), (5) render, (6) preview deployment. Target: under 2 minutes p50 to preview; throughput target 1,000 sites/day sustained with burst to 300 per hour (P2), with per-site LLM cost tracked and capped.
- [ ] [WEB-011](../../../requirements/WEB.md#web-011): WEB-011 [P2] MUST support bulk operations: template updates rolled out across all sites (with canary and rollback), bulk regeneration, and bulk domain checks; all through queued jobs with progress reporting.

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
