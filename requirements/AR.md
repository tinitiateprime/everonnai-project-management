# AR - source requirement register

Definitions below preserve the supplied document records and continuation bullets. Source IDs are stable; SCF IDs are review-assigned identifiers for the 25 numbered scaffolding rows. Row numbers are extraction locations, not page numbers.

Related: [traceability matrix](../TRACEABILITY.md) | [document provenance](../SOURCES.md).

## AR-001

Assigned delivery tickets: [EVN-FND-101](../modules/00-foundations-governance/tickets/EVN-FND-101.md).

**Primary source:** TECH section 11.7 Architecture requirements; extraction row 731.

**Source record:** AR-001 [P0] MUST deliver a written architecture decision record (ADR) set covering every "Decision" in this document, before P1 build starts.

## AR-002

Assigned delivery tickets: [EVN-AIQ-101](../modules/03-ai-governance-evaluation/tickets/EVN-AIQ-101.md), [EVN-OWN-075](../modules/20-ownership-handover/tickets/EVN-OWN-075.md).

**Primary source:** TECH section 11.7 Architecture requirements; extraction row 732.

**Source record:** AR-002 [P0] MUST expose every external vendor behind an internal interface: TelephonyProvider, SttProvider, TtsProvider, LlmProvider, SmsProvider, EmailProvider, PaymentProvider, CalendarProvider, GeocodingProvider. Each MUST have at least one alternative implementation stubbed or contract-tested by end of P1 for telephony and LLM, by P2 for the rest.

## AR-003

Assigned delivery tickets: [EVN-OPS-101](../modules/18-reliability-deployment-scale/tickets/EVN-OPS-101.md), [EVN-WEB-101](../modules/06-website-generation-hosting/tickets/EVN-WEB-101.md).

**Primary source:** TECH section 11.7 Architecture requirements; extraction row 733.

**Source record:** AR-003 [P0] MUST use an event-driven backbone: state changes emit versioned domain events (Appendix C) via an outbox table, so that workers, analytics, webhooks and future services consume them without coupling. The outbox pattern MUST be used so events are never lost on commit.

## AR-004

Assigned delivery tickets: [EVN-OPS-068](../modules/18-reliability-deployment-scale/tickets/EVN-OPS-068.md), [EVN-OPS-103](../modules/18-reliability-deployment-scale/tickets/EVN-OPS-103.md).

**Primary source:** TECH section 11.7 Architecture requirements; extraction row 734.

**Source record:** AR-004 [P1] MUST ensure the voice path degrades gracefully: if the control plane, database or a primary vendor is down, calls still get answered with cached configuration and a fallback provider or a safe fallback flow (take a message, text the owner). Test with chaos drills in P2.

## AR-005

Assigned delivery tickets: [EVN-OPS-072](../modules/18-reliability-deployment-scale/tickets/EVN-OPS-072.md), [EVN-OPS-102](../modules/18-reliability-deployment-scale/tickets/EVN-OPS-102.md).

**Primary source:** TECH section 11.7 Architecture requirements; extraction row 735.

**Source record:** AR-005 [P1] MUST be cell-ready: a "cell" is a complete stack (API, workers, DB schema set, Redis, media/voice workers) serving a subset of tenants. tenants.cell_id and a routing map MUST exist from P1 even if only one cell runs. Adding a cell MUST be scriptable (infra as code).

## AR-006

Assigned delivery tickets: [EVN-OPS-101](../modules/18-reliability-deployment-scale/tickets/EVN-OPS-101.md).

**Primary source:** TECH section 11.7 Architecture requirements; extraction row 736.

**Source record:** AR-006 [P1] MUST make every service stateless where possible, with 12-factor configuration; state lives in MariaDB, Redis or object storage.

## AR-007

Assigned delivery tickets: [EVN-OPS-101](../modules/18-reliability-deployment-scale/tickets/EVN-OPS-101.md).

**Primary source:** TECH section 11.7 Architecture requirements; extraction row 737.

**Source record:** AR-007 [P1] MUST version all external APIs (/v1), all events, all agent configuration schemas, and all prompt templates.

## AR-008

Assigned delivery tickets: [EVN-FND-101](../modules/00-foundations-governance/tickets/EVN-FND-101.md), [EVN-OWN-101](../modules/20-ownership-handover/tickets/EVN-OWN-101.md).

**Primary source:** TECH section 11.7 Architecture requirements; extraction row 738.

**Source record:** AR-008 [P0] SHOULD produce a C4 model (context, container, component) and a data-flow diagram per channel, kept in the repo and updated per release.

## AR-009

Assigned delivery tickets: [EVN-OPS-069](../modules/18-reliability-deployment-scale/tickets/EVN-OPS-069.md), [EVN-OPS-102](../modules/18-reliability-deployment-scale/tickets/EVN-OPS-102.md).

**Primary source:** TECH section 11.7 Architecture requirements; extraction row 739.

**Source record:** AR-009 [P1] MUST support blue/green or rolling deploys with zero dropped calls: voice workers drain (finish active calls, accept none) before termination.

## AR-010

Assigned delivery tickets: [EVN-OPS-102](../modules/18-reliability-deployment-scale/tickets/EVN-OPS-102.md).

**Primary source:** TECH section 11.7 Architecture requirements; extraction row 740.

**Source record:** AR-010 [P2] SHOULD provide a path to Kubernetes/OpenShift (manifests or Helm charts and a documented migration plan) while running on Podman/Quadlet at P1.
