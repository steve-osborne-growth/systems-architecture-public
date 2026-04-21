# Design Decisions

This document captures the key architectural tradeoffs made in building Project Crosstalk and the reasoning behind each one.

---

## Google Colab as the Runtime Environment

**Decision:** Build and run the system in Google Colab rather than a local environment or hosted server.

**Why:** The team was small and distributed. Colab allowed both developers to work in the same live environment simultaneously without any setup overhead. New features could be added and tested in real time, side by side. Speed of development was the priority in the early stages.

**Tradeoff:** Colab is not designed for automation at scale. The system cannot run on a schedule or process large volumes without manual intervention. Every analysis run requires a human to initiate it.

**If rebuilt today:** A Flask application running on a hosted server would remove this limitation. The manual trigger step would be replaced with scheduled or event-driven runs.

---

## Snippet Extraction Before AI Ingestion

**Decision:** Never pass full transcripts to the AI model. Extract context windows around relevant signals first.

**Why:** Full transcripts are long, noisy, and expensive to process. Ingesting them wholesale produces lower quality outputs and higher costs. Extracting snippets keeps the model focused on what matters.

**Tradeoff:** The snippet extraction logic requires a maintained keyword and concept list. If a relevant topic is not on the list, the system will not flag it. The system finds what it is told to look for.

**Mitigation:** The keyword list is reviewed and updated regularly as new analysis needs emerge.

---

## Per-Request Prompt Configuration

**Decision:** Configure prompts manually for each business request rather than using a generalized prompt template.

**Why:** Every business use case that came in was unique. Attempts to create a generalized prompt produced worse results across the board. Manual configuration added a human step but dramatically improved output quality.

**Tradeoff:** The system cannot run fully automated. A human must configure and initiate each analysis run. This limits throughput but the static documents produced guide strategy effectively.

**Why it was worth it:** The improvement in output quality justified the added manual step. Stakeholders receive findings they can trust and act on.

---

## Multi-Pass AI Pipeline

**Decision:** Use four discrete AI passes rather than one large prompt.

**Why:** Single-prompt outputs were inconsistent and difficult to debug during early testing. Breaking the work into stages made it easy to identify where quality was degrading and fix only that stage without affecting the rest.

**Tradeoff:** Four passes means four sets of prompts to maintain and four points where the pipeline can fail. It is more complex to build than a single-prompt approach.

**Why it was worth it:** The improvement in output consistency and debuggability justified the added complexity.

---

## No Persistent Database

**Decision:** Store outputs in Excel files, Google Sheets, and PDFs rather than a structured database.

**Why:** When the system was first built, the organization was not yet integrated with DOMO, and setting up a database was outside the scope of an early-stage internal project. Google Sheets provided immediate, accessible storage that stakeholders could already use.

**Tradeoff:** There is no historical record of findings that can be queried over time. Trend analysis across multiple runs requires manual comparison of separate output files.

**If rebuilt today:** A Postgres database or DOMO integration would enable longitudinal analysis and make the system significantly more powerful over time.

---

## Starting with Cross-Sell Detection

**Decision:** Build the first version around identifying cross-sell and upsell opportunities in call transcripts.

**Why:** It was a clear, testable hypothesis with an obvious connection to revenue. It was easy to explain to stakeholders and easy to measure.

**What happened:** The hypothesis did not hold up. Sellers did not act on the signals the system surfaced, and the value was not where the original plan expected it to be.

**Why it was still the right call:** Testing and disproving the hypothesis required interviews across sales, product marketing, and business leadership. Those interviews revealed the real use case: strategic intelligence at scale. The system today is more valuable than the one originally planned, because the team followed the evidence rather than the original plan.

---

[Back to Project Crosstalk](../README.md)
