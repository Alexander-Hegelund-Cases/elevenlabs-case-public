[🏠 Home](../README.md) > [📁 02-customers-and-use-cases](README.md) > 📄 discovery-questions.md

# FDE Discovery Question Bank

To maximize the success of our DACH Telecom Flagship Scenario (Tier-1 Support Deflection), a Strategic FDE does not lead with features; they lead with systemic gap analysis. 

The questions below represent the core discovery track used during the initial Technical Kickoff Workshop with the customer's Voice/CCaaS engineers and compliance officers.

## 1. Network Architecture & Latency Budgets
*The goal is to sniff out network topologies that will destroy our <200ms Time-To-First-Audio (TTFA) mandate before we ever hit production.*

1. **SIP Termination**: Are your entry nodes terminating SIP traffic locally (e.g., Frankfurt/Zurich), or is there transatlantic routing happening in your legacy CCaaS provider before it hits our agent?
2. **Codec Standards**: Are your internal phone lines standardized on G.711 (PCMA/PCMU), or are you supporting Opus? Have you experienced transcoding penalties?
3. **Firewalls & Whitelisting**: Does your InfoSec team require static IP whitelisting for our SIP trunks, or do you support dynamic resolution via SRV records?

## 2. Compliance & Data Governance
*The goal is to prevent the "11th-hour compliance assassination" by addressing GDPR Article 9 directly.*

1. **Biometric Stance**: Does your legal team classify speech-to-speech audio as "biometric data" by default (requiring explicit opt-in), or do they only classify it as such if identity verification is actively occurring?
2. **The Zero-Retention Guarantee**: If we configure ElevenLabs to "Zero-Retention Mode" (no audio stored, transient memory only), does this bypass your requirement for an on-prem deployment?
3. **Redaction Requirements**: For transcript telemetry required to train the agent, do you have an upstream PII-redaction proxy, or are we expected to scrub Credit Card / ID numbers dynamically via LLM tooling?

## 3. Workflow & Tool Execution
*The goal is to map the boundaries of what the Agent is actually allowed to do.*

1. **The 'Deflection' Boundary**: In terms of state-mutation versus read-only workflows: Is this agent only allowed to *read* a customer's billing status via an API, or is it authorized to actively process a refund transaction?
2. **Handoff Mechanics**: If the agent detects high frustration or fails hallucination rails, what is the exact SIP header syntax (e.g., `UUI` or `X-` headers) required to pass the call metadata back to a human queue?
3. **Knowledge Base Volatility**: How frequently does the ground-truth technical documentation change? Are we pulling dynamically via RAG upon every call, or synchronizing daily into the Agent's specific memory banks?

## 4. Evaluation (The CI/CD "Evals" Rig)
*The goal is to establish the mathematical Definition of Done.*

1. **Baseline SLA**: What is the current human Average Handle Time (AHT) and First Contact Resolution (FCR) rate for this specific call queue? What constitutes a "win" for the bot?
2. **Failure Vectors**: Can we define the top 3 critical failure states (e.g., "Bot hallucinates a non-existent roaming package") so we can build deterministic regression tests for them before launch?

---

## 📚 Local Glossary:

_Consult the [Global Glossary](../docs/GLOSSARY.md) for the full list of terms used in this repo._

- **AHT (Average Handle Time)** (The total time a customer spends on a support call.)
- **DACH** (Region encompassing Germany (D), Austria (A), and Switzerland (CH).)
- **FCR (First Contact Resolution)** (The percentage of customer issues resolved without requiring an escalation or a callback.)
- **GDPR Article 9** (Explicitly governs the processing of "special categories of personal data," heavily restricting the capture and retention of human biometrics (including voice profiles).)
- **RAG (Retrieval-Augmented Generation)** (Architecture pattern linking LLMs to private databases (like a Neo4j Graph Database) to enforce deterministic, factual context prior to text synthesis.)
- **SIP (Session Initiation Protocol)** (The legacy signaling protocol utilized for maintaining real-time telephonic voice sessions (phone calls).)
- **TTFA (Time-To-First-Audio)** (The rigid latency metric calculating the explicit millisecond network delay from when a user finishes speaking to when the first synthesized audio byte returns.)
---
**🧭 Navigation**: Review [JTBD](jobs-pains-gains.md) | [Back to Home](../README.md)
