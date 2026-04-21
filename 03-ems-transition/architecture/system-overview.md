# System Overview

The EMS Transition system manages the migration of 5,500 Viewpoint customers from legacy licensing to a unified licensing management system. It coordinates data tracking, seller enablement, customer communication, and API-driven license enforcement across a 90-day per-customer lifecycle.

---

## Core Design Principles

**Waves, not waterfalls.** Customers migrate in cohorts, not all at once. This keeps the support burden manageable and allows each wave to inform the next.

**Seller-led conversion first.** The first 60 days of each customer's migration are seller-led. Sellers have tools and data to reach out and convert overages into upsells before enforcement kicks in.

**Automated enforcement as a backstop.** After 90 days, if a customer has not reached compliance through seller-led efforts, the system automatically enforces a hard license cap via the EMS API.

**Clear communication at every stage.** Customers receive targeted emails at specific points in their migration timeline. Cohort-based routing through MailChimp ensures the right message reaches the right customer at the right time.

**Data accuracy above all.** The system merges brand-new EMS assignment data with legacy license and subscription data. Every transformation is validated before any enforcement action is taken.

---

## System Components

| Component | Purpose |
|---|---|
| Compliance Tracking | Domo dashboard tracking compliance status for every customer across all products |
| Wave Management | Cohort-based communication system routing customers through MailChimp at the right stage |
| API Integration | Connects to the EMS API to flip customers from soft limits to hard limits in bulk |
| Internal User Filter | Filters out partners, consultants, and internal employees so they do not count against customer caps |
| Seller Enablement | Training, office hours, tools, and data to help sellers convert overages into upsells |

---

[Back to EMS Transition](../README.md)
