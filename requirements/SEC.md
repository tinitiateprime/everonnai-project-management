# SEC - source requirement register

Definitions below preserve the supplied document records and continuation bullets. Source IDs are stable; SCF IDs are review-assigned identifiers for the 25 numbered scaffolding rows. Row numbers are extraction locations, not page numbers.

Related: [traceability matrix](../TRACEABILITY.md) | [document provenance](../SOURCES.md).

## SEC-001

Assigned delivery tickets: [EVN-SEC-102](../modules/15-security-privacy-compliance/tickets/EVN-SEC-102.md).

**Primary source:** TECH section 22.2 Security requirements; extraction row 1641.

**Source record:** SEC-001 [P0] MUST run a secure SDLC: threat model per module (STRIDE plus LLM-specific), OWASP ASVS Level 2 as the target, OWASP Top 10 for LLM Applications mapped to controls (SEC-015), mandatory two-person review, protected branches, signed commits for release branches.

## SEC-002

Assigned delivery tickets: [EVN-SEC-101](../modules/15-security-privacy-compliance/tickets/EVN-SEC-101.md).

**Primary source:** TECH section 22.2 Security requirements; extraction row 1642.

**Source record:** SEC-002 [P1] MUST segment networks by tier, allow only required flows, keep the database and Vault private, and use service-to-service authentication (mTLS with SPIFFE-style identities or signed short-lived service tokens at P1; service mesh optional at P2). Egress from application tiers goes through an allow-listed proxy.

## SEC-003

Assigned delivery tickets: [EVN-ONB-101](../modules/01-onboarding-tenancy-identity/tickets/EVN-ONB-101.md).

**Primary source:** TECH section 22.2 Security requirements; extraction row 1643.

**Source record:** SEC-003 [P1] MUST implement strong identity: passkeys/TOTP MFA, secure session handling (rotating refresh tokens, idle and absolute timeouts, device binding for operators), brute-force and credential-stuffing protection, breached-password checks, and step-up authentication for sensitive actions (billing changes, data export, number release, API key creation).

## SEC-004

Assigned delivery tickets: [EVN-SEC-101](../modules/15-security-privacy-compliance/tickets/EVN-SEC-101.md).

**Primary source:** TECH section 22.2 Security requirements; extraction row 1644.

**Source record:** SEC-004 [P1] MUST encrypt in transit: TLS 1.2+ (1.3 preferred) everywhere including internal links, HSTS, modern cipher suites, SRTP/DTLS for media, and TLS SIP with carriers where supported.

## SEC-005

Assigned delivery tickets: [EVN-SEC-101](../modules/15-security-privacy-compliance/tickets/EVN-SEC-101.md).

**Primary source:** TECH section 22.2 Security requirements; extraction row 1645.

**Source record:** SEC-005 [P1] MUST encrypt at rest with envelope encryption: per-tenant data encryption keys wrapped by a key-encryption key in Vault Transit or a cloud KMS; applied to recordings, transcripts (at least sensitive fields), OAuth tokens and secrets, uploaded files; full-disk encryption on hosts; MariaDB encryption at rest for tablespaces and binlogs. Every ciphertext carries a key_id/version so keys can rotate and per-tenant (BYOK) keys can be introduced later without migration.

## SEC-006

Assigned delivery tickets: [EVN-SEC-101](../modules/15-security-privacy-compliance/tickets/EVN-SEC-101.md).

**Primary source:** TECH section 22.2 Security requirements; extraction row 1646.

**Source record:** SEC-006 [P1] MUST manage secrets with Vault/OpenBao: no secrets in git, images or plaintext environment files; dynamic short-lived database credentials; automated rotation; secret scanning in CI and pre-commit.

## SEC-007

Assigned delivery tickets: [EVN-SEC-101](../modules/15-security-privacy-compliance/tickets/EVN-SEC-101.md).

**Primary source:** TECH section 22.2 Security requirements; extraction row 1647.

**Source record:** SEC-007 [P1] MUST validate and sanitize all input at boundaries; encode output; strict CSP on all web properties; SSRF protection for any server-side fetch of user-supplied URLs (resolve-and-check, block private and link-local ranges, redirect limits, size and time limits); file upload security (type sniffing, size limits, AV scanning, image re-encoding, isolated storage, non-executable serving).

## SEC-008

Assigned delivery tickets: [EVN-BIL-010](../modules/09-plans-billing-usage-margin/tickets/EVN-BIL-010.md), [EVN-SEC-101](../modules/15-security-privacy-compliance/tickets/EVN-SEC-101.md).

**Primary source:** TECH section 22.2 Security requirements; extraction row 1648.

**Source record:** SEC-008 [P1] MUST implement abuse and fraud controls: per-IP, per-session, per-tenant rate limits and quotas; bot management on public forms and the widget; signup velocity and disposable-email checks; premium-rate and geo restrictions; unusual-usage alerts; identity verification (out-of-band OTP) before revealing or changing sensitive data over voice or chat.

## SEC-009

Assigned delivery tickets: [EVN-SEC-102](../modules/15-security-privacy-compliance/tickets/EVN-SEC-102.md).

**Primary source:** TECH section 22.2 Security requirements; extraction row 1649.

**Source record:** SEC-009 [P1] MUST keep an append-only, tamper-evident audit log: hash-chained entries (each includes the hash of the previous), periodic anchoring of the chain head to object storage with object lock (WORM), covering authentication events, permission changes, configuration publishes, staff access to tenant data, HITL actions, exports, deletions and admin actions. Tenants can view their own audit trail (P2).

## SEC-010

Assigned delivery tickets: [EVN-OPS-102](../modules/18-reliability-deployment-scale/tickets/EVN-OPS-102.md), [EVN-OWN-075](../modules/20-ownership-handover/tickets/EVN-OWN-075.md), [EVN-SEC-102](../modules/15-security-privacy-compliance/tickets/EVN-SEC-102.md).

**Primary source:** TECH section 22.2 Security requirements; extraction row 1650.

**Source record:** SEC-010 [P1] MUST secure the software supply chain: minimal base images (Red Hat UBI minimal), pinned image digests, SBOM (Syft/CycloneDX) per build, vulnerability scanning (Trivy or Grype) blocking on critical/high with agreed exceptions, image signing and verification (cosign or Podman signature policy), dependency review and license policy, automated update PRs (Renovate), private registry.

## SEC-011

Assigned delivery tickets: [EVN-SEC-073](../modules/15-security-privacy-compliance/tickets/EVN-SEC-073.md), [EVN-SEC-102](../modules/15-security-privacy-compliance/tickets/EVN-SEC-102.md).

**Primary source:** TECH section 22.2 Security requirements; extraction row 1651.

**Source record:** SEC-011 [P1] MUST run vulnerability management: SLAs (critical within 7 days, high within 30 days, or documented mitigation), monthly RHEL patch cycle with emergency path, weekly scans of images and hosts, an external penetration test before P1 launch and again after P2, and a vulnerability disclosure policy (security.txt), with a bug bounty considered at P3.

## SEC-012

Assigned delivery tickets: [EVN-SEC-102](../modules/15-security-privacy-compliance/tickets/EVN-SEC-102.md).

**Primary source:** TECH section 22.2 Security requirements; extraction row 1652.

**Source record:** SEC-012 [P1] MUST produce structured security logs with correlation ids, centralised and retained per policy, with alerting on suspicious patterns (impossible travel, mass reads, repeated authorization failures, unusual export or impersonation events). Logs are SIEM-ready; fail2ban or equivalent at hosts.

## SEC-013

Assigned delivery tickets: [EVN-OPS-103](../modules/18-reliability-deployment-scale/tickets/EVN-OPS-103.md).

**Primary source:** TECH section 22.2 Security requirements; extraction row 1653.

**Source record:** SEC-013 [P1] MUST protect backups: encrypted, access-separated credentials, an immutable copy, tested restores, and documented DR runbooks (§23.5).

## SEC-014

Assigned delivery tickets: [EVN-QA-101](../modules/19-testing-client-acceptance/tickets/EVN-QA-101.md), [EVN-SEC-063](../modules/15-security-privacy-compliance/tickets/EVN-SEC-063.md).

**Primary source:** TECH section 22.2 Security requirements; extraction row 1654.

**Source record:** SEC-014 [P1] MUST test isolation continuously (TEN-001) and include tenant-isolation cases in the pen-test scope.

## SEC-015

Assigned delivery tickets: [EVN-SEC-101](../modules/15-security-privacy-compliance/tickets/EVN-SEC-101.md).

**Primary source:** TECH section 22.2 Security requirements; extraction row 1655.

**Source record:** SEC-015 [P1] MUST implement AI-specific security mapped to the OWASP LLM Top 10: prompt injection (POL-003), insecure output handling (never execute or render model output unsafely), sensitive information disclosure (redaction, retrieval filters, no secrets in prompts), excessive agency (tool scoping, approvals, per-call tool tokens bound to tenant and conversation), model denial of service (token, time and cost budgets), supply chain (provider vetting, model version pinning), overreliance (uncertainty behaviours, human escalation), and model theft/abuse (no system prompt secrets). Maintain a red-team suite and run it in CI and before every release.

## SEC-016

Assigned delivery tickets: [EVN-SEC-073](../modules/15-security-privacy-compliance/tickets/EVN-SEC-073.md), [EVN-SEC-102](../modules/15-security-privacy-compliance/tickets/EVN-SEC-102.md).

**Primary source:** TECH section 22.2 Security requirements; extraction row 1656.

**Source record:** SEC-016 [P2] MUST follow a compliance roadmap: policy pack (access control, change management, incident response, vendor management, BCP/DR, data classification, secure development), evidence collection automated from CI and infrastructure, SOC 2 Type I readiness by end of P2 and Type II observation thereafter; PCI scope kept at SAQ A; HIPAA controls scaffolded (COM-010). ISO 27001 optional.

## SEC-017

Assigned delivery tickets: [EVN-SEC-101](../modules/15-security-privacy-compliance/tickets/EVN-SEC-101.md).

**Primary source:** TECH section 22.2 Security requirements; extraction row 1657.

**Source record:** SEC-017 [P1] MUST apply privacy by design: data inventory and map, DPIA template, minimization, purpose limitation, retention automation (COM-008), region tags (TEN-002), and a subprocessor register (COM-011).

## SEC-018

Assigned delivery tickets: [EVN-SEC-102](../modules/15-security-privacy-compliance/tickets/EVN-SEC-102.md).

**Primary source:** TECH section 22.2 Security requirements; extraction row 1658.

**Source record:** SEC-018 [P1] MUST define incident response: severity matrix, on-call rotation, runbooks (vendor outage, data exposure, toll fraud spike, prompt-injection incident, credential compromise), breach-notification workflow with statutory deadlines, tenant communication templates, post-incident review process. Run at least one tabletop exercise before launch.
