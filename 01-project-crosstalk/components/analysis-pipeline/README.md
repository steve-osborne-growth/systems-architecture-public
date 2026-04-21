# Component: Analysis Pipeline

## Purpose

The analysis pipeline takes the snippet pool produced by the extraction component and runs it through a structured four-pass AI process to produce validated, synthesized findings.

---

## Pipeline Stages

| Pass | Name | Input | Output |
|---|---|---|---|
| 1 | Extraction | Snippet pool | Structured list of customer statements |
| 2 | Synthesis | Extracted statements | Pattern summary with supporting evidence |
| 3 | Audit | Synthesized summary | Reviewed and corrected summary |
| 4 | Packaging | Audited summary | Final formatted output |

For detailed prompt design and reasoning behind each pass, see the [prompt pipeline documentation](../../architecture/prompt-pipeline.md).

---

## Model

Analysis runs on Azure-hosted GPT-4o-mini via the OpenAI API. Azure hosting was chosen for data residency and compliance reasons.

---

## Batching

When an analysis run covers a large number of transcripts, the snippet pool is split into batches. Each batch runs through Passes 1 and 2 independently. The resulting summaries are then merged and passed through a single consolidated Pass 3 and Pass 4.

This approach keeps individual prompts within a manageable context window while still producing a unified output across the full dataset.

---

## Error Handling

Each pass retries up to three times per transcript in the event of API timeouts or malformed responses. If all attempts fail, the transcript is flagged for manual review. This prevents errors from compounding through the pipeline and ensures the final output only contains verified results.

---

## Design Notes

The decision to use four discrete passes rather than one large prompt came from early testing. Single-prompt outputs were inconsistent and harder to debug. Breaking the work into stages made it easy to identify where output was degrading and fix only that stage without affecting the rest of the pipeline.

---

[Back to Project Crosstalk](../../README.md)
