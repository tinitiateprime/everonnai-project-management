# EVN-KNW-101 - Make approved business documents usable by the assistant

Project: EverOnnAI. Module: [Knowledge, agent configuration and approved business memory](../README.md). Technical delivery enabler allocated by this plan; source references below.

| Tracking dimension | Disposition |
| --- | --- |
| Engineering | Partial |
| QA | Existing checks are evidence for current slices; full ticket criteria remain pending |
| Deployment | Current local snapshot; verify ticket-specific hosted rollout and configuration |
| Business acceptance | Pending client review; no signed acceptance recorded |
| Owner | AI Lead + Backend Lead (proposed role; named person unassigned) |
| Priority / phase | Delivery enabler / P1 |
| Estimate | TBD after scope/architecture agreement; no delivery date committed |
| Dependencies | [EVN-FND-101](../../00-foundations-governance/tickets/EVN-FND-101.md), [EVN-ONB-102](../../01-onboarding-tenancy-identity/tickets/EVN-ONB-102.md) |

## Business deliverable

Make approved business documents usable by the assistant.

The client accepts the demonstrated outcome and evidence, rather than the existence of a route, table or screen. This ticket does not certify the whole source requirement as complete.

## Current implemented slice

- [x] Approved structured FAQs are composed into prompts.

## Remaining delivery checklist

- [ ] Build PDF/DOCX/TXT/website ingestion, source review, chunk/embedding index, conflict/staleness detection and tenant-filtered retrieval.

## Technical component

- [ ] Implement the module boundary and contracts for: Ingestion, embedding, retrieval and approval services.
- [ ] Maintain tenant boundaries, explicit state transitions, access policy and failure handling for the delivered workflow.
- [ ] Resolve applicable architecture decisions before committing to a new provider or infrastructure baseline.

## DB

Existing module persistence: business_profiles, business_services, knowledge_items; scoped website aiMemory in workspace payload.

The following records/contracts are proposed or require extension; their names are planning terms, not assertions that production tables exist.

- [ ] knowledge_sources, chunks, indexes, approvals, gap records.
- [ ] Review scope keys, uniqueness, indexes, retention and migration compatibility; backfill safely and preserve existing tenant records.

## UI

- [ ] Upload/import review, source/version/diff and unresolved conflicts.
- [ ] Provide loading, empty, validation, permission-denied and recoverable failure states with keyboard and mobile access.
- [ ] Show observed facts and pending states accurately; do not present estimates, configured flags or mock results as confirmed business actions.

## Translate - business-to-technical mapping

| Business rule / outcome | Technical responsibility | Evidence needed |
| --- | --- | --- |
| Make approved business documents usable by the assistant. | Ingestion, embedding, retrieval and approval services | Tenant-scoped end-to-end demonstration of the outcome |
| Build PDF/DOCX/TXT/website ingestion, source review, chunk/embedding index, conflict/staleness detection and tenant-filtered retrieval. | knowledge_sources, chunks, indexes, approvals, gap records; Upload/import review, source/version/diff and unresolved conflicts | Migration/contracts, visible state and failure-path evidence |
| Safe, truthful AI behaviour where applicable | Relevant approved chunks only; low confidence creates a knowledge gap | Approved context, verified side-effect receipts and evaluation results or justified N/A |
| Client can approve delivery | QA report, rollout evidence and named acceptance owner | Evidence links and dated client sign-off |

This section means requirements-to-implementation mapping. It does not mean language translation; source language obligations are tracked in their own requirements.

## Backend services

- [ ] Ingestion, embedding, retrieval and approval services.
- [ ] Define request/response/event schemas, authorisation and input validation for each affected operation.
- [ ] For writes and provider effects, define idempotency, retry/timeout, receipts and reconciliation; document N/A where no side effects exist.
- [ ] Expose actionable status and scoped logs without secrets; distinguish completed, failed and uncertain outcomes.

## AI component

- [ ] Relevant approved chunks only.
- [ ] low confidence creates a knowledge gap.
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
| [BRL-015](../../../requirements/BRL.md#brl-015) | Plan allocation / source cross-reference | 8. Business rules |
| [KNW-003](../../../requirements/KNW.md#knw-003) | Source-linked | 13.2 Unstructured knowledge (RAG) |
| [KNW-004](../../../requirements/KNW.md#knw-004) | Source-linked | 13.2 Unstructured knowledge (RAG) |
| [KNW-006](../../../requirements/KNW.md#knw-006) | Source-linked | 13.2 Unstructured knowledge (RAG) |
| [KNW-008](../../../requirements/KNW.md#knw-008) | Source-linked | 13.2 Unstructured knowledge (RAG) |
| [KNW-009](../../../requirements/KNW.md#knw-009) | Source-linked | 13.2 Unstructured knowledge (RAG) |
| [ONB-007](../../../requirements/ONB.md#onb-007) | Plan allocation / source cross-reference | 12.2 Requirements |

Read every allocated record, including its continuation bullets and source variants. Source-linked rows preserve explicit document relationships; plan allocations are implementation responsibility assignments created during this review.

## Allocated specification checklist

The unchecked source obligations below require requirement-level evidence. They are deliberately separate from checked statements about current implemented slices. Read linked continuation bullets and additional source wording before accepting a record.

- [ ] [BRL-015](../../../requirements/BRL.md#brl-015): BRL-015 | One client's data is never used to answer another client's callers or to build another client's site. | Platform | TEN-001, TEN-004, KNW-004.
- [ ] [KNW-003](../../../requirements/KNW.md#knw-003): KNW-003 [P1] MUST ingest: pasted FAQs, uploaded PDFs/DOCX/TXT, the tenant's website pages, and structured "custom Q&A" pairs. Each source has status, last-ingested time, and owner approval state.
- [ ] [KNW-004](../../../requirements/KNW.md#knw-004): KNW-004 [P1] MUST chunk, embed and index knowledge per tenant with metadata (source, version, section, language). Retrieval MUST be tenant-filtered at the query layer, top-k limited, with a relevance threshold: below threshold the agent MUST treat the answer as unknown (KNW-007).
- [ ] [KNW-006](../../../requirements/KNW.md#knw-006): KNW-006 [P1] SHOULD detect stale or conflicting content (for example two different hours) and prompt the owner to resolve.
- [ ] [KNW-008](../../../requirements/KNW.md#knw-008): KNW-008 [P2] SHOULD support a hybrid retrieval strategy (vector plus keyword/BM25) with reranking, and per-tenant retrieval evaluation.
- [ ] [KNW-009](../../../requirements/KNW.md#knw-009): KNW-009 [P1] MUST provide explainability: for any AI message, the dashboard shows which profile fields and KB chunks were used, which tools were called, and which policy rules fired.
- [ ] [ONB-007](../../../requirements/ONB.md#onb-007): ONB-007 [P1] SHOULD auto-import from Google Business Profile (name, hours, categories, reviews summary, photos) and from the existing website (services, FAQs) via the public web with respect for robots.txt and terms; failures MUST degrade to manual entry.

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

Dependencies: [EVN-FND-101](../../00-foundations-governance/tickets/EVN-FND-101.md), [EVN-ONB-102](../../01-onboarding-tenancy-identity/tickets/EVN-ONB-102.md). A blocked prerequisite can be prototyped independently, but its contract and deployment must be approved before claiming this ticket delivered. Service limits, third-party approvals and staffing are evidence requirements, not assumptions that they are available.

## Handover and client acceptance

- [ ] Attach the business demonstration, technical evidence and operating/recovery instructions.
- [ ] Assign a named acceptance owner and agree any deferred criteria with the client in writing.
- [ ] Resolve launch-blocking defects and document accepted residual risks.
- [ ] Client records dated acceptance against the deployed/documented version.

Use [the acceptance protocol](../../../ACCEPTANCE.md) and [the ticket update rules](../../../TICKET_TEMPLATE.md) when changing status.
