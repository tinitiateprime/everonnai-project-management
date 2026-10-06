# VOX - source requirement register

Definitions below preserve the supplied document records and continuation bullets. Source IDs are stable; SCF IDs are review-assigned identifiers for the 25 numbered scaffolding rows. Row numbers are extraction locations, not page numbers.

Related: [traceability matrix](../TRACEABILITY.md) | [document provenance](../SOURCES.md).

## VOX-001

Assigned delivery tickets: [EVN-VOX-001](../modules/04-telephone-voice-language/tickets/EVN-VOX-001.md).

**Primary source:** TECH section 14.3 Requirements: telephony and numbers; extraction row 831.

**Source record:** VOX-001 [P1] MUST answer inbound PSTN calls via a SIP/PSTN carrier through the TelephonyProvider interface. P1 MUST support two carriers (Twilio and Telnyx) with automatic failover routing at the number or trunk level (VOX-036).

## VOX-002

Assigned delivery tickets: [EVN-VOX-003](../modules/04-telephone-voice-language/tickets/EVN-VOX-003.md), [EVN-VOX-101](../modules/04-telephone-voice-language/tickets/EVN-VOX-101.md).

**Primary source:** TECH section 14.4 Requirements: real-time conversation quality; extraction row 845.

**Source record:** VOX-002 [P0] MUST implement a cascaded real-time pipeline (streaming STT → LLM → streaming TTS) behind provider interfaces, with the ability to swap in a speech-to-speech model as an alternative implementation later. P0 spike compares at least: two STT vendors, two TTS vendors, two LLM tiers, on real PSTN audio (8 kHz, noisy, accents) and reports latency, accuracy and cost.

## VOX-003

Assigned delivery tickets: [EVN-VOX-003](../modules/04-telephone-voice-language/tickets/EVN-VOX-003.md), [EVN-VOX-101](../modules/04-telephone-voice-language/tickets/EVN-VOX-101.md).

**Primary source:** TECH section 14.4 Requirements: real-time conversation quality; extraction row 846.

**Source record:** VOX-003 [P0] MUST meet the latency budget (planning targets, measured end-to-end as caller-perceived silence between end of caller speech and first agent audio):

## VOX-004

Assigned delivery tickets: [EVN-VOX-003](../modules/04-telephone-voice-language/tickets/EVN-VOX-003.md).

**Primary source:** TECH section 14.4 Requirements: real-time conversation quality; extraction row 855.

**Source record:** VOX-004 [P1] MUST support barge-in: the caller can interrupt; TTS stops within 200 ms; the agent resumes from the interrupted context and does not repeat itself.

## VOX-005

Assigned delivery tickets: [EVN-VOX-003](../modules/04-telephone-voice-language/tickets/EVN-VOX-003.md).

**Primary source:** TECH section 14.4 Requirements: real-time conversation quality; extraction row 856.

**Source record:** VOX-005 [P1] MUST implement robust turn-taking: semantic end-of-turn detection (not silence alone), tolerance for "um/uh", handling of caller thinking pauses, and detection of the caller reading back numbers or addresses (longer pauses).

## VOX-006

Assigned delivery tickets: [EVN-VOX-002](../modules/04-telephone-voice-language/tickets/EVN-VOX-002.md).

**Primary source:** TECH section 14.4 Requirements: real-time conversation quality; extraction row 857.

**Source record:** VOX-006 [P1] MUST handle noisy and degraded audio (car, wind, speakerphone): request repetition politely, confirm critical slots by read-back (phone number, address, name spelling), and fall back to SMS link capture ("I'll text you a link to share your location") when audio fails repeatedly.

## VOX-007

Assigned delivery tickets: [EVN-VOX-002](../modules/04-telephone-voice-language/tickets/EVN-VOX-002.md).

**Primary source:** TECH section 14.4 Requirements: real-time conversation quality; extraction row 858.

**Source record:** VOX-007 [P1] MUST implement read-back confirmation for high-value slots: callback number, service address, name, appointment time.

## VOX-008

Assigned delivery tickets: [EVN-VOX-006](../modules/04-telephone-voice-language/tickets/EVN-VOX-006.md).

**Primary source:** TECH section 14.4 Requirements: real-time conversation quality; extraction row 859.

**Source record:** VOX-008 [P1] MUST support English and Spanish at P1 (auto-detect and switch mid-call; caller-preferred language stored), with an extensible language framework (P3: more languages).

## VOX-009

Assigned delivery tickets: [EVN-HIL-024](../modules/07-human-operations-live-agent-desk/tickets/EVN-HIL-024.md).

**Primary source:** TECH section 14.4 Requirements: real-time conversation quality; extraction row 860.

**Source record:** VOX-009 [P1] MUST support DTMF input and output (for example "press 1 to speak to a person") and a universal "I want a person" intent that triggers HIL-003 within one turn.

## VOX-010

Assigned delivery tickets: [EVN-HIL-030](../modules/07-human-operations-live-agent-desk/tickets/EVN-HIL-030.md), [EVN-VOX-001](../modules/04-telephone-voice-language/tickets/EVN-VOX-001.md).

**Primary source:** TECH section 14.4 Requirements: real-time conversation quality; extraction row 861.

**Source record:** VOX-010 [P1] MUST detect voicemail/answering-machine and IVR situations on any outbound leg (transfers, callbacks) and behave appropriately (leave message or abort).

## VOX-011

Assigned delivery tickets: [EVN-INB-007](../modules/08-inbox-contacts-booking-followup/tickets/EVN-INB-007.md), [EVN-VOX-003](../modules/04-telephone-voice-language/tickets/EVN-VOX-003.md).

**Primary source:** TECH section 14.4 Requirements: real-time conversation quality; extraction row 862.

**Source record:** VOX-011 [P1] MUST manage silence, hold and dropped calls: prompts after configurable silence, hang-up after N prompts, graceful handling of caller hang-up mid-turn, and full post-call processing even on abrupt termination.

## VOX-012

Assigned delivery tickets: [EVN-VOX-003](../modules/04-telephone-voice-language/tickets/EVN-VOX-003.md), [EVN-VOX-006](../modules/04-telephone-voice-language/tickets/EVN-VOX-006.md).

**Primary source:** TECH section 14.4 Requirements: real-time conversation quality; extraction row 863.

**Source record:** VOX-012 [P1] MUST provide voice selection: a curated set of natural voices per language (with cloning of the owner's voice explicitly out of scope for P1, and only with documented consent in P3). Pronunciation dictionaries per tenant (business names, streets, terms).

## VOX-013

Assigned delivery tickets: [EVN-VOX-003](../modules/04-telephone-voice-language/tickets/EVN-VOX-003.md).

**Primary source:** TECH section 14.4 Requirements: real-time conversation quality; extraction row 864.

**Source record:** VOX-013 [P1] MUST support background-noise-safe barge-in (do not let TV/wind trigger interruption): use VAD tuned per carrier codec and echo cancellation.

## VOX-014

Assigned delivery tickets: [EVN-VOX-003](../modules/04-telephone-voice-language/tickets/EVN-VOX-003.md).

**Primary source:** TECH section 14.4 Requirements: real-time conversation quality; extraction row 865.

**Source record:** VOX-014 [P2] SHOULD provide prosody controls (pace, warmth) and backchanneling ("mm-hm") with per-tenant toggles.

## VOX-015

Assigned delivery tickets: [EVN-SEC-101](../modules/15-security-privacy-compliance/tickets/EVN-SEC-101.md), [EVN-VOX-003](../modules/04-telephone-voice-language/tickets/EVN-VOX-003.md).

**Primary source:** TECH section 14.4 Requirements: real-time conversation quality; extraction row 866.

**Source record:** VOX-015 [P2] SHOULD support multi-party awareness (speakerphone with two speakers) heuristics and safe behavior (confirm who the account holder is before sharing anything).

## VOX-016

Assigned delivery tickets: [EVN-VOX-001](../modules/04-telephone-voice-language/tickets/EVN-VOX-001.md), [EVN-VOX-002](../modules/04-telephone-voice-language/tickets/EVN-VOX-002.md).

**Primary source:** TECH section 14.5 Requirements: business behavior; extraction row 868.

**Source record:** VOX-016 [P1] MUST execute the vertical playbook: required slots (for example locksmith: lockout type, vehicle or property, address, safety status, ID-at-arrival note; HVAC: system type, symptom, urgency, occupants at risk). The agent asks one question at a time, adapts to volunteered information, and never re-asks for known data.

## VOX-017

Assigned delivery tickets: [EVN-VOX-002](../modules/04-telephone-voice-language/tickets/EVN-VOX-002.md).

**Primary source:** TECH section 14.5 Requirements: business behavior; extraction row 869.

**Source record:** VOX-017 [P1] MUST support urgency triage producing urgency ∈ {emergency, urgent, standard, info} with reason, and route accordingly (immediate owner transfer or text with priority flag).

## VOX-018

Assigned delivery tickets: [EVN-KNW-020](../modules/02-knowledge-agent-configuration/tickets/EVN-KNW-020.md), [EVN-VOX-002](../modules/04-telephone-voice-language/tickets/EVN-VOX-002.md).

**Primary source:** TECH section 14.5 Requirements: business behavior; extraction row 870.

**Source record:** VOX-018 [P1] MUST check service area using geocoding of the captured address and politely decline or route out-of-area requests per tenant policy.

## VOX-019

Assigned delivery tickets: [EVN-HIL-024](../modules/07-human-operations-live-agent-desk/tickets/EVN-HIL-024.md), [EVN-HIL-030](../modules/07-human-operations-live-agent-desk/tickets/EVN-HIL-030.md).

**Primary source:** TECH section 14.5 Requirements: business behavior; extraction row 871.

**Source record:** VOX-019 [P1] MUST support live transfer: warm transfer with a whispered context summary to the receiving party ("Caller Maria, lockout at 12 Oak St, urgent"), cold transfer, and transfer failure fallback (no answer → return to AI → capture message and schedule callback). Transfer targets and priority order are configured per hours mode. Targets are the client's own contacts and, in operator mode, EverOnn operators on the Live Agent Desk (§16.4).

## VOX-020

Assigned delivery tickets: [EVN-INB-008](../modules/08-inbox-contacts-booking-followup/tickets/EVN-INB-008.md).

**Primary source:** TECH section 14.5 Requirements: business behavior; extraction row 872.

**Source record:** VOX-020 [P1] MUST allow the AI to book appointments through the CalendarProvider (Google, Microsoft, Cal.com at P1; scheduling software integrations at P3) respecting buffers, service durations and territory, with confirmation SMS.

## VOX-021

Assigned delivery tickets: [EVN-INB-007](../modules/08-inbox-contacts-booking-followup/tickets/EVN-INB-007.md).

**Primary source:** TECH section 14.5 Requirements: business behavior; extraction row 873.

**Source record:** VOX-021 [P1] MUST send the owner summary within 30 seconds of call end via the tenant's preferred channels (SMS, push, email): who, what, where, urgency, next action, link to transcript and audio.

## VOX-022

Assigned delivery tickets: [EVN-CHT-012](../modules/05-chat-widget-sms/tickets/EVN-CHT-012.md), [EVN-SEC-064](../modules/15-security-privacy-compliance/tickets/EVN-SEC-064.md).

**Primary source:** TECH section 14.5 Requirements: business behavior; extraction row 874.

**Source record:** VOX-022 [P1] MUST send an optional customer confirmation SMS (subject to consent, COM-002).

## VOX-023

Assigned delivery tickets: [EVN-INB-007](../modules/08-inbox-contacts-booking-followup/tickets/EVN-INB-007.md), [EVN-INB-101](../modules/08-inbox-contacts-booking-followup/tickets/EVN-INB-101.md).

**Primary source:** TECH section 14.5 Requirements: business behavior; extraction row 875.

**Source record:** VOX-023 [P1] MUST produce the post-call package: transcript with timestamps and speaker labels, audio recording (if permitted), summary, structured Request, sentiment, outcome code, tool-call log, cost breakdown, guardrail events, latency per turn.

## VOX-024

Assigned delivery tickets: [EVN-INB-037](../modules/08-inbox-contacts-booking-followup/tickets/EVN-INB-037.md), [EVN-SEC-101](../modules/15-security-privacy-compliance/tickets/EVN-SEC-101.md).

**Primary source:** TECH section 14.5 Requirements: business behavior; extraction row 876.

**Source record:** VOX-024 [P1] MUST support returning-caller recognition (matched by verified phone number and tenant contacts) to personalize ("Welcome back, Maria") without exposing history to unverified callers beyond what policy allows.

## VOX-025

Assigned delivery tickets: [EVN-INB-038](../modules/08-inbox-contacts-booking-followup/tickets/EVN-INB-038.md), [EVN-SEC-064](../modules/15-security-privacy-compliance/tickets/EVN-SEC-064.md).

**Primary source:** TECH section 14.5 Requirements: business behavior; extraction row 877.

**Source record:** VOX-025 [P2] SHOULD support outbound callbacks initiated by operators or by rules for a tenant's own inbound leads, within TCPA and consent limits (COM-012).

## VOX-026

Assigned delivery tickets: [EVN-BIL-010](../modules/09-plans-billing-usage-margin/tickets/EVN-BIL-010.md).

**Primary source:** TECH section 14.5 Requirements: business behavior; extraction row 878.

**Source record:** VOX-026 [P1] MUST support per-call and per-day cost circuit breakers (for example a call exceeding 15 minutes triggers a graceful wrap-up or human transfer).

## VOX-030

Assigned delivery tickets: [EVN-VOX-001](../modules/04-telephone-voice-language/tickets/EVN-VOX-001.md), [EVN-VOX-009](../modules/04-telephone-voice-language/tickets/EVN-VOX-009.md).

**Primary source:** TECH section 14.3 Requirements: telephony and numbers; extraction row 832.

**Source record:** VOX-030 [P1] MUST support three ways to put EverOnn in front of a business's calls:

- 1.  Provisioned local/toll-free number (new number shown on the site);

- 2.  Forwarding from the business's existing number (all calls, no-answer, busy, or after-hours; generate carrier-specific setup instructions and verify with a test call);

- 3.  Number porting into EverOnn (P2, with a guided LOA workflow and status tracking).

## VOX-031

Assigned delivery tickets: [EVN-VOX-009](../modules/04-telephone-voice-language/tickets/EVN-VOX-009.md).

**Primary source:** TECH section 14.3 Requirements: telephony and numbers; extraction row 836.

**Source record:** VOX-031 [P1] MUST verify that forwarding is actually working (automated test call and confirmation) before marking the channel live.

## VOX-032

Assigned delivery tickets: [EVN-VOX-001](../modules/04-telephone-voice-language/tickets/EVN-VOX-001.md), [EVN-VOX-009](../modules/04-telephone-voice-language/tickets/EVN-VOX-009.md).

**Primary source:** TECH section 14.3 Requirements: telephony and numbers; extraction row 837.

**Source record:** VOX-032 [P1] MUST provide a ring-owner-first option: ring the owner's phone (and staff numbers) for N seconds (default 15, configurable), then AI answers. Whisper: when the owner answers a forwarded call, no AI disclosure is played.

## VOX-033

Assigned delivery tickets: [EVN-CHT-012](../modules/05-chat-widget-sms/tickets/EVN-CHT-012.md).

**Primary source:** TECH section 14.3 Requirements: telephony and numbers; extraction row 838.

**Source record:** VOX-033 [P1] MUST support missed-call text-back as a fallback and supplement: if a call ends unanswered (or was answered by AI but the caller dropped), send an SMS (subject to consent rules) inviting them to continue by text (handled by the chat agent).

## VOX-034

Assigned delivery tickets: [EVN-SEC-101](../modules/15-security-privacy-compliance/tickets/EVN-SEC-101.md), [EVN-VOX-001](../modules/04-telephone-voice-language/tickets/EVN-VOX-001.md).

**Primary source:** TECH section 14.3 Requirements: telephony and numbers; extraction row 839.

**Source record:** VOX-034 [P1] MUST support caller ID handling: pass caller ID into context; treat as untrusted; never assume identity from caller ID.

## VOX-035

Assigned delivery tickets: [EVN-CHT-012](../modules/05-chat-widget-sms/tickets/EVN-CHT-012.md), [EVN-SEC-064](../modules/15-security-privacy-compliance/tickets/EVN-SEC-064.md).

**Primary source:** TECH section 14.3 Requirements: telephony and numbers; extraction row 840.

**Source record:** VOX-035 [P1] MUST handle A2P 10DLC registration (brand and campaign) and toll-free verification for SMS as a managed background workflow with status visible to support (COM-005).

## VOX-036

Assigned delivery tickets: [EVN-OPS-068](../modules/18-reliability-deployment-scale/tickets/EVN-OPS-068.md).

**Primary source:** TECH section 14.3 Requirements: telephony and numbers; extraction row 841.

**Source record:** VOX-036 [P2] MUST support multi-carrier failover with health checks and automatic reroute within 60 seconds of detected carrier degradation.

## VOX-037

Assigned delivery tickets: [EVN-BIL-010](../modules/09-plans-billing-usage-margin/tickets/EVN-BIL-010.md).

**Primary source:** TECH section 14.3 Requirements: telephony and numbers; extraction row 842.

**Source record:** VOX-037 [P1] MUST implement toll-fraud and traffic-pumping defenses: per-tenant concurrent-call and daily-minute caps, geographic permission lists (default US/Canada), premium-rate and high-cost destination blocks for transfers, alerts on anomalies, and an emergency "kill switch" per tenant and per number.

## VOX-038

Assigned delivery tickets: [EVN-VOX-009](../modules/04-telephone-voice-language/tickets/EVN-VOX-009.md).

**Primary source:** TECH section 14.3 Requirements: telephony and numbers; extraction row 843.

**Source record:** VOX-038 [P1] SHOULD support STIR/SHAKEN attestation awareness and reputation monitoring of provisioned numbers (spam-label detection; P2 for automated remediation).

## VOX-040

Assigned delivery tickets: [EVN-VOX-101](../modules/04-telephone-voice-language/tickets/EVN-VOX-101.md).

**Primary source:** TECH section 14.6 Voice runtime deployment requirements; extraction row 880.

**Source record:** VOX-040 [P1] MUST run voice workers as horizontally scalable, stateless containers that pull tenant configuration from a cache keyed by version, with graceful draining (AR-009).

## VOX-041

Assigned delivery tickets: [EVN-VOX-101](../modules/04-telephone-voice-language/tickets/EVN-VOX-101.md).

**Primary source:** TECH section 14.6 Voice runtime deployment requirements; extraction row 881.

**Source record:** VOX-041 [P1] MUST be latency-aware in placement: media and voice workers deployed in the same region as the carrier edge; multi-region capable by config (P2).

## VOX-042

Assigned delivery tickets: [EVN-OPS-104](../modules/18-reliability-deployment-scale/tickets/EVN-OPS-104.md), [EVN-VOX-101](../modules/04-telephone-voice-language/tickets/EVN-VOX-101.md).

**Primary source:** TECH section 14.6 Voice runtime deployment requirements; extraction row 882.

**Source record:** VOX-042 [P1] MUST emit per-turn traces (OpenTelemetry) covering endpointing, STT, retrieval, LLM, tool, TTS spans, plus per-call cost attribution.

## VOX-043

Assigned delivery tickets: [EVN-VOX-101](../modules/04-telephone-voice-language/tickets/EVN-VOX-101.md).

**Primary source:** TECH section 14.6 Voice runtime deployment requirements; extraction row 883.

**Source record:** VOX-043 [P1] MUST support call replay in staging from recorded audio and transcripts for debugging and regression (with redaction, COM-007).

## VOX-044

Assigned delivery tickets: [EVN-VOX-101](../modules/04-telephone-voice-language/tickets/EVN-VOX-101.md).

**Primary source:** TECH section 14.6 Voice runtime deployment requirements; extraction row 884.

**Source record:** VOX-044 [P2] SHOULD support warm pools of pre-initialized agent sessions for common tenants to cut first-turn latency.
