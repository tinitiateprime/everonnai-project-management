# Current project status and verification

Snapshot: 6 October 2026 (Asia/Kolkata). This is an assessment of the inspected local application working tree, including uncommitted work, at base commit `73080bc507e4747224ef8553294352e68a08eaf3`. It is not a claim that all changes are present on GitHub main or deployed. File fingerprints and scope are in [EVIDENCE.md](EVIDENCE.md).

## What is implemented today

| Capability | Evidence-backed current slice | Boundary before full acceptance |
| --- | --- | --- |
| Tenant accounts and access | Workspace signup, scrypt passwords, hashed opaque sessions, invitations, password change, same-origin mutations and owner/manager/agent/viewer permissions | Recovery, email verification, MFA/SSO, brand/operator identities and independent business ownership verification remain |
| Persistence | Private relational `everonn` PostgreSQL schema, tenant-scoped stores, optimistic revisions; local JSON and Netlify Blob alternatives | These alternatives do not satisfy the specified MariaDB/cell/HA baseline without an approved exception; a single local file is a development persistence option |
| Knowledge | Approved profile/services/FAQs feed the runtime; unapproved knowledge is excluded | No full document ingestion, vector retrieval, immutable published KB/agent configuration or per-message source provenance |
| Skills and memory | Allowlisted shared/capability/HVAC Markdown is loaded with versions/digests; tenant/project website preferences and the last 20 approved owner requests persist | Only general/HVAC packs exist. No `ai/MEMORY.md` or full assistant long-term memory. Website design memory does not implement every memory requirement |
| AI website authoring | Gemini writes original multipage HTML/CSS; three independently generated concepts; small batches, bounded concurrency, fallbacks, validation/repair and NDJSON progress with heartbeat | Labels identify concepts, not fixed layouts. Durable job/resume across process loss and premium visual acceptance remain. AI-authored JavaScript is blocked; platform forms/chat/voice are attached |
| Website publication | Safe parsing/CSS scoping, private capability previews with noindex, draft/live snapshots, guarded publication ordering and rollback to three prior releases | Ownership verification is currently a state flag rather than independent proof. Preview contact masking/TTL, custom DNS/TLS and isolated tenant-site domain delivery need work. Some saved publications retain the legacy renderer until an owner approves a replacement |
| Assistant channels | Gemini text and ElevenLabs browser voice sessions use approved tenant context, validated capture and factual booking-result checks | Current session language is explicitly English. No proven dual-carrier PSTN ingress, porting, Spanish telephone quality, warm transfer or staffed live desk |
| Leads and bookings | Contacts/conversations/leads, selected inbox filters/status updates, appointment detail/time-zone checks, Google Calendar/Gmail OAuth/free-busy, recoverable event creation, workspace leases and duplicate/uncertain-delivery guards | Microsoft/Cal.com, full business-hours rules, SMS/reminders, assignment/notes/merge/PWA and real provider/customer launch acceptance remain |
| Usage accounting | Gemini attempts/tokens including retries/rejected outputs; reported ElevenLabs credits/USD; durable journals/outbox/reconciliation, signed worker/webhooks, scoped summaries and coverage labels | Unknown is not zero; dated estimates are distinct from bills. No subscriptions, invoices, enforced plan allowances or all-provider/operator margin engine |
| Security controls | Scoped APIs, private RLS/invoker SQL, server-side access, encrypted OAuth/GitHub tokens and replay/origin checks | No full KMS/Vault tenant-key lifecycle, tamper-evident compliance audit, recording/consent ledger, DSR/retention operations, penetration-test or restore certification |
| Customer project repositories | Tenant-scoped read-only GitHub public/private connections, branch/folder choice, Markdown/task/code/Mermaid/image viewer, filename/path search, manual sync, role controls and encrypted tokens | Hosted app needs the current snapshot deployed. Public GitHub access was exercised; a real authorised customer private PAT journey is pending. The viewer does not run viewed skills or become a writable issue tracker |

## Fresh checks completed during this planning review

| Check | Result | What it establishes |
| --- | --- | --- |
| `npm test` | 127 passed, 0 failed | Deterministic automated checks in the local application snapshot; not all 60 source acceptance scenarios |
| `npm run lint` | Passed | Current lint checks; not independent security/a11y certification |
| `npm run build` | Passed, Next.js 16.3.6 | Application production build completes locally; not hosted feature availability |

## Earlier recorded operational/browser evidence

The maintained application guides record shared PostgreSQL/usage-worker operational verification on 4 October 2026. They also record the customer repository migration applied on 6 October: `everonn.project_repositories`, private RLS/invoker access and preservation of 95 tables belonging to other projects. A rolled-back database probe exercised scoped CRUD, encrypted tokens, compare-and-swap and cross-tenant protections without retained probe rows.

Earlier HVAC and Project Workspace desktop/mobile production browser smoke checks passed. Project Workspace fixtures covered public/private behaviour; an actual public `actions/hello-world-javascript-action` manifest/README read also succeeded. Actual private customer-token access was not demonstrated. An isolated website review reported 51 AI-authored pages across 102 desktop/mobile checks; that is prior engineering evidence, not this client's published site or a premium visual sign-off.

The shared-database migration/worker checks do not establish every current app route's deployed status. Hosted environment, provider approval, remote assistant configuration and customer-specific access must be verified explicitly.

## What is not complete

- Real 24/7 telephone answering, two carriers, verified forwarding/porting, bilingual audio quality and warm transfers.
- Multi-client Live Agent Desk, time-boxed grants, audio privacy, authority enforcement, staffing and guaranteed human response.
- Subscription/payment/invoice/plan enforcement and full cost/margin reconciliation.
- First-class brands and reviewed vertical packs beyond HVAC; acquisition/source licences/outreach, full migration/cutover and restaurant/POS workflows.
- Durable general jobs, full domain-event backbone, custom domains/CDN, capacity/SLO proof and backup/restore exercises.
- Full legal/privacy/recording policy, independent security/accessibility review and signed client UAT.

## Ground truth for planning

No complete source BR is marked Done. Two implementation enablers (the existing provider usage slice and customer repository viewer) and this documentation pack have bounded implementation labels. All business acceptance remains pending. Owner/configuration flags, mocked provider results and a green build are not substitutes for proof of business delivery.
