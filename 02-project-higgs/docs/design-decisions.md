# Design Decisions

Key architectural tradeoffs made in building Project Higgs.

---

## Reusing Crosstalk Instead of Building New

**Decision:** Use the Crosstalk snippet extraction engine for the customer evidence component rather than building a separate system.

**Why:** The extraction and analysis pipeline was already proven, tested, and reliable. Building a new one would have duplicated effort without adding value.

**Why it matters:** This demonstrates the composability of the original Crosstalk architecture. A system designed with discrete, reusable components can serve multiple use cases without modification. Project Higgs exists partly because Crosstalk was designed well enough to be extended.

---

## Google Colab for Development Speed

**Decision:** Build and run the system in Google Colab, consistent with the Crosstalk approach.

**Why:** Speed of iteration matters more than automation at this stage. The system runs quarterly, not daily. Manual initiation is acceptable for a quarterly cadence.

**If rebuilt today:** An n8n workflow or Flask application would allow the system to run on a schedule and be operated by someone other than the architect. See the [MD[MD&A Workflow project](../../project-mda-workflow/)A Workflow project](../../05-mda-workflow-(aspirational)/) for an example of this approach.

---

## Positive Framing by Design

**Decision:** Focus the customer evidence component on positive examples of the initiative working.

**Why:** This was a stakeholder-driven scoping decision. The immediate need was evidence to include in board narratives that demonstrated progress on strategic initiatives.

**Tradeoff:** Excluding negative signals introduces selection bias. The system shows where things are working but not where they are failing. This limits its value as a true diagnostic tool.

**Mitigation:** The system is fully capable of surfacing negative signals with a configuration change. Expanding to include counterexamples is a planned next step.

---

## Multi-Pass Bias Review

**Decision:** Include a dedicated bias review pass in the AI pipeline specifically to counteract LLM positive framing.

**Why:** LLMs default to optimistic, enthusiastic language. Board materials written in that tone read like marketing and lose credibility. The bias review pass forces the model to challenge its own output before a human sees it.

**Why it was worth it:** Adding a fourth pass increases token cost and pipeline complexity. But the improvement in output credibility justifies it. Leadership trusts the output more because it reads as balanced rather than promotional.

---

[Back to Project Higgs](../README.md)
