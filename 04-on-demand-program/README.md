# On-Demand Program: Revenue Operations System

Rebuilding a fragmented, manual program into a fully systematized revenue engine that grew from $3.5M to $15M per year.

---

## The Problem

When this program was inherited, it was barely functioning as a business process.

Five or six employees were pulled away from their primary roles to manually execute a program with unreliable data, no auditing, no standardized workflows, and no integration into core business systems. The program covered only about 500 of an estimated 5,000 eligible customers, roughly 10% of the addressable base. It had generated approximately $3.5M for two consecutive years with no growth trajectory and no path to scale.

The core mechanic of the program is straightforward: customers using Trimble products can assign more users than their license contract allows. When that happens, the system identifies the overage and bills in arrears. The goal is not to collect the invoice. The goal is to use the invoice as a trigger for a sales conversation that converts the overage into new contracted ARR.

What existed when this program was inherited could not support that goal at any meaningful scale.

---

## Outcomes

- Revenue grew from $3.5M per year to $15M per year
- Program expanded from covering roughly 10% of eligible customers to organization-wide reach
- Eliminated the need for five or six employees to contribute significant time to the program
- Built the data infrastructure now powering the organization-wide transition from Viewpoint licensing to EMS unified licensing
- Sellers consistently rely on the program to meet monthly and quarterly revenue targets

---

## Repo Structure

```
project-on-demand/
├── architecture/
│   ├── system-overview.md       # How the full program fits together
│   ├── data-flow.md             # Mermaid diagram of end-to-end data flow
├── components/
│   ├── data-ingestion/          # License count collection across 11 products
│   ├── data-normalization/      # Transformation and merging into unified view
│   ├── billing-system/          # Invoice preparation and SKU management
│   ├── seller-tools/            # Bulk email, forgiveness requests, self-serve tools
│   ├── knowledge-base/          # Internal site, training, and AI chatbot
│   └── reporting-dashboard/     # Domo dashboard for all stakeholders
└── docs/
    └── design-decisions.md      # Key tradeoffs and architectural choices
```

---

## Quick Links

- [System Overview](./architecture/system-overview.md)
- [Data Flow Diagram](./architecture/data-flow.md)
- [Design Decisions](./docs/design-decisions.md)

---

[Back to portfolio](../README.md)
