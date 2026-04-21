# EMS Transition: Unified Licensing Migration System

Guiding 5,500 customers and 500,000+ users through a structured migration from legacy licensing to a unified system, while keeping sellers enabled and customers informed at every stage.

---

## The Problem

Trimble's product team built EMS, a unified licensing management system. Viewpoint is the hardest organization to migrate because it has never enforced license caps. Customers have always been able to assign more users than their contract allows.

To complete the EMS migration, every customer must first be in compliance, meaning assigned users cannot exceed contracted licenses. This creates three simultaneous problems:

1. The migration must happen in waves, not all at once, across 5,500 customers
2. Customers need consistent, clear communication at every stage of the transition
3. Sellers need tools, data, and training to carry out the initiative and convert overages into upsells

On top of this, the EMS system had no mechanism to filter out internal employees, partners, and consultants who log into customer systems. Without a filter, those users would count against customer license caps, which is unacceptable. A stopgap solution had to be designed and built before the migration could proceed.

---

## Outcomes

- Expected to generate $5 to $7 million in license revenue through upsells during the transition
- Built a soft cap filtering solution for partners, consultants, and internal users in both Vista and Spectrum, unblocking the entire migration timeline
- Reduced organizational stress and confusion around the transition through structured communication and seller enablement
- Currently in progress

---

## Repo Structure

```
project-ems-transition/
├── architecture/
│   ├── system-overview.md       # How the full transition system fits together
│   ├── data-flow.md             # Mermaid diagram of the migration data flow
├── components/
│   ├── compliance-tracking/     # Dashboard and logic for tracking customer compliance
│   ├── wave-management/         # Cohort-based customer communication system
│   ├── api-integration/         # EMS API for soft-to-hard limit flipping
│   ├── internal-user-filter/    # Partner, consultant, and employee filtering
│   └── seller-enablement/       # Training, tools, and communication systems
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
