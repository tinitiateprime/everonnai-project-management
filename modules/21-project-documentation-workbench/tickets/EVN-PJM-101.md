# EVN-PJM-101 - Share a customer's own GitHub project documentation safely

Project: EverOnnAI. Module: [Customer repositories and client project delivery documentation](../README.md). Session-added scope; see [extension record](../../../SCOPE_EXTENSIONS.md).

| Tracking dimension | Disposition |
| --- | --- |
| Engineering | Implemented (bounded slice) |
| QA | Existing checks are evidence for current slices; full ticket criteria remain pending |
| Deployment | Current local snapshot; verify ticket-specific hosted rollout and configuration |
| Business acceptance | Pending client review; no signed acceptance recorded |
| Owner | Product Owner + Backend/Frontend Leads (proposed role; named person unassigned) |
| Priority / phase | Session-added scope / Extension |
| Estimate | TBD after scope/architecture agreement; no delivery date committed |
| Dependencies | None; independent entry point |

## Business deliverable

Share a customer's own GitHub project documentation safely.

The client accepts the demonstrated outcome and evidence, rather than the existence of a route, table or screen. This ticket does not certify the whole source requirement as complete.

## Current implemented slice

- [x] Tenant-scoped public/private GitHub connections, read-only Markdown/Mermaid/images, search/sync, role checks and encrypted tokens are implemented.

## Remaining delivery checklist

- [ ] Deploy the current application snapshot and verify one authorised private repository; do not treat viewed SKILL.md as runtime instructions.

## Technical component

- [ ] Implement the module boundary and contracts for: Fixed-host GitHub tree/blob adapter, bounded catalog and conditional persistence.
- [ ] Maintain tenant boundaries, explicit state transitions, access policy and failure handling for the delivered workflow.
- [ ] Resolve applicable architecture decisions before committing to a new provider or infrastructure baseline.

## DB

Existing module persistence: everonn.project_repositories; additive migration applied to configured PostgreSQL on 2026-10-06.

The following records/contracts are proposed or require extension; their names are planning terms, not assertions that production tables exist.

- [ ] everonn.project_repositories.
- [ ] per-workspace CAS Blobs/local alternative.
- [ ] Version the relevant evidence/registers and keep customer secrets out of the documentation repository.

## UI

- [ ] Repository selection, source/diagram views, tasks and mobile/light/dark viewer.
- [ ] Provide loading, empty, validation, permission-denied and recoverable failure states with keyboard and mobile access.
- [ ] Show observed facts and pending states accurately; do not present estimates, configured flags or mock results as confirmed business actions.

## Translate - business-to-technical mapping

| Business rule / outcome | Technical responsibility | Evidence needed |
| --- | --- | --- |
| Share a customer's own GitHub project documentation safely. | Fixed-host GitHub tree/blob adapter, bounded catalog and conditional persistence | Tenant-scoped end-to-end demonstration of the outcome |
| Deploy the current application snapshot and verify one authorised private repository; do not treat viewed SKILL.md as runtime instructions. | everonn.project_repositories; per-workspace CAS Blobs/local alternative; Repository selection, source/diagram views, tasks and mobile/light/dark viewer | Migration/contracts, visible state and failure-path evidence |
| Safe, truthful AI behaviour where applicable | N/A; viewed repository Markdown does not execute AI tools or replace platform skills | Approved context, verified side-effect receipts and evaluation results or justified N/A |
| Client can approve delivery | QA report, rollout evidence and named acceptance owner | Evidence links and dated client sign-off |

This section means requirements-to-implementation mapping. It does not mean language translation; source language obligations are tracked in their own requirements.

## Backend services

- [ ] Fixed-host GitHub tree/blob adapter, bounded catalog and conditional persistence.
- [ ] Define request/response/event schemas, authorisation and input validation for each affected operation.
- [ ] For writes and provider effects, define idempotency, retry/timeout, receipts and reconciliation; document N/A where no side effects exist.
- [ ] Expose actionable status and scoped logs without secrets; distinguish completed, failed and uncertain outcomes.

## AI component

N/A; viewed repository Markdown does not execute AI tools or replace platform skills. AI is outside this ticket's runtime scope.

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

Session-added customer requirement; no formal ID is claimed from either original document.

Read every allocated record, including its continuation bullets and source variants. Source-linked rows preserve explicit document relationships; plan allocations are implementation responsibility assignments created during this review.

## Allocated specification checklist

The unchecked source obligations below require requirement-level evidence. They are deliberately separate from checked statements about current implemented slices. Read linked continuation bullets and additional source wording before accepting a record.

This ticket allocates scope/governance or session extension requirements. Its review/acceptance evidence is the required completion checklist above; no technical source obligation is claimed complete.

## Existing code / check evidence

- `app/workspace/page.tsx` - inspected current application working tree; see [snapshot evidence](../../../EVIDENCE.md).
- `app/api/project-workspace/route.ts` - inspected current application working tree; see [snapshot evidence](../../../EVIDENCE.md).
- `features/project-workspace/github.ts` - inspected current application working tree; see [snapshot evidence](../../../EVIDENCE.md).
- `features/project-workspace/repositories.ts` - inspected current application working tree; see [snapshot evidence](../../../EVIDENCE.md).
- `lib/project-repository-store.ts` - inspected current application working tree; see [snapshot evidence](../../../EVIDENCE.md).
- `components/project-workspace/project-workspace.tsx` - inspected current application working tree; see [snapshot evidence](../../../EVIDENCE.md).
- Relevant automated checks: `tests/project-workspace.test.ts`, `scripts/smoke-project-workspace.ts`. Their scope is bounded by [current validation](../../../CURRENT_STATE.md).

## Blockers and boundaries

Module risk: Customer GitHub Markdown is read-only documentation; it does not execute platform skills. Hosted UI deployment and real private-repository access still require verification.

Dependencies: None; independent entry point. A blocked prerequisite can be prototyped independently, but its contract and deployment must be approved before claiming this ticket delivered. Service limits, third-party approvals and staffing are evidence requirements, not assumptions that they are available.

## Handover and client acceptance

- [ ] Attach the business demonstration, technical evidence and operating/recovery instructions.
- [ ] Assign a named acceptance owner and agree any deferred criteria with the client in writing.
- [ ] Resolve launch-blocking defects and document accepted residual risks.
- [ ] Client records dated acceptance against the deployed/documented version.

Use [the acceptance protocol](../../../ACCEPTANCE.md) and [the ticket update rules](../../../TICKET_TEMPLATE.md) when changing status.
