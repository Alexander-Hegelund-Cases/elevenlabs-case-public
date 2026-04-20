[🏠 Home](../README.md) > [📁 02-customers-and-use-cases](README.md) > 📄 use-case-prioritization.md

# Use-Case Prioritization Matrix

The core responsibility of a Strategic FDE is separating *technical distractions* from *enterprise value*. This matrix filters ElevenLabs' functional capabilities (Agents, API, Creative) against the dual mandates of **Commercial Impact** and **Integration Gravity**.

## 1. The EU Opportunity Backlog (Top 10)
Based on Perplexity market guidelines, we evaluated 10 concrete EU vectors. We score them across **Commercial Impact (ACV)** and **Integration Gravity (Technical FDE Requirement)** to determine the ultimate flagship prototype.

| Rank | EU Use Case Archetype | ACV Potential | Integration Gravity / Compliance Risk | FDE Flagship Viability |
| :--- | :--- | :--- | :--- | :--- |
| **1** | **DACH Telecom/Banking CX (Voice Agent)** | **Extremely High** | **Extreme** (Legacy SIP, GDPR Art 9, <200ms TTFA, Multi-Dialect) | **10/10 (Selected Flagship)** |
| **2** | Pan-EU Logistics Fleet Dispatch | High | High (Noisy environment VAD, Edge latency) | 8/10 |
| **3** | Automotive Dealership Outbound (Bavarian Region) | High | Medium (CRM connection, Dialect Heavy) | 7.5/10 |
| **4** | Medical Triage & Appointment Booking | Medium | Extreme (HIPAA / GDPR Art 9 Health Data) | 7/10 |
| **5** | Public Sector / Gov Deflection Desks | High | Extreme (On-Prem/Sovereign Cloud mandate) | 6.5/10 |
| **6** | Hospitality & Luxury Travel Concierge | Medium | Low (Standard API, WebRTC) | 5/10 |
| **7** | IT Helpdesk (Password Reset, SSO) | Medium | Medium (Internal Auth, Active Directory) | 5/10 |
| **8** | E-Commerce Post-Purchase Returns | Low | Low (Standard REST API) | 4/10 |
| **9** | Utilities Outage Reporting | Low | Low (Spiky volume, standard IVR replacement) | 3/10 |
| **10** | Smart Home Assistant (IoT UI) | Variable | Low (Developer API integration) | 2/10 |

## 2. Flagship Scenario Lock-in (Why #1 Wins)
We selected **DACH Telecom CX Deflection** as our flagship discovery scenario because it possesses the highest requirement for *sub-minute determinism* and the most brutal risk parameters. 

This scenario forces us to solve the hardest problems directly at the intersection of AI Research and Enterprise IT:
*   Overcoming the **Curse of Multidialectality**: We must build speech-to-speech bridging that can handle **Swiss-German**, **Austrian German (Wienerisch)**, and **Bavarian (Bairisch)** identically to standard High-German.
*   Solving the **Transatlantic Penalty** latency budgets (WebRTC to PSTN legacy integrations).
*   Enabling **Zero-Retention Mode** to bypass strict EU biometric compliance audits.

---

## 📚 Local Glossary:

_Consult the [Global Glossary](../docs/GLOSSARY.md) for the full list of terms used in this repo._

- **DACH** (Region encompassing Germany (D), Austria (A), and Switzerland (CH).)
- **SIP (Session Initiation Protocol)** (The legacy signaling protocol utilized for maintaining real-time telephonic voice sessions (phone calls).)
- **TTFA (Time-To-First-Audio)** (The rigid latency metric calculating the explicit millisecond network delay from when a user finishes speaking to when the first synthesized audio byte returns.)
- **WebRTC** (An open-source protocol universally providing web browsers and mobile applications with real-time audio and video communications capabilities.)
---
**🧭 Navigation**: Review [Discovery Questions](discovery-questions.md) | [Back to Home](../README.md)
