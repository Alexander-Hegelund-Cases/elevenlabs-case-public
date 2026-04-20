# The DACH Telecom & Voice AI Glossary

This global glossary defines the strict vocabulary utilized across this ElevenLabs FDE Strategic Sprint. It standardizes the semantic layer across Commercial, Regulatory, and Infrastructure vectors.

## A - E
*   **ACV (Annual Contract Value)**: The normalized revenue a customer generates in a single year. FDEs operate to unblock seven-factor ACV deals.
*   **AHT (Average Handle Time)**: The total time a customer spends on a support call. Voice proxies drive value by slashing AHT.
*   **Barge-in**: The ability for a human user to interrupt the AI agent mid-sentence, triggering a hard cancellation of the active TTS stream and recalculating the audio interface input based on the new visual or audio context. Strict Voice Activity Detection (VAD) is required.
*   **DACH**: Region encompassing Germany (D), Austria (A), and Switzerland (CH). The primary strategic growth vector for European enterprise software defined by extreme regulatory constraints and deep dialectal variances.
*   **DORA (Digital Operational Resilience Act)**: An EU regulation enforcing strict disaster recovery, fallback, and SLA resilience for financial entities and their ICT providers.

## F - R
*   **FCR (First Contact Resolution)**: The percentage of customer issues resolved without requiring an escalation or a callback.
*   **GDPR Article 9**: Explicitly governs the processing of "special categories of personal data," heavily restricting the capture and retention of human biometrics (including voice profiles). Enterprise AI fails without explicit architectural compliance.
*   **Knowledge Dissonance**: The failure state where a generative AI possesses extremely human conversational cadence but hallucinates or lacks access to the exact deterministic business facts (e.g. an account balance). Solved via rigorous tool calling.
*   **RAG (Retrieval-Augmented Generation)**: Architecture pattern linking LLMs to private databases (like a Neo4j Graph Database) to enforce deterministic, factual context prior to text synthesis.

## S - Z
*   **Schrems II**: A landmark legal ruling enforcing that European civilian data accessing US-owned servers remains highly legally porous, thereby enforcing strict Data Localization (using EU-anchored servers) for Tier-1 institutions.
*   **SIP (Session Initiation Protocol)**: The legacy signaling protocol utilized for maintaining real-time telephonic voice sessions (phone calls).
*   **SIP Trunking**: The digital highway connecting an organization's internal PBX system to the public telephone network via the internet.
*   **TTFA (Time-To-First-Audio)**: The rigid latency metric calculating the explicit millisecond network delay from when a user finishes speaking to when the first synthesized audio byte returns. (<200ms is the "Gold Standard" to emulate genuine human conversation).
*   **WebRTC**: An open-source protocol universally providing web browsers and mobile applications with real-time audio and video communications capabilities. Often the bridge protocol sitting between ElevenLabs API boundaries and SIP infrastructure.
*   **Zero-Retention Architecture**: The strictest enterprise deployment posture where Audio/Biometric payloads are securely processed in RAM uniquely for immediate ASR/Transcription, and then permanently obliterated without ever hitting persistent disc storage.
