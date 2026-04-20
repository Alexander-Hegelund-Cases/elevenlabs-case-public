[🏠 Home](../README.md) > [📁 02-customers-and-use-cases](README.md) > 📄 02_USE_CASE_CLASSIFICATION.md

# Use Case Classification & The OPEX Equation

> [!NOTE]  
> **Strategic Intent:** Technology looking for a problem fails. This file proves that the target Flagship Prototype (SIM Activation with WebRTC) is not chosen randomly, but mathematically derived from the "Deflection-Resolution Gap" currently hemorrhaging OPEX in Tier-1 DACH Telecoms.

## 1. The OPEX Hemorrhage Equation
In a Tier-1 telecommunications environment, Call Center OPEX is a dynamic metric governed by Volume, Average Handle Time (AHT), and First Contact Resolution (FCR).

The mathematical reality is:
> $$OPEX_{Total} = \sum (V_i \times AHT_i \times C_{min}) + (V_i \times (1 - FCR_i) \times C_{repeat})$$

*   $C_{min}$ = Agent cost per minute.
*   $(1 - FCR_i)$ = The *Deflection-Resolution Gap* (The user was deflected by an old IVR, but the problem wasn't resolved, so they call back and cost the company $C_{repeat}$).

## 2. Target Selection Matrix
We mapped the primary 2025 DACH call drivers against the OPEX equation to identify the optimal integration targets for ElevenLabs Conversational AI.

| Call Driver | Volume | AHT | Legacy IVR FCR | ElevenLabs AI Suitability |
| :--- | :--- | :--- | :--- | :--- |
| **Billing Disputes** | 25-30% | 10–15m | **65-75%** | **Perfect Fit** - Non-linear semantic interpretation required. |
| **SIM Activation** | 15-20% | 6–8m | **75-80%** | **Flagship Target** - Extreme abandonment rate with DTMF keypads. Voice capture eliminates the friction. |
| **Technical Outage** | Spiky | 3-5m | **85-90%** | **Poor Fit** - Massive concurrency handled easily by stateless IVR alerts. |

## 3. The "ElevenLabs Fit" Rationale
We selected **SIM Activation** as the primary POC for this repository because it possesses the highest requirement for *sub-minute determinism*. 

Why Legacy Phone Trees Fail at SIM Activation:
*   Users hate typing 19-digit ICCID numbers into keypads. The dropout rate hits 35%.
*   If the CRM provisioning fails, legacy IVRs route the user into a hold queue. 

By wrapping ElevenLabs around the CRM API using a sub-200ms WebRTC connection, the user reads the ICCID naturally, is authenticated via SMS token, and the AI provisions the SIM live on the call.

---

## 📚 Local Glossary:

_Consult the [Global Glossary](../docs/GLOSSARY.md) for the full list of terms used in this repo._

- **AHT (Average Handle Time)** (The total time a customer spends on a support call.)
- **DACH** (Region encompassing Germany (D), Austria (A), and Switzerland (CH).)
- **FCR (First Contact Resolution)** (The percentage of customer issues resolved without requiring an escalation or a callback.)
- **WebRTC** (An open-source protocol universally providing web browsers and mobile applications with real-time audio and video communications capabilities.)
---
**🧭 Navigation**: Review the [Next File](03_CASE_CANDIDATE_SWOT.md) | [Back to README](../README.md)
