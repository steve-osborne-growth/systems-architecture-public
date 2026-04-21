# Component: Data Ingestion

## Purpose

The data ingestion component collects inputs from four sources and stages them for normalization.

---

## Sources

- **Domo:** Firmographic and financial data for each customer and deal
- **Gong API:** Call transcripts for customer evidence extraction
- **Salesforce API:** Deal records, pipeline data, and account context
- **Google Forms:** Qualitative input from sellers who worked the deals and leadership who submitted context for the QBR

---

## Design Notes

The Google Forms input is the most important non-obvious source. Raw deal data from Salesforce tells you what happened. Seller input tells you why it happened. Including the human perspective alongside the structured data produces significantly better "so what" analysis in the AI passes downstream.

---

[Back to Project Higgs](../../README.md)
