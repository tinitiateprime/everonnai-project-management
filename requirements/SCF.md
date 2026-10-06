# SCF - source requirement register

Definitions below preserve the supplied document records and continuation bullets. Source IDs are stable; SCF IDs are review-assigned identifiers for the 25 numbered scaffolding rows. Row numbers are extraction locations, not page numbers.

Related: [traceability matrix](../TRACEABILITY.md) | [document provenance](../SOURCES.md).

## SCF-001

Assigned delivery tickets: [EVN-ONB-102](../modules/01-onboarding-tenancy-identity/tickets/EVN-ONB-102.md).

**Primary source:** TECH section 22.3 Scaffolding checklist; extraction row 1662.

**Source record:** 1 | tenant_id first in every key + tenant-scoped repository layer + isolation tests | Dedicated schema or database per tenant; regulated and enterprise tenants

## SCF-002

Assigned delivery tickets: [EVN-ONB-102](../modules/01-onboarding-tenancy-identity/tickets/EVN-ONB-102.md).

**Primary source:** TECH section 22.3 Scaffolding checklist; extraction row 1663.

**Source record:** 2 | cell_id, region, data_residency columns and a routing map; scripted cell creation | Multiple cells for capacity; EU or regional data residency; blast-radius reduction

## SCF-003

Assigned delivery tickets: [EVN-OPS-101](../modules/18-reliability-deployment-scale/tickets/EVN-OPS-101.md).

**Primary source:** TECH section 22.3 Scaffolding checklist; extraction row 1664.

**Source record:** 3 | Transactional outbox and versioned domain events | Kafka-class bus, analytics warehouse, partner webhooks, agency integrations

## SCF-004

Assigned delivery tickets: [EVN-AIQ-101](../modules/03-ai-governance-evaluation/tickets/EVN-AIQ-101.md).

**Primary source:** TECH section 22.3 Scaffolding checklist; extraction row 1665.

**Source record:** 4 | Provider interfaces (Telephony, Stt, Tts, Llm, Sms, Email, Payment, Calendar, Geocoding, Fsm) with contract tests and a second implementation | Vendor swaps for cost/quality/outage; multi-carrier routing; on-prem models

## SCF-005

Assigned delivery tickets: [EVN-BIL-040](../modules/09-plans-billing-usage-margin/tickets/EVN-BIL-040.md).

**Primary source:** TECH section 22.3 Scaffolding checklist; extraction row 1666.

**Source record:** 5 | Plans and entitlements as data; metering events with idempotency keys | New plans, usage pricing, outcome pricing, agencies, marketplace

## SCF-006

Assigned delivery tickets: [EVN-SEC-063](../modules/15-security-privacy-compliance/tickets/EVN-SEC-063.md).

**Primary source:** TECH section 22.3 Scaffolding checklist; extraction row 1667.

**Source record:** 6 | Consent ledger and fail-closed sending guard | Marketing and outbound campaigns; HIPAA mode; regulatory audits

## SCF-007

Assigned delivery tickets: [EVN-SEC-102](../modules/15-security-privacy-compliance/tickets/EVN-SEC-102.md).

**Primary source:** TECH section 22.3 Scaffolding checklist; extraction row 1668.

**Source record:** 7 | Hash-chained audit log with WORM anchoring | SOC 2 evidence, tenant-visible audit, forensic investigations

## SCF-008

Assigned delivery tickets: [EVN-SEC-101](../modules/15-security-privacy-compliance/tickets/EVN-SEC-101.md).

**Primary source:** TECH section 22.3 Scaffolding checklist; extraction row 1669.

**Source record:** 8 | Envelope encryption with key ids/versions and per-tenant DEKs | BYOK/HYOK for enterprise; crypto-erasure on deletion; key rotation at scale

## SCF-009

Assigned delivery tickets: [EVN-SEC-065](../modules/15-security-privacy-compliance/tickets/EVN-SEC-065.md).

**Primary source:** TECH section 22.3 Scaffolding checklist; extraction row 1670.

**Source record:** 9 | compliance_profile on tenants and jurisdiction tables as data | HIPAA, state-specific rules, new countries

## SCF-010

Assigned delivery tickets: [EVN-HIL-024](../modules/07-human-operations-live-agent-desk/tickets/EVN-HIL-024.md).

**Primary source:** TECH section 22.3 Scaffolding checklist; extraction row 1671.

**Source record:** 10 | Operator org and identity model (internal and external orgs) | BPO/partner operator pools; follow-the-sun coverage

## SCF-011

Assigned delivery tickets: [EVN-HIL-024](../modules/07-human-operations-live-agent-desk/tickets/EVN-HIL-024.md).

**Primary source:** TECH section 22.3 Scaffolding checklist; extraction row 1672.

**Source record:** 11 | EscalationRouter, OperatorDirectory, ShiftCalendar interfaces with a simple P1 implementation | Skills-based routing, workforce management, overflow pools

## SCF-012

Assigned delivery tickets: [EVN-OPS-102](../modules/18-reliability-deployment-scale/tickets/EVN-OPS-102.md).

**Primary source:** TECH section 22.3 Scaffolding checklist; extraction row 1673.

**Source record:** 12 | OpenFeature-compatible flags, canary and kill switches | Experiments, staged rollouts, instant mitigation

## SCF-013

Assigned delivery tickets: [EVN-INT-071](../modules/11-api-connectors-integrations/tickets/EVN-INT-071.md).

**Primary source:** TECH section 22.3 Scaffolding checklist; extraction row 1674.

**Source record:** 13 | API versioning, scopes, OAuth-ready client model | Partner apps, marketplace, agency access

## SCF-014

Assigned delivery tickets: [EVN-SEC-101](../modules/15-security-privacy-compliance/tickets/EVN-SEC-101.md).

**Primary source:** TECH section 22.3 Scaffolding checklist; extraction row 1675.

**Source record:** 14 | Service-to-service auth via signed tokens with identity claims | mTLS service mesh, zero-trust networking

## SCF-015

Assigned delivery tickets: [EVN-KNW-102](../modules/02-knowledge-agent-configuration/tickets/EVN-KNW-102.md).

**Primary source:** TECH section 22.3 Scaffolding checklist; extraction row 1676.

**Source record:** 15 | Config and prompt versioning with immutable published versions | A/B testing, canary prompts, instant rollback, audit of behavior changes

## SCF-016

Assigned delivery tickets: [EVN-ONB-101](../modules/01-onboarding-tenancy-identity/tickets/EVN-ONB-101.md).

**Primary source:** TECH section 22.3 Scaffolding checklist; extraction row 1677.

**Source record:** 16 | Role/permission model with attribute hooks (location, tenant tier, time-boxed grants) | Custom roles, delegated admin, tenant SSO, ABAC

## SCF-017

Assigned delivery tickets: [EVN-BIL-043](../modules/09-plans-billing-usage-margin/tickets/EVN-BIL-043.md).

**Primary source:** TECH section 22.3 Scaffolding checklist; extraction row 1678.

**Source record:** 17 | Quotas and rate-limit framework keyed by tenant, plan, route and provider | Abuse control at scale, fair-use enforcement, tiered API limits

## SCF-018

Assigned delivery tickets: [EVN-OPS-104](../modules/18-reliability-deployment-scale/tickets/EVN-OPS-104.md).

**Primary source:** TECH section 22.3 Scaffolding checklist; extraction row 1679.

**Source record:** 18 | Trace ids and tenant/cost labels on every log, event and span | SLOs per tenant, cost attribution, faster incident forensics

## SCF-019

Assigned delivery tickets: [EVN-VOX-006](../modules/04-telephone-voice-language/tickets/EVN-VOX-006.md).

**Primary source:** TECH section 22.3 Scaffolding checklist; extraction row 1680.

**Source record:** 19 | i18n keys and locale-aware formatting in all UIs, prompts and templates | New languages and markets without refactor

## SCF-020

Assigned delivery tickets: [EVN-BIL-101](../modules/09-plans-billing-usage-margin/tickets/EVN-BIL-101.md).

**Primary source:** TECH section 22.3 Scaffolding checklist; extraction row 1681.

**Source record:** 20 | Idempotency keys and exactly-once-in-effect patterns for payments, metering, SMS | Safe retries, replays, reconciliation and billing accuracy

## SCF-021

Assigned delivery tickets: [EVN-SEC-101](../modules/15-security-privacy-compliance/tickets/EVN-SEC-101.md).

**Primary source:** TECH section 22.3 Scaffolding checklist; extraction row 1682.

**Source record:** 21 | Data classification tags in schema registry and redaction hooks | DLP, privacy tooling, safe analytics and eval datasets

## SCF-022

Assigned delivery tickets: [EVN-OPS-102](../modules/18-reliability-deployment-scale/tickets/EVN-OPS-102.md).

**Primary source:** TECH section 22.3 Scaffolding checklist; extraction row 1683.

**Source record:** 22 | Infra as code for every environment (Ansible/OpenTofu) and Kubernetes-compatible packaging | Multi-region, cloud burst, OpenShift migration, DR automation

## SCF-023

Assigned delivery tickets: [EVN-WEB-102](../modules/06-website-generation-hosting/tickets/EVN-WEB-102.md).

**Primary source:** TECH section 22.3 Scaffolding checklist; extraction row 1684.

**Source record:** 23 | Site Spec schema and component versioning | Bulk template upgrades, new verticals, white-label themes

## SCF-024

Assigned delivery tickets: [EVN-AIQ-101](../modules/03-ai-governance-evaluation/tickets/EVN-AIQ-101.md).

**Primary source:** TECH section 22.3 Scaffolding checklist; extraction row 1685.

**Source record:** 24 | Vendor health checks and circuit breakers with per-tenant fallback modes | Automated failover, graceful degradation at scale

## SCF-025

Assigned delivery tickets: [EVN-HIL-036](../modules/07-human-operations-live-agent-desk/tickets/EVN-HIL-036.md).

**Primary source:** TECH section 22.3 Scaffolding checklist; extraction row 1686.

**Source record:** 25 | Client desk profile, authority matrix and operator grants as data; line-based routing key | Dedicated operator teams per client, partner operator pools, premium human-service tiers
