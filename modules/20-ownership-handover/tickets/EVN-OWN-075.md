# EVN-OWN-075 - EverOnn owns everything

Project: EverOnnAI. Module: [Ownership, licensing, documentation and operational handover](../README.md). Source business requirement [BR-075](../../../requirements/BR.md#br-075).

| Tracking dimension | Disposition |
| --- | --- |
| Engineering | Partial |
| QA | Existing checks are evidence for current slices; full ticket criteria remain pending |
| Deployment | Current local snapshot; verify ticket-specific hosted rollout and configuration |
| Business acceptance | Pending client review; no signed acceptance recorded |
| Owner | EverOnn Owner + Technical Lead (proposed role; named person unassigned) |
| Priority / phase | Must / P0 |
| Estimate | TBD after scope/architecture agreement; no delivery date committed |
| Dependencies | [EVN-OWN-101](EVN-OWN-101.md) |

## Business deliverable

EverOnn owns everything. EverOnn owns all code, prompts, data and infrastructure accounts, with no vendor lock-in.

The client accepts the demonstrated outcome and evidence, rather than the existence of a route, table or screen. This ticket does not certify the whole source requirement as complete.

## Current implemented slice

- [x] Application and planning repositories use the named EverOnn GitHub namespace.

## Remaining delivery checklist

- [ ] Verify IP/account ownership, licensing/SBOM, key/infra access, portability and paired handover.

## Technical component

- [ ] Implement the module boundary and contracts for: Account inventory, export/exit plan and operations docs.
- [ ] Maintain tenant boundaries, explicit state transitions, access policy and failure handling for the delivered workflow.
- [ ] Resolve applicable architecture decisions before committing to a new provider or infrastructure baseline.

## DB

Existing module persistence: No completed asset/account/licence/handover acceptance register.

The following records/contracts are proposed or require extension; their names are planning terms, not assertions that production tables exist.

- [ ] asset_register, licence_inventory, access_grants.
- [ ] Version the relevant evidence/registers and keep customer secrets out of the documentation repository.

## UI

- [ ] Ownership/handover evidence checklist.
- [ ] Provide loading, empty, validation, permission-denied and recoverable failure states with keyboard and mobile access.
- [ ] Show observed facts and pending states accurately; do not present estimates, configured flags or mock results as confirmed business actions.

## Translate - business-to-technical mapping

| Business rule / outcome | Technical responsibility | Evidence needed |
| --- | --- | --- |
| EverOnn owns everything. EverOnn owns all code, prompts, data and infrastructure accounts, with no vendor lock-in. | Account inventory, export/exit plan and operations docs | Tenant-scoped end-to-end demonstration of the outcome |
| Verify IP/account ownership, licensing/SBOM, key/infra access, portability and paired handover. | asset_register, licence_inventory, access_grants; Ownership/handover evidence checklist | Migration/contracts, visible state and failure-path evidence |
| Safe, truthful AI behaviour where applicable | EverOnn-owned prompts/datasets and portable provider contracts | Approved context, verified side-effect receipts and evaluation results or justified N/A |
| Client can approve delivery | QA report, rollout evidence and named acceptance owner | Evidence links and dated client sign-off |

This section means requirements-to-implementation mapping. It does not mean language translation; source language obligations are tracked in their own requirements.

## Backend services

- [ ] Account inventory, export/exit plan and operations docs.
- [ ] Define request/response/event schemas, authorisation and input validation for each affected operation.
- [ ] For writes and provider effects, define idempotency, retry/timeout, receipts and reconciliation; document N/A where no side effects exist.
- [ ] Expose actionable status and scoped logs without secrets; distinguish completed, failed and uncertain outcomes.

## AI component

- [ ] EverOnn-owned prompts/datasets and portable provider contracts.
- [ ] Record instruction/knowledge/tool versions, measured quality, tenant scope, cost and safe fallback; a Markdown standard alone is not a passed evaluation.

## Testing / QA

- [ ] Exercise the intended user journey with real tenant-scoped state; cover forbidden role and cross-tenant requests.
- [ ] Test malformed inputs, provider failure, retries/replays and cancellation as applicable; keep deterministic mocks separate from live-provider evidence.
- [ ] Review desktop/mobile accessibility, factual copy and failure recovery in the delivered UI.
- [ ] Attach test environment, code/config/instruction versions, results and remaining defects to the acceptance report.

| Source test | Scenario | Required pass criteria | Current disposition |
| --- | --- | --- | --- |
| [AT-60](../../../requirements/AT.md#at-60) | Ownership and handover | Repositories, accounts, keys and documentation are in EverOnn's control; EverOnn staff can build and deploy from the repository; software bill of materials and license report delivered | Full source scenario not evidenced; client acceptance pending |

Source stories: [US-054](../../../requirements/US.md#us-054).

## Deployment

- [ ] Confirm approved hosting/database/provider architecture and required credentials in the deployment environment.
- [ ] Apply compatible migrations/configuration in staging, rehearse rollback, then promote the reviewed artifact.
- [ ] Verify the actual hosted workflow, monitoring, fallback and customer-visible errors after release.
- [ ] Update CODE_PROFILE.md, PROJECT_DATA_FLOW.md and CLIENT_TECHNICAL_QA.md in the application when behaviour or architecture changes.
- [ ] Record deployment identity, operator, timestamp and rollback evidence; document-only tickets instead record the reviewed Git commit.

## Source traceability

| Source ID | Mapping basis | Source section |
| --- | --- | --- |
| [AR-002](../../../requirements/AR.md#ar-002) | Source-linked | 11.7 Architecture requirements |
| [AT-60](../../../requirements/AT.md#at-60) | Source-linked | 25.2 Acceptance tests |
| [BO-9](../../../requirements/BO.md#bo-9) | Source-linked | 3.1 Business objectives |
| [BR-075](../../../requirements/BR.md#br-075) | Source-linked | 7.12 Ownership and engineering |
| [SEC-010](../../../requirements/SEC.md#sec-010) | Source-linked | 22.2 Security requirements |
| [US-054](../../../requirements/US.md#us-054) | Source-linked | EP-11 Integrations, scale and ownership |

Read every allocated record, including its continuation bullets and source variants. Source-linked rows preserve explicit document relationships; plan allocations are implementation responsibility assignments created during this review.

## Allocated specification checklist

The unchecked source obligations below require requirement-level evidence. They are deliberately separate from checked statements about current implemented slices. Read linked continuation bullets and additional source wording before accepting a record.

- [ ] [AR-002](../../../requirements/AR.md#ar-002): AR-002 [P0] MUST expose every external vendor behind an internal interface: TelephonyProvider, SttProvider, TtsProvider, LlmProvider, SmsProvider, EmailProvider, PaymentProvider, CalendarProvider, GeocodingProvider. Each MUST have at least one alternative implementation stubbed or contract-tested by end of P1 for telephony and LLM, by P2 for the rest.
- [ ] [SEC-010](../../../requirements/SEC.md#sec-010): SEC-010 [P1] MUST secure the software supply chain: minimal base images (Red Hat UBI minimal), pinned image digests, SBOM (Syft/CycloneDX) per build, vulnerability scanning (Trivy or Grype) blocking on critical/high with agreed exceptions, image signing and verification (cosign or Podman signature policy), dependency review and license policy, automated update PRs (Renovate), private registry.

## Existing code / check evidence

- `README.md` - inspected current application working tree; see [snapshot evidence](../../../EVIDENCE.md).
- `CODE_PROFILE.md` - inspected current application working tree; see [snapshot evidence](../../../EVIDENCE.md).
- `PROJECT_DATA_FLOW.md` - inspected current application working tree; see [snapshot evidence](../../../EVIDENCE.md).
- `CLIENT_TECHNICAL_QA.md` - inspected current application working tree; see [snapshot evidence](../../../EVIDENCE.md).
- `USAGE_OPERATIONS.md` - inspected current application working tree; see [snapshot evidence](../../../EVIDENCE.md).

## Blockers and boundaries

Module risk: A GitHub namespace proves repository location, not every infrastructure account, IP assignment, vendor exit right or trained operations team.

Dependencies: [EVN-OWN-101](EVN-OWN-101.md). A blocked prerequisite can be prototyped independently, but its contract and deployment must be approved before claiming this ticket delivered. Service limits, third-party approvals and staffing are evidence requirements, not assumptions that they are available.

## Handover and client acceptance

- [ ] Attach the business demonstration, technical evidence and operating/recovery instructions.
- [ ] Assign a named acceptance owner and agree any deferred criteria with the client in writing.
- [ ] Resolve launch-blocking defects and document accepted residual risks.
- [ ] Client records dated acceptance against the deployed/documented version.

Use [the acceptance protocol](../../../ACCEPTANCE.md) and [the ticket update rules](../../../TICKET_TEMPLATE.md) when changing status.
