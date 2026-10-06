# EVN-INT-049 - Connect the systems each vertical uses

Project: EverOnnAI. Module: [Public API, webhooks and vertical connectors](../README.md). Source business requirement [BR-049](../../../requirements/BR.md#br-049).

| Tracking dimension | Disposition |
| --- | --- |
| Engineering | Partial |
| QA | Existing checks are evidence for current slices; full ticket criteria remain pending |
| Deployment | Current local snapshot; verify ticket-specific hosted rollout and configuration |
| Business acceptance | Pending client review; no signed acceptance recorded |
| Owner | Integration Lead + Backend Lead (proposed role; named person unassigned) |
| Priority / phase | Should / P1 framework, P2 connectors |
| Estimate | TBD after scope/architecture agreement; no delivery date committed |
| Dependencies | [EVN-ONB-102](../../01-onboarding-tenancy-identity/tickets/EVN-ONB-102.md), [EVN-SEC-101](../../15-security-privacy-compliance/tickets/EVN-SEC-101.md), [EVN-OPS-101](../../18-reliability-deployment-scale/tickets/EVN-OPS-101.md) |

## Business deliverable

Connect the systems each vertical uses. The platform connects to the shop-management, field-service, practice-management, accounting, agency, calendar and point-of-sale systems each vertical uses, and works fully without any connection.

The client accepts the demonstrated outcome and evidence, rather than the existence of a route, table or screen. This ticket does not certify the whole source requirement as complete.

## Current implemented slice

- [x] Google Calendar/Gmail and customer GitHub are separate integrations.

## Remaining delivery checklist

- [ ] Define connector contracts, health/sync/retries/mapping and offline fallback; approve access per vertical.

## Technical component

- [ ] Implement the module boundary and contracts for: ConnectorProvider, retries, contract tests and fallback.
- [ ] Maintain tenant boundaries, explicit state transitions, access policy and failure handling for the delivered workflow.
- [ ] Resolve applicable architecture decisions before committing to a new provider or infrastructure baseline.

## DB

Existing module persistence: Encrypted Google connections, GitHub repository credentials and specialised metering ingress records.

The following records/contracts are proposed or require extension; their names are planning terms, not assertions that production tables exist.

- [ ] connector_configs, sync_runs, connector_health.
- [ ] Review scope keys, uniqueness, indexes, retention and migration compatibility; backfill safely and preserve existing tenant records.

## UI

- [ ] Connector catalog, mapping and health.
- [ ] Provide loading, empty, validation, permission-denied and recoverable failure states with keyboard and mobile access.
- [ ] Show observed facts and pending states accurately; do not present estimates, configured flags or mock results as confirmed business actions.

## Translate - business-to-technical mapping

| Business rule / outcome | Technical responsibility | Evidence needed |
| --- | --- | --- |
| Connect the systems each vertical uses. The platform connects to the shop-management, field-service, practice-management, accounting, agency, calendar and point-of-sale systems each vertical uses, and works fully without any connection. | ConnectorProvider, retries, contract tests and fallback | Tenant-scoped end-to-end demonstration of the outcome |
| Define connector contracts, health/sync/retries/mapping and offline fallback; approve access per vertical. | connector_configs, sync_runs, connector_health; Connector catalog, mapping and health | Migration/contracts, visible state and failure-path evidence |
| Safe, truthful AI behaviour where applicable | Validated tool data; unknown state never means success | Approved context, verified side-effect receipts and evaluation results or justified N/A |
| Client can approve delivery | QA report, rollout evidence and named acceptance owner | Evidence links and dated client sign-off |

This section means requirements-to-implementation mapping. It does not mean language translation; source language obligations are tracked in their own requirements.

## Backend services

- [ ] ConnectorProvider, retries, contract tests and fallback.
- [ ] Define request/response/event schemas, authorisation and input validation for each affected operation.
- [ ] For writes and provider effects, define idempotency, retry/timeout, receipts and reconciliation; document N/A where no side effects exist.
- [ ] Expose actionable status and scoped logs without secrets; distinguish completed, failed and uncertain outcomes.

## AI component

- [ ] Validated tool data.
- [ ] unknown state never means success.
- [ ] Record instruction/knowledge/tool versions, measured quality, tenant scope, cost and safe fallback; a Markdown standard alone is not a passed evaluation.

## Testing / QA

- [ ] Exercise the intended user journey with real tenant-scoped state; cover forbidden role and cross-tenant requests.
- [ ] Test malformed inputs, provider failure, retries/replays and cancellation as applicable; keep deterministic mocks separate from live-provider evidence.
- [ ] Review desktop/mobile accessibility, factual copy and failure recovery in the delivered UI.
- [ ] Attach test environment, code/config/instruction versions, results and remaining defects to the acceptance report.

| Source test | Scenario | Required pass criteria | Current disposition |
| --- | --- | --- | --- |
| [AT-10](../../../requirements/AT.md#at-10) | Connector framework and fallback | A test connector authenticates, syncs and reports health; with the connector disabled, the vertical still captures requests, notifies the team and books through the calendar | Full source scenario not evidenced; client acceptance pending |

Source stories: [US-059](../../../requirements/US.md#us-059).

## Deployment

- [ ] Confirm approved hosting/database/provider architecture and required credentials in the deployment environment.
- [ ] Apply compatible migrations/configuration in staging, rehearse rollback, then promote the reviewed artifact.
- [ ] Verify the actual hosted workflow, monitoring, fallback and customer-visible errors after release.
- [ ] Update CODE_PROFILE.md, PROJECT_DATA_FLOW.md and CLIENT_TECHNICAL_QA.md in the application when behaviour or architecture changes.
- [ ] Record deployment identity, operator, timestamp and rollback evidence; document-only tickets instead record the reviewed Git commit.

## Source traceability

| Source ID | Mapping basis | Source section |
| --- | --- | --- |
| [API-005](../../../requirements/API.md#api-005) | Plan allocation / source cross-reference | 19.4 Public API, webhooks and integrations (API) |
| [AT-10](../../../requirements/AT.md#at-10) | Source-linked | 25.2 Acceptance tests |
| [BKG-005](../../../requirements/BKG.md#bkg-005) | Plan allocation / source cross-reference | 17.2 Requirements |
| [BO-8](../../../requirements/BO.md#bo-8) | Source-linked | 3.1 Business objectives |
| [BO-10](../../../requirements/BO.md#bo-10) | Source-linked | 3.1 Business objectives |
| [BR-049](../../../requirements/BR.md#br-049) | Source-linked | 7.8 Suite, verticals and brands |
| [INT-001](../../../requirements/INT.md#int-001) | Source-linked | 19.10 Integration framework and vertical connectors (INT) |
| [INT-002](../../../requirements/INT.md#int-002) | Source-linked | 19.10 Integration framework and vertical connectors (INT) |
| [INT-003](../../../requirements/INT.md#int-003) | Source-linked | 19.10 Integration framework and vertical connectors (INT) |
| [INT-004](../../../requirements/INT.md#int-004) | Plan allocation / source cross-reference | 19.10 Integration framework and vertical connectors (INT) |
| [INT-005](../../../requirements/INT.md#int-005) | Plan allocation / source cross-reference | 19.10 Integration framework and vertical connectors (INT) |
| [US-059](../../../requirements/US.md#us-059) | Source-linked | EP-12 Verticals and brands |

Read every allocated record, including its continuation bullets and source variants. Source-linked rows preserve explicit document relationships; plan allocations are implementation responsibility assignments created during this review.

## Allocated specification checklist

The unchecked source obligations below require requirement-level evidence. They are deliberately separate from checked statements about current implemented slices. Read linked continuation bullets and additional source wording before accepting a record.

- [ ] [API-005](../../../requirements/API.md#api-005): API-005 [P2] SHOULD provide first integrations: Google Calendar and Microsoft 365 (BKG-001), Google Business Profile, QuickBooks (invoice/customer sync, P3), and one field-service system (BKG-005).
- [ ] [BKG-005](../../../requirements/BKG.md#bkg-005): BKG-005 [P3] MAY integrate field-service systems (Jobber, Housecall Pro, ServiceTitan, Workiz) via an FsmProvider interface scaffolded at P2.
- [ ] [INT-001](../../../requirements/INT.md#int-001): INT-001 [P1] MUST provide a connector framework: a standard interface for authentication (OAuth or API key), initial and incremental sync, webhooks, field mapping, retries, rate-limit handling and health reporting; per-tenant credentials held in the secrets vault; a connector development kit; contract tests; versioning; a sandbox mode; failure isolation so that one connector cannot affect others; and audit of every action. Calendar, point-of-sale, field-service, shop-management, practice-management, accounting and agency systems all use it.
- [ ] [INT-002](../../../requirements/INT.md#int-002): INT-002 [P1] SHOULD maintain a connector catalog by vertical, in priority tiers with status (planned, beta, generally available). Candidates, each subject to confirmed access and terms before anything is promised to a client: auto repair (Tekmetric, Shop-Ware, Mitchell1, Shopmonkey and similar); home and urgent services (ServiceTitan, Housecall Pro, Jobber, FieldEdge); accounting (TaxDome, Canopy, Karbon, QuickBooks, Xero, SmartVault); law (Clio, MyCase, Lawmatics, Filevine); insurance (Applied Epic, EZLynx, HawkSoft, AMS360, AgencyZoom); dental (Dentrix, Eaglesoft, Open Dental); chiropractic (ChiroTouch); veterinary (Cornerstone, ezyVet, Shepherd, Neo); medical and med spa (Nextech, Zenoti, Boulevard); restaurants (Square, Toast, Clover). A connector appears in client-facing material only when it is generally available.
- [ ] [INT-003](../../../requirements/INT.md#int-003): INT-003 [P1] MUST ensure every vertical pack works without any connector: requests are captured and structured, the team is notified, calendars and email or text are used, and nothing depends on a third-party system being connected. Connectors add automation; they are never required for the core service.
- [ ] [INT-004](../../../requirements/INT.md#int-004): INT-004 [P2] SHOULD track integration access as managed work: partner-program applications, terms, certification stages, commercial conditions and owners, visible to the vertical manager.
- [ ] [INT-005](../../../requirements/INT.md#int-005): INT-005 [P2] MUST apply data minimization and the vertical's compliance profile to connectors, and for health-care connectors permit only subprocessors covered by business associate agreements (COM-015).

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
