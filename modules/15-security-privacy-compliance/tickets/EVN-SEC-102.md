# EVN-SEC-102 - Prove important actions and incidents with tamper-evident evidence

Project: EverOnnAI. Module: [Security, consent, privacy, legal terms and assurance](../README.md). Technical delivery enabler allocated by this plan; source references below.

| Tracking dimension | Disposition |
| --- | --- |
| Engineering | Planned |
| QA | Existing checks are evidence for current slices; full ticket criteria remain pending |
| Deployment | Current local snapshot; verify ticket-specific hosted rollout and configuration |
| Business acceptance | Pending client review; no signed acceptance recorded |
| Owner | Security Lead + Counsel + Product Owner (proposed role; named person unassigned) |
| Priority / phase | Delivery enabler / P1 |
| Estimate | TBD after scope/architecture agreement; no delivery date committed |
| Dependencies | [EVN-SEC-101](EVN-SEC-101.md), [EVN-OPS-102](../../18-reliability-deployment-scale/tickets/EVN-OPS-102.md) |

## Business deliverable

Prove important actions and incidents with tamper-evident evidence.

The client accepts the demonstrated outcome and evidence, rather than the existence of a route, table or screen. This ticket does not certify the whole source requirement as complete.

## Current implemented slice

- [ ] Operational usage journals are not a full security audit chain.

The current statement describes prerequisites or context; this business deliverable has not been demonstrated.

## Remaining delivery checklist

- [ ] Implement hash-chained audit/WORM anchors, central security logs, incident runbooks and independent review evidence.

## Technical component

- [ ] Implement the module boundary and contracts for: Audit writer, anchor worker, SIEM export and incident escalation.
- [ ] Maintain tenant boundaries, explicit state transitions, access policy and failure handling for the delivered workflow.
- [ ] Resolve applicable architecture decisions before committing to a new provider or infrastructure baseline.

## DB

Existing module persistence: Private entity tables, scoped auth, encrypted provider payloads and invoker write functions.

The following records/contracts are proposed or require extension; their names are planning terms, not assertions that production tables exist.

- [ ] audit_log, anchors, incident/evidence records.
- [ ] Review scope keys, uniqueness, indexes, retention and migration compatibility; backfill safely and preserve existing tenant records.

## UI

- [ ] Audit search and authorised incident toolkit.
- [ ] Provide loading, empty, validation, permission-denied and recoverable failure states with keyboard and mobile access.
- [ ] Show observed facts and pending states accurately; do not present estimates, configured flags or mock results as confirmed business actions.

## Translate - business-to-technical mapping

| Business rule / outcome | Technical responsibility | Evidence needed |
| --- | --- | --- |
| Prove important actions and incidents with tamper-evident evidence. | Audit writer, anchor worker, SIEM export and incident escalation | Tenant-scoped end-to-end demonstration of the outcome |
| Implement hash-chained audit/WORM anchors, central security logs, incident runbooks and independent review evidence. | audit_log, anchors, incident/evidence records; Audit search and authorised incident toolkit | Migration/contracts, visible state and failure-path evidence |
| Safe, truthful AI behaviour where applicable | Record policy/tool/approval interventions without exposing sensitive payloads | Approved context, verified side-effect receipts and evaluation results or justified N/A |
| Client can approve delivery | QA report, rollout evidence and named acceptance owner | Evidence links and dated client sign-off |

This section means requirements-to-implementation mapping. It does not mean language translation; source language obligations are tracked in their own requirements.

## Backend services

- [ ] Audit writer, anchor worker, SIEM export and incident escalation.
- [ ] Define request/response/event schemas, authorisation and input validation for each affected operation.
- [ ] For writes and provider effects, define idempotency, retry/timeout, receipts and reconciliation; document N/A where no side effects exist.
- [ ] Expose actionable status and scoped logs without secrets; distinguish completed, failed and uncertain outcomes.

## AI component

- [ ] Record policy/tool/approval interventions without exposing sensitive payloads.
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
| [BRL-012](../../../requirements/BRL.md#brl-012) | Plan allocation / source cross-reference | 8. Business rules |
| [SCF-007](../../../requirements/SCF.md#scf-007) | Plan allocation / source cross-reference | 22.3 Scaffolding checklist |
| [SEC-001](../../../requirements/SEC.md#sec-001) | Source-linked | 22.2 Security requirements |
| [SEC-009](../../../requirements/SEC.md#sec-009) | Source-linked | 22.2 Security requirements |
| [SEC-010](../../../requirements/SEC.md#sec-010) | Source-linked | 22.2 Security requirements |
| [SEC-011](../../../requirements/SEC.md#sec-011) | Source-linked | 22.2 Security requirements |
| [SEC-012](../../../requirements/SEC.md#sec-012) | Source-linked | 22.2 Security requirements |
| [SEC-016](../../../requirements/SEC.md#sec-016) | Source-linked | 22.2 Security requirements |
| [SEC-018](../../../requirements/SEC.md#sec-018) | Source-linked | 22.2 Security requirements |

Read every allocated record, including its continuation bullets and source variants. Source-linked rows preserve explicit document relationships; plan allocations are implementation responsibility assignments created during this review.

## Allocated specification checklist

The unchecked source obligations below require requirement-level evidence. They are deliberately separate from checked statements about current implemented slices. Read linked continuation bullets and additional source wording before accepting a record.

- [ ] [BRL-012](../../../requirements/BRL.md#brl-012): BRL-012 | Every human intervention by an operator, staff member or support agent is recorded with who, what and when. | Platform | HIL-011, SEC-009, DSK-024.
- [ ] [SCF-007](../../../requirements/SCF.md#scf-007): 7 | Hash-chained audit log with WORM anchoring | SOC 2 evidence, tenant-visible audit, forensic investigations.
- [ ] [SEC-001](../../../requirements/SEC.md#sec-001): SEC-001 [P0] MUST run a secure SDLC: threat model per module (STRIDE plus LLM-specific), OWASP ASVS Level 2 as the target, OWASP Top 10 for LLM Applications mapped to controls (SEC-015), mandatory two-person review, protected branches, signed commits for release branches.
- [ ] [SEC-009](../../../requirements/SEC.md#sec-009): SEC-009 [P1] MUST keep an append-only, tamper-evident audit log: hash-chained entries (each includes the hash of the previous), periodic anchoring of the chain head to object storage with object lock (WORM), covering authentication events, permission changes, configuration publishes, staff access to tenant data, HITL actions, exports, deletions and admin actions. Tenants can view their own audit trail (P2).
- [ ] [SEC-010](../../../requirements/SEC.md#sec-010): SEC-010 [P1] MUST secure the software supply chain: minimal base images (Red Hat UBI minimal), pinned image digests, SBOM (Syft/CycloneDX) per build, vulnerability scanning (Trivy or Grype) blocking on critical/high with agreed exceptions, image signing and verification (cosign or Podman signature policy), dependency review and license policy, automated update PRs (Renovate), private registry.
- [ ] [SEC-011](../../../requirements/SEC.md#sec-011): SEC-011 [P1] MUST run vulnerability management: SLAs (critical within 7 days, high within 30 days, or documented mitigation), monthly RHEL patch cycle with emergency path, weekly scans of images and hosts, an external penetration test before P1 launch and again after P2, and a vulnerability disclosure policy (security.txt), with a bug bounty considered at P3.
- [ ] [SEC-012](../../../requirements/SEC.md#sec-012): SEC-012 [P1] MUST produce structured security logs with correlation ids, centralised and retained per policy, with alerting on suspicious patterns (impossible travel, mass reads, repeated authorization failures, unusual export or impersonation events). Logs are SIEM-ready; fail2ban or equivalent at hosts.
- [ ] [SEC-016](../../../requirements/SEC.md#sec-016): SEC-016 [P2] MUST follow a compliance roadmap: policy pack (access control, change management, incident response, vendor management, BCP/DR, data classification, secure development), evidence collection automated from CI and infrastructure, SOC 2 Type I readiness by end of P2 and Type II observation thereafter; PCI scope kept at SAQ A; HIPAA controls scaffolded (COM-010). ISO 27001 optional.
- [ ] [SEC-018](../../../requirements/SEC.md#sec-018): SEC-018 [P1] MUST define incident response: severity matrix, on-call rotation, runbooks (vendor outage, data exposure, toll fraud spike, prompt-injection incident, credential compromise), breach-notification workflow with statutory deadlines, tenant communication templates, post-incident review process. Run at least one tabletop exercise before launch.

## Existing code / check evidence

- `features/auth/request-origin.ts` - inspected current application working tree; see [snapshot evidence](../../../EVIDENCE.md).
- `features/auth/session.ts` - inspected current application working tree; see [snapshot evidence](../../../EVIDENCE.md).
- `features/auth/rbac.ts` - inspected current application working tree; see [snapshot evidence](../../../EVIDENCE.md).
- `lib/provider-credentials.ts` - inspected current application working tree; see [snapshot evidence](../../../EVIDENCE.md).
- `lib/app-records.ts` - inspected current application working tree; see [snapshot evidence](../../../EVIDENCE.md).
- `supabase/migrations/202610040003_everonn_relational.sql` - inspected current application working tree; see [snapshot evidence](../../../EVIDENCE.md).
- `supabase/migrations/202610060004_project_repositories.sql` - inspected current application working tree; see [snapshot evidence](../../../EVIDENCE.md).
- Relevant automated checks: `tests/workspace-security.test.ts`, `tests/request-origin.test.ts`, `tests/provider-credentials.test.ts`, `tests/everonn-relational.test.ts`, `tests/project-workspace.test.ts`. Their scope is bounded by [current validation](../../../CURRENT_STATE.md).

## Blockers and boundaries

Module risk: Private PostgreSQL and AES-GCM tokens are not a consent ledger, per-tenant KMS keys, audit/WORM chain, privacy operations, pen-test pass or SOC 2 certification.

Dependencies: [EVN-SEC-101](EVN-SEC-101.md), [EVN-OPS-102](../../18-reliability-deployment-scale/tickets/EVN-OPS-102.md). A blocked prerequisite can be prototyped independently, but its contract and deployment must be approved before claiming this ticket delivered. Service limits, third-party approvals and staffing are evidence requirements, not assumptions that they are available.

## Handover and client acceptance

- [ ] Attach the business demonstration, technical evidence and operating/recovery instructions.
- [ ] Assign a named acceptance owner and agree any deferred criteria with the client in writing.
- [ ] Resolve launch-blocking defects and document accepted residual risks.
- [ ] Client records dated acceptance against the deployed/documented version.

Use [the acceptance protocol](../../../ACCEPTANCE.md) and [the ticket update rules](../../../TICKET_TEMPLATE.md) when changing status.
