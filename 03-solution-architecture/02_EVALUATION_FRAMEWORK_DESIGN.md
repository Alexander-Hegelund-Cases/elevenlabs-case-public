[🏠 Home](../README.md) > [📁 03-solution-architecture](README.md) > 📄 02_EVALUATION_FRAMEWORK_DESIGN.md

# Solution Architecture: Automated Evaluation Framework (Evals)

## 1. The Problem: "Going Rogue" in Production
A "cool voice" is a liability if the agent hallucinates or uses non-branded language in a regulated environment like DACH Telecommunications. To unblock Staff-level pilots, we must prove **Reliability via Evals**.

## 2. The Eval Stack (Braintrust & Local Parallel)
We implement a multi-layered evaluation suite that runs on every deployment cycle and mid-call update. To ensure transparency, we maintain a dual-execution model: you can run the pure local JSON harness, or hook it into Braintrust for enterprise visualization.

> [!TIP]
> **Live Demonstration (Proof of Work):** We have successfully executed the automated evaluation harness (`03_braintrust_eval_pipeline.py`), capturing a **90% Baseline Pass Rate** across all dialect edge-cases. The raw CI verification trace has been exported from the Braintrust dashboard and is permanently anchored in the repository here: [`../04-flagship-scenario/eval_results.json`](../04-flagship-scenario/eval_results.json).

| Eval Metric | Technique | Strategic Signal |
| :--- | :--- | :--- |
| **First Contact Resolution (FCR)** | LLM-as-a-Judge | Proves the bot actually solved the user's problem without human routing. |
| **Dialect Intelligibility** | Factuality / Match | Proves the Speech-to-Standard pipeline understands Swiss-German and Austrian. |
| **Regulatory Guardrail** | Semantic Similarity Check | Ensures the bot doesn't mention prohibited actions or bypass JWT auth scopes. |
| **Latency Budget Compliance** | TTFA Logging | Flags any WebSocket event that exceeds the **200ms budget**. |

## 3. The "Golden Dataset" Strategy
We maintain a "Golden Dataset" (`04-flagship-scenario/02_DACH_GOLDEN_DATASET.json`) of core telecommunications scenarios, including noisy environments and heavy code-switching.
- **Continuous Assessment**: Automated regression testing via `03_braintrust_eval_pipeline.py`.
- **Human-in-the-Loop (HITL)**: Periodic expert review of "low-confidence" dialect classifications.

## 4. Operationalizing Evals
Evals are not a "side project"; they are a **Production Gate**.
- **The Red-Line**: No deployment to the Swiss/Austrian Telecom pilot occurs if the **FCR Confidence Score** drops beneath 90%.
- **Fail-Forward**: If the live eval detects an intent drift or dialect confusion (confidence < 0.82) during a session, the **Fail-Forward loop** triggers an immediate human handoff.

---

## 📚 Local Glossary:

_Consult the [Global Glossary](../docs/GLOSSARY.md) for the full list of terms used in this repo._

- **FCR (First Contact Resolution)**: The percentage of customer issues resolved without requiring an escalation or a callback.
- **TTFA (Time-To-First-Audio)**: The rigid latency metric calculating the explicit millisecond network delay from when a user finishes speaking to when the first synthesized audio byte returns.
- **Braintrust**: The enterprise evaluation and prompt-engineering platform used for tracking model regressions.
---
**🧭 Navigation**: Review the [Next File](data-governance-and-risk-notes.md) | [Back to README](../README.md)
