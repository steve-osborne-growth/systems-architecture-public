# Component: Seller Tools

## Purpose

The seller tools component gives sales teams the ability to act on on-demand data quickly and independently, without relying on manual support from a central team.

---

## Tools Built

**Bulk Email Outreach Tool**
Allows sellers to send templated outreach to their customers about on-demand invoices in bulk. Before this tool existed, sellers had to manually identify affected customers, look up contact information, and send individual emails. The tool reduces this to a few clicks.

**Forgiveness Request Tool**
Built using Google Forms and Google Apps Script. When a seller converts an on-demand overage into a new ARR contract, they submit a forgiveness request through the tool. The tool automatically alerts finance, updates the billing record, and logs the conversion. No ticket or manual handoff required.

**Do-Not-Bill Self-Service**
Sellers can flag individual accounts to be excluded from the next billing cycle directly through a self-serve interface. Finance is automatically notified. The flag is applied before invoices are generated.

**License Audit Tool**
Allows sellers to quickly review the license counts and overage details for their accounts without navigating raw data in Domo. Built to reduce the time a seller spends understanding an account's situation before reaching out.

---

## Design Notes

Every tool in this component was built because a manual process was creating friction that slowed down seller action. Speed matters in this program. The longer it takes a seller to understand an overage and reach out to a customer, the lower the conversion rate.

Google Apps Script was used extensively here because it integrates directly with the Google Workspace tools the sales team already uses daily. Adoption was faster because sellers did not have to learn a new platform.

---

[Back to On-Demand Program](../../README.md)
