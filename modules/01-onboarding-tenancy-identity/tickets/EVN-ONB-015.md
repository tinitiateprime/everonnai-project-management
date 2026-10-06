# EVN-ONB-015 - Verify ownership before anything is public

Project: EverOnnAI. Module: [Onboarding, identity and tenant lifecycle](../README.md). Source business requirement [BR-015](../../../requirements/BR.md#br-015).

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

Verify ownership before anything is public. Clients can preview for free; nothing goes public or uses a real phone number until ownership is verified.

The client accepts the demonstrated outcome and evidence, rather than the existence of a route, table or screen. This ticket does not certify the whole source requirement as complete.

## Current implemented slice

- [x] Server publishing transitions and role/tenant guards exist.

## Remaining delivery checklist

- [ ] Replace a status/verified flag with independent ownership proof, OTP/GBP/manual review, audit and contact masking.

## Technical component

- [ ] Implement the module boundary and contracts for: Verification service and publish/number activation gate.
- [ ] Maintain tenant boundaries, explicit state transitions, access policy and failure handling for the delivered workflow.
- [ ] Resolve applicable architecture decisions before committing to a new provider or infrastructure baseline.

## DB

Existing module persistence: workspaces, business_profiles, users, auth_sessions, invitations, team_members, record_revisions.

The following records/contracts are proposed or require extension; their names are planning terms, not assertions that production tables exist.

- [ ] ownership_proofs, claims, approval_events.
- [ ] Review scope keys, uniqueness, indexes, retention and migration compatibility; backfill safely and preserve existing tenant records.

## UI

- [ ] Verification and publication-block reason.
- [ ] Provide loading, empty, validation, permission-denied and recoverable failure states with keyboard and mobile access.
- [ ] Show observed facts and pending states accurately; do not present estimates, configured flags or mock results as confirmed business actions.

## Translate - business-to-technical mapping

| Business rule / outcome | Technical responsibility | Evidence needed |
| --- | --- | --- |
| Verify ownership before anything is public. Clients can preview for free; nothing goes public or uses a real phone number until ownership is verified. | Verification service and publish/number activation gate | Tenant-scoped end-to-end demonstration of the outcome |
| Replace a status/verified flag with independent ownership proof, OTP/GBP/manual review, audit and contact masking. | ownership_proofs, claims, approval_events; Verification and publication-block reason | Migration/contracts, visible state and failure-path evidence |
| Safe, truthful AI behaviour where applicable | AI cannot bypass proof or self-approve ownership | Approved context, verified side-effect receipts and evaluation results or justified N/A |
| Client can approve delivery | QA report, rollout evidence and named acceptance owner | Evidence links and dated client sign-off |

This section means requirements-to-implementation mapping. It does not mean language translation; source language obligations are tracked in their own requirements.

## Backend services

- [ ] Verification service and publish/number activation gate.
- [ ] Define request/response/event schemas, authorisation and input validation for each affected operation.
- [ ] For writes and provider effects, define idempotency, retry/timeout, receipts and reconciliation; document N/A where no side effects exist.
- [ ] Expose actionable status and scoped logs without secrets; distinguish completed, failed and uncertain outcomes.

## AI component

- [ ] AI cannot bypass proof or self-approve ownership.
- [ ] Record instruction/knowledge/tool versions, measured quality, tenant scope, cost and safe fallback; a Markdown standard alone is not a passed evaluation.

## Testing / QA

- [ ] Exercise the intended user journey with real tenant-scoped state; cover forbidden role and cross-tenant requests.
- [ ] Test malformed inputs, provider failure, retries/replays and cancellation as applicable; keep deterministic mocks separate from live-provider evidence.
- [ ] Review desktop/mobile accessibility, factual copy and failure recovery in the delivered UI.
- [ ] Attach test environment, code/config/instruction versions, results and remaining defects to the acceptance report.

| Source test | Scenario | Required pass criteria | Current disposition |
| --- | --- | --- | --- |
| [AT-01](../../../requirements/AT.md#at-01) | Owner claims a business from a Google listing | Private preview and draft profile in under 2 minutes; page is not indexable; no real phone number shown; unverified claims are highlighted for the owner | Full source scenario not evidenced; client acceptance pending |

Source stories: [US-001](../../../requirements/US.md#us-001), [US-002](../../../requirements/US.md#us-002).

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
| [BO-2](../../../requirements/BO.md#bo-2) | Source-linked | 3.1 Business objectives |
| [BO-7](../../../requirements/BO.md#bo-7) | Source-linked | 3.1 Business objectives |
| [BR-015](../../../requirements/BR.md#br-015) | Source-linked | 7.3 Websites |
| [BRL-006](../../../requirements/BRL.md#brl-006) | Plan allocation / source cross-reference | 8. Business rules |
| [ONB-002](../../../requirements/ONB.md#onb-002) | Source-linked | 12.2 Requirements |
| [ONB-007](../../../requirements/ONB.md#onb-007) | Plan allocation / source cross-reference | 12.2 Requirements |
| [ONB-010](../../../requirements/ONB.md#onb-010) | Plan allocation / source cross-reference | 12.2 Requirements |
| [US-001](../../../requirements/US.md#us-001) | Source-linked | EP-01 Onboarding and claim |
| [US-002](../../../requirements/US.md#us-002) | Source-linked | EP-01 Onboarding and claim |
| [WEB-003](../../../requirements/WEB.md#web-003) | Source-linked | 18.3 Requirements |

Read every allocated record, including its continuation bullets and source variants. Source-linked rows preserve explicit document relationships; plan allocations are implementation responsibility assignments created during this review.

## Allocated specification checklist

The unchecked source obligations below require requirement-level evidence. They are deliberately separate from checked statements about current implemented slices. Read linked continuation bullets and additional source wording before accepting a record.

- [ ] [BRL-006](../../../requirements/BRL.md#brl-006): BRL-006 | A preview site stays private, and shows no real phone number, until ownership is verified and the owner approves. | Website engine | ONB-002, WEB-003.
- [ ] [ONB-002](../../../requirements/ONB.md#onb-002): ONB-002 [P1] MUST prevent impersonation: a preview MUST NOT go public, receive real calls, or display the business's real phone number until ownership is verified (phone OTP to the number on the listing, or Google Business Profile ownership, or a document/manual review path handled by support). Verification method and result are stored.
- [ ] [ONB-007](../../../requirements/ONB.md#onb-007): ONB-007 [P1] SHOULD auto-import from Google Business Profile (name, hours, categories, reviews summary, photos) and from the existing website (services, FAQs) via the public web with respect for robots.txt and terms; failures MUST degrade to manual entry.
- [ ] [ONB-010](../../../requirements/ONB.md#onb-010): ONB-010 [P1] MUST be resumable and idempotent: repeated claim submissions for the same business MUST NOT create duplicate tenants (dedupe on normalized phone, domain and Place ID).
- [ ] [WEB-003](../../../requirements/WEB.md#web-003): WEB-003 [P1] MUST keep previews private and non-indexable (noindex, unguessable URLs, no real phone or address exposure per ONB-002) until verification and owner approval; preview TTL and cleanup jobs apply to unclaimed prospects.

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
