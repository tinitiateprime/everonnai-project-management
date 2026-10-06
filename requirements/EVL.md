# EVL - source requirement register

Definitions below preserve the supplied document records and continuation bullets. Source IDs are stable; SCF IDs are review-assigned identifiers for the 25 numbered scaffolding rows. Row numbers are extraction locations, not page numbers.

Related: [traceability matrix](../TRACEABILITY.md) | [document provenance](../SOURCES.md).

## EVL-001

Assigned delivery tickets: [EVN-AIQ-103](../modules/03-ai-governance-evaluation/tickets/EVN-AIQ-103.md).

**Primary source:** TECH section 24.5 AI evaluation and safety framework; extraction row 1793.

**Source record:** EVL-001 [P0] MUST deliver an eval harness in the repo that can run (a) text-level simulations (fast, in CI on every prompt/policy/model change) and (b) audio-level simulations (synthetic caller over SIP, nightly and pre-release).

## EVL-002

Assigned delivery tickets: [EVN-AIQ-103](../modules/03-ai-governance-evaluation/tickets/EVN-AIQ-103.md).

**Primary source:** TECH section 24.5 AI evaluation and safety framework; extraction row 1794.

**Source record:** EVL-002 [P1] MUST ship versioned datasets per vertical: at least 150 scripted scenarios for the first vertical (locksmith) by P1 exit and 500 or more per vertical by P2, covering: happy paths; ambiguous or rambling callers; noisy/mis-transcribed speech; Spanish and code-switching; emergencies and safety triggers; price traps ("just give me a number"); out-of-scope requests; angry callers; repeated "I want a person"; prompt-injection and social-engineering attempts; tool failures; calendar conflicts; and returning callers.

## EVL-003

Assigned delivery tickets: [EVN-AIQ-103](../modules/03-ai-governance-evaluation/tickets/EVN-AIQ-103.md).

**Primary source:** TECH section 24.5 AI evaluation and safety framework; extraction row 1795.

**Source record:** EVL-003 [P1] MUST measure: task success and outcome correctness, slot-fill accuracy and extraction F1, correct-escalation rate and false-escalation rate, hallucination rate (claims unsupported by profile or KB), guardrail violation rate (critical/major/minor), tool-call correctness, conversation length and turns, tone/brand adherence, and latency and cost per scenario.

## EVL-004

Assigned delivery tickets: [EVN-AIQ-103](../modules/03-ai-governance-evaluation/tickets/EVN-AIQ-103.md).

**Primary source:** TECH section 24.5 AI evaluation and safety framework; extraction row 1796.

**Source record:** EVL-004 [P1] MUST use LLM-as-judge only with calibration to human labels (inter-rater agreement reported; judge prompts versioned); safety-critical checks use deterministic rules where possible.

## EVL-005

Assigned delivery tickets: [EVN-AIQ-076](../modules/03-ai-governance-evaluation/tickets/EVN-AIQ-076.md), [EVN-AIQ-103](../modules/03-ai-governance-evaluation/tickets/EVN-AIQ-103.md).

**Primary source:** TECH section 24.5 AI evaluation and safety framework; extraction row 1797.

**Source record:** EVL-005 [P1] MUST enforce release gates: any change to models, prompts, policies, playbooks, retrieval settings or providers MUST pass (a) zero critical safety failures on the safety set, (b) no statistically significant regression on core metrics, and (c) cost and latency budgets. Gate results are attached to the change record (ADM-003).

## EVL-006

Assigned delivery tickets: [EVN-AIQ-103](../modules/03-ai-governance-evaluation/tickets/EVN-AIQ-103.md).

**Primary source:** TECH section 24.5 AI evaluation and safety framework; extraction row 1798.

**Source record:** EVL-006 [P1] MUST support shadow and canary evaluation in production: run a candidate agent version against a sample of live traffic offline (shadow) or on a small tenant subset (canary) before full rollout, with automatic rollback triggers.

## EVL-007

Assigned delivery tickets: [EVN-AIQ-103](../modules/03-ai-governance-evaluation/tickets/EVN-AIQ-103.md).

**Primary source:** TECH section 24.5 AI evaluation and safety framework; extraction row 1799.

**Source record:** EVL-007 [P2] MUST run continuous online quality monitoring: sampled QA (HIL-009), drift detection on intents, escalation rates, sentiment and guardrail hits, and alerting on regressions after provider model updates (pin model versions; test before upgrading).

## EVL-008

Assigned delivery tickets: [EVN-AIQ-103](../modules/03-ai-governance-evaluation/tickets/EVN-AIQ-103.md).

**Primary source:** TECH section 24.5 AI evaluation and safety framework; extraction row 1800.

**Source record:** EVL-008 [P2] MUST feed owner corrections and operator resolutions into datasets (HIL-010) with anonymization and consent (COM-007).

## EVL-009

Assigned delivery tickets: [EVN-AIQ-103](../modules/03-ai-governance-evaluation/tickets/EVN-AIQ-103.md).

**Primary source:** TECH section 24.5 AI evaluation and safety framework; extraction row 1801.

**Source record:** EVL-009 [P1] MUST maintain a red-team suite (SEC-015) executed on every release, with a report that a human reviews before production promotion.

## EVL-010

Assigned delivery tickets: [EVN-AIQ-103](../modules/03-ai-governance-evaluation/tickets/EVN-AIQ-103.md), [EVN-VRT-047](../modules/10-brands-vertical-packs/tickets/EVN-VRT-047.md).

**Primary source:** TECH section 24.5 AI evaluation and safety framework; extraction row 1802.

**Source record:** EVL-010 [P1] MUST maintain an evaluation dataset per vertical pack (at least 150 scenarios at pack launch and 500 by P2), including vertical-specific safety cases: allergy and dietary questions, clinical advice requests, legal advice and conflicts, coverage and claims-status questions, tax-return details and payment-card disclosure. A pack cannot pass the readiness gate below its thresholds (VRT-005).
