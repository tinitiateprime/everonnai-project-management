# US - source requirement register

Definitions below preserve the supplied document records and continuation bullets. Source IDs are stable; SCF IDs are review-assigned identifiers for the 25 numbered scaffolding rows. Row numbers are extraction locations, not page numbers.

Related: [traceability matrix](../TRACEABILITY.md) | [document provenance](../SOURCES.md).

## US-001

Assigned delivery tickets: [EVN-ONB-015](../modules/01-onboarding-tenancy-identity/tickets/EVN-ONB-015.md), [EVN-WEB-014](../modules/06-website-generation-hosting/tickets/EVN-WEB-014.md).

**Primary source:** TECH section EP-01 Onboarding and claim; extraction row 2377.

**Source record:** US-001 | As a prospect, I want to see a private preview of my website within two minutes of entering my business name, so that I can judge the offer without committing. | Given a valid business name and phone, when I submit, then a private preview and draft profile are ready within 2 minutes, are not indexable, and do not show my phone number | BR-014, BR-015

**Also documented:** BRD section EP-01 Onboarding and claim; extraction row 754.

## US-002

Assigned delivery tickets: [EVN-ONB-015](../modules/01-onboarding-tenancy-identity/tickets/EVN-ONB-015.md), [EVN-WEB-019](../modules/06-website-generation-hosting/tickets/EVN-WEB-019.md).

**Primary source:** TECH section EP-01 Onboarding and claim; extraction row 2378.

**Source record:** US-002 | As an owner, I want to verify that I own the business before anything goes public, so that nobody else can publish under my name. | Given a claimed preview, when ownership is not verified, then no public site exists and no real number is attached | BR-015, BR-019

**Also documented:** BRD section EP-01 Onboarding and claim; extraction row 755.

## US-003

Assigned delivery tickets: [EVN-VOX-001](../modules/04-telephone-voice-language/tickets/EVN-VOX-001.md), [EVN-VOX-009](../modules/04-telephone-voice-language/tickets/EVN-VOX-009.md).

**Primary source:** TECH section EP-01 Onboarding and claim; extraction row 2379.

**Source record:** US-003 | As an owner, I want to connect my existing number by forwarding and have the platform confirm it works, so that calls are answered without changing my number. | Given forwarding is configured, when the platform places a test call, then the channel is marked live only after the test passes | BR-009, BR-001

**Also documented:** BRD section EP-01 Onboarding and claim; extraction row 756.

## US-004

Assigned delivery tickets: [EVN-ONB-022](../modules/01-onboarding-tenancy-identity/tickets/EVN-ONB-022.md), [EVN-VOX-009](../modules/04-telephone-voice-language/tickets/EVN-VOX-009.md).

**Primary source:** TECH section EP-01 Onboarding and claim; extraction row 2380.

**Source record:** US-004 | As an owner, I want to finish setup in a few guided steps from my phone, so that I am live within minutes. | Given the setup wizard, when I complete all steps, then my first AI-answered call happens within 15 minutes of claiming | BR-009, BR-022

**Also documented:** BRD section EP-01 Onboarding and claim; extraction row 757.

## US-005

Assigned delivery tickets: [EVN-KNW-020](../modules/02-knowledge-agent-configuration/tickets/EVN-KNW-020.md).

**Primary source:** TECH section EP-02 Knowledge and agent control; extraction row 2383.

**Source record:** US-005 | As an owner, I want to approve exactly what the AI knows and says before it answers a call, so that it never states something I have not approved. | Given imported knowledge, when I have not approved it, then the agent cannot go live; approval is recorded with the version | BR-020

**Also documented:** BRD section EP-02 Knowledge and agent control; extraction row 760.

## US-006

Assigned delivery tickets: [EVN-AIQ-076](../modules/03-ai-governance-evaluation/tickets/EVN-AIQ-076.md), [EVN-KNW-021](../modules/02-knowledge-agent-configuration/tickets/EVN-KNW-021.md), [EVN-ONB-022](../modules/01-onboarding-tenancy-identity/tickets/EVN-ONB-022.md).

**Primary source:** TECH section EP-02 Knowledge and agent control; extraction row 2384.

**Source record:** US-006 | As an owner, I want to change my greeting, hours, escalation and pricing behavior and test it before publishing, so that I stay in control without a developer. | Given a draft change, when I test and publish it, then callers hear the new behavior; I can roll back in one click | BR-021, BR-022, BR-076

**Also documented:** BRD section EP-02 Knowledge and agent control; extraction row 761.

## US-007

Assigned delivery tickets: [EVN-KNW-020](../modules/02-knowledge-agent-configuration/tickets/EVN-KNW-020.md), [EVN-KNW-023](../modules/02-knowledge-agent-configuration/tickets/EVN-KNW-023.md).

**Primary source:** TECH section EP-02 Knowledge and agent control; extraction row 2385.

**Source record:** US-007 | As an owner, I want to see the questions the AI could not answer and add the answers, so that it improves every week. | Given a knowledge gap, when I answer it and approve, then the agent uses the answer on the next call | BR-023, BR-020

**Also documented:** BRD section EP-02 Knowledge and agent control; extraction row 762.

## US-008

Assigned delivery tickets: [EVN-HIL-029](../modules/07-human-operations-live-agent-desk/tickets/EVN-HIL-029.md), [EVN-HIL-034](../modules/07-human-operations-live-agent-desk/tickets/EVN-HIL-034.md).

**Primary source:** TECH section EP-02 Knowledge and agent control; extraction row 2386.

**Source record:** US-008 | As an owner, I want to set what EverOnn operators may and may not do for my business, so that they never promise what I would not. | Given my authority settings, when an operator attempts a restricted action, then it is blocked or sent to me for approval | BR-029, BR-034

**Also documented:** BRD section EP-02 Knowledge and agent control; extraction row 763.

## US-009

Assigned delivery tickets: [EVN-HIL-027](../modules/07-human-operations-live-agent-desk/tickets/EVN-HIL-027.md), [EVN-HIL-029](../modules/07-human-operations-live-agent-desk/tickets/EVN-HIL-029.md).

**Primary source:** TECH section EP-02 Knowledge and agent control; extraction row 2387.

**Source record:** US-009 | As an owner, I want to give operators my greeting, how to say my business name, and special instructions such as VIP customers, so that callers hear my business, not a generic call center. | Given my desk profile, when an operator receives my call, then my greeting, spoken name and notes are shown | BR-027, BR-029

**Also documented:** BRD section EP-02 Knowledge and agent control; extraction row 764.

## US-010

Assigned delivery tickets: [EVN-VOX-001](../modules/04-telephone-voice-language/tickets/EVN-VOX-001.md), [EVN-VOX-002](../modules/04-telephone-voice-language/tickets/EVN-VOX-002.md).

**Primary source:** TECH section EP-03 AI voice front desk; extraction row 2390.

**Source record:** US-010 | As a caller, I want to have my request understood and confirmed when I call a business at night, so that I know someone is coming. | Given an after-hours call, when I give my details, then the agent reads back my address and number and I receive a confirmation | BR-001, BR-002

**Also documented:** BRD section EP-03 AI voice front desk; extraction row 767.

## US-011

Assigned delivery tickets: [EVN-AIQ-004](../modules/03-ai-governance-evaluation/tickets/EVN-AIQ-004.md).

**Primary source:** TECH section EP-03 AI voice front desk; extraction row 2391.

**Source record:** US-011 | As a caller, I want to be told the truth and not be given invented prices, so that I can trust what I hear. | Given a price question under a never-quote policy, when I ask, then no figure is stated and a callback is offered | BR-004

**Also documented:** BRD section EP-03 AI voice front desk; extraction row 768.

## US-012

Assigned delivery tickets: [EVN-VOX-006](../modules/04-telephone-voice-language/tickets/EVN-VOX-006.md).

**Primary source:** TECH section EP-03 AI voice front desk; extraction row 2392.

**Source record:** US-012 | As a caller, I want to talk in Spanish, so that I can be helped in my language. | Given a Spanish-speaking caller, when the call starts or switches, then the agent responds in Spanish | BR-006

**Also documented:** BRD section EP-03 AI voice front desk; extraction row 769.

## US-013

Assigned delivery tickets: [EVN-VOX-005](../modules/04-telephone-voice-language/tickets/EVN-VOX-005.md).

**Primary source:** TECH section EP-03 AI voice front desk; extraction row 2393.

**Source record:** US-013 | As a caller, I want to be advised to call emergency services and reach a person immediately in an emergency, so that I am safe. | Given an emergency phrase, when detected, then advice is given and a person is connected with the highest priority | BR-005

**Also documented:** BRD section EP-03 AI voice front desk; extraction row 770.

## US-014

Assigned delivery tickets: [EVN-VOX-003](../modules/04-telephone-voice-language/tickets/EVN-VOX-003.md).

**Primary source:** TECH section EP-03 AI voice front desk; extraction row 2394.

**Source record:** US-014 | As a caller, I want to speak naturally and interrupt without long silences, so that the call feels like talking to a person. | Given a live call, when I interrupt, then the agent stops within 200 ms; response gap is under 1.8 s at p95 | BR-003

**Also documented:** BRD section EP-03 AI voice front desk; extraction row 771.

## US-015

Assigned delivery tickets: [EVN-INB-007](../modules/08-inbox-contacts-booking-followup/tickets/EVN-INB-007.md).

**Primary source:** TECH section EP-03 AI voice front desk; extraction row 2395.

**Source record:** US-015 | As an owner, I want to receive a text summary within 30 seconds of every call, so that I can act while I am on a job. | Given a finished call, then the summary arrives within 30 seconds with who, what, where, urgency and a link | BR-007

**Also documented:** BRD section EP-03 AI voice front desk; extraction row 772.

## US-016

Assigned delivery tickets: [EVN-INB-008](../modules/08-inbox-contacts-booking-followup/tickets/EVN-INB-008.md).

**Primary source:** TECH section EP-03 AI voice front desk; extraction row 2396.

**Source record:** US-016 | As an owner, I want to have the AI book appointments into my calendar, so that jobs are scheduled without me. | Given availability rules, when a caller accepts a slot, then it is booked once and confirmed | BR-008

**Also documented:** BRD section EP-03 AI voice front desk; extraction row 773.

## US-017

Assigned delivery tickets: [EVN-CHT-011](../modules/05-chat-widget-sms/tickets/EVN-CHT-011.md), [EVN-WEB-013](../modules/06-website-generation-hosting/tickets/EVN-WEB-013.md).

**Primary source:** TECH section EP-04 Chat and messaging; extraction row 2399.

**Source record:** US-017 | As a website visitor, I want to chat with the business at any hour and send a photo, so that I get help without calling. | Given the site widget, when I chat and upload a photo, then a structured request is created and the owner is notified | BR-011, BR-013

**Also documented:** BRD section EP-04 Chat and messaging; extraction row 776.

## US-018

Assigned delivery tickets: [EVN-CHT-012](../modules/05-chat-widget-sms/tickets/EVN-CHT-012.md).

**Primary source:** TECH section EP-04 Chat and messaging; extraction row 2400.

**Source record:** US-018 | As a customer, I want to text the business and stop messages by replying STOP, so that I control what I receive. | Given consent is on record, when I reply STOP, then no further messages are sent | BR-012

**Also documented:** BRD section EP-04 Chat and messaging; extraction row 777.

## US-019

Assigned delivery tickets: [EVN-CHT-012](../modules/05-chat-widget-sms/tickets/EVN-CHT-012.md).

**Primary source:** TECH section EP-04 Chat and messaging; extraction row 2401.

**Source record:** US-019 | As an owner, I want to have missed calls followed by an automatic text, so that callers who hung up still reach me. | Given an abandoned call and valid consent, then a text is sent inviting the caller to continue | BR-012

**Also documented:** BRD section EP-04 Chat and messaging; extraction row 778.

## US-020

Assigned delivery tickets: [EVN-HIL-024](../modules/07-human-operations-live-agent-desk/tickets/EVN-HIL-024.md).

**Primary source:** TECH section EP-05 Human operations and the Live Agent Desk; extraction row 2404.

**Source record:** US-020 | As a caller, I want to reach a person whenever I ask, or be guaranteed a callback, so that I am never trapped with an automated system. | Given I say "let me talk to a person", when an operator is available, then I am connected; otherwise a callback is scheduled within one turn | BR-024

**Also documented:** BRD section EP-05 Human operations and the Live Agent Desk; extraction row 781.

## US-021

Assigned delivery tickets: [EVN-HIL-026](../modules/07-human-operations-live-agent-desk/tickets/EVN-HIL-026.md), [EVN-HIL-027](../modules/07-human-operations-live-agent-desk/tickets/EVN-HIL-027.md).

**Primary source:** TECH section EP-05 Human operations and the Live Agent Desk; extraction row 2405.

**Source record:** US-021 | As an operator, I want to see the client name in large type, the line dialed, the exact greeting to say, the caller, why the call reached me and what the AI captured, the moment the call rings, so that I greet the caller in the right client's name and carry on where the AI left off. | Given an escalation for Acme Locksmith, when the offer rings, then within 500 ms the offer card shows Acme Locksmith, the line label, the greeting text, the caller, the trigger and the captured details | BR-027, BR-026

**Also documented:** BRD section EP-05 Human operations and the Live Agent Desk; extraction row 782.

## US-022

Assigned delivery tickets: [EVN-HIL-027](../modules/07-human-operations-live-agent-desk/tickets/EVN-HIL-027.md), [EVN-HIL-028](../modules/07-human-operations-live-agent-desk/tickets/EVN-HIL-028.md).

**Primary source:** TECH section EP-05 Human operations and the Live Agent Desk; extraction row 2406.

**Source record:** US-022 | As an operator, I want to be warned when the line cannot be identified, so that I never greet a caller as the wrong business. | Given an unresolved line, then the desk shows UNKNOWN LINE with no client data and only a neutral greeting | BR-027, BR-028

**Also documented:** BRD section EP-05 Human operations and the Live Agent Desk; extraction row 783.

## US-023

Assigned delivery tickets: [EVN-HIL-028](../modules/07-human-operations-live-agent-desk/tickets/EVN-HIL-028.md), [EVN-SEC-063](../modules/15-security-privacy-compliance/tickets/EVN-SEC-063.md).

**Primary source:** TECH section EP-05 Human operations and the Live Agent Desk; extraction row 2407.

**Source record:** US-023 | As an operator, I want to see only the current client's data and always see which client I am serving, so that I cannot mix clients up. | Given several open interactions, then each is labeled with its client and no panel shows two clients' data | BR-028, BR-063

**Also documented:** BRD section EP-05 Human operations and the Live Agent Desk; extraction row 784.

## US-024

Assigned delivery tickets: [EVN-HIL-029](../modules/07-human-operations-live-agent-desk/tickets/EVN-HIL-029.md), [EVN-HIL-034](../modules/07-human-operations-live-agent-desk/tickets/EVN-HIL-034.md).

**Primary source:** TECH section EP-05 Human operations and the Live Agent Desk; extraction row 2408.

**Source record:** US-024 | As an operator, I want to know what I may promise for this client, so that I stay within their rules. | Given the authority matrix, then restricted actions are disabled or request approval | BR-029, BR-034

**Also documented:** BRD section EP-05 Human operations and the Live Agent Desk; extraction row 785.

## US-025

Assigned delivery tickets: [EVN-HIL-030](../modules/07-human-operations-live-agent-desk/tickets/EVN-HIL-030.md).

**Primary source:** TECH section EP-05 Human operations and the Live Agent Desk; extraction row 2409.

**Source record:** US-025 | As an operator, I want to hold, transfer to the owner with a briefing, conference a technician, schedule a callback, or hand the caller back to the AI, so that I can resolve the call however it needs. | Given an active call, when I use each control, then it works and is logged | BR-030

**Also documented:** BRD section EP-05 Human operations and the Live Agent Desk; extraction row 786.

## US-026

Assigned delivery tickets: [EVN-HIL-028](../modules/07-human-operations-live-agent-desk/tickets/EVN-HIL-028.md), [EVN-HIL-030](../modules/07-human-operations-live-agent-desk/tickets/EVN-HIL-030.md).

**Primary source:** TECH section EP-05 Human operations and the Live Agent Desk; extraction row 2410.

**Source record:** US-026 | As an operator, I want to handle chats and texts in the same desk, each clearly labeled by client, so that I stay productive between calls. | Given a call is accepted, then open chats are parked and restored after wrap-up | BR-030, BR-028

**Also documented:** BRD section EP-05 Human operations and the Live Agent Desk; extraction row 787.

## US-027

Assigned delivery tickets: [EVN-HIL-030](../modules/07-human-operations-live-agent-desk/tickets/EVN-HIL-030.md), [EVN-HIL-033](../modules/07-human-operations-live-agent-desk/tickets/EVN-HIL-033.md).

**Primary source:** TECH section EP-05 Human operations and the Live Agent Desk; extraction row 2411.

**Source record:** US-027 | As an operator, I want to finish each interaction with a quick wrap-up, so that the client gets a clear record. | Given an ended interaction, when I submit disposition and notes, then the request is updated and the owner is notified | BR-033, BR-030

**Also documented:** BRD section EP-05 Human operations and the Live Agent Desk; extraction row 788.

## US-028

Assigned delivery tickets: [EVN-HIL-031](../modules/07-human-operations-live-agent-desk/tickets/EVN-HIL-031.md), [EVN-HIL-032](../modules/07-human-operations-live-agent-desk/tickets/EVN-HIL-032.md).

**Primary source:** TECH section EP-05 Human operations and the Live Agent Desk; extraction row 2412.

**Source record:** US-028 | As an operator lead, I want to see queues by client and monitor, whisper to and reassign operators, so that service levels hold and quality improves. | Given the wall board, then queues, waits and operators are visible by client; monitoring actions are logged | BR-031, BR-032

**Also documented:** BRD section EP-05 Human operations and the Live Agent Desk; extraction row 789.

## US-029

Assigned delivery tickets: [EVN-HIL-028](../modules/07-human-operations-live-agent-desk/tickets/EVN-HIL-028.md), [EVN-HIL-032](../modules/07-human-operations-live-agent-desk/tickets/EVN-HIL-032.md).

**Primary source:** TECH section EP-05 Human operations and the Live Agent Desk; extraction row 2413.

**Source record:** US-029 | As an operator lead, I want to grant, change and revoke operators' access to clients, so that only trained operators handle each client. | Given a revoked grant, then the operator loses access within 5 seconds | BR-032, BR-028

**Also documented:** BRD section EP-05 Human operations and the Live Agent Desk; extraction row 790.

## US-030

Assigned delivery tickets: [EVN-INB-035](../modules/08-inbox-contacts-booking-followup/tickets/EVN-INB-035.md).

**Primary source:** TECH section EP-05 Human operations and the Live Agent Desk; extraction row 2414.

**Source record:** US-030 | As an owner, I want to see which interactions were handled by the EverOnn team, by whom, and what they noted, so that I can verify the service. | Given a human-handled call, then my inbox flags it with the operator's first name, duration, disposition and notes | BR-035

**Also documented:** BRD section EP-05 Human operations and the Live Agent Desk; extraction row 791.

## US-031

Assigned delivery tickets: [EVN-HIL-025](../modules/07-human-operations-live-agent-desk/tickets/EVN-HIL-025.md), [EVN-VOX-005](../modules/04-telephone-voice-language/tickets/EVN-VOX-005.md).

**Primary source:** TECH section EP-05 Human operations and the Live Agent Desk; extraction row 2415.

**Source record:** US-031 | As an owner, I want to choose who is called first, who next and when EverOnn operators join, so that escalation matches how my business works. | Given my escalation settings, then the cascade runs in that order and emergencies alert until acknowledged | BR-025, BR-005

**Also documented:** BRD section EP-05 Human operations and the Live Agent Desk; extraction row 792.

## US-032

Assigned delivery tickets: [EVN-HIL-034](../modules/07-human-operations-live-agent-desk/tickets/EVN-HIL-034.md).

**Primary source:** TECH section EP-05 Human operations and the Live Agent Desk; extraction row 2416.

**Source record:** US-032 | As an owner, I want to approve sensitive actions such as sending a price, so that nothing binding is promised without me. | Given a restricted action, when requested, then I receive an approval request and the result flows to the operator | BR-034

**Also documented:** BRD section EP-05 Human operations and the Live Agent Desk; extraction row 793.

## US-033

Assigned delivery tickets: [EVN-HIL-033](../modules/07-human-operations-live-agent-desk/tickets/EVN-HIL-033.md).

**Primary source:** TECH section EP-05 Human operations and the Live Agent Desk; extraction row 2417.

**Source record:** US-033 | As a quality reviewer, I want to review sampled interactions, including whether the right greeting was used, so that quality and correctness stay high. | Given the sampling queue, then interactions appear by risk and my scores are recorded | BR-033

**Also documented:** BRD section EP-05 Human operations and the Live Agent Desk; extraction row 794.

## US-034

Assigned delivery tickets: [EVN-HIL-036](../modules/07-human-operations-live-agent-desk/tickets/EVN-HIL-036.md).

**Primary source:** TECH section EP-05 Human operations and the Live Agent Desk; extraction row 2418.

**Source record:** US-034 | As an operator, I want to keep working through a page reload or brief network drop, so that no caller is lost. | Given a reload, then the desk restores state within 3 seconds and the call continues | BR-036

**Also documented:** BRD section EP-05 Human operations and the Live Agent Desk; extraction row 795.

## US-035

Assigned delivery tickets: [EVN-INB-037](../modules/08-inbox-contacts-booking-followup/tickets/EVN-INB-037.md).

**Primary source:** TECH section EP-06 Inbox, booking and follow-up; extraction row 2421.

**Source record:** US-035 | As a staff member, I want to work one inbox of calls, chats, texts and forms, so that nothing falls through the cracks. | Given new interactions, then each appears as a request with assignment, notes and status | BR-037

**Also documented:** BRD section EP-06 Inbox, booking and follow-up; extraction row 798.

## US-036

Assigned delivery tickets: [EVN-INB-038](../modules/08-inbox-contacts-booking-followup/tickets/EVN-INB-038.md).

**Primary source:** TECH section EP-06 Inbox, booking and follow-up; extraction row 2422.

**Source record:** US-036 | As an owner, I want to have reminders, text-back sequences and review requests sent automatically, so that customers come back and I get reviews. | Given a sequence, then messages respect consent and quiet hours | BR-038

**Also documented:** BRD section EP-06 Inbox, booking and follow-up; extraction row 799.

## US-037

Assigned delivery tickets: [EVN-ANL-039](../modules/16-business-value-analytics/tickets/EVN-ANL-039.md).

**Primary source:** TECH section EP-06 Inbox, booking and follow-up; extraction row 2423.

**Source record:** US-037 | As an owner, I want to see calls answered, jobs captured and estimated recovered revenue, so that I know EverOnn is paying for itself. | Given the dashboard, then figures and a weekly digest are shown | BR-039

**Also documented:** BRD section EP-06 Inbox, booking and follow-up; extraction row 800.

## US-038

Assigned delivery tickets: [EVN-WEB-016](../modules/06-website-generation-hosting/tickets/EVN-WEB-016.md), [EVN-WEB-017](../modules/06-website-generation-hosting/tickets/EVN-WEB-017.md).

**Primary source:** TECH section EP-07 Websites; extraction row 2426.

**Source record:** US-038 | As an owner, I want to edit my website easily and use my own domain, so that it looks like my business. | Given the editor, when I publish, then the site updates; my domain gets a certificate automatically | BR-016, BR-017

**Also documented:** BRD section EP-07 Websites; extraction row 803.

## US-039

Assigned delivery tickets: [EVN-WEB-018](../modules/06-website-generation-hosting/tickets/EVN-WEB-018.md), [EVN-WEB-019](../modules/06-website-generation-hosting/tickets/EVN-WEB-019.md).

**Primary source:** TECH section EP-07 Websites; extraction row 2427.

**Source record:** US-039 | As an EverOnn product owner, I want to generate 1,000 websites per day without publishing fake or impersonating sites, so that growth is safe. | Given a bulk run, then throughput is met and prohibited or impersonating sites are blocked | BR-018, BR-019

**Also documented:** BRD section EP-07 Websites; extraction row 804.

## US-040

Assigned delivery tickets: [EVN-WEB-013](../modules/06-website-generation-hosting/tickets/EVN-WEB-013.md).

**Primary source:** TECH section EP-07 Websites; extraction row 2428.

**Source record:** US-040 | As an owner, I want to have chat, click-to-call and forms on my site by default, so that visitors can always reach me. | Given a published site, then the widget, call button and form are present | BR-013

**Also documented:** BRD section EP-07 Websites; extraction row 805.

## US-041

Assigned delivery tickets: [EVN-BIL-040](../modules/09-plans-billing-usage-margin/tickets/EVN-BIL-040.md), [EVN-BIL-041](../modules/09-plans-billing-usage-margin/tickets/EVN-BIL-041.md).

**Primary source:** TECH section EP-08 Billing, plans and cost; extraction row 2431.

**Source record:** US-041 | As an owner, I want to choose a plan and pay securely, and see my usage and alerts, so that there are no billing surprises. | Given a plan, then usage meters and 80% and 100% alerts are visible; emergencies are never blocked at limits | BR-040, BR-041

**Also documented:** BRD section EP-08 Billing, plans and cost; extraction row 808.

## US-042

Assigned delivery tickets: [EVN-BIL-040](../modules/09-plans-billing-usage-margin/tickets/EVN-BIL-040.md), [EVN-BIL-043](../modules/09-plans-billing-usage-margin/tickets/EVN-BIL-043.md).

**Primary source:** TECH section EP-08 Billing, plans and cost; extraction row 2432.

**Source record:** US-042 | As a prospect, I want to see plan prices and contents that are accurate and consistent everywhere I look, so that I can trust what I am buying. | Given the pricing page, then plan cards, comparison table and checkout show the same contents, generated from one source | BR-043, BR-040

**Also documented:** BRD section EP-08 Billing, plans and cost; extraction row 809.

## US-043

Assigned delivery tickets: [EVN-BIL-010](../modules/09-plans-billing-usage-margin/tickets/EVN-BIL-010.md), [EVN-BIL-042](../modules/09-plans-billing-usage-margin/tickets/EVN-BIL-042.md).

**Primary source:** TECH section EP-08 Billing, plans and cost; extraction row 2433.

**Source record:** US-043 | As an EverOnn finance, I want to see cost and margin per client, plan and vendor, including operator minutes, so that we keep healthy margins. | Given the cost dashboard, then per-client margin is shown and circuit breakers are configured | BR-042, BR-010

**Also documented:** BRD section EP-08 Billing, plans and cost; extraction row 810.

## US-044

Assigned delivery tickets: [EVN-ADM-070](../modules/17-admin-backoffice/tickets/EVN-ADM-070.md), [EVN-KNW-023](../modules/02-knowledge-agent-configuration/tickets/EVN-KNW-023.md).

**Primary source:** TECH section EP-09 Administration and operations; extraction row 2436.

**Source record:** US-044 | As a support agent, I want to find a client, replay a call and see why the AI said something, so that I can resolve issues quickly. | Given a client, then I can replay and view sources, tools and rules; impersonation shows a banner | BR-070, BR-023

**Also documented:** BRD section EP-09 Administration and operations; extraction row 813.

## US-045

Assigned delivery tickets: [EVN-ADM-070](../modules/17-admin-backoffice/tickets/EVN-ADM-070.md), [EVN-OPS-068](../modules/18-reliability-deployment-scale/tickets/EVN-OPS-068.md).

**Primary source:** TECH section EP-09 Administration and operations; extraction row 2437.

**Source record:** US-045 | As a platform admin, I want to switch off a capability or a vendor instantly and fail over, so that an outage does not stop calls. | Given a vendor outage, then failover happens and calls complete or capture safely | BR-068, BR-070

**Also documented:** BRD section EP-09 Administration and operations; extraction row 814.

## US-046

Assigned delivery tickets: [EVN-AIQ-076](../modules/03-ai-governance-evaluation/tickets/EVN-AIQ-076.md).

**Primary source:** TECH section EP-09 Administration and operations; extraction row 2438.

**Source record:** US-046 | As a product owner, I want to release prompt and policy changes safely with automatic checks, so that quality never regresses. | Given a change, then it must pass the evaluation gate and can be rolled back instantly | BR-076

**Also documented:** BRD section EP-09 Administration and operations; extraction row 815.

## US-047

Assigned delivery tickets: [EVN-SEC-066](../modules/15-security-privacy-compliance/tickets/EVN-SEC-066.md).

**Primary source:** TECH section EP-10 Compliance, security and privacy; extraction row 2441.

**Source record:** US-047 | As an owner, I want to read and accept plain terms that say what EverOnn does and what my business remains responsible for, so that I understand my obligations before I go live. | Given onboarding, when I have not accepted the terms, then I cannot go live; recording and AI-disclosure choices are explained and recorded | BR-066

**Also documented:** BRD section EP-10 Compliance, security and privacy; extraction row 818.

## US-048

Assigned delivery tickets: [EVN-SEC-067](../modules/15-security-privacy-compliance/tickets/EVN-SEC-067.md).

**Primary source:** TECH section EP-10 Compliance, security and privacy; extraction row 2442.

**Source record:** US-048 | As an owner, I want to export or delete my data, so that I control my information. | Given a request, then a complete export or verified deletion is delivered on time | BR-067

**Also documented:** BRD section EP-10 Compliance, security and privacy; extraction row 819.

## US-049

Assigned delivery tickets: [EVN-CHT-012](../modules/05-chat-widget-sms/tickets/EVN-CHT-012.md), [EVN-SEC-064](../modules/15-security-privacy-compliance/tickets/EVN-SEC-064.md).

**Primary source:** TECH section EP-10 Compliance, security and privacy; extraction row 2443.

**Source record:** US-049 | As an EverOnn product owner, I want to have consent, recording and disclosure rules enforced automatically, so that we stay compliant. | Given jurisdiction rules, then announcements, consent and sending guards behave accordingly | BR-064, BR-012

**Also documented:** BRD section EP-10 Compliance, security and privacy; extraction row 820.

## US-050

Assigned delivery tickets: [EVN-SEC-063](../modules/15-security-privacy-compliance/tickets/EVN-SEC-063.md), [EVN-SEC-073](../modules/15-security-privacy-compliance/tickets/EVN-SEC-073.md).

**Primary source:** TECH section EP-10 Compliance, security and privacy; extraction row 2444.

**Source record:** US-050 | As an EverOnn product owner, I want to guarantee that no client can see or affect another client's data, verified by an independent test, so that trust is protected. | Given the isolation suite and penetration test, then there are no leaks and no open high findings | BR-063, BR-073

**Also documented:** BRD section EP-10 Compliance, security and privacy; extraction row 821.

## US-051

Assigned delivery tickets: [EVN-INT-071](../modules/11-api-connectors-integrations/tickets/EVN-INT-071.md).

**Primary source:** TECH section EP-11 Integrations, scale and ownership; extraction row 2447.

**Source record:** US-051 | As a partner developer, I want to use an API and webhooks, so that I can connect other tools. | Given API keys, then documented endpoints and signed webhooks work | BR-071

**Also documented:** BRD section EP-11 Integrations, scale and ownership; extraction row 824.

## US-052

Assigned delivery tickets: [EVN-OPS-069](../modules/18-reliability-deployment-scale/tickets/EVN-OPS-069.md), [EVN-OPS-072](../modules/18-reliability-deployment-scale/tickets/EVN-OPS-072.md).

**Primary source:** TECH section EP-11 Integrations, scale and ownership; extraction row 2448.

**Source record:** US-052 | As an EverOnn product owner, I want to grow to 1,000 and then 10,000 clients by adding capacity, with releases that never drop calls, so that growth does not need a rebuild. | Given load and deployment tests, then service levels hold and no calls drop | BR-072, BR-069

**Also documented:** BRD section EP-11 Integrations, scale and ownership; extraction row 825.

## US-053

Assigned delivery tickets: [EVN-QA-074](../modules/19-testing-client-acceptance/tickets/EVN-QA-074.md).

**Primary source:** TECH section EP-11 Integrations, scale and ownership; extraction row 2449.

**Source record:** US-053 | As an user of any EverOnn screen, I want to use an accessible interface, so that everyone can use it. | Given an audit, then WCAG 2.1 AA is met | BR-074

**Also documented:** BRD section EP-11 Integrations, scale and ownership; extraction row 826.

## US-054

Assigned delivery tickets: [EVN-OWN-075](../modules/20-ownership-handover/tickets/EVN-OWN-075.md).

**Primary source:** TECH section EP-11 Integrations, scale and ownership; extraction row 2450.

**Source record:** US-054 | As an EverOnn owner, I want to own all code, data, prompts and accounts, so that I am never locked in. | Given handover, then EverOnn staff can build and deploy from EverOnn-owned repositories and accounts | BR-075

**Also documented:** BRD section EP-11 Integrations, scale and ownership; extraction row 827.

## US-055

Assigned delivery tickets: [EVN-VRT-046](../modules/10-brands-vertical-packs/tickets/EVN-VRT-046.md), [EVN-VRT-047](../modules/10-brands-vertical-packs/tickets/EVN-VRT-047.md).

**Primary source:** TECH section EP-12 Verticals and brands; extraction row 2453.

**Source record:** US-055 | As an EverOnn product owner, I want to launch a new industry from a configuration bundle after a readiness review, so that we can grow quickly without risking quality or compliance. | Given a new pack, when the readiness checklist is approved, then the industry goes live without platform code changes; an incomplete checklist blocks it | BR-046, BR-047

**Also documented:** BRD section EP-12 Verticals and brands; extraction row 830.

## US-056

Assigned delivery tickets: [EVN-VRT-044](../modules/10-brands-vertical-packs/tickets/EVN-VRT-044.md), [EVN-VRT-045](../modules/10-brands-vertical-packs/tickets/EVN-VRT-045.md).

**Primary source:** TECH section EP-12 Verticals and brands; extraction row 2454.

**Source record:** US-056 | As an EverOnn owner, I want to present each vertical as its own brand with its own name, site and legal identity, all on one platform, so that each audience sees a solution made for it and we run one business. | Given two brands, then each shows its own identity and pricing, and every legal page names EverOnn as the contracting entity | BR-044, BR-045

**Also documented:** BRD section EP-12 Verticals and brands; extraction row 831.

## US-057

Assigned delivery tickets: [EVN-VRT-045](../modules/10-brands-vertical-packs/tickets/EVN-VRT-045.md).

**Primary source:** TECH section EP-12 Verticals and brands; extraction row 2455.

**Source record:** US-057 | As a client owner, I want to receive a dashboard, emails and texts under my industry's brand, so that the service feels made for my business. | Given my brand, then all client-facing surfaces use its name, theme and sender identity and never expose another brand | BR-045

**Also documented:** BRD section EP-12 Verticals and brands; extraction row 832.

## US-058

Assigned delivery tickets: [EVN-VRT-048](../modules/10-brands-vertical-packs/tickets/EVN-VRT-048.md).

**Primary source:** TECH section EP-12 Verticals and brands; extraction row 2456.

**Source record:** US-058 | As an owner switching from another provider, I want to keep the capabilities my current provider gave me, so that I lose nothing by moving. | Given my industry's parity list, then each capability is present, embedded or connected before I go live | BR-048

**Also documented:** BRD section EP-12 Verticals and brands; extraction row 833.

## US-059

Assigned delivery tickets: [EVN-INT-049](../modules/11-api-connectors-integrations/tickets/EVN-INT-049.md).

**Primary source:** TECH section EP-12 Verticals and brands; extraction row 2457.

**Source record:** US-059 | As an owner, I want to have EverOnn connect to the software I already use, and still work well if it cannot, so that my daily tools keep working. | Given a supported system, when I connect it, then data syncs and health is visible; without it the front desk still captures and notifies | BR-049

**Also documented:** BRD section EP-12 Verticals and brands; extraction row 834.

## US-060

Assigned delivery tickets: [EVN-SEC-065](../modules/15-security-privacy-compliance/tickets/EVN-SEC-065.md), [EVN-VRT-047](../modules/10-brands-vertical-packs/tickets/EVN-VRT-047.md).

**Primary source:** TECH section EP-12 Verticals and brands; extraction row 2458.

**Source record:** US-060 | As an EverOnn compliance lead, I want to run regulated industries under enforced compliance profiles, so that we handle patient, legal, tax and insurance conversations safely. | Given a regulated pack, then disclosures, data handling, subprocessors and advice limits are enforced and a pack that cannot meet them cannot go live | BR-065, BR-047

**Also documented:** BRD section EP-12 Verticals and brands; extraction row 835.

## US-061

Assigned delivery tickets: [EVN-ACQ-050](../modules/12-customer-acquisition-claims/tickets/EVN-ACQ-050.md).

**Primary source:** TECH section EP-13 Customer acquisition and migration; extraction row 2461.

**Source record:** US-061 | As an acquisition manager, I want to add any competitor as a target with its signatures, sources, pricing, features, contract notes and migration playbook, so that the same process works against any provider. | Given a new target, then prospects can be imported and the playbook is selected automatically | BR-050

**Also documented:** BRD section EP-13 Customer acquisition and migration; extraction row 838.

## US-062

Assigned delivery tickets: [EVN-ACQ-051](../modules/12-customer-acquisition-claims/tickets/EVN-ACQ-051.md), [EVN-ACQ-052](../modules/12-customer-acquisition-claims/tickets/EVN-ACQ-052.md).

**Primary source:** TECH section EP-13 Customer acquisition and migration; extraction row 2462.

**Source record:** US-062 | As an acquisition analyst, I want to import prospects with their source, date and evidence and see unknowns as unknown, so that we never treat a detection as a confirmed customer. | Given an import, then duplicates merge, provenance is stored, and unverified facts show as unknown | BR-051, BR-052

**Also documented:** BRD section EP-13 Customer acquisition and migration; extraction row 839.

## US-063

Assigned delivery tickets: [EVN-ACQ-053](../modules/12-customer-acquisition-claims/tickets/EVN-ACQ-053.md).

**Primary source:** TECH section EP-13 Customer acquisition and migration; extraction row 2463.

**Source record:** US-063 | As a salesperson, I want to send compliant outreach that respects opt-outs across every brand, so that we protect prospects and the company. | Given an opt-out on any brand, then no brand contacts that person again; blocked channels stay blocked without consent | BR-053

**Also documented:** BRD section EP-13 Customer acquisition and migration; extraction row 840.

## US-064

Assigned delivery tickets: [EVN-ACQ-054](../modules/12-customer-acquisition-claims/tickets/EVN-ACQ-054.md).

**Primary source:** TECH section EP-13 Customer acquisition and migration; extraction row 2464.

**Source record:** US-064 | As a salesperson, I want to show a prospect a private preview and a demonstration built from their own business, so that they can judge the offer before committing. | Given a prospect, then a private, non-indexed preview and a demo agent are ready and nothing is published or dialed without approval or consent | BR-054

**Also documented:** BRD section EP-13 Customer acquisition and migration; extraction row 841.

## US-065

Assigned delivery tickets: [EVN-ACQ-055](../modules/12-customer-acquisition-claims/tickets/EVN-ACQ-055.md), [EVN-MIG-057](../modules/13-customer-migration-offboarding/tickets/EVN-MIG-057.md).

**Primary source:** TECH section EP-13 Customer acquisition and migration; extraction row 2465.

**Source record:** US-065 | As a salesperson, I want to show an honest all-in comparison of what the prospect pays now and would pay with EverOnn, so that the prospect can trust the numbers. | Given confirmed inputs, then the comparison includes contract term, termination fee, retained services and break-even; estimates are labeled | BR-055, BR-057

**Also documented:** BRD section EP-13 Customer acquisition and migration; extraction row 842.

## US-066

Assigned delivery tickets: [EVN-MIG-056](../modules/13-customer-migration-offboarding/tickets/EVN-MIG-056.md).

**Primary source:** TECH section EP-13 Customer acquisition and migration; extraction row 2466.

**Source record:** US-066 | As a prospect owner, I want to switch providers without losing calls, email or my website's search visibility, so that my business is not disrupted. | Given a cut-over, then calls and forms keep working, email continues, redirects are in place and rollback is available | BR-056

**Also documented:** BRD section EP-13 Customer acquisition and migration; extraction row 843.

## US-067

Assigned delivery tickets: [EVN-MIG-056](../modules/13-customer-migration-offboarding/tickets/EVN-MIG-056.md), [EVN-MIG-057](../modules/13-customer-migration-offboarding/tickets/EVN-MIG-057.md).

**Primary source:** TECH section EP-13 Customer acquisition and migration; extraction row 2467.

**Source record:** US-067 | As a migration specialist, I want to follow a checklist that verifies domain ownership, email continuity, phone forwarding and rollback, so that every switch is safe. | Given a migration project, then each asset is inventoried and checked and cut-over is blocked until checks pass | BR-056, BR-057

**Also documented:** BRD section EP-13 Customer acquisition and migration; extraction row 844.

## US-068

Assigned delivery tickets: [EVN-ANL-058](../modules/16-business-value-analytics/tickets/EVN-ANL-058.md).

**Primary source:** TECH section EP-13 Customer acquisition and migration; extraction row 2468.

**Source record:** US-068 | As an acquisition manager, I want to see funnel, cost, time to switch, savings and retention by target and vertical, so that we invest in what works. | Given the analytics, then figures are shown by target, vertical, brand and channel | BR-058

**Also documented:** BRD section EP-13 Customer acquisition and migration; extraction row 845.

## US-069

Assigned delivery tickets: [EVN-ORD-059](../modules/14-restaurant-ordering/tickets/EVN-ORD-059.md), [EVN-ORD-061](../modules/14-restaurant-ordering/tickets/EVN-ORD-061.md).

**Primary source:** TECH section EP-14 Restaurant ordering; extraction row 2471.

**Source record:** US-069 | As a restaurant owner, I want to let customers order for pickup online from my real menu, so that I keep my sales without a percentage fee. | Given my menu, when a customer orders, then tax, pickup time and payment work and the ticket reaches my kitchen | BR-059, BR-061

**Also documented:** BRD section EP-14 Restaurant ordering; extraction row 848.

## US-070

Assigned delivery tickets: [EVN-ORD-060](../modules/14-restaurant-ordering/tickets/EVN-ORD-060.md), [EVN-ORD-061](../modules/14-restaurant-ordering/tickets/EVN-ORD-061.md).

**Primary source:** TECH section EP-14 Restaurant ordering; extraction row 2472.

**Source record:** US-070 | As a restaurant owner, I want to have phone orders read back accurately and sent to my kitchen, so that I can serve callers during the rush. | Given a phone order, then the AI reads back the whole order, gets confirmation and the ticket arrives; allergy questions go to staff | BR-060, BR-061

**Also documented:** BRD section EP-14 Restaurant ordering; extraction row 849.

## US-071

Assigned delivery tickets: [EVN-ORD-061](../modules/14-restaurant-ordering/tickets/EVN-ORD-061.md), [EVN-ORD-062](../modules/14-restaurant-ordering/tickets/EVN-ORD-062.md).

**Primary source:** TECH section EP-14 Restaurant ordering; extraction row 2473.

**Source record:** US-071 | As a restaurant staff member, I want to accept orders on a screen, print bilingual tickets and be alerted to unaccepted orders, so that no order is missed. | Given a new order, then an alert sounds, I can accept with a prep time, and a ticket prints | BR-061, BR-062

**Also documented:** BRD section EP-14 Restaurant ordering; extraction row 850.

## US-072

Assigned delivery tickets: [EVN-ORD-062](../modules/14-restaurant-ordering/tickets/EVN-ORD-062.md).

**Primary source:** TECH section EP-14 Restaurant ordering; extraction row 2474.

**Source record:** US-072 | As a restaurant owner, I want to be able to take orders in the languages my customers use, so that no customer is turned away. | Given tested languages, then orders in those languages meet accuracy thresholds | BR-062

**Also documented:** BRD section EP-14 Restaurant ordering; extraction row 851.
