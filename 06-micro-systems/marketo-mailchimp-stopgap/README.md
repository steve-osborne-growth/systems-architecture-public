# Marketo/Mailchimp Stopgap Solution

A customizable bulk email system built to fill a six-month gap when the organization had zero ability to contact customers at scale.

---

## The Problem

When Marketo was decommissioned, it was overlooked that the organization lost its only method of contacting customers in bulk. Mailchimp was eventually adopted as the replacement, but for approximately six months there was no bulk communication tool at all.

The problem surfaced first in the On-Demand program, where customers need to receive notices before they are billed for license overages. Without advance notification, customers were receiving unexpected invoices, leading to a spike in complaints, forgiveness requests, and billing disputes. After investigating further, the gap was affecting teams across marketing, product marketing, and product as well.

---

## How It Works

The system runs inside a Google Sheet with a connected Apps Script.

1. Enter customer data into the sheet with required columns for DX ID and contact email. Any additional columns are treated as dynamic data fields.
2. The system reads whatever column headers are present and formats them into a data table inside the email body. Column order is customizable.
3. Choose a sending option: send from your own email, send from a delegated email address (used for On-Demand notices so they come from a program address rather than a personal inbox), or create as a draft for review before sending.
4. Add a custom email signature.
5. Run the script. Emails are generated and either sent or placed as drafts depending on the selected option.

The delegated email feature was the most technically challenging piece and the most important for the On-Demand program. Billing notices needed to come from an official address, not a personal inbox.

---

## Tech Used

- Google Apps Script (JavaScript)
- Gmail API (email sending and draft creation)
- AI-assisted development

---

## Time to Build

Approximately three to four hours including testing, iteration, and solving the delegated email challenge.

---

## Impact

The tool restored the ability to contact customers at scale during a critical six-month gap. For the On-Demand program specifically, it reduced billing disputes and forgiveness requests by ensuring customers always received advance notice before invoicing. The tool was also made available to others in the organization who needed bulk communication during the same period.

---

## AI Angle

AI was used to assist in building the system and refining it for production use. The runtime workflow does not use AI because the communications are standardized financial notices where consistency matters more than personalization. However, the same architecture could support AI-generated personalized email copy using the OpenAI API, similar to the approach prototyped in the Seller Email Generator.

---

## Links

- [Mail Merge Template](#)

---

[Back to micro systems](../README.md)
