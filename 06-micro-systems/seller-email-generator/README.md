# Seller Email Generator

A one-click tool that turns raw license data into personalized, ready-to-review email drafts delivered directly into a seller's Gmail inbox.

---

## The Problem

Sellers using the On-Demand Program had access to a dashboard showing 60 to 100 accounts with license overage data. To act on that data, a seller had to manually review each account, export the relevant rows, build a formatted email with the right numbers, and send it to the right contact at each company.

Most sellers knew that reaching out proactively to customers about overages led to upsells. Most of them did not do it anyway because the manual process was too slow and too tedious to justify at scale. Revenue was being left on the table not because the opportunity was unclear but because the friction was too high.

---

## How It Works

The tool lives inside the existing On-Demand Google Sheet that sellers already use.

1. A seller clicks a custom menu item in the sheet labeled "Generate email"
2. They select the rows for the customers they want to contact
3. They click run
4. The script groups selected rows by unique Salesforce DX account ID, so customers with multiple products appear in one consolidated email rather than separate messages
5. For each company, a personalized email draft appears in the seller's Gmail inbox, pre-populated with a formatted table showing license counts, contracted amounts, and overage details

Drafts land in the inbox rather than sending automatically. This was a deliberate decision made with the sales team. Sellers review and send each draft themselves, which lets them verify contacts, adjust tone, and add personal context before it goes out.

---

## Tech Used

- Google Sheets (data source and UI)
- Google Apps Script (JavaScript)
- Gmail API via Apps Script (draft creation)
- Domo data connector (live license data feed into the sheet)

---

## Time to Build

The working MVP took approximately 45 minutes to one hour. Several additional hours of iteration over the following weeks incorporated seller feedback and added features including the mail merge table format and multi-product grouping logic.

---

## Impact

Direct revenue attribution was not measured for this tool. Sellers who use it report significantly faster outreach to customers, which compresses the time between overage detection and upsell conversation. The tool removes the main reason sellers gave for not doing proactive outreach at all.

---

## AI Angle

AI was not used in this version. A fully AI-powered version is possible and has been prototyped separately: a Google Sheet pulls data points across accounts, passes them to the OpenAI API, and generates fully personalized email copy for each customer before inserting it as a mail merge. That approach could be applied here to move beyond templated outreach and into emails that reference specific customer context, product usage patterns, and account history.

---

## Links

- [Email Generator Tool](#)

---

[Back to micro systems](../README.md)
