# Technical deliverables and business mapping

Every ticket has the requested dimensions: **technical component, DB, UI, Translate (business-to-technical mapping), backend services, AI component, testing/QA and deployment**. Planning entity/service names below are proposed contracts, not claims of existing production tables or endpoints.

## Architecture disposition

| Concern | Inspected implementation | Source production direction | Delivery decision |
| --- | --- | --- | --- |
| Web/control plane | Next.js App Router/React/TypeScript and scoped server APIs | Next/React frontend; NestJS/Fastify control-plane boundaries | Preserve useful modular services; agree deployment/service split |
| Database | Supabase-hosted PostgreSQL private `everonn` relational schema; alternate local/Blob stores | MariaDB, tenant-first repositories, schema/data contracts and cell routing | D-2 exception or reviewed migration; never run unapproved destructive DDL |
| Infrastructure | Amplify build/hosting adapters and signed scheduled usage operations | RHEL, Podman/Quadlet, SELinux/firewalld, Valkey/Redis, S3-compatible storage and two failure domains | D-8 plus architecture exception; no Java/Tomcat requirement is introduced |
| Identity | Custom scrypt/opaque-session identities and role checks | Keycloak or approved provider, MFA/SSO/operator model | D-5; safe account/session migration if changing |
| Voice | Managed ElevenLabs browser sessions, Gemini text | Real SIP/PSTN with two carriers; LiveKit Agents/Pipecat-style runtime or approved managed pilot | D-7/D-15; measured proof before vendor/topology commitment |
| AI | Gemini remains the user's current direction; approved skills/context and validation | Portable provider interfaces/task tiers, typed tools, fallbacks, evaluations and budgets | Keep existing choice while contract-testing alternatives; do not claim a model is best without evidence |
| Website renderer | Original AI-authored HTML/CSS, safe parsing/scoping, platform-owned interactions | SiteSpec schema, versioned section components/static bundles | Explicit renderer ADR; reconcile original design freedom with release/upgrade safety |
| Long-running work | Synchronous website batching and specialised usage outbox | General events, outbox, durable jobs/timers, cancellation/resume and fair queues | OPS-101/WEB-101; progress heartbeat does not persist lost work |
| Operators | Basic handoff state only | Grant-scoped multi-client Live Agent Desk, authoritative offers, private briefing/bridge, staffing | HIL/DSK module; owner fallback is not a guaranteed staffed service |

## Technical component contracts

- Tenant/identity/config boundaries must carry tenant, role, published version, correlation ID and explicit entitlement/authority.
- Request/response, tool and domain-event schemas must be versioned. Proposed public APIs use `/v1`; current internal routes do not prove a public API product.
- Side effects require idempotency keys, persisted outcomes, uncertain-result handling and reconciliation. Usage's existing specialised outbox does not satisfy all domain events.
- Provider interfaces cover Telephony, STT, TTS, LLM, SMS, Email, Payment, Calendar, Geocoding and field-service connectors, with contract tests and recorded alternatives.
- A published business/knowledge/agent configuration must remain stable during an active conversation; draft edits and website preference memory are separate state.

## DB inventory - existing versus planned

| Module | Existing persistence | Proposed/extended records per tickets |
| --- | --- | --- |
| FND | Private everonn schema, guarded migrations and shape-preserving stores | ADR register and migration inventory; no unapproved production DDL |
| ONB | workspaces, business_profiles, users, auth_sessions, invitations, team_members, record_revisions | ownership_proofs, claims, approval_events; sandbox_sessions, test_calls, draft_versions; users, sessions, recovery_tokens, identity_bindings; tenant placement, brand/location references and published JSON schemas |
| KNW | business_profiles, business_services, knowledge_items; scoped website aiMemory in workspace payload | profile_versions, kb_items, kb_approvals; agent_config_versions, config_publications; message_provenance, corrections, knowledge_gaps; knowledge_sources, chunks, indexes, approvals, gap records; profile_versions, kb_versions, agent_versions, publications |
| AIQ | Skill version/digest traces, generation metadata, scoped preferences and usage records | policy_versions, guardrail_events, knowledge_gaps; agent_versions, eval_runs, rollout_assignments; provider_config, task_routes, provider_health, budget records; tool_definitions, grants, action_receipts; eval_datasets, eval_runs, metrics, rollout gates; skill_registry, memory scopes, immutable instruction versions |
| VOX | conversations, conversation_messages, contacts, leads; browser voice usage sessions | calls, lines, number_routes, routing_tests; requests, request_fields, transcripts, contacts; call_turns, stage_latency, provider_health; emergency_rules, escalations, acknowledgements; language_preferences, voice_profiles, operator_skills; numbers, forwarding_tests, port_requests; call_spike_runs, latency/cost results, topology evidence |
| CHT | conversations, messages, contacts, leads and scoped visitor/provider sessions | visitor_sessions, threads, messages, attachments; sms_threads, sms_messages, consents, suppressions; widget_keys, origin_grants, visitor_sessions |
| WEB | website_projects and immutable draft/live release snapshots in scoped workspace records | form_submissions, widget_origins, consent_events; generation_jobs, draft_sites, preview_capabilities; domains, dns_checks, certificates; seo_artifacts, site_quality_reports; generation_jobs, checkpoints, queue_metrics; abuse_reports, claims_provenance, takedowns; generation_jobs, checkpoints, budgets, artifact versions; visual_reports, review_signoffs, website_releases; domain maps, bundles, asset hashes, CDN release metadata |
| HIL | Basic tenant conversation handoff status and transfer-number facts only; no managed desk domain | escalations, callback_tasks, routing_attempts; escalation_policies, coverage_windows, acknowledgements; operators, client_grants, offers, interactions; line_registry, context_snapshots, greeting_versions; client_grants, interactions, desk_audit; authority_versions, action_approvals; media_sessions, desk_commands, transfers; queue_metrics, supervision_events; operator_skills, shifts, certifications; interventions, qa_reviews, learning_candidates; approvals, action_drafts, approval_events; offers, assignments, desk_sessions, command_receipts |
| INB | contacts, leads, conversations, conversation_messages, appointments, encrypted Google provider connections | notification_preferences, delivery_receipts, summary_jobs; appointments, booking_rules, calendar_connections; operator_interactions, dispositions, feedback; contacts, requests, threads, assignments, notes; sequences, sequence_runs, consents, suppressions; requests, fields, confidence/evidence, assignments |
| BIL | usage_events, usage_sessions, usage_outbox, usage_claims, billing_reports, worker state/nonces/receipts | cost_budgets, call_caps, fraud_events; plans, entitlements, subscriptions, invoices; usage_events, allowances, meter_rollups; provider_costs, operator_minutes, margin_rollups; price_books, claims_register, claim_approvals; Private usage ledger, outbox/session/claim and billing-report tables |
| VRT | Explicit skillId/domain selection and generation skill traces; no first-class brand/pack governance tables | brands, brand_domains, sender_identities; brand_grants, tenant_brand_links, legal_versions; vertical_packs, pack_versions, pack_bindings; readiness_checks, approvals, pack_evaluations; parity_requirements, connector_capabilities |
| INT | Encrypted Google connections, GitHub repository credentials and specialised metering ingress records | connector_configs, sync_runs, connector_health; api_clients, api_keys, webhook_endpoints, deliveries |
| ACQ | No acquisition target/prospect/provenance/claims domain | targets, source_licenses, target_playbooks; prospects, evidence, source_records; prospect_scores, stages, activities; outreach_consents, suppressions, activities; prospect_previews, demo_configs, claims; comparison_inputs, price_books, comparison_versions |
| MIG | Website snapshot rollback only; no whole-business migration inventory/rights/cutover model | migration_projects, asset_inventory, cutover_checks; contracts, asset_rights, authorisations |
| ORD | No menu/cart/order/payment/kitchen domain | menus, items, modifiers, carts, orders; order_drafts, confirmations, menu_versions; order_events, kitchen_receipts, printer_jobs; menu_localisations, pronunciations, ticket_locales |
| SEC | Private entity tables, scoped auth, encrypted provider payloads and invoker write functions | workspaces, scoped_entities, routing_map; consents, jurisdiction_rules, recording_events; compliance_profiles, subprocessor_approvals; legal_documents, acceptances, dp_roles; dsr_requests, exports, retention_jobs, key_registry; security_findings, audit_chain, evidence_records; key versions, service identities, secret references, data classification; audit_log, anchors, incident/evidence records |
| ANL | Operational lead/conversation/appointment counters and metering summaries | outcome_events, analytics_rollups, revenue_assumptions; acquisition_events, cohort_rollups |
| ADM | No separate staff admin, support impersonation, flag or number-inventory domain | staff_roles, support_sessions, incidents |
| OPS | Guarded migrations and usage-worker infrastructure; no general domain bus/cells/media drain | health_events, fallback_config, buffered_events; releases, deployment_events, drain_sessions; tenant_placement, cells, capacity_metrics; domain_outbox, jobs, timers, receipts, dead_letters; release manifests and deployment evidence; no customer schema change by default; backup manifests, restore evidence, failure-domain routing; telemetry labels, SLO reports, capacity/cost results |
| QA | No signed client AT-result repository in the application | accessibility_findings, remediation_evidence; acceptance_results, defects, signoffs, release_evidence |
| OWN | No completed asset/account/licence/handover acceptance register | asset_register, licence_inventory, access_grants; Ownership/access and licence registers; no new business table required |
| PJM | everonn.project_repositories; additive migration applied to configured PostgreSQL on 2026-10-06 | everonn.project_repositories; per-workspace CAS Blobs/local alternative; Versioned Markdown in Git; no new production schema |

For each proposed migration: define ownership/scope keys, uniqueness/idempotency, indexes/EXPLAIN, field classification, retention/deletion, encryption and version compatibility. Prove tenant boundaries on the approved target database and preserve existing records. Conceptual plural names do not authorise production SQL changes.

## UI deliverables

Owner UI covers onboarding/verification, knowledge review and publication, agent test/configuration, original website concepts and revision/publish, domains, inbox/contacts/booking, plans/usage/value and team permissions. The operator UI is a separate multi-client workbench with grants, line-aware screen-pop, private briefing, offer state and authority controls. Admin UI needs audited support/incident access. Acquisition and restaurant screens have independent source deliverables.

Every affected surface needs responsive navigation, keyboard/screen-reader access, visible state, understandable errors and role-appropriate controls. Customer requests to revise a website remain governed owner requests; customers do not edit platform security, runtime guardrails or provider/model configuration directly. Their approved business facts and design preferences should influence the generated result.

## Translate - business-to-technical mapping

| Business promise | Technical ownership | Proof |
| --- | --- | --- |
| Every call is answered or safely captured | Telephony/media runtime, routing, cached configuration, carrier fallback and capture receipt | Real call and outage scenarios, latency/availability measurements |
| Answers use approved business knowledge | Published KB/agent resolver, scoped retrieval, guardrails and provenance | Known/unknown/adversarial cases with pinned versions |
| Owner gets a premium site | Original generation, durable jobs, factual/visual review, safe assets, release/domain services | Owner-approved real pages, a11y/performance reports and hosted release |
| AI actions are truthful | Typed executor, validators, entitlement/authority policy and provider receipts | Actual booking/payment/message success/failure/uncertain-result tests |
| A person can take over safely | Operator grants, authoritative offers, separate briefing/audio, shift coverage and conservative permissions | Cross-tenant/race/audio privacy and staffed service tests |
| Client receives transparent pricing and value | Entitlements, billing/metering/reconciliation and evidence-based analytics | Accurate invoice/allowance/cost tests and reproducible report calculations |

This mapping dimension is not UI localisation. The genuine English/Spanish and later restaurant-language obligations remain in VOX/ORD/source records and are not removed.

## Backend services and integrations

Current routes include `/api/auth/*`, `/api/agent-runtime/memory`, `/api/website-studio` and `/api/website-studio/status`, `/api/assistant/message`, `/api/voice/session`, `/api/site-assistant/session`, `/api/site-assistant/lead` and `/api/project-workspace`. See the fingerprinted application route inventory for exact file paths and maintained architecture guides for current semantics.

Current Google booking/Gmail automation and provider usage operations have concrete scoped implementations. Proposed telephony/SMS/Stripe/Microsoft/POS/partner connectors require scoped credentials, provider approval, contracts, consent/quotas, receipts and safe retries. A future public API needs API keys/scopes, OpenAPI, version policy, outgoing webhook signatures/retries and connector lifecycle; existing internal APIs are insufficient.

## AI component deliverables

- Shared safety and capability standards plus a distinct service pack with intake/domain/design standards. Only general/HVAC currently exists.
- Explicit `MEMORY.md` policy: scope, fact/preferences separation, owner approval, retention, deletion, versioning and conflict handling. The document and assistant persistence are planned; existing website memory is a narrower implemented slice.
- Task-specific provider routing and budgets, typed tools, retrieved approved knowledge, instruction/source traces and safe unknown-answer capture.
- Real golden scenario datasets, human calibration, text/audio/red-team regressions, canary/shadow tests and drift monitoring. EVALS Markdown defines standards but does not execute them.
- Premium generation informed by service context and art direction, then validated against actual facts, functionality, accessibility, performance and visual standards.

Repository documents are untrusted content inputs. Viewing a customer's `SKILL.md` in Project Management must not grant tool authority or replace the platform's allowlisted instruction registry.

## Testing / QA deliverables

Maintain focused unit/contract/isolation tests; run genuine browser/provider journeys for workflows; build voice/media, operator concurrency, billing/replay, consent/privacy, security/a11y, load/soak and restore suites. Map results to all assigned source AT/US records and attach environment/version/timestamp/evidence. The current 127-test result establishes only its exercised slice.

## Deployment and operating deliverables

Approved environments/IaC, migration/backfill/rollback, secret provisioning, release promotion, drain-safe voice deployment, telemetry/SLOs, alert/incident and support runbooks, durable workers, backup/restore and owned vendor/accounts are required. Source baseline and hosted exceptions must be resolved before production commitments. Document evidence of each actual rollout; an environment variable name or configured state does not prove the corresponding provider service works.

Customer documentation extension: Markdown remains in this GitHub repository; the existing customer Project Workspace reads it through its safe GitHub adapter. This publication creates no production DB changes and deploys no application code.
