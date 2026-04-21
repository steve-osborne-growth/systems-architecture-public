# Component: Reporting Dashboard

## Purpose

The reporting dashboard gives every stakeholder in the program a single, reliable view of licensing data, overage status, and program performance without needing to pull raw data or ask for a manual report.

---

## What It Shows

- Assigned user counts vs contracted license counts per account per product
- Current overage amounts and estimated invoice values
- Historical billing and conversion data
- Program revenue totals by month, quarter, and year
- Seller-level performance on overage conversion
- Accounts on the do-not-bill list and their status

---

## Who Uses It

- **Sellers:** Review their accounts, understand overages, and identify outreach priorities
- **Sales managers:** Monitor team performance and program contribution to quota
- **Finance:** Track invoice status, forgiveness requests, and revenue booked
- **Leadership:** View program-level revenue trends and forecast

---

## Tech

Built in Domo using SQL-based data transformations connected to the normalized data pipeline. All data flows through the normalization layer before surfacing in the dashboard, which ensures what stakeholders see is always accurate and consistent.

---

## Design Notes

The original program had no shared reporting. Each person involved maintained their own version of the data in a separate spreadsheet. This created constant reconciliation problems and meant no two people ever had the same number.

Building a single Domo dashboard as the authoritative source eliminated that problem. It also made the program visible to leadership in a way it never had been before, which was a factor in the investment and organizational attention the program received as it scaled.

---

[Back to On-Demand Program](../../README.md)
