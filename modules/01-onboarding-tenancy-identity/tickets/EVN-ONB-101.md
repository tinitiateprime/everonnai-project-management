# EVN-ONB-101 - Deliver account access that satisfies production identity requirements

Project: EverOnnAI. Module: [Onboarding, identity and tenant lifecycle](../README.md). Technical delivery enabler allocated by this plan; source references below.

| Tracking dimension | Disposition |
| --- | --- |
| Engineering | Partial |
| QA | Existing checks are evidence for current slices; full ticket criteria remain pending |
| Deployment | Current local snapshot; verify ticket-specific hosted rollout and configuration |
| Business acceptance | Pending client review; no signed acceptance recorded |
| Owner | Backend Lead + Frontend Lead (proposed role; named person unassigned) |
| Priority / phase | Delivery enabler / P1 |
| Estimate | TBD after scope/architecture agreement; no delivery date committed |
| Dependencies | [EVN-FND-101](../../00-foundations-governance/tickets/EVN-FND-101.md) |

## Business deliverable

Deliver account access that satisfies production identity requirements.

The client accepts the demonstrated outcome and evidence, rather than the existence of a route, table or screen. This ticket does not certify the whole source requirement as complete.

## Current implemented slice

- [x] Owner/customer signup, invitations, scrypt sessions, password change and lockouts work.

## Remaining delivery checklist

- [ ] Add recovery, email verification, MFA/passkeys, operator identity, step-up and SSO behind an approved identity ADR.

## Technical component

- [ ] Implement the module boundary and contracts for: IdentityProvider, secure session policy and least-privilege roles.
- [ ] Maintain tenant boundaries, explicit state transitions, access policy and failure handling for the delivered workflow.
- [ ] Resolve applicable architecture decisions before committing to a new provider or infrastructure baseline.

## DB

Existing module persistence: workspaces, business_profiles, users, auth_sessions, invitations, team_members, record_revisions.

The following records/contracts are proposed or require extension; their names are planning terms, not assertions that production tables exist.

- [ ] users, sessions, recovery_tokens, identity_bindings.
- [ ] Review scope keys, uniqueness, indexes, retention and migration compatibility; backfill safely and preserve existing tenant records.

## UI

- [ ] Signup/login/recovery/MFA and invite management.
- [ ] Provide loading, empty, validation, permission-denied and recoverable failure states with keyboard and mobile access.
- [ ] Show observed facts and pending states accurately; do not present estimates, configured flags or mock results as confirmed business actions.

## Translate - business-to-technical mapping

| Business rule / outcome | Technical responsibility | Evidence needed |
| --- | --- | --- |
| Deliver account access that satisfies production identity requirements. | IdentityProvider, secure session policy and least-privilege roles | Tenant-scoped end-to-end demonstration of the outcome |
| Add recovery, email verification, MFA/passkeys, operator identity, step-up and SSO behind an approved identity ADR. | users, sessions, recovery_tokens, identity_bindings; Signup/login/recovery/MFA and invite management | Migration/contracts, visible state and failure-path evidence |
| Safe, truthful AI behaviour where applicable | N/A; no AI in identity or access decisions | Approved context, verified side-effect receipts and evaluation results or justified N/A |
| Client can approve delivery | QA report, rollout evidence and named acceptance owner | Evidence links and dated client sign-off |

This section means requirements-to-implementation mapping. It does not mean language translation; source language obligations are tracked in their own requirements.

## Backend services

- [ ] IdentityProvider, secure session policy and least-privilege roles.
- [ ] Define request/response/event schemas, authorisation and input validation for each affected operation.
- [ ] For writes and provider effects, define idempotency, retry/timeout, receipts and reconciliation; document N/A where no side effects exist.
- [ ] Expose actionable status and scoped logs without secrets; distinguish completed, failed and uncertain outcomes.

## AI component

N/A; no AI in identity or access decisions. AI is outside this ticket's runtime scope.

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
| [ACC-001](../../../requirements/ACC.md#acc-001) | Source-linked | 10.3 Access requirements |
| [ACC-002](../../../requirements/ACC.md#acc-002) | Source-linked | 10.3 Access requirements |
| [ACC-003](../../../requirements/ACC.md#acc-003) | Source-linked | 10.3 Access requirements |
| [ACC-004](../../../requirements/ACC.md#acc-004) | Source-linked | 10.3 Access requirements |
| [ACC-006](../../../requirements/ACC.md#acc-006) | Source-linked | 10.3 Access requirements |
| [API-002](../../../requirements/API.md#api-002) | Plan allocation / source cross-reference | 19.4 Public API, webhooks and integrations (API) |
| [ONB-009](../../../requirements/ONB.md#onb-009) | Source-linked | 12.2 Requirements |
| [SCF-016](../../../requirements/SCF.md#scf-016) | Plan allocation / source cross-reference | 22.3 Scaffolding checklist |
| [SEC-003](../../../requirements/SEC.md#sec-003) | Source-linked | 22.2 Security requirements |

Read every allocated record, including its continuation bullets and source variants. Source-linked rows preserve explicit document relationships; plan allocations are implementation responsibility assignments created during this review.

## Allocated specification checklist

The unchecked source obligations below require requirement-level evidence. They are deliberately separate from checked statements about current implemented slices. Read linked continuation bullets and additional source wording before accepting a record.

- [ ] [ACC-001](../../../requirements/ACC.md#acc-001): ACC-001 [P1] MUST enforce authorization in a single policy layer (not scattered in handlers). Every request carries a resolved tenant_id and actor; operator requests additionally carry the operator's client grant (DSK-002).
- [ ] [ACC-002](../../../requirements/ACC.md#acc-002): ACC-002 [P1] MUST log every cross-client access by internal staff and operators to an append-only audit log with reason code. Support impersonation MUST show a banner to the client user and be revocable.
- [ ] [ACC-003](../../../requirements/ACC.md#acc-003): ACC-003 [P1] MUST support multi-factor authentication for all internal roles and operators and offer it to clients (mandatory for tenant_owner on paid plans at P2).
- [ ] [ACC-004](../../../requirements/ACC.md#acc-004): ACC-004 [P2] SHOULD support single sign-on (OIDC or SAML) for internal roles; scaffold client single sign-on for P3.
- [ ] [ACC-006](../../../requirements/ACC.md#acc-006): ACC-006 [P1] MUST support brand-scoped and vertical-scoped roles (brand_admin, vertical_manager, acquisition_manager, migration_specialist) with least privilege; acquisition and migration roles MUST NOT be able to read clients' conversations, recordings or transcripts.
- [ ] [API-002](../../../requirements/API.md#api-002): API-002 [P1] MUST support authentication: OAuth2/OIDC for users; API keys (scoped, hashed at rest, rotatable) and short-lived JWTs for tenant integrations; widget keys scoped to allowed origins.
- [ ] [ONB-009](../../../requirements/ONB.md#onb-009): ONB-009 [P1] MUST support team invitations with roles from §10.2 and per-user notification preferences.
- [ ] [SCF-016](../../../requirements/SCF.md#scf-016): 16 | Role/permission model with attribute hooks (location, tenant tier, time-boxed grants) | Custom roles, delegated admin, tenant SSO, ABAC.
- [ ] [SEC-003](../../../requirements/SEC.md#sec-003): SEC-003 [P1] MUST implement strong identity: passkeys/TOTP MFA, secure session handling (rotating refresh tokens, idle and absolute timeouts, device binding for operators), brute-force and credential-stuffing protection, breached-password checks, and step-up authentication for sensitive actions (billing changes, data export, number release, API key creation).

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

Dependencies: [EVN-FND-101](../../00-foundations-governance/tickets/EVN-FND-101.md). A blocked prerequisite can be prototyped independently, but its contract and deployment must be approved before claiming this ticket delivered. Service limits, third-party approvals and staffing are evidence requirements, not assumptions that they are available.

## Handover and client acceptance

- [ ] Attach the business demonstration, technical evidence and operating/recovery instructions.
- [ ] Assign a named acceptance owner and agree any deferred criteria with the client in writing.
- [ ] Resolve launch-blocking defects and document accepted residual risks.
- [ ] Client records dated acceptance against the deployed/documented version.

Use [the acceptance protocol](../../../ACCEPTANCE.md) and [the ticket update rules](../../../TICKET_TEMPLATE.md) when changing status.
