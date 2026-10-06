# EVN-ONB-022 - Test before going live

Project: EverOnnAI. Module: [Onboarding, identity and tenant lifecycle](../README.md). Source business requirement [BR-022](../../../requirements/BR.md#br-022).

| Tracking dimension | Disposition |
| --- | --- |
| Engineering | Partial |
| QA | Existing checks are evidence for current slices; full ticket criteria remain pending |
| Deployment | Current local snapshot; verify ticket-specific hosted rollout and configuration |
| Business acceptance | Pending client review; no signed acceptance recorded |
| Owner | Backend Lead + Frontend Lead (proposed role; named person unassigned) |
| Priority / phase | Must / P1 |
| Estimate | TBD after scope/architecture agreement; no delivery date committed |
| Dependencies | [EVN-ONB-101](EVN-ONB-101.md), [EVN-ONB-102](EVN-ONB-102.md) |

## Business deliverable

Test before going live. Clients test the AI by phone and chat before it goes live.

The client accepts the demonstrated outcome and evidence, rather than the existence of a route, table or screen. This ticket does not certify the whole source requirement as complete.

## Current implemented slice

- [x] Dashboard text and browser voice tests exist.

## Remaining delivery checklist

- [ ] Add sandbox telephone numbers, draft isolation, no customer notifications/billing and explanation traces.

## Technical component

- [ ] Implement the module boundary and contracts for: Sandbox routing and side-effect suppression.
- [ ] Maintain tenant boundaries, explicit state transitions, access policy and failure handling for the delivered workflow.
- [ ] Resolve applicable architecture decisions before committing to a new provider or infrastructure baseline.

## DB

Existing module persistence: workspaces, business_profiles, users, auth_sessions, invitations, team_members, record_revisions.

The following records/contracts are proposed or require extension; their names are planning terms, not assertions that production tables exist.

- [ ] sandbox_sessions, test_calls, draft_versions.
- [ ] Review scope keys, uniqueness, indexes, retention and migration compatibility; backfill safely and preserve existing tenant records.

## UI

- [ ] Phone/chat test workspace, transcript and provenance.
- [ ] Provide loading, empty, validation, permission-denied and recoverable failure states with keyboard and mobile access.
- [ ] Show observed facts and pending states accurately; do not present estimates, configured flags or mock results as confirmed business actions.

## Translate - business-to-technical mapping

| Business rule / outcome | Technical responsibility | Evidence needed |
| --- | --- | --- |
| Test before going live. Clients test the AI by phone and chat before it goes live. | Sandbox routing and side-effect suppression | Tenant-scoped end-to-end demonstration of the outcome |
| Add sandbox telephone numbers, draft isolation, no customer notifications/billing and explanation traces. | sandbox_sessions, test_calls, draft_versions; Phone/chat test workspace, transcript and provenance | Migration/contracts, visible state and failure-path evidence |
| Safe, truthful AI behaviour where applicable | Run the same agent against an explicit draft version | Approved context, verified side-effect receipts and evaluation results or justified N/A |
| Client can approve delivery | QA report, rollout evidence and named acceptance owner | Evidence links and dated client sign-off |

This section means requirements-to-implementation mapping. It does not mean language translation; source language obligations are tracked in their own requirements.

## Backend services

- [ ] Sandbox routing and side-effect suppression.
- [ ] Define request/response/event schemas, authorisation and input validation for each affected operation.
- [ ] For writes and provider effects, define idempotency, retry/timeout, receipts and reconciliation; document N/A where no side effects exist.
- [ ] Expose actionable status and scoped logs without secrets; distinguish completed, failed and uncertain outcomes.

## AI component

- [ ] Run the same agent against an explicit draft version.
- [ ] Record instruction/knowledge/tool versions, measured quality, tenant scope, cost and safe fallback; a Markdown standard alone is not a passed evaluation.

## Testing / QA

- [ ] Exercise the intended user journey with real tenant-scoped state; cover forbidden role and cross-tenant requests.
- [ ] Test malformed inputs, provider failure, retries/replays and cancellation as applicable; keep deterministic mocks separate from live-provider evidence.
- [ ] Review desktop/mobile accessibility, factual copy and failure recovery in the delivered UI.
- [ ] Attach test environment, code/config/instruction versions, results and remaining defects to the acceptance report.

| Source test | Scenario | Required pass criteria | Current disposition |
| --- | --- | --- | --- |
| [AT-02](../../../requirements/AT.md#at-02) | Owner verifies, approves knowledge, connects forwarding, tests and goes live | Forwarding verified by an automated test call before the channel is live; approval recorded with the version id; test call and chat run against the draft without billing | Full source scenario not evidenced; client acceptance pending |

Source stories: [US-004](../../../requirements/US.md#us-004), [US-006](../../../requirements/US.md#us-006).

## Deployment

- [ ] Confirm approved hosting/database/provider architecture and required credentials in the deployment environment.
- [ ] Apply compatible migrations/configuration in staging, rehearse rollback, then promote the reviewed artifact.
- [ ] Verify the actual hosted workflow, monitoring, fallback and customer-visible errors after release.
- [ ] Update CODE_PROFILE.md, PROJECT_DATA_FLOW.md and CLIENT_TECHNICAL_QA.md in the application when behaviour or architecture changes.
- [ ] Record deployment identity, operator, timestamp and rollback evidence; document-only tickets instead record the reviewed Git commit.

## Source traceability

| Source ID | Mapping basis | Source section |
| --- | --- | --- |
| [AT-02](../../../requirements/AT.md#at-02) | Source-linked | 25.2 Acceptance tests |
| [BO-2](../../../requirements/BO.md#bo-2) | Source-linked | 3.1 Business objectives |
| [BR-022](../../../requirements/BR.md#br-022) | Source-linked | 7.4 Knowledge and client control |
| [ONB-004](../../../requirements/ONB.md#onb-004) | Source-linked | 12.2 Requirements |
| [US-004](../../../requirements/US.md#us-004) | Source-linked | EP-01 Onboarding and claim |
| [US-006](../../../requirements/US.md#us-006) | Source-linked | EP-02 Knowledge and agent control |

Read every allocated record, including its continuation bullets and source variants. Source-linked rows preserve explicit document relationships; plan allocations are implementation responsibility assignments created during this review.

## Allocated specification checklist

The unchecked source obligations below require requirement-level evidence. They are deliberately separate from checked statements about current implemented slices. Read linked continuation bullets and additional source wording before accepting a record.

- [ ] [ONB-004](../../../requirements/ONB.md#onb-004): ONB-004 [P1] MUST provide a test mode: a sandbox number and chat widget that run the real agent against the draft configuration without billing or notifying customers, with full transcript and "why did it say that" explanations (KNW-009).

## Existing code / check evidence

- `features/auth/rbac.ts` - inspected current application working tree; see [snapshot evidence](../../../EVIDENCE.md).
- `features/auth/session.ts` - inspected current application working tree; see [snapshot evidence](../../../EVIDENCE.md).
- `features/auth/password.ts` - inspected current application working tree; see [snapshot evidence](../../../EVIDENCE.md).
- `lib/auth-store.ts` - inspected current application working tree; see [snapshot evidence](../../../EVIDENCE.md).
- `lib/json-workspace-store.ts` - inspected current application working tree; see [snapshot evidence](../../../EVIDENCE.md).
- `features/everonn/starter-workspace.ts` - inspected current application working tree; see [snapshot evidence](../../../EVIDENCE.md).
- `app/api/auth/register/route.ts` - inspected current application working tree; see [snapshot evidence](../../../EVIDENCE.md).
- Relevant automated checks: `tests/auth.test.ts`, `tests/workspace-security.test.ts`, `tests/app-records.test.ts`, `tests/everonn-relational.test.ts`, `scripts/smoke-auth-database.ts`. Their scope is bounded by [current validation](../../../CURRENT_STATE.md).

## Blockers and boundaries

Module risk: A boolean verified state does not establish independent business ownership; MFA/recovery and operator/brand identities remain incomplete.

Dependencies: [EVN-ONB-101](EVN-ONB-101.md), [EVN-ONB-102](EVN-ONB-102.md). A blocked prerequisite can be prototyped independently, but its contract and deployment must be approved before claiming this ticket delivered. Service limits, third-party approvals and staffing are evidence requirements, not assumptions that they are available.

## Handover and client acceptance

- [ ] Attach the business demonstration, technical evidence and operating/recovery instructions.
- [ ] Assign a named acceptance owner and agree any deferred criteria with the client in writing.
- [ ] Resolve launch-blocking defects and document accepted residual risks.
- [ ] Client records dated acceptance against the deployed/documented version.

Use [the acceptance protocol](../../../ACCEPTANCE.md) and [the ticket update rules](../../../TICKET_TEMPLATE.md) when changing status.
