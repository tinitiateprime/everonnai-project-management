# Technology used and document comparison

[Project guide](README.md) | [Architecture](ARCHITECTURE.md) | [Data flow](DATA_FLOW.md) | [Delivery status](DELIVERY_STATUS.md)

This table compares the implemented technology with the supplied BRD/technical specification. A difference calls for an agreed decision or implementation work; it does not automatically authorise replacing the current technology.

| Area | Used in the current project | Requested/proposed in the documents | What needs to happen |
| --- | --- | --- | --- |
| Website/dashboard UI | Next.js 16, React 19, TypeScript, Tailwind CSS 4 and project CSS | Next.js/React/TypeScript/Tailwind; additional UI and inbox capabilities | Core stack aligns; finish the required experience and accessibility |
| Backend | Next.js server APIs and TypeScript business modules | NestJS on Fastify, or a reviewed Fastify module approach | Agree whether to retain the current server design or split services |
| Database | Supabase PostgreSQL, private `everonn` tables | MariaDB with tenant-scoped records and future capacity groups | Approve an exception or plan a data-preserving migration |
| Hosting/infrastructure | AWS Amplify hosting/build configuration | RHEL, Podman/Quadlet, supported cache/storage and separate failure domains | Agree the hosting baseline, ownership and recovery design |
| Authentication | Custom passwords/sessions, invitations and role checks | Approved identity provider, proposed Keycloak, MFA/SSO and operator identities | Agree identity approach; add missing account/security features |
| Text and website AI | Gemini REST API; configured models and bounded fallbacks | Portable provider interfaces, task-based routing, alternatives and measured budgets | Continue Gemini as agreed; add provider contracts and quality/cost gates |
| Voice | ElevenLabs browser conversations | Full phone/media runtime, proposed LiveKit Agents/Pipecat or approved managed pilot | Decide the runtime and prove real phone handling |
| Telephone carriers | Full business-line integration remains planned | Two carriers, with Twilio/Telnyx as proposed choices | Add numbers, verified forwarding, transfers and carrier fallback |
| Website rendering | Original AI HTML/CSS, validation and release snapshots | SiteSpec schema and versioned website components/static delivery | Record a renderer decision that preserves the agreed design quality and safe updates |
| Website images | Pexels photography and approved asset references | Rights-approved business/media assets and secure processing | Keep image-source rights, relevance and processing review in the delivery checks |
| Assets and domains | Website releases in workspace storage; provider image references; application-path sites | S3-compatible artifact storage, CDN and custom-domain TLS; reviewed Cloudflare/ACME options | Agree edge/storage approach and implement domains and immutable website delivery |
| Knowledge and memory | Approved structured FAQs; service Markdown; verified general reference notes; `MEMORY.md` policy and scoped website preferences with reset controls | Document import/retrieval, published knowledge/agent versions and governed memory | Add document retrieval, stable approvals and full long-term assistant memory |
| Background work | Usage-specific ledger/outbox/worker; website generation runs within its request | BullMQ with Valkey/Redis, durable jobs/timers and domain events | Generalise reliable jobs; persist generation progress for restart recovery |
| Calendar/email | Google Calendar/Gmail through OAuth; task-specific action guidance reflects actual connection permissions | Provider interfaces, Google/Microsoft options and workflow connectors | Complete booking rules, provider interfaces and plan-aware typed tool execution |
| Billing | Gemini/ElevenLabs usage tracking and labelled cost estimates | Subscriptions, payment/invoice flows, entitlements, all-provider/operator costs | Add payment integration, plan enforcement and cost reconciliation |
| Secrets/security | Server configuration, encrypted provider tokens and private-table controls | Vault/OpenBao or approved key service, key rotation, audit and consent controls | Complete the agreed security/key lifecycle and assurance work |
| Monitoring/testing | Node/tsx tests, executable `EVALS.md` checks, browser checks and usage-worker health | Full functional/AI/audio/accessibility/security/load/restore evidence | Expand model/audio datasets and release gates; complete document criteria and client acceptance |
| Project documents | GitHub REST, Markdown/Mermaid viewer, encrypted repository tokens | Added by the user's project scope | Existing read-only documentation integration; future editing/issue workflows need separate scope |

## Decisions to settle first

- **Database and hosting:** retain PostgreSQL/Amplify under an approved exception, or agree the migration to the specified baseline (D-2/D-8).
- **Identity:** extend current account controls or adopt the approved identity provider (D-5).
- **Voice:** select the phone/media runtime and operator audio design using real call evidence (D-7/D-15).
- **Website generation:** reconcile the document's component renderer with the agreed original AI HTML/CSS direction.

The documents' default choices are proposals until approved. Current Gemini usage is the user's agreed direction. Remaining product work and approvals are tracked in [DELIVERY_STATUS.md](DELIVERY_STATUS.md).

## How the comparison is grounded

The review uses the current application code, package dependencies and maintained code/data-flow/client Q&A guides. The specification's technology baseline is in section 20 and constraints/architecture requirements; decision IDs above refer to its decision register. The current specification does not introduce a Java/Tomcat backend requirement.
