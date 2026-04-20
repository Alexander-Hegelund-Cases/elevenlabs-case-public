[🏠 Home](../README.md) > [📁 04-flagship-scenario](README.md) > 📄 mock-interaction-transcripts.md

# Flagship AI: Mock Interaction Transcripts

> [!NOTE]  
> **Strategic Intent:** This document maps the exact tool-calling orchestration required to resolve the SIM Activation use case. It explicitly defines the "Friction Paths" (Barge-in and Context Drift) where legacy IVRs fail and LLM Agents succeed.

## Scenario 1: The Happy Path (Autonomous Provisioning)
*The caller explicitly follows the guided path to completion.*

**[AI]**: Guten Tag, Thomas. I see you’ve received a new SIM card for your Magenta Mobil plan. Would you like to activate it now?
**[Caller]**: Yes, please activate it.
**[AI - *[TOOL CALL: Send_OTP]*]**: For your security, I’ve just sent an SMS code to your secondary mobile number. Please read those four digits back to me.
**[Caller]**: 4, 8, 2, 1.
**[AI - *[TOOL CALL: Validate_OTP]*]**: Perfect. Could you please read the last five digits of the new SIM card number starting with 8-9-4-9?
**[Caller]**: 3, 2, 1, 9, 0.
**[AI - *[TOOL CALL: Provision_SIM_HSS]*]**: Thank you. I am activating your service now. This will take about 5 seconds... Okay, your 5G data and roaming within the EU are now active. Is there anything else I can help with?

---

## Scenario 2: The "Topic Drift" (Context Switching)
*The caller abruptly pivots the conversation to a completely different domain mid-flow. A legacy IVR would reset or hang up. The LLM handles the scope-shift via tool routing.*

**[AI]**: I see you’ve received a new SIM card for your Magenta Mobil plan. Would you like to activate it now?
**[Caller]**: Wait, before we do that, why was my last bill 5 Euros more?
**[AI - *[PAUSE SIM_FLOW: TRUE]* -> *[TOOL CALL: Fetch_Billing_Variance]*]**: Ah, let me check. That 5 Euro difference was a one-time data pass you purchased on August 14th while traveling. Does that make sense?
**[Caller]**: Oh right, I forgot. Yeah, that's fine.
**[AI - *[RESUME SIM_FLOW: TRUE]*]**: No problem. So, shall we get back to activating that new SIM card?
**[Caller]**: Yes let's do it.

---

## Scenario 3: The DACH "Barge-in" (Linguistic Friction)
*The caller interrupts the AI during a long-winded compliance output. The VAD (Voice Activity Detection) must trigger under 100ms to halt the TTS buffer.*

**[AI]**: Thank you. I am activating your service now. Before we finalize, please note that international roaming outside of the European Union carries standard zone—
**[Caller - *[BARGE-IN TRIGGERED: TTS CANCELLED]*]**: Yeah, yeah, I already read the roaming terms, just activate.
**[AI]**: Understood, skipping the terms. And we are complete. Your SIM is active.

---

## 📚 Local Glossary:

_Consult the [Global Glossary](../docs/GLOSSARY.md) for the full list of terms used in this repo._

- **Barge-in** (The ability for a human user to interrupt the AI agent mid-sentence, triggering a hard cancellation of the active TTS stream and recalculating the audio interface input based on the new visual or audio context.)
- **DACH** (Region encompassing Germany (D), Austria (A), and Switzerland (CH).)
---
**🧭 Navigation**: Review [Implementation Plan](01_PROTOTYPE_IMPLEMENTATION_PLAN.md) | [Back to Home](../README.md)
