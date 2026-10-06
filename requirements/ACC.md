# ACC - source requirement register

Definitions below preserve the supplied document records and continuation bullets. Source IDs are stable; SCF IDs are review-assigned identifiers for the 25 numbered scaffolding rows. Row numbers are extraction locations, not page numbers.

Related: [traceability matrix](../TRACEABILITY.md) | [document provenance](../SOURCES.md).

## ACC-001

Assigned delivery tickets: [EVN-ONB-101](../modules/01-onboarding-tenancy-identity/tickets/EVN-ONB-101.md).

**Primary source:** TECH section 10.3 Access requirements; extraction row 576.

**Source record:** ACC-001 [P1] MUST enforce authorization in a single policy layer (not scattered in handlers). Every request carries a resolved tenant_id and actor; operator requests additionally carry the operator's client grant (DSK-002).

## ACC-002

Assigned delivery tickets: [EVN-ONB-101](../modules/01-onboarding-tenancy-identity/tickets/EVN-ONB-101.md).

**Primary source:** TECH section 10.3 Access requirements; extraction row 577.

**Source record:** ACC-002 [P1] MUST log every cross-client access by internal staff and operators to an append-only audit log with reason code. Support impersonation MUST show a banner to the client user and be revocable.

## ACC-003

Assigned delivery tickets: [EVN-ONB-101](../modules/01-onboarding-tenancy-identity/tickets/EVN-ONB-101.md).

**Primary source:** TECH section 10.3 Access requirements; extraction row 578.

**Source record:** ACC-003 [P1] MUST support multi-factor authentication for all internal roles and operators and offer it to clients (mandatory for tenant_owner on paid plans at P2).

## ACC-004

Assigned delivery tickets: [EVN-ONB-101](../modules/01-onboarding-tenancy-identity/tickets/EVN-ONB-101.md).

**Primary source:** TECH section 10.3 Access requirements; extraction row 579.

**Source record:** ACC-004 [P2] SHOULD support single sign-on (OIDC or SAML) for internal roles; scaffold client single sign-on for P3.

## ACC-005

Assigned delivery tickets: [EVN-INT-071](../modules/11-api-connectors-integrations/tickets/EVN-INT-071.md).

**Primary source:** TECH section 10.3 Access requirements; extraction row 580.

**Source record:** ACC-005 [P1] MUST issue scoped, revocable API keys per client with rotation and last-used tracking.

## ACC-006

Assigned delivery tickets: [EVN-ONB-101](../modules/01-onboarding-tenancy-identity/tickets/EVN-ONB-101.md).

**Primary source:** TECH section 10.3 Access requirements; extraction row 581.

**Source record:** ACC-006 [P1] MUST support brand-scoped and vertical-scoped roles (brand_admin, vertical_manager, acquisition_manager, migration_specialist) with least privilege; acquisition and migration roles MUST NOT be able to read clients' conversations, recordings or transcripts.
