# Component: Billing System

## Purpose

The billing system takes validated overage data and converts it into actionable invoices that can be delivered to customers and tracked through to resolution.

---

## What It Does

- Compares assigned user counts against contracted license counts for every account across all 11 products
- Identifies accounts with overages and calculates the billable amount
- Creates DX records for each overage event
- Generates order products using a custom SKU designed specifically for on-demand invoicing
- Maintains a do-not-bill list that excludes specific accounts from invoicing based on seller or finance decisions

---

## Custom SKU Design

Standard Trimble billing infrastructure was not designed to handle on-demand overage invoices. A new SKU had to be designed and implemented specifically for this program. This required working across sales operations and finance to define the billing structure, get it approved, and integrate it into the DX system.

---

## Do-Not-Bill List

Sellers can flag accounts to be excluded from billing for a given cycle. This is handled through a self-serve tool that automatically updates the do-not-bill list and alerts finance. Accounts on this list are filtered out before invoices are generated.

---

## Design Notes

Building a proper billing structure from scratch was one of the more complex parts of the program because it required coordinating across multiple teams and systems that had no prior connection to each other. The decision to build a dedicated SKU rather than repurpose an existing one was made to keep on-demand invoices clearly identifiable in reporting and avoid contaminating existing billing data.

---

[Back to On-Demand Program](../../README.md)
