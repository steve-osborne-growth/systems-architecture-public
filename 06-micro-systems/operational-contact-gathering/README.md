# Viewpoint Operational Contact Gathering System

A four-layer automated system that gathers validated customer contacts from 5,500 accounts in five minutes, replacing a six-hour manual process.

---

## The Problem

The Viewpoint organization had no reliable, scalable way to gather operational contacts for customer communication. One employee would spend approximately six hours of continuous manual work editing, downloading, reformatting, and appending Salesforce reports just to compile a contact list. The process was not only exhausting but prone to errors because every step was manual.

This had to be repeated multiple times during the EMS transition. Every time an updated contact list was needed, someone had to endure the same six-hour marathon. There was no way to scale the EMS transition communication without solving this first.

---

## How It Works

The system runs through four layers to maximize contact coverage across all 5,500 accounts.

**Layer 1:** Finds accounts with both key contacts and operational opt-ins. Extracts contacts from those accounts first.

**Layer 2:** Takes the remaining accounts that have key contacts but no opt-ins. Gathers those contacts.

**Layer 3:** For accounts with neither key contacts nor opt-ins, the system analyzes available titles and builds an email list from the best available contacts.

**Layer 4:** Any accounts still unmatched move to DX, where available contacts are extracted as a final fallback.

After all four layers run, the system generates a series of batch files containing SOQL queries. The queries are split into multiple batches to avoid Salesforce timeout limits. The user opens PowerShell, runs one command, and the batch files execute in sequence. A final PowerShell command combines all results into a single CSV.

The output: approximately 20,000 contacts from 5,500 accounts, ready in about five minutes.

---

## Tech Used

- Google Sheets and Google Apps Script (JavaScript) for the four-layer logic
- Salesforce CLI for query execution
- SOQL batch files for data extraction
- Windows PowerShell for combining output files

---

## Time to Build

Approximately five to six hours. A one-time build that takes the same amount of time as one manual run of the old process.

---

## Impact

The system has been run four times to date, saving approximately 24 total hours of manual work. More importantly, the contact quality is significantly higher because the four-layer approach ensures coverage across all accounts rather than relying on a single data source. The system can now be run on demand whenever an updated contact list is needed, which is critical for the ongoing EMS transition.

---

## AI Angle

AI was not part of the runtime workflow. It was used to assist in developing the system itself, particularly in structuring the SOQL queries and the batch file logic.

---

## Links

- [SOQL Contact Extraction Video](#)

---

[Back to micro systems](../README.md)
