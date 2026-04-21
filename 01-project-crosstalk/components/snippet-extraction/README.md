# Component: Snippet Extraction

## Purpose

The snippet extraction component isolates the relevant portions of each transcript before anything is sent to the AI analysis pipeline. This is the most architecturally distinctive part of Project Crosstalk.

---

## The Problem It Solves

A typical customer call transcript runs 60 to 90 minutes. Passing a full transcript to an AI model creates two problems:

1. The model reads a large amount of irrelevant content, which dilutes the signal and degrades output quality.
2. Token costs scale with input length, making full-transcript ingestion expensive at volume.

Snippet extraction solves both problems by sending only the relevant context, not the full document.

---

## How It Works

**Step 1: Internal speaker filter**
All turns from internal Trimble speakers are removed. Only customer voice passes through.

**Step 2: Keyword and concept scan**
The filtered transcript is scanned for a predefined list of target keywords, competitor names, product mentions, and thematic concepts. Each match is flagged with its position in the transcript.

**Step 3: Context window extraction**
For each flagged match, the system extracts a window of approximately 10 sentences before and 10 sentences after the match. This preserves the conversational context around the signal without pulling in the entire transcript.

**Step 4: Snippet compilation**
All extracted windows are compiled into a snippet pool. Snippets can be grouped per individual call or aggregated across all calls for a given customer, depending on the analysis type requested.

---

## Design Notes

The window size of 10 sentences before and after was arrived at through iteration. Smaller windows lost too much context. Larger windows reintroduced noise. Ten sentences captures enough of the conversation to understand what was being discussed without pulling in unrelated content.

The keyword and concept list is maintained separately and updated as new analysis needs emerge. Adding a new topic to track requires only updating the scan list, not changing the extraction logic.

---

[Back to Project Crosstalk](../../README.md)
