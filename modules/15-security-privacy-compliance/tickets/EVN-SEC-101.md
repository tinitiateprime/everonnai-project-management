# EVN-SEC-101 - Protect access, data and secrets with an approved security design

Project: EverOnnAI. Module: [Security, consent, privacy, legal terms and assurance](../README.md). Technical delivery enabler allocated by this plan; source references below.

| Tracking dimension | Disposition |
| --- | --- |
| Engineering | Partial |
| QA | Existing checks are evidence for current slices; full ticket criteria remain pending |
| Deployment | Current local snapshot; verify ticket-specific hosted rollout and configuration |
| Business acceptance | Pending client review; no signed acceptance recorded |
| Owner | Security Lead + Counsel + Product Owner (proposed role; named person unassigned) |
| Priority / phase | Delivery enabler / P1 |
| Estimate | TBD after scope/architecture agreement; no delivery date committed |
| Dependencies | [EVN-FND-101](../../00-foundations-governance/tickets/EVN-FND-101.md), [EVN-ONB-102](../../01-onboarding-tenancy-identity/tickets/EVN-ONB-102.md) |

## Business deliverable

Protect access, data and secrets with an approved security design.

The client accepts the demonstrated outcome and evidence, rather than the existence of a route, table or screen. This ticket does not certify the whole source requirement as complete.

## Current implemented slice

- [x] Sessions/origin checks, private SQL, AES-GCM provider secrets and isolation tests exist.

## Remaining delivery checklist

- [ ] Add Vault/KMS tenant keys, rotation, secret scanning, service auth, egress controls and privacy/redaction enforcement.

## Technical component

- [ ] Implement the module boundary and contracts for: SecretProvider, key lifecycle, egress/input controls and service policy.
- [ ] Maintain tenant boundaries, explicit state transitions, access policy and failure handling for the delivered workflow.
- [ ] Resolve applicable architecture decisions before committing to a new provider or infrastructure baseline.

## DB

Existing module persistence: Private entity tables, scoped auth, encrypted provider payloads and invoker write functions.

The following records/contracts are proposed or require extension; their names are planning terms, not assertions that production tables exist.

- [ ] key versions, service identities, secret references, data classification.
- [ ] Review scope keys, uniqueness, indexes, retention and migration compatibility; backfill safely and preserve existing tenant records.

## UI

- [ ] Security configuration and reasoned step-up controls.
- [ ] Provide loading, empty, validation, permission-denied and recoverable failure states with keyboard and mobile access.
- [ ] Show observed facts and pending states accurately; do not present estimates, configured flags or mock results as confirmed business actions.

## Translate - business-to-technical mapping

| Business rule / outcome | Technical responsibility | Evidence needed |
| --- | --- | --- |
| Protect access, data and secrets with an approved security design. | SecretProvider, key lifecycle, egress/input controls and service policy | Tenant-scoped end-to-end demonstration of the outcome |
| Add Vault/KMS tenant keys, rotation, secret scanning, service auth, egress controls and privacy/redaction enforcement. | key versions, service identities, secret references, data classification; Security configuration and reasoned step-up controls | Migration/contracts, visible state and failure-path evidence |
| Safe, truthful AI behaviour where applicable | Never put secrets/customer cross-tenant data into prompts or traces | Approved context, verified side-effect receipts and evaluation results or justified N/A |
| Client can approve delivery | QA report, rollout evidence and named acceptance owner | Evidence links and dated client sign-off |

This section means requirements-to-implementation mapping. It does not mean language translation; source language obligations are tracked in their own requirements.

## Backend services

- [ ] SecretProvider, key lifecycle, egress/input controls and service policy.
- [ ] Define request/response/event schemas, authorisation and input validation for each affected operation.
- [ ] For writes and provider effects, define idempotency, retry/timeout, receipts and reconciliation; document N/A where no side effects exist.
- [ ] Expose actionable status and scoped logs without secrets; distinguish completed, failed and uncertain outcomes.

## AI component

- [ ] Never put secrets/customer cross-tenant data into prompts or traces.
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
| [COM-007](../../../requirements/COM.md#com-007) | Plan allocation / source cross-reference | 19.5 Compliance and legal-by-design (COM) |
| [HIL-013](../../../requirements/HIL.md#hil-013) | Plan allocation / source cross-reference | 16.5 Quality, learning and control of the human layer |
| [SCF-008](../../../requirements/SCF.md#scf-008) | Plan allocation / source cross-reference | 22.3 Scaffolding checklist |
| [SCF-014](../../../requirements/SCF.md#scf-014) | Plan allocation / source cross-reference | 22.3 Scaffolding checklist |
| [SCF-021](../../../requirements/SCF.md#scf-021) | Plan allocation / source cross-reference | 22.3 Scaffolding checklist |
| [SEC-002](../../../requirements/SEC.md#sec-002) | Source-linked | 22.2 Security requirements |
| [SEC-004](../../../requirements/SEC.md#sec-004) | Source-linked | 22.2 Security requirements |
| [SEC-005](../../../requirements/SEC.md#sec-005) | Source-linked | 22.2 Security requirements |
| [SEC-006](../../../requirements/SEC.md#sec-006) | Source-linked | 22.2 Security requirements |
| [SEC-007](../../../requirements/SEC.md#sec-007) | Source-linked | 22.2 Security requirements |
| [SEC-008](../../../requirements/SEC.md#sec-008) | Source-linked | 22.2 Security requirements |
| [SEC-015](../../../requirements/SEC.md#sec-015) | Source-linked | 22.2 Security requirements |
| [SEC-017](../../../requirements/SEC.md#sec-017) | Source-linked | 22.2 Security requirements |
| [VOX-015](../../../requirements/VOX.md#vox-015) | Plan allocation / source cross-reference | 14.4 Requirements: real-time conversation quality |
| [VOX-024](../../../requirements/VOX.md#vox-024) | Plan allocation / source cross-reference | 14.5 Requirements: business behavior |
| [VOX-034](../../../requirements/VOX.md#vox-034) | Plan allocation / source cross-reference | 14.3 Requirements: telephony and numbers |

Read every allocated record, including its continuation bullets and source variants. Source-linked rows preserve explicit document relationships; plan allocations are implementation responsibility assignments created during this review.

## Allocated specification checklist

The unchecked source obligations below require requirement-level evidence. They are deliberately separate from checked statements about current implemented slices. Read linked continuation bullets and additional source wording before accepting a record.

- [ ] [COM-007](../../../requirements/COM.md#com-007): COM-007 [P1] MUST implement PII redaction in logs, traces, analytics and eval datasets (names, phones, emails, addresses, card and government IDs), with reversible tokenization only in the primary store. Training or eval use of customer conversations requires opt-in and anonymization.
- [ ] [HIL-013](../../../requirements/HIL.md#hil-013): HIL-013 [P1] MUST apply operator security controls (minimum set at P1, full set at P2): least-privilege access (only assigned tenants and only the fields needed), MFA, device posture checks, session recording of console actions (not customer audio beyond policy), NDA/training attestation tracking, IP allow-listing for pooled operators, and automatic access expiry at shift end. Operators MUST NOT be able to export bulk data.
- [ ] [SCF-008](../../../requirements/SCF.md#scf-008): 8 | Envelope encryption with key ids/versions and per-tenant DEKs | BYOK/HYOK for enterprise; crypto-erasure on deletion; key rotation at scale.
- [ ] [SCF-014](../../../requirements/SCF.md#scf-014): 14 | Service-to-service auth via signed tokens with identity claims | mTLS service mesh, zero-trust networking.
- [ ] [SCF-021](../../../requirements/SCF.md#scf-021): 21 | Data classification tags in schema registry and redaction hooks | DLP, privacy tooling, safe analytics and eval datasets.
- [ ] [SEC-002](../../../requirements/SEC.md#sec-002): SEC-002 [P1] MUST segment networks by tier, allow only required flows, keep the database and Vault private, and use service-to-service authentication (mTLS with SPIFFE-style identities or signed short-lived service tokens at P1; service mesh optional at P2). Egress from application tiers goes through an allow-listed proxy.
- [ ] [SEC-004](../../../requirements/SEC.md#sec-004): SEC-004 [P1] MUST encrypt in transit: TLS 1.2+ (1.3 preferred) everywhere including internal links, HSTS, modern cipher suites, SRTP/DTLS for media, and TLS SIP with carriers where supported.
- [ ] [SEC-005](../../../requirements/SEC.md#sec-005): SEC-005 [P1] MUST encrypt at rest with envelope encryption: per-tenant data encryption keys wrapped by a key-encryption key in Vault Transit or a cloud KMS; applied to recordings, transcripts (at least sensitive fields), OAuth tokens and secrets, uploaded files; full-disk encryption on hosts; MariaDB encryption at rest for tablespaces and binlogs. Every ciphertext carries a key_id/version so keys can rotate and per-tenant (BYOK) keys can be introduced later without migration.
- [ ] [SEC-006](../../../requirements/SEC.md#sec-006): SEC-006 [P1] MUST manage secrets with Vault/OpenBao: no secrets in git, images or plaintext environment files; dynamic short-lived database credentials; automated rotation; secret scanning in CI and pre-commit.
- [ ] [SEC-007](../../../requirements/SEC.md#sec-007): SEC-007 [P1] MUST validate and sanitize all input at boundaries; encode output; strict CSP on all web properties; SSRF protection for any server-side fetch of user-supplied URLs (resolve-and-check, block private and link-local ranges, redirect limits, size and time limits); file upload security (type sniffing, size limits, AV scanning, image re-encoding, isolated storage, non-executable serving).
- [ ] [SEC-008](../../../requirements/SEC.md#sec-008): SEC-008 [P1] MUST implement abuse and fraud controls: per-IP, per-session, per-tenant rate limits and quotas; bot management on public forms and the widget; signup velocity and disposable-email checks; premium-rate and geo restrictions; unusual-usage alerts; identity verification (out-of-band OTP) before revealing or changing sensitive data over voice or chat.
- [ ] [SEC-015](../../../requirements/SEC.md#sec-015): SEC-015 [P1] MUST implement AI-specific security mapped to the OWASP LLM Top 10: prompt injection (POL-003), insecure output handling (never execute or render model output unsafely), sensitive information disclosure (redaction, retrieval filters, no secrets in prompts), excessive agency (tool scoping, approvals, per-call tool tokens bound to tenant and conversation), model denial of service (token, time and cost budgets), supply chain (provider vetting, model version pinning), overreliance (uncertainty behaviours, human escalation), and model theft/abuse (no system prompt secrets). Maintain a red-team suite and run it in CI and before every release.
- [ ] [SEC-017](../../../requirements/SEC.md#sec-017): SEC-017 [P1] MUST apply privacy by design: data inventory and map, DPIA template, minimization, purpose limitation, retention automation (COM-008), region tags (TEN-002), and a subprocessor register (COM-011).
- [ ] [VOX-015](../../../requirements/VOX.md#vox-015): VOX-015 [P2] SHOULD support multi-party awareness (speakerphone with two speakers) heuristics and safe behavior (confirm who the account holder is before sharing anything).
- [ ] [VOX-024](../../../requirements/VOX.md#vox-024): VOX-024 [P1] MUST support returning-caller recognition (matched by verified phone number and tenant contacts) to personalize ("Welcome back, Maria") without exposing history to unverified callers beyond what policy allows.
- [ ] [VOX-034](../../../requirements/VOX.md#vox-034): VOX-034 [P1] MUST support caller ID handling: pass caller ID into context; treat as untrusted; never assume identity from caller ID.

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

Dependencies: [EVN-FND-101](../../00-foundations-governance/tickets/EVN-FND-101.md), [EVN-ONB-102](../../01-onboarding-tenancy-identity/tickets/EVN-ONB-102.md). A blocked prerequisite can be prototyped independently, but its contract and deployment must be approved before claiming this ticket delivered. Service limits, third-party approvals and staffing are evidence requirements, not assumptions that they are available.

## Handover and client acceptance

- [ ] Attach the business demonstration, technical evidence and operating/recovery instructions.
- [ ] Assign a named acceptance owner and agree any deferred criteria with the client in writing.
- [ ] Resolve launch-blocking defects and document accepted residual risks.
- [ ] Client records dated acceptance against the deployed/documented version.

Use [the acceptance protocol](../../../ACCEPTANCE.md) and [the ticket update rules](../../../TICKET_TEMPLATE.md) when changing status.
