# API - source requirement register

Definitions below preserve the supplied document records and continuation bullets. Source IDs are stable; SCF IDs are review-assigned identifiers for the 25 numbered scaffolding rows. Row numbers are extraction locations, not page numbers.

Related: [traceability matrix](../TRACEABILITY.md) | [document provenance](../SOURCES.md).

## API-001

Assigned delivery tickets: [EVN-BIL-043](../modules/09-plans-billing-usage-margin/tickets/EVN-BIL-043.md), [EVN-INT-071](../modules/11-api-connectors-integrations/tickets/EVN-INT-071.md).

**Primary source:** TECH section 19.4 Public API, webhooks and integrations (API); extraction row 1168.

**Source record:** API-001 [P1] MUST expose a versioned REST API (/v1) described by OpenAPI 3.1, used by EverOnn's own frontends (no private back doors), with resource-oriented design, cursor pagination, idempotency keys on POST, consistent error format (RFC 9457 Problem Details), rate limit headers, and SDK generation (TypeScript first).

## API-002

Assigned delivery tickets: [EVN-INT-071](../modules/11-api-connectors-integrations/tickets/EVN-INT-071.md), [EVN-ONB-101](../modules/01-onboarding-tenancy-identity/tickets/EVN-ONB-101.md).

**Primary source:** TECH section 19.4 Public API, webhooks and integrations (API); extraction row 1169.

**Source record:** API-002 [P1] MUST support authentication: OAuth2/OIDC for users; API keys (scoped, hashed at rest, rotatable) and short-lived JWTs for tenant integrations; widget keys scoped to allowed origins.

## API-003

Assigned delivery tickets: [EVN-INT-071](../modules/11-api-connectors-integrations/tickets/EVN-INT-071.md).

**Primary source:** TECH section 19.4 Public API, webhooks and integrations (API); extraction row 1170.

**Source record:** API-003 [P1] MUST deliver outbound webhooks for domain events (for example request.created, call.completed, appointment.booked) with HMAC signatures, retries with exponential backoff, dead-letter queues, replay from the dashboard, and per-tenant delivery logs.

## API-004

Assigned delivery tickets: [EVN-INT-071](../modules/11-api-connectors-integrations/tickets/EVN-INT-071.md).

**Primary source:** TECH section 19.4 Public API, webhooks and integrations (API); extraction row 1171.

**Source record:** API-004 [P1] SHOULD provide native Zapier and Make connectors (or generic webhook triggers plus REST actions) at P1; P2 for listed apps.

## API-005

Assigned delivery tickets: [EVN-INB-008](../modules/08-inbox-contacts-booking-followup/tickets/EVN-INB-008.md), [EVN-INT-049](../modules/11-api-connectors-integrations/tickets/EVN-INT-049.md).

**Primary source:** TECH section 19.4 Public API, webhooks and integrations (API); extraction row 1172.

**Source record:** API-005 [P2] SHOULD provide first integrations: Google Calendar and Microsoft 365 (BKG-001), Google Business Profile, QuickBooks (invoice/customer sync, P3), and one field-service system (BKG-005).

## API-006

Assigned delivery tickets: [EVN-HIL-036](../modules/07-human-operations-live-agent-desk/tickets/EVN-HIL-036.md), [EVN-INB-037](../modules/08-inbox-contacts-booking-followup/tickets/EVN-INB-037.md).

**Primary source:** TECH section 19.4 Public API, webhooks and integrations (API); extraction row 1173.

**Source record:** API-006 [P1] MUST provide realtime channels for the dashboard (WebSocket or SSE) for live call status, inbox updates and escalation alerts.

## API-007

Assigned delivery tickets: [EVN-INT-071](../modules/11-api-connectors-integrations/tickets/EVN-INT-071.md).

**Primary source:** TECH section 19.4 Public API, webhooks and integrations (API); extraction row 1174.

**Source record:** API-007 [P1] MUST publish an API changelog and deprecation policy (minimum 6 months notice for breaking changes).

## API-008

Assigned delivery tickets: [EVN-INT-071](../modules/11-api-connectors-integrations/tickets/EVN-INT-071.md).

**Primary source:** TECH section 19.4 Public API, webhooks and integrations (API); extraction row 1175.

**Source record:** API-008 [P3] MAY provide a partner/marketplace program (OAuth apps, scopes, review process).
