# Design Decisions

Key architectural tradeoffs in the Programmatic MD&A Workflow design.

---

## n8n as the Workflow Engine

**Decision:** Build the entire system as an n8n workflow rather than a Python script, Flask app, or custom application.

**Why:** n8n provides visual workflow design, built-in API connectors, time-based triggers, and branching logic without writing a full application. It is the right tool for a multi-step, multi-source workflow that needs to run on a schedule and involve human checkpoints.

**Tradeoff:** n8n adds a dependency on a specific platform. If the organization does not adopt n8n broadly, the workflow may be harder to maintain long-term.

**Why it was worth it:** The alternative was building a custom orchestration layer in Python, which would take significantly longer and produce something harder for others to understand, modify, or maintain.

---

## Google Sheets as a Makeshift Database

**Decision:** Use Google Sheets as the temporary data store for the MVP rather than setting up a proper database.

**Why:** The goal is to validate the workflow end to end before investing in permanent infrastructure. Sheets is fast to set up, easy to inspect during development, and sufficient for quarterly-cadence data.

**Tradeoff:** Sheets is not a real database. It does not support proper querying, indexing, or concurrent access at scale. It will become a bottleneck if the system expands.

**If rebuilt with full resources:** Postgres would be the target. It would enable historical trend analysis across quarters and support the prediction models planned for the long-term roadmap.

---

## Atomic Findings Before Narrative

**Decision:** Extract individual atomic findings from the data before generating any narrative text.

**Why:** Asking AI to write a full MD&A narrative from raw data in one pass produces vague, generic output. Breaking the data into discrete findings first means each one can be individually analyzed, reviewed, and validated. The narrative is assembled from verified pieces rather than generated from scratch.

**Why it matters:** This is the same principle used in Crosstalk and Higgs. Small, scoped AI tasks produce better results than large, ambiguous ones.

---

## Contradiction Detection Across Departments

**Decision:** Include a dedicated AI pass that checks for contradictions between departments.

**Why:** Different departments sometimes tell conflicting stories. Sales may report strong pipeline while finance flags slowing revenue. Without a contradiction check, the MD&A could contain internally inconsistent narratives that undermine its credibility.

**Why it was worth it:** This pass catches problems that a single department reviewer would never notice because they only see their own section.

---

## NotebookLM as the Queryable Layer

**Decision:** Upload the final document and all raw inputs to NotebookLM after delivery.

**Why:** The MD&A is a point-in-time document. Leadership often has follow-up questions days or weeks after receiving it. NotebookLM allows them to query the underlying data conversationally without requesting another report or scheduling a meeting.

**Why it matters:** This turns a static quarterly document into a living, queryable knowledge base. It extends the value of the work far beyond the initial delivery.

---

[Back to MD&A Workflow](../README.md)
