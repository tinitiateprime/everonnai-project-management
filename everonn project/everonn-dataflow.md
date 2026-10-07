# EverOnn End-to-End Data Flow

**Document basis:** EverOnn Business Requirements and Technical Specification v1.0  
**Classification:** Confidential

## End-to-End Data Flow

This flow shows how a business moves from setup to live customer handling, human escalation, owner follow-up, billing, and continuous quality improvement.

```mermaid
%%{init: {
  "theme": "base",
  "flowchart": {
    "curve": "linear",
    "nodeSpacing": 30,
    "rankSpacing": 46,
    "htmlLabels": false
  }
}}%%
flowchart TB

    subgraph SETUP["1. Business Setup and Activation"]
        direction LR
        S1["Business joins or switches to EverOnn"]
        S2["Private preview and draft business profile"]
        S3["Owner verifies ownership"]
        S4["Owner approves knowledge, rules and handoff preferences"]
        S5["Connect phone, website chat, SMS and billing"]
        S6["Business goes live"]
        S1 --> S2 --> S3 --> S4 --> S5 --> S6
    end

    subgraph INTAKE["2. Customer Interaction Intake"]
        direction LR
        I1["Customer calls, chats, texts or submits a form"]
        I2["Resolve tenant, brand, line and channel"]
        I3["Load consent, hours, agent version and approved configuration"]
        I1 --> I2 --> I3
    end

    subgraph AI["3. AI Front Desk Processing"]
        direction LR
        A1["Greet in the client's business name"]
        A2["Use approved knowledge and policies"]
        A3["Capture customer and job details"]
        A4["Check availability, booking rules and allowed actions"]
        A5{"Can the AI complete the request safely?"}
        A1 --> A2 --> A3 --> A4 --> A5
    end

    subgraph COMPLETE["4A. AI Completes the Request"]
        direction LR
        C1["Answer the question"]
        C2["Create structured request"]
        C3["Book appointment or schedule callback"]
        C1 --> C2 --> C3
    end

    subgraph HUMAN["4B. Human Handoff"]
        direction LR
        H1["Create escalation with reason, severity and context"]
        H2["Select eligible operator or owner"]
        H3["Show client identity, greeting, caller and AI-captured context"]
        H4["Human continues the conversation"]
        H5["Wrap up outcome and notes"]
        H1 --> H2 --> H3 --> H4 --> H5
    end

    subgraph FALLBACK["4C. Safe Fallback"]
        direction LR
        F1["No human accepts in time"]
        F2["Try next pool or client owner"]
        F3["Capture message and promise callback"]
        F1 --> F2 --> F3
    end

    subgraph RESULT["5. Save Result and Serve the Client"]
        direction LR
        R1["Store conversation, transcript, recording and structured request"]
        R2["Place item in unified inbox"]
        R3["Send owner summary and notifications"]
        R4["Run booking confirmation and consent-aware follow-up"]
        R1 --> R2 --> R3 --> R4
    end

    subgraph PLATFORM["6. Platform Processing"]
        direction LR
        P1["Meter voice, messaging, operator and site usage"]
        P2["Update subscription, billing and margin reporting"]
        P3["Sample for QA and safety review"]
        P4["Update analytics and proof-of-value reporting"]
        P1 --> P2
        P3 --> P4
    end

    subgraph IMPROVE["7. Continuous Improvement"]
        direction LR
        Q1["Flag wrong answer, missing fact or poor outcome"]
        Q2["Propose knowledge or playbook change"]
        Q3["Run evaluation and regression gates"]
        Q4["Approve, publish and version the change"]
        Q1 --> Q2 --> Q3 --> Q4
    end

    S6 --> I1
    I3 --> A1

    A5 -->|"Yes"| C1
    A5 -->|"Human needed"| H1

    H2 -->|"No eligible human"| F1

    C3 --> R1
    H5 --> R1
    F3 --> R1

    R1 --> P1
    R1 --> P3
    R4 --> P4

    P3 --> Q1
    Q4 --> A2

    classDef setup fill:#EEF6FF,stroke:#3B82F6,color:#172554,stroke-width:1px;
    classDef intake fill:#F8FAFC,stroke:#64748B,color:#0F172A,stroke-width:1px;
    classDef ai fill:#ECFEFF,stroke:#0891B2,color:#164E63,stroke-width:1.2px;
    classDef decision fill:#FFF7ED,stroke:#EA580C,color:#7C2D12,stroke-width:1.4px;
    classDef human fill:#FEF3C7,stroke:#D97706,color:#78350F,stroke-width:1px;
    classDef result fill:#ECFDF5,stroke:#059669,color:#064E3B,stroke-width:1px;
    classDef platform fill:#F5F3FF,stroke:#7C3AED,color:#3B0764,stroke-width:1px;
    classDef improve fill:#FDF2F8,stroke:#DB2777,color:#831843,stroke-width:1px;

    class S1,S2,S3,S4,S5,S6 setup;
    class I1,I2,I3 intake;
    class A1,A2,A3,A4 ai;
    class A5 decision;
    class C1,C2,C3 result;
    class H1,H2,H3,H4,H5,F1,F2,F3 human;
    class R1,R2,R3,R4 result;
    class P1,P2,P3,P4 platform;
    class Q1,Q2,Q3,Q4 improve;
```

## Data Flow Summary

1. **Business setup:** a prospect receives a private preview, verifies ownership, approves business knowledge and handoff rules, connects channels, and goes live.
2. **Customer intake:** every call, chat, SMS, or form is mapped to the correct tenant, brand, line, configuration, and consent state.
3. **AI handling:** the AI answers in the client's name, uses only approved knowledge, captures structured details, and performs only permitted actions.
4. **Human handoff when required:** an eligible owner or EverOnn operator receives the correct client identity and conversation context before taking over.
5. **Safe fallback:** if nobody accepts in time, the platform continues the escalation cascade and ultimately captures a message with a callback promise.
6. **Unified result:** conversation data, transcript, recording, summary, and structured request are stored and surfaced in one inbox.
7. **Notifications and follow-up:** the owner is informed quickly; booking confirmations and consent-aware follow-up continue automatically.
8. **Metering and billing:** billable usage is recorded and feeds subscription, allowance, cost, and margin reporting.
9. **Quality improvement:** selected interactions are reviewed; wrong answers and missing facts become proposed knowledge or playbook changes that must pass evaluation before release.
