# System Overview

The Programmatic MD&A Workflow automates the quarterly process of generating management discussion and analysis narratives. It replaces an inconsistent, manual process with a structured pipeline that collects data, generates analysis, reviews for bias, and assembles a finished document.

---

## Core Design Principles

**Automate collection, not judgment.** The system automates data gathering, normalization, and initial analysis. Humans remain in the loop for all judgment calls about what the data means and how it should be framed.

**Break analysis into small, testable pieces.** Rather than asking AI to write an entire narrative from a massive dataset, the system extracts atomic findings first, analyzes each one individually, and assembles the final narrative from reviewed pieces.

**Bias detection is built in, not bolted on.** One of the three AI passes exists solely to challenge the output for positive spin, contradictions, and unsupported claims. This runs before any human sees the output.

**Queryable after delivery.** The final document and all raw inputs are uploaded to NotebookLM so leadership can ask follow-up questions conversationally rather than requesting another report.

---

## System Components

| Component | Purpose |
|---|---|
| Trigger and Collection | Time-based trigger sends forms and pulls API data at end of quarter |
| Normalization | Merges qualitative and quantitative inputs into a single dataset |
| Atomic Findings | AI extracts discrete, testable statements from the normalized data |
| Three-Pass Analysis | So-what analysis, contradiction detection, and bias review |
| Human Review | Leaders approve, edit, or reject findings before assembly |
| Document Assembly | AI drafts narrative blocks assembled into a Google Doc |
| NotebookLM Upload | Final output and raw data pushed to NotebookLM for conversational querying |

---

[Back to MD&A Workflow](../README.md)
