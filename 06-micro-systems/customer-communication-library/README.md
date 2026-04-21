# Customer Communication Library

A system that pulls all customer email and call transcript history into two consolidated PDFs ready to upload into NotebookLM as a queryable customer knowledge base.

---

## The Problem

A seller had large enterprise customers with years of communication history scattered across Gmail and Gong. There was no way to consolidate that history into one place. When a customer was handed off to a new seller, the incoming seller inherited the account with no context and no practical way to get up to speed.

The problem was especially relevant during organizational changes where sellers moved from single-product assignments to managing entire verticals. Understanding years of prior customer relationships became critical, but the tools to do it did not exist.

---

## How It Works

The system has two collection paths that run independently.

**Email collection:**
1. An Apps Script calls the Gmail API filtered by customer email domain and date range
2. It automatically excludes irrelevant messages like meeting invites and calendar notifications
3. Each qualifying email is extracted and placed as a single page in a PDF
4. All pages are combined into one consolidated PDF

**Call transcript collection:**
1. Enter a Salesforce DX ID and date range
2. The script hits the Gong API and pulls all matching transcripts
3. Each transcript is separated with clear markers for queryability
4. All transcripts are combined into a single PDF

The end result is two documents: one covering all email communication, one covering all call transcripts. Upload both into NotebookLM along with any other relevant files and you have a complete, queryable customer knowledge base.

---

## Tech Used

- Gmail API (email extraction)
- Gong API (transcript extraction)
- Google Apps Script (JavaScript)
- PDF generation and compilation

---

## Time to Build

Approximately five to six hours across multiple sessions, including requirements gathering, testing, and iteration.

---

## Impact

Sellers now have a fast way to build a comprehensive knowledge base for their most important accounts. Customer handoffs between sellers went from losing months of context to having a fully queryable history available in minutes. The system also retrieves email history going back further than Salesforce or Gong retention limits, which was previously inaccessible.

---

## AI Angle

AI was used to assist in building the system. The primary AI application is the end use: the consolidated PDFs are designed specifically for ingestion into NotebookLM, which turns the raw communication history into a conversational interface a seller can query naturally.

---

## Links

- [Example Seller Notebook (Sensitive)](#)

---

[Back to micro systems](../README.md)
