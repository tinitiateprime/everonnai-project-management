# LT - source requirement register

Definitions below preserve the supplied document records and continuation bullets. Source IDs are stable; SCF IDs are review-assigned identifiers for the 25 numbered scaffolding rows. Row numbers are extraction locations, not page numbers.

Related: [traceability matrix](../TRACEABILITY.md) | [document provenance](../SOURCES.md).

## LT-001

Assigned delivery tickets: [EVN-OPS-104](../modules/18-reliability-deployment-scale/tickets/EVN-OPS-104.md).

**Primary source:** TECH section 23.7 Load and soak testing requirements; extraction row 1761.

**Source record:** LT-001 [P1] MUST simulate concurrent calls end to end (synthetic callers over SIP with TTS audio and noise) at 2x P1 design capacity for 60 minutes with no SLO breach, and report per-stage latency percentiles.

## LT-002

Assigned delivery tickets: [EVN-OPS-072](../modules/18-reliability-deployment-scale/tickets/EVN-OPS-072.md), [EVN-OPS-104](../modules/18-reliability-deployment-scale/tickets/EVN-OPS-104.md).

**Primary source:** TECH section 23.7 Load and soak testing requirements; extraction row 1762.

**Source record:** LT-002 [P2] MUST repeat at 3x projected P2 peak (about 200 concurrent calls) plus a 24-hour soak test to detect leaks.

## LT-003

Assigned delivery tickets: [EVN-OPS-104](../modules/18-reliability-deployment-scale/tickets/EVN-OPS-104.md), [EVN-WEB-018](../modules/06-website-generation-hosting/tickets/EVN-WEB-018.md).

**Primary source:** TECH section 23.7 Load and soak testing requirements; extraction row 1763.

**Source record:** LT-003 [P2] MUST load-test the generation pipeline at 1,000 sites/day with bursts of 300/hour, including provider rate-limit behavior and cost accounting.

## LT-004

Assigned delivery tickets: [EVN-OPS-104](../modules/18-reliability-deployment-scale/tickets/EVN-OPS-104.md).

**Primary source:** TECH section 23.7 Load and soak testing requirements; extraction row 1764.

**Source record:** LT-004 [P2] MUST load-test the API and inbox with 100,000 conversations per tenant on the largest tenant profile, and 10,000 tenants of synthetic data.

## LT-005

Assigned delivery tickets: [EVN-OPS-103](../modules/18-reliability-deployment-scale/tickets/EVN-OPS-103.md).

**Primary source:** TECH section 23.7 Load and soak testing requirements; extraction row 1766.

**Source record:** LT-005 [P1] MUST run chaos scenarios from §23.5 in staging during load tests.

## LT-006

Assigned delivery tickets: [EVN-OPS-104](../modules/18-reliability-deployment-scale/tickets/EVN-OPS-104.md).

**Primary source:** TECH section 23.7 Load and soak testing requirements; extraction row 1765.

**Source record:** LT-006 [P2] MUST load-test the Live Agent Desk with 300 concurrent operator sessions, 100 offers per minute, simultaneous acceptance races, and forced reconnects, verifying the desk performance targets in §16.7.4.
