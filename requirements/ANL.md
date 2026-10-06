# ANL - source requirement register

Definitions below preserve the supplied document records and continuation bullets. Source IDs are stable; SCF IDs are review-assigned identifiers for the 25 numbered scaffolding rows. Row numbers are extraction locations, not page numbers.

Related: [traceability matrix](../TRACEABILITY.md) | [document provenance](../SOURCES.md).

## ANL-001

Assigned delivery tickets: [EVN-ANL-039](../modules/16-business-value-analytics/tickets/EVN-ANL-039.md).

**Primary source:** TECH section 19.2 Analytics and reporting (ANL); extraction row 1153.

**Source record:** ANL-001 [P1] MUST provide an owner dashboard: calls answered, after-hours calls captured, requests created, booked, estimated recovered revenue, average response time, top questions, knowledge gaps, missed-call rate before/after EverOnn (when baseline data exists), and a weekly emailed digest.

## ANL-002

Assigned delivery tickets: [EVN-ANL-039](../modules/16-business-value-analytics/tickets/EVN-ANL-039.md), [EVN-OPS-101](../modules/18-reliability-deployment-scale/tickets/EVN-OPS-101.md).

**Primary source:** TECH section 19.2 Analytics and reporting (ANL); extraction row 1154.

**Source record:** ANL-002 [P1] MUST provide a platform analytics pipeline: events (Appendix C) flow to an analytics store for internal reporting. P1 MAY use MariaDB read replicas and materialized summary tables; P2 SHOULD introduce a columnar store (for example ClickHouse or MariaDB ColumnStore, subject to the RHEL/MariaDB exception process) fed by the outbox stream.

## ANL-003

Assigned delivery tickets: [EVN-ANL-039](../modules/16-business-value-analytics/tickets/EVN-ANL-039.md), [EVN-OPS-104](../modules/18-reliability-deployment-scale/tickets/EVN-OPS-104.md).

**Primary source:** TECH section 19.2 Analytics and reporting (ANL); extraction row 1155.

**Source record:** ANL-003 [P1] MUST provide quality dashboards: latency per stage, guardrail hits, escalation rates and reasons, QA scores, eval pass rates by agent version, cost per call and per tenant, and vendor error rates.

## ANL-004

Assigned delivery tickets: [EVN-ANL-039](../modules/16-business-value-analytics/tickets/EVN-ANL-039.md), [EVN-ANL-058](../modules/16-business-value-analytics/tickets/EVN-ANL-058.md).

**Primary source:** TECH section 19.2 Analytics and reporting (ANL); extraction row 1156.

**Source record:** ANL-004 [P2] SHOULD provide cohort and funnel analysis for onboarding (claim → verified → live → first call → first booked job → paid).
