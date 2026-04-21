# Prompt Pipeline Design

The AI analysis in Project Crosstalk does not run on a single prompt. It runs through four distinct passes, each with a scoped job. This structure was chosen deliberately to improve reliability, reduce bias, and produce outputs that hold up under scrutiny.

---

## Why Multi-Pass

A single prompt asking the model to extract, synthesize, audit, and format in one step produces inconsistent results, especially across large volumes of input. Breaking the work into stages means each prompt is simpler, more focused, and easier to validate.

It also makes the system easier to improve over time. If the synthesis output is weak, only Pass 2 needs to be updated. The other stages are unaffected.

Each business request that comes in requires its own prompt configuration because use cases vary significantly. This is a deliberate design choice. The manual prompting step adds human judgment at the point where it matters most.

---

## The Four Passes

### Pass 1: Extraction

**Input:** A batch of snippets from the snippet pool.

**Job:** Identify what the customer is saying about the target topic in each snippet. Pull out direct statements, concerns, comparisons, and questions.

**Output:** A structured list of extracted statements tagged by snippet source.

---

### Pass 2: Synthesis

**Input:** All extracted statements from Pass 1.

**Job:** Identify patterns across the full set. What themes appear repeatedly? What is the distribution of sentiment? What is being said most often, and by what type of customer?

**Output:** A synthesized summary of findings with supporting evidence from the extracted statements.

---

### Pass 3: Audit

**Input:** The synthesized summary from Pass 2.

**Job:** Check the output for bias, overstatement, and internal voice contamination. Flag anything that does not hold up. This pass acts as a quality control layer before the output reaches stakeholders.

**Output:** A reviewed and corrected version of the synthesis, with a brief audit note if any changes were made.

---

### Pass 4: Packaging

**Input:** The audited synthesis from Pass 3.

**Job:** Format the findings for the intended audience. This includes structuring sections, writing summaries, selecting representative customer quotes, and tailoring language to the stakeholder context.

**Output:** A final document ready for delivery as an Excel file, Google Sheets, or PDF.

---

## Error Handling

Each pass includes retry logic that attempts the analysis up to three times per transcript in the event of API timeouts or malformed responses. If all three attempts fail, the transcript is flagged for manual review rather than passing an empty or corrupted result downstream.

---

## Human-in-the-Loop

After Pass 4, a human reviewer checks the packaged output before it is shared with stakeholders. This step is not optional. It exists because the system is designed to assist judgment, not replace it.

---

## Prompt Engineering Approach

Each prompt is written to be explicit about three things:

1. What the model should focus on
2. What the model should ignore
3. What format the output should follow

Because every business use case is unique, prompts are configured per request rather than generalized. This adds a manual step but produces significantly better results than a one-size-fits-all approach.

---

[Back to Project Crosstalk](../README.md)
