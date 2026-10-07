# Current architecture

[Project guide](README.md) | [Data flow](DATA_FLOW.md) | [Technology comparison](TECH_STACK.md) | [Delivery status](DELIVERY_STATUS.md)

## How the application is built

EverOnnAI currently uses one Next.js application containing the dashboard, website pages and server APIs. Its features are organised into separate business modules. Those modules share access rules and connect to the database and external providers.

```mermaid
flowchart TD
    Owner[Business owner and team] --> Dashboard[Dashboard and project workspace]
    Visitor[Website visitor] --> Site[Website and assistant]
    Dashboard --> Server[Next.js server and business modules]
    Site --> Server
    Server --> DB[(Supabase PostgreSQL - private EverOnn tables)]
    Server --> Gemini[Gemini - website creation and text AI]
    Server --> Pexels[Pexels - website photography]
    Server --> Google[Google Calendar and Gmail]
    Server --> Github[GitHub - project documents]
    Server --> Voice[ElevenLabs - browser voice session setup]
    Site --> Voice
    Dashboard --> Voice
```

The server authorises access before reading business data or creating provider sessions. Browser voice connects to ElevenLabs using the server-created session.

## Main parts and their responsibilities

| Part | Current responsibility |
| --- | --- |
| Dashboard | Business profile, knowledge, website review, assistant tests, enquiries, appointments, team and usage |
| Server APIs | Check the user's role/business, validate requests and coordinate workflows |
| Business database | Store separate business workspaces, profiles, services, knowledge, contacts, leads, conversations and appointments |
| AI runtime | Combine approved business facts with shared rules, service skills, verified reference notes and task-specific workflow availability |
| Website Studio | Generate original HTML/CSS through saved resumable steps, validate facts/code, review drafts and publish approved releases |
| Assistant channels | Gemini text replies and ElevenLabs browser voice with lead capture and booking actions |
| Google integrations | Authorised calendar availability/event creation and Gmail owner summaries |
| Usage services | Record provider usage, recover pending records and reconcile through scheduled work/webhooks |
| Project Workspace | Browse a business's connected GitHub Markdown, diagrams and images with read-only access |

## Business separation and access

Each business has a workspace. The server selects that workspace from the authenticated account and checks its role. Business records and provider connections stay scoped to it. Private database tables and encrypted provider tokens support that separation.

The current roles are owner, manager, agent and viewer. Broader brand/operator identities and stronger account/security controls remain part of the requirement work.

## Website and assistant design

Gemini creates original page layouts and CSS within the platform's navigation, safety and interaction rules. The platform adds the working forms/chat/booking controls and validates generated content. Some older saved publications retain a compatibility renderer until an approved replacement is published.

The server explicitly loads versioned Markdown from `ai/`: shared rules, capability skills, the selected service pack, `PLUGINS.md` action guidance and `MEMORY.md` memory rules. `SOURCES.md` contributes verified general reference notes separately from business facts. Calendar/email availability reflects the business's connection permissions; server checks still control every action.

Website design preferences and recent approved change requests are saved per business/project. Owners and managers can clear saved preferences with revision protection. Full long-term assistant memory remains planned. `EVALS.md` supplies executable checks and stays outside customer prompts.

## Architecture work still required

The documents propose additional queue/workflow, telephone/media, operator and infrastructure components. Their full implementations are not present in the current architecture. The database, hosting, identity, voice and website-renderer differences are explained in [the technology comparison](TECH_STACK.md).
