# Component: Output Layer

## Purpose

The output layer takes the packaged findings from the analysis pipeline and delivers them in a format that works for the intended stakeholder.

---

## Output Formats

**Excel (.xlsx)**
The primary output format. Built using openpyxl with formatted headers, color fills, custom column widths, and clickable hyperlinks back to the original Gong calls and transcripts. Designed for stakeholders who need to verify findings against source material.

**Google Sheets**
Used for outputs that need to be filtered, sorted, or explored interactively. Structured with one row per finding or customer, with columns for relevant metadata including account name, product ownership, and call date.

**PDF Report**
Used for executive summaries, QBR materials, and board narratives. Formatted with section headers, key findings, and curated customer quotes. Designed for outputs that will be presented or shared broadly.

The format is chosen at the start of each analysis run based on the stakeholder and use case.

---

## Data Normalization

A significant challenge early in the project was ensuring consistent output across different analysis types. This was solved by creating standardized intake forms for each use case. When a stakeholder requests an analysis, they complete a form that captures the required parameters. Python then normalizes the input before the pipeline runs, ensuring the output structure is consistent every time regardless of what is being analyzed.

---

## Human Review Step

Before any output is delivered, it goes through a human review. The reviewer checks for factual accuracy against the source snippets, appropriate tone for the audience, and any model errors or formatting issues. This step is built into the process, not optional.

---

## Design Notes

Keeping delivery as a manual step was an intentional tradeoff. Automated delivery would be faster, but it removes the final human checkpoint before findings reach decision-makers. Given that some outputs inform QBR content and board narratives, that checkpoint matters.

---

[Back to Project Crosstalk](../../README.md)
