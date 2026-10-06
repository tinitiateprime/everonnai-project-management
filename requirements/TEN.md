# TEN - source requirement register

Definitions below preserve the supplied document records and continuation bullets. Source IDs are stable; SCF IDs are review-assigned identifiers for the 25 numbered scaffolding rows. Row numbers are extraction locations, not page numbers.

Related: [traceability matrix](../TRACEABILITY.md) | [document provenance](../SOURCES.md).

## TEN-001

Assigned delivery tickets: [EVN-HIL-028](../modules/07-human-operations-live-agent-desk/tickets/EVN-HIL-028.md), [EVN-ONB-102](../modules/01-onboarding-tenancy-identity/tickets/EVN-ONB-102.md), [EVN-SEC-063](../modules/15-security-privacy-compliance/tickets/EVN-SEC-063.md).

**Primary source:** TECH section 12.3 Tenancy model requirements; extraction row 766.

**Source record:** TEN-001 [P0] MUST use a shared-schema, tenant_id-keyed model in MariaDB for P1 and P2, with these guarantees:

- every tenant-owned table has tenant_id as the leading column of its primary key or of a unique key, and as the leading column of every tenant-scoped index;

- all data access goes through a tenant-scoped repository layer that injects tenant_id from the request context; raw queries outside this layer are forbidden by lint rules and code review;

- automated cross-tenant isolation tests run in CI and nightly (attempt to read/write tenant B's rows as tenant A through every API route and worker job);

- MariaDB has no native row-level security, so the above compensates; the studio MUST document this trade-off in an ADR.

## TEN-002

Assigned delivery tickets: [EVN-ONB-102](../modules/01-onboarding-tenancy-identity/tickets/EVN-ONB-102.md), [EVN-OPS-072](../modules/18-reliability-deployment-scale/tickets/EVN-OPS-072.md).

**Primary source:** TECH section 12.3 Tenancy model requirements; extraction row 771.

**Source record:** TEN-002 [P1] MUST include tenants.cell_id, tenants.region, tenants.data_residency and tenants.tier columns and a routing map from day one (scaffolding for cells, regional residency and dedicated-schema enterprise tenants).

## TEN-003

Assigned delivery tickets: [EVN-ONB-102](../modules/01-onboarding-tenancy-identity/tickets/EVN-ONB-102.md).

**Primary source:** TECH section 12.3 Tenancy model requirements; extraction row 772.

**Source record:** TEN-003 [P2] SHOULD support schema-per-tenant or database-per-tenant placement for large or regulated tenants without code changes (the repository layer resolves the connection from the routing map).

## TEN-004

Assigned delivery tickets: [EVN-ONB-102](../modules/01-onboarding-tenancy-identity/tickets/EVN-ONB-102.md), [EVN-SEC-063](../modules/15-security-privacy-compliance/tickets/EVN-SEC-063.md).

**Primary source:** TECH section 12.3 Tenancy model requirements; extraction row 773.

**Source record:** TEN-004 [P1] MUST namespace all cache keys, queue names, object-storage paths and search indexes by tenant (t/{tenant_id}/...). Recordings and exports MUST be encrypted with keys derived per tenant (envelope encryption, SEC-005).

## TEN-005

Assigned delivery tickets: [EVN-ONB-102](../modules/01-onboarding-tenancy-identity/tickets/EVN-ONB-102.md), [EVN-WEB-101](../modules/06-website-generation-hosting/tickets/EVN-WEB-101.md).

**Primary source:** TECH section 12.3 Tenancy model requirements; extraction row 774.

**Source record:** TEN-005 [P1] MUST enforce per-tenant quotas and rate limits (API, calls per minute, concurrent calls, SMS per hour, generation jobs) with a noisy-neighbor policy: one tenant MUST NOT be able to starve others (fair queuing in workers).

## TEN-006

Assigned delivery tickets: [EVN-SEC-067](../modules/15-security-privacy-compliance/tickets/EVN-SEC-067.md).

**Primary source:** TECH section 12.3 Tenancy model requirements; extraction row 775.

**Source record:** TEN-006 [P1] MUST support tenant data export (full, machine-readable) and deletion (hard delete plus cryptographic erasure of keys) on request within statutory timelines.

## TEN-007

Assigned delivery tickets: [EVN-ONB-102](../modules/01-onboarding-tenancy-identity/tickets/EVN-ONB-102.md), [EVN-VRT-045](../modules/10-brands-vertical-packs/tickets/EVN-VRT-045.md).

**Primary source:** TECH section 12.3 Tenancy model requirements; extraction row 776.

**Source record:** TEN-007 [P1] MUST record brand_id and vertical_pack_id on every tenant, and run brand isolation tests alongside the tenant isolation tests (TEN-001): users, APIs, emails and pages of one brand MUST NOT expose another brand's data.
