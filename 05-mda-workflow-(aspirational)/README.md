# Programmatic MD&A Workflow

An automated system for generating quarterly management discussion and analysis narratives, from data collection through bias review to final document assembly.

*Status: Aspirational. Full prototype designed and architecture defined. Awaiting implementation.*

---

## The Problem

Every quarter, Trimble produces a management discussion and analysis for its annual report. The process has no standardization. Business leaders submit information in different formats, on different timelines, and with different levels of completeness. The materials arrive late. The quality is inconsistent. There is no way to compare this quarter's narrative against previous quarters to identify trends or validate past projections.

The goal is to automate as much of this process as possible while keeping humans in the loop for quality review at critical checkpoints.

---

## System Design

The entire workflow is designed to run in n8n, connecting to multiple data sources and producing a finished document with minimal manual intervention.

The flow has six stages:

1. **Trigger and collection:** At the end of each quarter, the system sends customized Google Forms to each department for qualitative input. Simultaneously, it connects to Domo, Gong, and Salesforce APIs to pull quantitative data.

2. **Normalization:** All inputs are merged into a single normalized dataset stored temporarily in Google Sheets as a makeshift database for the MVP.

3. **Atomic findings:** AI extracts individual findings from the normalized data, breaking large narratives into discrete, testable statements.

4. **Three-pass analysis:** Each finding runs through three AI passes. The first generates "so what" context. The second checks for contradictions across departments. The third reviews for bias and applies skepticism.

5. **Human review:** Leaders are notified and review the AI-generated findings. They can approve, edit, or reject before the output moves to final assembly.

6. **Document assembly:** AI drafts narrative blocks from the reviewed findings. Blocks are programmatically assembled into a Google Doc. The final document and all raw inputs are uploaded to NotebookLM so leadership can query the data conversationally.

---

## Tech Stack

| Layer | Technology |
|---|---|
| Workflow engine | n8n |
| Data sources | Salesforce API, Gong API, Domo API |
| Qualitative input | Google Forms |
| Data transformation | JSON, Python, SQL |
| AI analysis | OpenAI API |
| Temporary storage | Google Sheets (MVP) |
| Output | Google Docs, NotebookLM |
| Automation | Time-based triggers, automated email notifications |

---

## Repo Structure

```
project-mda-workflow/
├── architecture/
│   ├── system-overview.md
│   └── data-flow.md
└── docs/
    └── design-decisions.md
```

---

[Back to portfolio](../README.md)
