# EVN-INT-071 - API and integrations

Project: EverOnnAI. Module: [Public API, webhooks and vertical connectors](../README.md). Source business requirement [BR-071](../../../requirements/BR.md#br-071).

| Tracking dimension | Disposition |
| --- | --- |
| Engineering | Partial |
| QA | Existing checks are evidence for current slices; full ticket criteria remain pending |
| Deployment | Current local snapshot; verify ticket-specific hosted rollout and configuration |
| Business acceptance | Pending client review; no signed acceptance recorded |
| Owner | Integration Lead + Backend Lead (proposed role; named person unassigned) |
| Priority / phase | Should / P1 |
| Estimate | TBD after scope/architecture agreement; no delivery date committed |
| Dependencies | [EVN-ONB-102](../../01-onboarding-tenancy-identity/tickets/EVN-ONB-102.md), [EVN-SEC-101](../../15-security-privacy-compliance/tickets/EVN-SEC-101.md), [EVN-OPS-101](../../18-reliability-deployment-scale/tickets/EVN-OPS-101.md) |

## Business deliverable

API and integrations. Clients and partners can integrate through an API, webhooks and Zapier-style connectors.

The client accepts the demonstrated outcome and evidence, rather than the existence of a route, table or screen. This ticket does not certify the whole source requirement as complete.

## Current implemented slice

- [x] Internal scoped APIs, Google integrations and signed usage ingress exist.

## Remaining delivery checklist

- [ ] Publish /v1 OpenAPI, keys/OAuth, partner webhooks/replay and Zapier/Make adapters.

## Technical component

- [ ] Implement the module boundary and contracts for: Gateway, idempotency, signed outbox and SDKs.
- [ ] Maintain tenant boundaries, explicit state transitions, access policy and failure handling for the delivered workflow.
- [ ] Resolve applicable architecture decisions before committing to a new provider or infrastructure baseline.

## DB

Existing module persistence: Encrypted Google connections, GitHub repository credentials and specialised metering ingress records.

The following records/contracts are proposed or require extension; their names are planning terms, not assertions that production tables exist.

- [ ] api_clients, api_keys, webhook_endpoints, deliveries.
- [ ] Review scope keys, uniqueness, indexes, retention and migration compatibility; backfill safely and preserve existing tenant records.

## UI

- [ ] API keys, webhook status and replay.
- [ ] Provide loading, empty, validation, permission-denied and recoverable failure states with keyboard and mobile access.
- [ ] Show observed facts and pending states accurately; do not present estimates, configured flags or mock results as confirmed business actions.

## Translate - business-to-technical mapping

| Business rule / outcome | Technical responsibility | Evidence needed |
| --- | --- | --- |
| API and integrations. Clients and partners can integrate through an API, webhooks and Zapier-style connectors. | Gateway, idempotency, signed outbox and SDKs | Tenant-scoped end-to-end demonstration of the outcome |
| Publish /v1 OpenAPI, keys/OAuth, partner webhooks/replay and Zapier/Make adapters. | api_clients, api_keys, webhook_endpoints, deliveries; API keys, webhook status and replay | Migration/contracts, visible state and failure-path evidence |
| Safe, truthful AI behaviour where applicable | Approved typed/scoped tools only | Approved context, verified side-effect receipts and evaluation results or justified N/A |
| Client can approve delivery | QA report, rollout evidence and named acceptance owner | Evidence links and dated client sign-off |

This section means requirements-to-implementation mapping. It does not mean language translation; source language obligations are tracked in their own requirements.

## Backend services

- [ ] Gateway, idempotency, signed outbox and SDKs.
- [ ] Define request/response/event schemas, authorisation and input validation for each affected operation.
- [ ] For writes and provider effects, define idempotency, retry/timeout, receipts and reconciliation; document N/A where no side effects exist.
- [ ] Expose actionable status and scoped logs without secrets; distinguish completed, failed and uncertain outcomes.

## AI component

- [ ] Approved typed/scoped tools only.
- [ ] Record instruction/knowledge/tool versions, measured quality, tenant scope, cost and safe fallback; a Markdown standard alone is not a passed evaluation.

## Testing / QA

- [ ] Exercise the intended user journey with real tenant-scoped state; cover forbidden role and cross-tenant requests.
- [ ] Test malformed inputs, provider failure, retries/replays and cancellation as applicable; keep deterministic mocks separate from live-provider evidence.
- [ ] Review desktop/mobile accessibility, factual copy and failure recovery in the delivered UI.
- [ ] Attach test environment, code/config/instruction versions, results and remaining defects to the acceptance report.

| Source test | Scenario | Required pass criteria | Current disposition |
| --- | --- | --- | --- |
| [AT-59](../../../requirements/AT.md#at-59) | API and webhooks | OpenAPI contract tests pass; webhook signatures, retries and replay verified; a Zapier-style trigger works | Full source scenario not evidenced; client acceptance pending |

Source stories: [US-051](../../../requirements/US.md#us-051).

## Deployment

- [ ] Confirm approved hosting/database/provider architecture and required credentials in the deployment environment.
- [ ] Apply compatible migrations/configuration in staging, rehearse rollback, then promote the reviewed artifact.
- [ ] Verify the actual hosted workflow, monitoring, fallback and customer-visible errors after release.
- [ ] Update CODE_PROFILE.md, PROJECT_DATA_FLOW.md and CLIENT_TECHNICAL_QA.md in the application when behaviour or architecture changes.
- [ ] Record deployment identity, operator, timestamp and rollback evidence; document-only tickets instead record the reviewed Git commit.

## Source traceability

| Source ID | Mapping basis | Source section |
| --- | --- | --- |
| [ACC-005](../../../requirements/ACC.md#acc-005) | Plan allocation / source cross-reference | 10.3 Access requirements |
| [API-001](../../../requirements/API.md#api-001) | Source-linked | 19.4 Public API, webhooks and integrations (API) |
| [API-002](../../../requirements/API.md#api-002) | Plan allocation / source cross-reference | 19.4 Public API, webhooks and integrations (API) |
| [API-003](../../../requirements/API.md#api-003) | Source-linked | 19.4 Public API, webhooks and integrations (API) |
| [API-004](../../../requirements/API.md#api-004) | Source-linked | 19.4 Public API, webhooks and integrations (API) |
| [API-007](../../../requirements/API.md#api-007) | Plan allocation / source cross-reference | 19.4 Public API, webhooks and integrations (API) |
| [API-008](../../../requirements/API.md#api-008) | Plan allocation / source cross-reference | 19.4 Public API, webhooks and integrations (API) |
| [AT-59](../../../requirements/AT.md#at-59) | Source-linked | 25.2 Acceptance tests |
| [BO-8](../../../requirements/BO.md#bo-8) | Source-linked | 3.1 Business objectives |
| [BR-071](../../../requirements/BR.md#br-071) | Source-linked | 7.11 Platform, security, compliance and reliability |
| [BRL-024](../../../requirements/BRL.md#brl-024) | Plan allocation / source cross-reference | 8. Business rules |
| [BRL-025](../../../requirements/BRL.md#brl-025) | Plan allocation / source cross-reference | 8. Business rules |
| [SCF-013](../../../requirements/SCF.md#scf-013) | Plan allocation / source cross-reference | 22.3 Scaffolding checklist |
| [US-051](../../../requirements/US.md#us-051) | Source-linked | EP-11 Integrations, scale and ownership |

Read every allocated record, including its continuation bullets and source variants. Source-linked rows preserve explicit document relationships; plan allocations are implementation responsibility assignments created during this review.

## Allocated specification checklist

The unchecked source obligations below require requirement-level evidence. They are deliberately separate from checked statements about current implemented slices. Read linked continuation bullets and additional source wording before accepting a record.

- [ ] [ACC-005](../../../requirements/ACC.md#acc-005): ACC-005 [P1] MUST issue scoped, revocable API keys per client with rotation and last-used tracking.
- [ ] [API-001](../../../requirements/API.md#api-001): API-001 [P1] MUST expose a versioned REST API (/v1) described by OpenAPI 3.1, used by EverOnn's own frontends (no private back doors), with resource-oriented design, cursor pagination, idempotency keys on POST, consistent error format (RFC 9457 Problem Details), rate limit headers, and SDK generation (TypeScript first).
- [ ] [API-002](../../../requirements/API.md#api-002): API-002 [P1] MUST support authentication: OAuth2/OIDC for users; API keys (scoped, hashed at rest, rotatable) and short-lived JWTs for tenant integrations; widget keys scoped to allowed origins.
- [ ] [API-003](../../../requirements/API.md#api-003): API-003 [P1] MUST deliver outbound webhooks for domain events (for example request.created, call.completed, appointment.booked) with HMAC signatures, retries with exponential backoff, dead-letter queues, replay from the dashboard, and per-tenant delivery logs.
- [ ] [API-004](../../../requirements/API.md#api-004): API-004 [P1] SHOULD provide native Zapier and Make connectors (or generic webhook triggers plus REST actions) at P1; P2 for listed apps.
- [ ] [API-007](../../../requirements/API.md#api-007): API-007 [P1] MUST publish an API changelog and deprecation policy (minimum 6 months notice for breaking changes).
- [ ] [API-008](../../../requirements/API.md#api-008): API-008 [P3] MAY provide a partner/marketplace program (OAuth apps, scopes, review process).
- [ ] [BRL-024](../../../requirements/BRL.md#brl-024): BRL-024 | EverOnn's public statements about customers, results and capabilities are supported by evidence; illustrative examples are labeled as illustrative, and named results are published only with the customer's approval. | Marketing | BIL-001, API-001.
- [ ] [BRL-025](../../../requirements/BRL.md#brl-025): BRL-025 | Public descriptions of what a plan includes come from the same entitlement data the platform enforces, so a published plan never promises what the platform does not deliver. | Pricing and marketing | BIL-001, API-001, ADM-002.
- [ ] [SCF-013](../../../requirements/SCF.md#scf-013): 13 | API versioning, scopes, OAuth-ready client model | Partner apps, marketplace, agency access.

## Existing code / check evidence

- `features/integrations/google.ts` - inspected current application working tree; see [snapshot evidence](../../../EVIDENCE.md).
- `features/integrations/google-oauth.ts` - inspected current application working tree; see [snapshot evidence](../../../EVIDENCE.md).
- `lib/provider-credentials.ts` - inspected current application working tree; see [snapshot evidence](../../../EVIDENCE.md).
- `app/api/integrations/google/route.ts` - inspected current application working tree; see [snapshot evidence](../../../EVIDENCE.md).
- `app/api/usage/elevenlabs/webhook/route.ts` - inspected current application working tree; see [snapshot evidence](../../../EVIDENCE.md).
- `features/project-workspace/github.ts` - inspected current application working tree; see [snapshot evidence](../../../EVIDENCE.md).
- Relevant automated checks: `tests/provider-credentials.test.ts`, `tests/usage-reliability.test.ts`, `tests/project-workspace.test.ts`. Their scope is bounded by [current validation](../../../CURRENT_STATE.md).

## Blockers and boundaries

Module risk: Internal app endpoints and provider ingress do not establish a public /v1 API, tenant API keys, partner webhooks or a connector SDK.

Dependencies: [EVN-ONB-102](../../01-onboarding-tenancy-identity/tickets/EVN-ONB-102.md), [EVN-SEC-101](../../15-security-privacy-compliance/tickets/EVN-SEC-101.md), [EVN-OPS-101](../../18-reliability-deployment-scale/tickets/EVN-OPS-101.md). A blocked prerequisite can be prototyped independently, but its contract and deployment must be approved before claiming this ticket delivered. Service limits, third-party approvals and staffing are evidence requirements, not assumptions that they are available.

## Handover and client acceptance

- [ ] Attach the business demonstration, technical evidence and operating/recovery instructions.
- [ ] Assign a named acceptance owner and agree any deferred criteria with the client in writing.
- [ ] Resolve launch-blocking defects and document accepted residual risks.
- [ ] Client records dated acceptance against the deployed/documented version.

Use [the acceptance protocol](../../../ACCEPTANCE.md) and [the ticket update rules](../../../TICKET_TEMPLATE.md) when changing status.
