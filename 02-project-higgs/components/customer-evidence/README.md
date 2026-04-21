# Component: Customer Evidence

## Purpose

The customer evidence component surfaces real, candid customer quotes that demonstrate whether Trimble's customer adoption initiative is working.

---

## How It Works

This component reuses the Crosstalk snippet extraction engine. It scans across the full Gong transcript database for customer mentions of customer adoption initiative related topics. Internal speakers are filtered out so the analysis reflects only the customer voice.

Each extracted quote is categorized by:
- Product being discussed
- Customer vertical
- Speaker title and role
- Sentiment and relevance

The output is a curated library of quotes ready for direct inclusion in board narratives. These are candid statements from real customer conversations, not marketing-approved testimonials.

---

## Design Notes

The current implementation focuses on positive examples of the initiative working. This was a deliberate scoping decision made by the project stakeholder. The system is fully capable of surfacing negative signals as well. Expanding to include counterexamples would provide a more complete picture and is a natural next step.

Reusing the Crosstalk engine rather than building a new extraction system was a key architectural decision. It demonstrates the composability of the original Crosstalk design: the same snippet extraction and analysis pipeline can serve multiple use cases without modification.

---

[Back to Project Higgs](../../README.md)
