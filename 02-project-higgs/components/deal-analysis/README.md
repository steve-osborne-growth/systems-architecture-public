# Component: Deal Analysis

## Purpose

The deal analysis component takes raw deal data and transforms it into contextualized narratives that explain why each deal matters, not just that it happened.

---

## How It Works

Each deal runs through a three-pass AI pipeline followed by a human review. The passes are extraction, "so what" analysis, and bias review. See the [prompt pipeline documentation](../../architecture/prompt-pipeline.md) for detailed design.

The output for each deal includes: the core facts, the strategic significance, the connection to broader initiatives, and any market signals or expansion opportunities the deal represents.

Individual deal narratives are also aggregated into a summary view that highlights patterns across the full set of deals for the quarter.

---

## Design Notes

The bias review pass exists specifically because LLMs default to positive framing. Board materials that read like press releases are not useful. The skeptic review forces the model to challenge its own output before a human sees it, which produces more balanced and credible narratives.

---

[Back to Project Higgs](../../README.md)
