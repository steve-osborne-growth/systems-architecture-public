# System Overview

Project Crosstalk is a customer intelligence platform built to extract strategic insight from customer conversations at scale.

The system connects to live data sources, isolates relevant signal from large volumes of raw text, runs that signal through a structured AI analysis pipeline, and delivers packaged outputs to business stakeholders.

---

## Core Design Principles

**Signal over noise.** The system never ingests full transcripts into the AI layer. It isolates only the relevant context before analysis begins. This keeps outputs accurate and reduces cost.

**Multi-pass analysis.** No single prompt produces the final output. Each analysis runs through distinct stages: extraction, synthesis, audit, and packaging. Each stage has a defined job.

**Human-in-the-loop.** Key outputs are reviewed before delivery. The system is designed to assist human judgment, not replace it.

**External voice only.** Internal speaker turns are filtered out at the ingestion stage. Analysis reflects what customers said, not what sellers said.

**Composable architecture.** The system is built in discrete components. Each component can be updated, replaced, or reused independently. Project Higgs, a downstream system, was built by reusing core components from Crosstalk.

---

## System Components

| Component | Purpose |
|---|---|
| Environment Setup | Initializes runtime, installs dependencies, mounts storage, loads credentials |
| Ingestion | Pulls raw transcripts and metadata from Gong and Salesforce |
| Snippet Extraction | Scans transcripts for target signals and isolates relevant context windows |
| Analysis Pipeline | Runs multi-pass AI analysis across extracted snippets |
| Output Layer | Packages results into Excel, PDF, or Google Sheets for stakeholder delivery |

---

## How the Components Connect

See the [data flow diagram](./data-flow.md) for a visual map of how data moves through the system from source to output.

---

[Back to Project Crosstalk](../README.md)
