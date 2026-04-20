[🏠 Home](../README.md) > [📁 02-customers-and-use-cases](README.md) > 📄 jobs-pains-gains.md

# Jobs, Pains, and Gains (JTBD)

A Strategic FDE must understand that the "Customer" is not a monolith. For our flagship scenario (DACH Telecom/Banking CX), we must solve for two distinct personas: **The Executive Buyer** (who cares about business ROI and risk) and **The Technical Sponsor** (who cares about deployment latency and integration friction).

## Persona 1: The Executive Buyer
*e.g., VP of Customer Operations / Head of Digital Transformation*

| Core Dimension | Description & Examples |
| :--- | :--- |
| **Primary Job-to-be-Done** | Radically reduce Tier-1 operational costs by deflecting repetitive support calls without sacrificing Customer Satisfaction (CSAT) or violating aggressive EU data privacy laws. |
| **Pains** | **1. The "Press 1" Penalty**: Existing legacy IVR phone trees infuriate customers and cause high abandonment rates.<br>**2. The Compliance Blocker**: They cannot deploy standard US-based cloud AI because voice data triggers GDPR Article 9 (Biometric Data) strict-scrutiny.<br>**3. Cost Volatility**: Human agent availability scales poorly during network outages, leading to huge spike costs. |
| **Gains** | **1. Uncapped Elasticity**: An agent that answers instantly 24/7 during a localized internet outage.<br>**2. Compliance Zero-trust**: Successfully passing the Risk/Audit committee with a "Zero-Retention" vendor architecture.<br>**3. NPS Protection**: A voice agent so natural that older demographics do not realize they are speaking to software. |

## Persona 2: The Technical Sponsor
*e.g., Lead Voice Engineer / CCaaS Solutions Architect*

| Core Dimension | Description & Examples |
| :--- | :--- |
| **Primary Job-to-be-Done** | Integrate a bleeding-edge AI system into a 15-year-old, heavily fortified on-premises SIP/telephony network predictably. |
| **Pains** | **1. The "Barge-in" Collision Limit**: Cloud LLM vendors routinely hit >700ms latencies, causing awful conversational collisions where the AI and human talk over each other.<br>**2. Middleware Nightmares**: Building custom WebSocket-to-SIP translation layers just to get the audio out of the cloud and into the call center platform (e.g., Genesys, Avaya).<br>**3. "Black-Box" Evals**: The inability to deterministically test whether an AI agent will hallucinate a fake billing policy during a high-stress call. |
| **Gains** | **1. Native SIP Trunking**: A platform that provides a direct SIP URI and IP whitelisting so the AI agent acts exactly like a traditional internal phone line.<br>**2. The <200ms Standard**: Hitting Time-to-First-Audio (TTFA) targets so fast that turn-taking feels physically natural.<br>**3. Programmatic Telemetry**: Deterministic logs and transcriptions that allow the engineer to build CI/CD evaluation pipelines before rolling out to production. |

---

## 📚 Local Glossary:

_Consult the [Global Glossary](../docs/GLOSSARY.md) for the full list of terms used in this repo._

- **Barge-in** (The ability for a human user to interrupt the AI agent mid-sentence, triggering a hard cancellation of the active TTS stream and recalculating the audio interface input based on the new visual or audio context.)
- **DACH** (Region encompassing Germany (D), Austria (A), and Switzerland (CH).)
- **GDPR Article 9** (Explicitly governs the processing of "special categories of personal data," heavily restricting the capture and retention of human biometrics (including voice profiles).)
- **SIP (Session Initiation Protocol)** (The legacy signaling protocol utilized for maintaining real-time telephonic voice sessions (phone calls).)
- **SIP Trunking** (The digital highway connecting an organization's internal PBX system to the public telephone network via the internet.)
- **TTFA (Time-To-First-Audio)** (The rigid latency metric calculating the explicit millisecond network delay from when a user finishes speaking to when the first synthesized audio byte returns.)
---
**🧭 Navigation**: Review the [Next File](use-case-prioritization.md) | [Back to README](../README.md)
