# ADM - source requirement register

Definitions below preserve the supplied document records and continuation bullets. Source IDs are stable; SCF IDs are review-assigned identifiers for the 25 numbered scaffolding rows. Row numbers are extraction locations, not page numbers.

Related: [traceability matrix](../TRACEABILITY.md) | [document provenance](../SOURCES.md).

## ADM-001

Assigned delivery tickets: [EVN-ADM-070](../modules/17-admin-backoffice/tickets/EVN-ADM-070.md).

**Primary source:** TECH section 19.3 Admin back-office (ADM); extraction row 1158.

**Source record:** ADM-001 [P1] MUST provide an internal admin app (separate deployment and hostname, SSO plus MFA, IP-restricted) to search tenants; view state, config versions, numbers, usage and cost; replay and inspect conversations with reasons; manage plans and entitlements; suspend, unsuspend and close tenants; run support impersonation (ACC-002).

## ADM-002

Assigned delivery tickets: [EVN-ADM-070](../modules/17-admin-backoffice/tickets/EVN-ADM-070.md), [EVN-BIL-043](../modules/09-plans-billing-usage-margin/tickets/EVN-BIL-043.md).

**Primary source:** TECH section 19.3 Admin back-office (ADM); extraction row 1159.

**Source record:** ADM-002 [P1] MUST provide feature flags and staged rollouts (per tenant, per plan, percentage), a kill switch per capability and per vendor, and audit of flag changes. Flags are evaluated via an OpenFeature-compatible interface.

## ADM-003

Assigned delivery tickets: [EVN-ADM-070](../modules/17-admin-backoffice/tickets/EVN-ADM-070.md), [EVN-AIQ-076](../modules/03-ai-governance-evaluation/tickets/EVN-AIQ-076.md).

**Primary source:** TECH section 19.3 Admin back-office (ADM); extraction row 1160.

**Source record:** ADM-003 [P1] MUST provide prompt and policy management: versioned platform policy and vertical templates with diff, review and approval, staged rollout with canary tenants, automated eval gate (§24.5), and instant rollback.

## ADM-004

Assigned delivery tickets: [EVN-BIL-042](../modules/09-plans-billing-usage-margin/tickets/EVN-BIL-042.md).

**Primary source:** TECH section 19.3 Admin back-office (ADM); extraction row 1161.

**Source record:** ADM-004 [P1] MUST provide cost and margin dashboards per tenant, per plan and per vendor, with alerting on abnormal spend.

## ADM-005

Assigned delivery tickets: [EVN-ADM-070](../modules/17-admin-backoffice/tickets/EVN-ADM-070.md).

**Primary source:** TECH section 19.3 Admin back-office (ADM); extraction row 1162.

**Source record:** ADM-005 [P1] MUST provide number inventory management (search, buy, assign, release, port status), and compliance registration status (A2P 10DLC, toll-free verification).

## ADM-006

Assigned delivery tickets: [EVN-ADM-070](../modules/17-admin-backoffice/tickets/EVN-ADM-070.md).

**Primary source:** TECH section 19.3 Admin back-office (ADM); extraction row 1163.

**Source record:** ADM-006 [P2] SHOULD provide bulk tenant operations with dry-run and audit.

## ADM-007

Assigned delivery tickets: [EVN-ADM-070](../modules/17-admin-backoffice/tickets/EVN-ADM-070.md), [EVN-OPS-068](../modules/18-reliability-deployment-scale/tickets/EVN-OPS-068.md).

**Primary source:** TECH section 19.3 Admin back-office (ADM); extraction row 1164.

**Source record:** ADM-007 [P1] MUST provide an incident toolkit: broadcast banner to tenants, per-tenant fallback switch (route all calls to owner or to message-capture), and vendor failover controls.

## ADM-008

Assigned delivery tickets: [EVN-ADM-070](../modules/17-admin-backoffice/tickets/EVN-ADM-070.md).

**Primary source:** TECH section 19.3 Admin back-office (ADM); extraction row 1165.

**Source record:** ADM-008 [P1] MUST provide administration for brands, vertical packs, targets and prospects: create and configure brands and packs; manage the target registry and the claims register; view the pipeline and migration boards; roles limited to acquisition and vertical staff (ACC-006).

## ADM-009

Assigned delivery tickets: [EVN-VRT-047](../modules/10-brands-vertical-packs/tickets/EVN-VRT-047.md).

**Primary source:** TECH section 19.3 Admin back-office (ADM); extraction row 1166.

**Source record:** ADM-009 [P1] MUST provide the readiness-gate console (VRT-005) showing checklist status, approvers and evidence.
