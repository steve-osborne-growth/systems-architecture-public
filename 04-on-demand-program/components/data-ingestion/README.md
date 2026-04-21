# Component: Data Ingestion

## Purpose

The data ingestion component pulls raw license count and subscription data from 11 different product sources on a monthly basis and stages it for normalization.

---

## Data Sources

The program spans 11 Trimble products. Each product exposes its data differently:

- **Vista Web:** Requires logging into a remote desktop connection to retrieve data manually. This was one of the more significant operational constraints of the program.
- **Spectrum and other products:** Data is exposed through SQL feeds that can be queried directly.

Each source provides assigned user counts, contracted license counts, and account identifiers that are used to match records to Salesforce accounts downstream.

---

## What Gets Passed Forward

A raw dataset per product containing:
- Customer account identifier
- Product name
- Assigned user count
- Contracted license count
- Data pull date

---

## Design Notes

The ingestion stage runs monthly because billing is calculated in arrears. Data pulled mid-month would not reflect the full picture of user assignment activity for that period.

The manual step required for Vista Web was a known limitation. It was flagged early as a candidate for automation but depended on infrastructure access that was not available within the scope of the program.

---

[Back to On-Demand Program](../../README.md)
