# CST - source requirement register

Definitions below preserve the supplied document records and continuation bullets. Source IDs are stable; SCF IDs are review-assigned identifiers for the 25 numbered scaffolding rows. Row numbers are extraction locations, not page numbers.

Related: [traceability matrix](../TRACEABILITY.md) | [document provenance](../SOURCES.md).

## CST-001

Assigned delivery tickets: [EVN-AIQ-101](../modules/03-ai-governance-evaluation/tickets/EVN-AIQ-101.md), [EVN-BIL-042](../modules/09-plans-billing-usage-margin/tickets/EVN-BIL-042.md), [EVN-VOX-101](../modules/04-telephone-voice-language/tickets/EVN-VOX-101.md).

**Primary source:** TECH section 23.6 Unit economics and cost controls; extraction row 1753.

**Source record:** CST-001 [P0] MUST produce a cost model and measured per-minute cost in the P0 spike for at least three vendor combinations, and recommend the default stack by cost and quality.

## CST-002

Assigned delivery tickets: [EVN-BIL-042](../modules/09-plans-billing-usage-margin/tickets/EVN-BIL-042.md), [EVN-OPS-104](../modules/18-reliability-deployment-scale/tickets/EVN-OPS-104.md).

**Primary source:** TECH section 23.6 Unit economics and cost controls; extraction row 1754.

**Source record:** CST-002 [P1] MUST implement per-call, per-tenant and global cost budgets with alerts and circuit breakers (VOX-026), and dashboards for margin by tenant (ADM-004).

## CST-003

Assigned delivery tickets: [EVN-AIQ-101](../modules/03-ai-governance-evaluation/tickets/EVN-AIQ-101.md).

**Primary source:** TECH section 23.6 Unit economics and cost controls; extraction row 1755.

**Source record:** CST-003 [P1] MUST use prompt caching, compact prompts, retrieval limits, and short-turn design to minimize tokens; record tokens and cost per turn.

## CST-004

Assigned delivery tickets: [EVN-OPS-104](../modules/18-reliability-deployment-scale/tickets/EVN-OPS-104.md).

**Primary source:** TECH section 23.6 Unit economics and cost controls; extraction row 1756.

**Source record:** CST-004 [P1] MUST avoid paying for silence: end calls on abandonment quickly, no long dead-air billing, and detect voicemail or automated systems early.

## CST-005

Assigned delivery tickets: [EVN-OPS-104](../modules/18-reliability-deployment-scale/tickets/EVN-OPS-104.md).

**Primary source:** TECH section 23.6 Unit economics and cost controls; extraction row 1757.

**Source record:** CST-005 [P2] SHOULD evaluate self-hosted STT and open-weight LLMs and speech-to-speech models once volume justifies, guided by the eval harness so quality does not regress.

## CST-006

Assigned delivery tickets: [EVN-OPS-104](../modules/18-reliability-deployment-scale/tickets/EVN-OPS-104.md).

**Primary source:** TECH section 23.6 Unit economics and cost controls; extraction row 1758.

**Source record:** CST-006 [P1] MUST set plan-level minute allowances and overage (Decision D-1) and fair-use rules; enforce through BIL-004/005.

## CST-007

Assigned delivery tickets: [EVN-BIL-042](../modules/09-plans-billing-usage-margin/tickets/EVN-BIL-042.md), [EVN-OPS-104](../modules/18-reliability-deployment-scale/tickets/EVN-OPS-104.md).

**Primary source:** TECH section 23.6 Unit economics and cost controls; extraction row 1759.

**Source record:** CST-007 [P2] MUST model, meter and report the cost of operator-handled time per client, vertical and escalation reason (§16.7.5), so that operator add-on pricing (D-1) covers it and escalation rate can be managed as a margin lever.
