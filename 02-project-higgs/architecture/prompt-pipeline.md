# Prompt Pipeline Design

Project Higgs uses AI extensively across both the deal analysis and customer evidence paths. Like Crosstalk, it runs through multiple passes rather than a single prompt.

---

## Deal Analysis Pipeline

### Pass 1: Atomic Findings

**Input:** Normalized deal data combined with firmographic context and seller input.

**Job:** Extract the core facts from each deal. What happened, who was involved, what products were included, and what the financial outcome was.

**Output:** A structured list of atomic findings per deal.

### Pass 2: So What Analysis

**Input:** Atomic findings from Pass 1.

**Job:** Answer three questions for each deal: Why does this matter? Who cares about this? How does this connect to broader business initiatives or market trends?

**Output:** Contextualized deal narratives that explain significance, not just facts.

### Pass 3: Bias and Skeptic Review

**Input:** Contextualized narratives from Pass 2.

**Job:** Review each narrative for positive bias, overstatement, or unsupported claims. LLMs are known for adding a positive spin. This pass is specifically designed to counteract that tendency.

**Output:** Reviewed narratives with bias flags removed or corrected.

### Human-in-the-Loop Review

After Pass 3, leadership reviews the output. They can approve, edit, or reject any narrative before it enters the final assembly.

---

## Customer Evidence Pipeline

The customer evidence path reuses the Crosstalk snippet extraction engine. It scans transcripts for customer adoption initiative signals, filters to external voice only, and then runs a categorization pass that tags each quote by product, customer vertical, and speaker title.

The output is a curated set of real customer quotes organized for easy inclusion in board materials.

---

## Why Multi-Pass

The same reasoning applies here as in Crosstalk. Single prompts attempting extraction, analysis, bias review, and formatting simultaneously produce inconsistent results. Breaking the work into stages makes each prompt simpler, more focused, and easier to validate or improve independently.

---

[Back to Project Higgs](../README.md)
