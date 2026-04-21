# Project Crosstalk: Customer Intelligence Platform

Turning thousands of hours of customer conversations into actionable strategic intelligence.

---

## The Problem

Trimble's sales teams were sitting on information they could not access.

Every day, sellers were having detailed conversations with customers. Those conversations contained competitive intelligence, product feedback, unmet needs, buying signals, and candid language that no survey or CRM field would ever capture. But the information lived in call recordings and email threads, scattered and unsearchable, invisible to the business.

The starting hypothesis was narrow: sellers trained on one product line were probably missing opportunities to flag needs to other teams. Could we listen for those signals and route them to the right seller? The bigger question turned out to be much more valuable.

---

## Outcomes

- Approximately $3M in estimated sales influence in 2025, spanning lead identification, opportunity acceleration, and deal support
- Research timelines for product marketing and sales enablement teams reduced from weeks to days
- Analysis that would require a team of analysts weeks to compile is now produced in one to two days
- Spawned Project Higgs, a downstream system using the same architecture focused on board-level narratives and QBR preparation
- Three years in production and still actively used for strategic analysis

---

## Repo Structure

```
project-crosstalk/
├── architecture/
│   ├── system-overview.md       # How the system fits together
│   ├── data-flow.md             # Mermaid diagram of end-to-end data flow
│   └── prompt-pipeline.md       # How the AI analysis pipeline is structured
├── components/
│   ├── environment-setup/       # Runtime initialization and configuration
│   ├── ingestion/               # Data collection from Gong and Salesforce
│   ├── snippet-extraction/      # Context isolation before AI ingestion
│   ├── analysis-pipeline/       # AI-driven insight generation
│   └── output-layer/            # Formatted report delivery
└── docs/
    └── design-decisions.md      # Key tradeoffs and architectural choices
```

---

## Quick Links

- [System Overview](./architecture/system-overview.md)
- [Data Flow Diagram](./architecture/data-flow.md)
- [Prompt Pipeline Design](./architecture/prompt-pipeline.md)
- [Design Decisions](./docs/design-decisions.md)

---

[Back to portfolio](../README.md)
