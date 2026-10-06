# EVN-OPS-102 - Deploy repeatably with a reviewed rollback and secure supply chain

Project: EverOnnAI. Module: [Infrastructure, durable workflows, reliability and scale](../README.md). Technical delivery enabler allocated by this plan; source references below.

| Tracking dimension | Disposition |
| --- | --- |
| Engineering | Partial |
| QA | Existing checks are evidence for current slices; full ticket criteria remain pending |
| Deployment | Current local snapshot; verify ticket-specific hosted rollout and configuration |
| Business acceptance | Pending client review; no signed acceptance recorded |
| Owner | SRE/Platform Lead (proposed role; named person unassigned) |
| Priority / phase | Delivery enabler / P0 |
| Estimate | TBD after scope/architecture agreement; no delivery date committed |
| Dependencies | [EVN-FND-101](../../00-foundations-governance/tickets/EVN-FND-101.md) |

## Business deliverable

Deploy repeatably with a reviewed rollback and secure supply chain.

The client accepts the demonstrated outcome and evidence, rather than the existence of a route, table or screen. This ticket does not certify the whole source requirement as complete.

## Current implemented slice

- [x] Amplify build/environment adapters and production build scripts exist.

## Remaining delivery checklist

- [ ] Approve RHEL/Podman or exception, create environments/IaC, protected CI, image/SBOM scanning/signing and artifact promotions.

## Technical component

- [ ] Implement the module boundary and contracts for: CI/CD, IaC, registry and canary/rollback automation.
- [ ] Maintain tenant boundaries, explicit state transitions, access policy and failure handling for the delivered workflow.
- [ ] Resolve applicable architecture decisions before committing to a new provider or infrastructure baseline.

## DB

Existing module persistence: Guarded migrations and usage-worker infrastructure; no general domain bus/cells/media drain.

The following records/contracts are proposed or require extension; their names are planning terms, not assertions that production tables exist.

- [ ] release manifests and deployment evidence.
- [ ] no customer schema change by default.
- [ ] Review scope keys, uniqueness, indexes, retention and migration compatibility; backfill safely and preserve existing tenant records.

## UI

- [ ] Release approval and environment status.
- [ ] Provide loading, empty, validation, permission-denied and recoverable failure states with keyboard and mobile access.
- [ ] Show observed facts and pending states accurately; do not present estimates, configured flags or mock results as confirmed business actions.

## Translate - business-to-technical mapping

| Business rule / outcome | Technical responsibility | Evidence needed |
| --- | --- | --- |
| Deploy repeatably with a reviewed rollback and secure supply chain. | CI/CD, IaC, registry and canary/rollback automation | Tenant-scoped end-to-end demonstration of the outcome |
| Approve RHEL/Podman or exception, create environments/IaC, protected CI, image/SBOM scanning/signing and artifact promotions. | release manifests and deployment evidence; no customer schema change by default; Release approval and environment status | Migration/contracts, visible state and failure-path evidence |
| Safe, truthful AI behaviour where applicable | Prompt/model releases require the AI gate as well as app tests | Approved context, verified side-effect receipts and evaluation results or justified N/A |
| Client can approve delivery | QA report, rollout evidence and named acceptance owner | Evidence links and dated client sign-off |

This section means requirements-to-implementation mapping. It does not mean language translation; source language obligations are tracked in their own requirements.

## Backend services

- [ ] CI/CD, IaC, registry and canary/rollback automation.
- [ ] Define request/response/event schemas, authorisation and input validation for each affected operation.
- [ ] For writes and provider effects, define idempotency, retry/timeout, receipts and reconciliation; document N/A where no side effects exist.
- [ ] Expose actionable status and scoped logs without secrets; distinguish completed, failed and uncertain outcomes.

## AI component

- [ ] Prompt/model releases require the AI gate as well as app tests.
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
| [AR-005](../../../requirements/AR.md#ar-005) | Source-linked | 11.7 Architecture requirements |
| [AR-009](../../../requirements/AR.md#ar-009) | Source-linked | 11.7 Architecture requirements |
| [AR-010](../../../requirements/AR.md#ar-010) | Source-linked | 11.7 Architecture requirements |
| [SCF-012](../../../requirements/SCF.md#scf-012) | Plan allocation / source cross-reference | 22.3 Scaffolding checklist |
| [SCF-022](../../../requirements/SCF.md#scf-022) | Plan allocation / source cross-reference | 22.3 Scaffolding checklist |
| [SEC-010](../../../requirements/SEC.md#sec-010) | Source-linked | 22.2 Security requirements |

Read every allocated record, including its continuation bullets and source variants. Source-linked rows preserve explicit document relationships; plan allocations are implementation responsibility assignments created during this review.

## Allocated specification checklist

The unchecked source obligations below require requirement-level evidence. They are deliberately separate from checked statements about current implemented slices. Read linked continuation bullets and additional source wording before accepting a record.

- [ ] [AR-005](../../../requirements/AR.md#ar-005): AR-005 [P1] MUST be cell-ready: a "cell" is a complete stack (API, workers, DB schema set, Redis, media/voice workers) serving a subset of tenants. tenants.cell_id and a routing map MUST exist from P1 even if only one cell runs. Adding a cell MUST be scriptable (infra as code).
- [ ] [AR-009](../../../requirements/AR.md#ar-009): AR-009 [P1] MUST support blue/green or rolling deploys with zero dropped calls: voice workers drain (finish active calls, accept none) before termination.
- [ ] [AR-010](../../../requirements/AR.md#ar-010): AR-010 [P2] SHOULD provide a path to Kubernetes/OpenShift (manifests or Helm charts and a documented migration plan) while running on Podman/Quadlet at P1.
- [ ] [SCF-012](../../../requirements/SCF.md#scf-012): 12 | OpenFeature-compatible flags, canary and kill switches | Experiments, staged rollouts, instant mitigation.
- [ ] [SCF-022](../../../requirements/SCF.md#scf-022): 22 | Infra as code for every environment (Ansible/OpenTofu) and Kubernetes-compatible packaging | Multi-region, cloud burst, OpenShift migration, DR automation.
- [ ] [SEC-010](../../../requirements/SEC.md#sec-010): SEC-010 [P1] MUST secure the software supply chain: minimal base images (Red Hat UBI minimal), pinned image digests, SBOM (Syft/CycloneDX) per build, vulnerability scanning (Trivy or Grype) blocking on critical/high with agreed exceptions, image signing and verification (cosign or Podman signature policy), dependency review and license policy, automated update PRs (Renovate), private registry.

## Existing code / check evidence

- `amplify.yml` - inspected current application working tree; see [snapshot evidence](../../../EVIDENCE.md).
- `scripts/write-amplify-env.mjs` - inspected current application working tree; see [snapshot evidence](../../../EVIDENCE.md).
- `scripts/migrate-everonn-database.ts` - inspected current application working tree; see [snapshot evidence](../../../EVIDENCE.md).
- `scripts/configure-usage-scheduler.ts` - inspected current application working tree; see [snapshot evidence](../../../EVIDENCE.md).
- `features/usage/worker.ts` - inspected current application working tree; see [snapshot evidence](../../../EVIDENCE.md).
- `lib/usage-scheduler.ts` - inspected current application working tree; see [snapshot evidence](../../../EVIDENCE.md).
- `lib/app-records.ts` - inspected current application working tree; see [snapshot evidence](../../../EVIDENCE.md).
- `lib/usage-postgres.ts` - inspected current application working tree; see [snapshot evidence](../../../EVIDENCE.md).
- Relevant automated checks: `tests/amplify-env.test.ts`, `tests/usage-scheduler.test.ts`, `tests/app-records.test.ts`, `scripts/smoke-auth-database.ts`. Their scope is bounded by [current validation](../../../CURRENT_STATE.md).

## Blockers and boundaries

Module risk: A build and scheduled usage worker are not a 99.9% voice SLO, restore/PITR proof, multi-region service or 1,000-sites/day load pass.

Dependencies: [EVN-FND-101](../../00-foundations-governance/tickets/EVN-FND-101.md). A blocked prerequisite can be prototyped independently, but its contract and deployment must be approved before claiming this ticket delivered. Service limits, third-party approvals and staffing are evidence requirements, not assumptions that they are available.

## Handover and client acceptance

- [ ] Attach the business demonstration, technical evidence and operating/recovery instructions.
- [ ] Assign a named acceptance owner and agree any deferred criteria with the client in writing.
- [ ] Resolve launch-blocking defects and document accepted residual risks.
- [ ] Client records dated acceptance against the deployed/documented version.

Use [the acceptance protocol](../../../ACCEPTANCE.md) and [the ticket update rules](../../../TICKET_TEMPLATE.md) when changing status.
