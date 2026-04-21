# System Overview

The On-Demand Program is a revenue operations system built to identify, bill, and convert customer license overages into contracted ARR.

It is not a single system. It is a collection of interconnected systems and processes that together form a complete operational program. Each component was built to replace a manual or missing workflow. The result is a program that one person can now run end to end, at a scale that previously required multiple employees working across fragmented tools and unreliable data.

---

## Core Program Mechanic

Customers can assign more users to a Trimble product than their license contract allows. The system monitors assigned user counts against contracted license counts across 11 products each month. When an overage is detected, the program generates an invoice billed in arrears for the excess users.

The invoice is not the goal. It is the trigger. The goal is to use the invoice as a prompt for a sales conversation. A seller contacts the customer, explains the overage, and proposes adding the excess users to the contract as new ARR. When the customer agrees, the invoice is forgiven and the ARR is booked. This creates a low-friction path to license expansion that bypasses the lengthy standard sales and implementation process.

---

## Core Design Principles

**Reliability over speed.** The program failed for years because the data was unreliable. Every system built prioritizes data accuracy and auditability above all else.

**Self-service where possible.** Sellers should be able to handle routine actions without submitting a ticket or waiting for a manual process. Forgiveness requests, do-not-bill flags, and customer outreach are all self-serve.

**Normalization at ingestion.** Data comes from 11 different product sources in 11 different formats. The system normalizes everything into a single structure before it enters any downstream process. This is the foundation everything else depends on.

**Enablement is part of the system.** A technically correct system that sellers do not understand or trust does not produce revenue. Training, documentation, a knowledge base, and an AI chatbot are treated as first-class components of the program, not afterthoughts.

---

## System Components

| Component | Purpose |
|---|---|
| Data Ingestion | Pulls license and subscription counts from 11 product data sources |
| Data Normalization | Transforms and merges all inputs into a single unified data structure |
| Billing System | Prepares invoices, manages SKUs, and handles DX record creation |
| Seller Tools | Self-serve tools for bulk outreach, forgiveness requests, and billing status changes |
| Knowledge Base | Internal Google Site with training, documentation, and an AI chatbot |
| Reporting Dashboard | Domo dashboard giving all stakeholders a unified view of licensing and program status |

---

[Back to On-Demand Program](../README.md)
