# MIG - source requirement register

Definitions below preserve the supplied document records and continuation bullets. Source IDs are stable; SCF IDs are review-assigned identifiers for the 25 numbered scaffolding rows. Row numbers are extraction locations, not page numbers.

Related: [traceability matrix](../TRACEABILITY.md) | [document provenance](../SOURCES.md).

## MIG-001

Assigned delivery tickets: [EVN-MIG-056](../modules/13-customer-migration-offboarding/tickets/EVN-MIG-056.md).

**Primary source:** TECH section 19.8 Migration (MIG); extraction row 1225.

**Source record:** MIG-001 [P1] MUST create a migration project for each switching client, recording the incumbent and an inventory of assets: domain and DNS, email hosting, site content and images, forms, client portal or documents, customer lists, phone numbers and call-tracking numbers, Google Business Profile and ordering or reservation links, and integrations; the owner's authorization for each; status per asset; timeline; risks; and the rollback plan.

## MIG-002

Assigned delivery tickets: [EVN-MIG-056](../modules/13-customer-migration-offboarding/tickets/EVN-MIG-056.md).

**Primary source:** TECH section 19.8 Migration (MIG); extraction row 1226.

**Source record:** MIG-002 [P1] MUST support content import from the client's own existing public site (respecting robots directives and the incumbent's terms): pages, text, images (with a rights check), services, hours, FAQs, forms and structured data are mapped to the Site Spec, with a URL map for redirects, and reviewed by the owner. The incumbent's proprietary templates, code and licensed media are never copied.

## MIG-003

Assigned delivery tickets: [EVN-MIG-056](../modules/13-customer-migration-offboarding/tickets/EVN-MIG-056.md), [EVN-MIG-057](../modules/13-customer-migration-offboarding/tickets/EVN-MIG-057.md).

**Primary source:** TECH section 19.8 Migration (MIG); extraction row 1227.

**Source record:** MIG-003 [P1] MUST provide a domain workflow: verify who is the registrant and who controls the registrar account; guide the owner through unlocking the domain and obtaining the authorization code, or through repointing DNS where transfer is not needed; copy mail and verification records before any change; confirm that email continues; issue certificates on the new host; cut over only after the checks pass; roll back within a stated time if a check fails.

## MIG-004

Assigned delivery tickets: [EVN-MIG-056](../modules/13-customer-migration-offboarding/tickets/EVN-MIG-056.md).

**Primary source:** TECH section 19.8 Migration (MIG); extraction row 1228.

**Source record:** MIG-004 [P1] MUST support a parallel run and cut-over: the new site and front desk run on a staging address and, where safe, in shadow (calls still reach the old routing) before a scheduled cut-over window; post-cut-over checks cover forms, chat, call routing, tracking, sitemap and email; a hypercare period follows.

## MIG-005

Assigned delivery tickets: [EVN-MIG-056](../modules/13-customer-migration-offboarding/tickets/EVN-MIG-056.md).

**Primary source:** TECH section 19.8 Migration (MIG); extraction row 1229.

**Source record:** MIG-005 [P1] MUST preserve phone continuity: set up and verify forwarding so that no call is missed during the change; plan what happens to incumbent-owned call-tracking numbers (replace, forward or, from P2, port); confirm numbers and routing before the incumbent service is ended.

## MIG-006

Assigned delivery tickets: [EVN-MIG-057](../modules/13-customer-migration-offboarding/tickets/EVN-MIG-057.md).

**Primary source:** TECH section 19.8 Migration (MIG); extraction row 1230.

**Source record:** MIG-006 [P1] MUST record the incumbent contract: term, renewal date, notice requirement, early-termination fee and the customer's confirmation. The platform schedules cut-over around notice dates, never cancels or instructs cancellation on the client's behalf without written authorization, and supplies a cancellation-notice template for the client to send.

## MIG-007

Assigned delivery tickets: [EVN-MIG-056](../modules/13-customer-migration-offboarding/tickets/EVN-MIG-056.md).

**Primary source:** TECH section 19.8 Migration (MIG); extraction row 1231.

**Source record:** MIG-007 [P1] MUST migrate client data only through client-authorized exports (for example accountants' portal documents, patient forms, order history, customer lists), under the vertical's compliance profile, with counts and checksums verified and the source retained until the client signs off.

## MIG-008

Assigned delivery tickets: [EVN-MIG-056](../modules/13-customer-migration-offboarding/tickets/EVN-MIG-056.md).

**Primary source:** TECH section 19.8 Migration (MIG); extraction row 1232.

**Source record:** MIG-008 [P1] SHOULD preserve search and listing value: redirect map, titles and metadata, structured data, and tasks to update Google Business Profile and directory links (including ordering and reservation links).

## MIG-009

Assigned delivery tickets: [EVN-ANL-058](../modules/16-business-value-analytics/tickets/EVN-ANL-058.md).

**Primary source:** TECH section 19.8 Migration (MIG); extraction row 1233.

**Source record:** MIG-009 [P2] SHOULD report migration metrics (time to cut-over, defects, rollbacks, support contacts in the first 30 days) by target and feed them back into the playbooks.

## MIG-010

Assigned delivery tickets: [EVN-ACQ-050](../modules/12-customer-acquisition-claims/tickets/EVN-ACQ-050.md).

**Primary source:** TECH section 19.8 Migration (MIG); extraction row 1234.

**Source record:** MIG-010 [P1] MUST hold migration playbooks as data (steps, checks, templates, known incumbent quirks), linked from the target registry (ACQ-001) and selected automatically when a prospect's incumbent is known.
