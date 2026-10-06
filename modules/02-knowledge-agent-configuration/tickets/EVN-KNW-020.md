# EVN-KNW-020 - Approve what the AI knows

Project: EverOnnAI. Module: [Knowledge, agent configuration and approved business memory](../README.md). Source business requirement [BR-020](../../../requirements/BR.md#br-020).

| Tracking dimension | Disposition |
| --- | --- |
| Engineering | Partial |
| QA | Existing checks are evidence for current slices; full ticket criteria remain pending |
| Deployment | Current local snapshot; verify ticket-specific hosted rollout and configuration |
| Business acceptance | Pending client review; no signed acceptance recorded |
| Owner | AI Lead + Backend Lead (proposed role; named person unassigned) |
| Priority / phase | Must / P1 |
| Estimate | TBD after scope/architecture agreement; no delivery date committed |
| Dependencies | [EVN-KNW-101](EVN-KNW-101.md), [EVN-KNW-102](EVN-KNW-102.md) |

## Business deliverable

Approve what the AI knows. Clients control what the AI knows and says and explicitly approve it before going live.

The client accepts the demonstrated outcome and evidence, rather than the existence of a route, table or screen. This ticket does not certify the whole source requirement as complete.

## Current implemented slice

- [x] Owners maintain facts, services and approved FAQs; unapproved knowledge is excluded from prompts.

## Remaining delivery checklist

- [ ] Add immutable published profile/KB versions, import approval diffs and recorded go-live approval.

## Technical component

- [ ] Implement the module boundary and contracts for: Ingestion, versioned approval and atomic publication.
- [ ] Maintain tenant boundaries, explicit state transitions, access policy and failure handling for the delivered workflow.
- [ ] Resolve applicable architecture decisions before committing to a new provider or infrastructure baseline.

## DB

Existing module persistence: business_profiles, business_services, knowledge_items; scoped website aiMemory in workspace payload.

The following records/contracts are proposed or require extension; their names are planning terms, not assertions that production tables exist.

- [ ] profile_versions, kb_items, kb_approvals.
- [ ] Review scope keys, uniqueness, indexes, retention and migration compatibility; backfill safely and preserve existing tenant records.

## UI

- [ ] Knowledge approval, diff and publication.
- [ ] Provide loading, empty, validation, permission-denied and recoverable failure states with keyboard and mobile access.
- [ ] Show observed facts and pending states accurately; do not present estimates, configured flags or mock results as confirmed business actions.

## Translate - business-to-technical mapping

| Business rule / outcome | Technical responsibility | Evidence needed |
| --- | --- | --- |
| Approve what the AI knows. Clients control what the AI knows and says and explicitly approve it before going live. | Ingestion, versioned approval and atomic publication | Tenant-scoped end-to-end demonstration of the outcome |
| Add immutable published profile/KB versions, import approval diffs and recorded go-live approval. | profile_versions, kb_items, kb_approvals; Knowledge approval, diff and publication | Migration/contracts, visible state and failure-path evidence |
| Safe, truthful AI behaviour where applicable | Agents use only the published approved knowledge version | Approved context, verified side-effect receipts and evaluation results or justified N/A |
| Client can approve delivery | QA report, rollout evidence and named acceptance owner | Evidence links and dated client sign-off |

This section means requirements-to-implementation mapping. It does not mean language translation; source language obligations are tracked in their own requirements.

## Backend services

- [ ] Ingestion, versioned approval and atomic publication.
- [ ] Define request/response/event schemas, authorisation and input validation for each affected operation.
- [ ] For writes and provider effects, define idempotency, retry/timeout, receipts and reconciliation; document N/A where no side effects exist.
- [ ] Expose actionable status and scoped logs without secrets; distinguish completed, failed and uncertain outcomes.

## AI component

- [ ] Agents use only the published approved knowledge version.
- [ ] Record instruction/knowledge/tool versions, measured quality, tenant scope, cost and safe fallback; a Markdown standard alone is not a passed evaluation.

## Testing / QA

- [ ] Exercise the intended user journey with real tenant-scoped state; cover forbidden role and cross-tenant requests.
- [ ] Test malformed inputs, provider failure, retries/replays and cancellation as applicable; keep deterministic mocks separate from live-provider evidence.
- [ ] Review desktop/mobile accessibility, factual copy and failure recovery in the delivered UI.
- [ ] Attach test environment, code/config/instruction versions, results and remaining defects to the acceptance report.

| Source test | Scenario | Required pass criteria | Current disposition |
| --- | --- | --- | --- |
| [AT-01](../../../requirements/AT.md#at-01) | Owner claims a business from a Google listing | Private preview and draft profile in under 2 minutes; page is not indexable; no real phone number shown; unverified claims are highlighted for the owner | Full source scenario not evidenced; client acceptance pending |
| [AT-02](../../../requirements/AT.md#at-02) | Owner verifies, approves knowledge, connects forwarding, tests and goes live | Forwarding verified by an automated test call before the channel is live; approval recorded with the version id; test call and chat run against the draft without billing | Full source scenario not evidenced; client acceptance pending |

Source stories: [US-005](../../../requirements/US.md#us-005), [US-007](../../../requirements/US.md#us-007).

## Deployment

- [ ] Confirm approved hosting/database/provider architecture and required credentials in the deployment environment.
- [ ] Apply compatible migrations/configuration in staging, rehearse rollback, then promote the reviewed artifact.
- [ ] Verify the actual hosted workflow, monitoring, fallback and customer-visible errors after release.
- [ ] Update CODE_PROFILE.md, PROJECT_DATA_FLOW.md and CLIENT_TECHNICAL_QA.md in the application when behaviour or architecture changes.
- [ ] Record deployment identity, operator, timestamp and rollback evidence; document-only tickets instead record the reviewed Git commit.

## Source traceability

| Source ID | Mapping basis | Source section |
| --- | --- | --- |
| [AT-01](../../../requirements/AT.md#at-01) | Source-linked | 25.2 Acceptance tests |
| [AT-02](../../../requirements/AT.md#at-02) | Source-linked | 25.2 Acceptance tests |
| [BO-3](../../../requirements/BO.md#bo-3) | Source-linked | 3.1 Business objectives |
| [BR-020](../../../requirements/BR.md#br-020) | Source-linked | 7.4 Knowledge and client control |
| [BRL-001](../../../requirements/BRL.md#brl-001) | Plan allocation / source cross-reference | 8. Business rules |
| [KNW-001](../../../requirements/KNW.md#knw-001) | Source-linked | 13.1 Business profile (structured facts) |
| [KNW-005](../../../requirements/KNW.md#knw-005) | Source-linked | 13.2 Unstructured knowledge (RAG) |
| [ONB-005](../../../requirements/ONB.md#onb-005) | Source-linked | 12.2 Requirements |
| [US-005](../../../requirements/US.md#us-005) | Source-linked | EP-02 Knowledge and agent control |
| [US-007](../../../requirements/US.md#us-007) | Source-linked | EP-02 Knowledge and agent control |
| [VOX-018](../../../requirements/VOX.md#vox-018) | Plan allocation / source cross-reference | 14.5 Requirements: business behavior |

Read every allocated record, including its continuation bullets and source variants. Source-linked rows preserve explicit document relationships; plan allocations are implementation responsibility assignments created during this review.

## Allocated specification checklist

The unchecked source obligations below require requirement-level evidence. They are deliberately separate from checked statements about current implemented slices. Read linked continuation bullets and additional source wording before accepting a record.

- [ ] [BRL-001](../../../requirements/BRL.md#brl-001): BRL-001 | The AI answers only from the client's approved knowledge. When it does not know, it says so and captures a callback. | AI agents | KNW-005, KNW-007, POL-001.
- [ ] [KNW-001](../../../requirements/KNW.md#knw-001): KNW-001 [P1] MUST store the profile as a versioned, schema-validated JSON document (JSON Schema published in the repo) plus normalized tables for query. Each save creates an immutable version; agents run against a published version, never a draft.
- [ ] [KNW-005](../../../requirements/KNW.md#knw-005): KNW-005 [P1] MUST support owner approval of every KB item before it becomes agent-visible, with diff view on edits. Auto-imported content enters as pending.
- [ ] [ONB-005](../../../requirements/ONB.md#onb-005): ONB-005 [P1] MUST require the owner to explicitly approve the AI's knowledge and greeting before go-live (a recorded approval event with the approved version id).
- [ ] [VOX-018](../../../requirements/VOX.md#vox-018): VOX-018 [P1] MUST check service area using geocoding of the captured address and politely decline or route out-of-area requests per tenant policy.

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
