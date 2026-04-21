# Component: Ingestion

## Purpose

The ingestion component pulls raw data from external sources and combines it into a unified record for each customer interaction.

---

## Data Sources

**Gong API**
Accepts a list of Call IDs provided by the user. Retrieves detailed call metadata, participant information, speaker labels, and full text transcripts for each call.

**Salesforce API**
Pulls firmographic data including company size, industry, product ownership, and opportunity stage. This context is attached to each transcript record so downstream analysis can filter and segment by customer type.

---

## What Gets Passed Forward

A combined record containing:
- Full transcript text with speaker labels
- Call date and duration
- Associated Salesforce account and opportunity data
- Product ownership flags

---

## What Does Not Get Passed Forward

- Internal Trimble meeting recordings
- Calls with no associated Salesforce record
- Calls below a minimum duration threshold

---

## Design Notes

Combining CRM context at the ingestion stage means every downstream component has the full picture without making additional API calls mid-pipeline. This keeps the pipeline fast and reduces the chance of mismatched records later in the flow.

Ingestion is triggered manually by providing a list of Call IDs. This was a deliberate choice. Automated ingestion of all calls would create noise. Human selection of relevant calls keeps the analysis focused.

---

[Back to Project Crosstalk](../../README.md)
