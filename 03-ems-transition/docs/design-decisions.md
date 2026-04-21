# Design Decisions

Key architectural tradeoffs made in building the EMS Transition system.

---

## Domo as the Central Platform

**Decision:** Run the majority of data transformation, tracking, and reporting through Domo.

**Why:** Most of the infrastructure from the On-Demand Program already lives in Domo. The organization is familiar with it. Building on top of existing data flows was faster than starting from scratch in a different platform.

**Tradeoff:** Domo is not ideal for every part of this system, particularly email list management and cohort exports. Those processes require extra steps to bridge the gap between Domo and MailChimp.

**Why it was worth it:** Speed of deployment and organizational familiarity outweighed the limitations. Sellers and stakeholders already know how to read Domo dashboards. That adoption advantage matters when the timeline is tight.

---

## Google Sheets as the Seller Interface

**Decision:** Give sellers their data in Google Sheets rather than building a custom interface or pointing them directly at Domo.

**Why:** Sellers are comfortable with Sheets. They know how to filter, sort, and work with data there. Any new tool would require training and would face adoption resistance during an already stressful transition.

**Tradeoff:** Sheets is not a real-time data source. Updates require refreshing connections or re-exporting data. Sellers sometimes work with slightly stale information.

**Why it was worth it:** A tool sellers actually use is more valuable than a tool that is technically superior but sits untouched. The data refresh cadence is monthly, which matches the billing cycle.

---

## Building the Internal User Filter as a Stopgap

**Decision:** Design and build a soft cap filtering solution for partners, consultants, and internal users rather than waiting for the EMS team to build it natively.

**Why:** Without the filter, the entire migration was blocked. Internal users logging into customer systems would consume license slots, which was unacceptable. Waiting for a native solution would have delayed the migration by months.

**Tradeoff:** The stopgap solution requires maintenance and will eventually be replaced when EMS builds native filtering. The work put into the stopgap will become throwaway.

**Why it was worth it:** The alternative was stopping the migration entirely. Building the stopgap allowed the EMS product team to continue their roadmap on schedule while the transition moved forward in parallel.

---

## Wave-Based Migration Over Mass Rollout

**Decision:** Migrate customers in cohorts over time rather than enforcing compliance for all 5,500 customers simultaneously.

**Why:** A mass rollout would overwhelm sellers, support teams, and customers. The operational burden would be unmanageable and the quality of customer experience would suffer.

**Tradeoff:** The migration takes longer. Each wave requires its own communication, tracking, and follow-up. The system is more complex to manage than a single enforcement event.

**Why it was worth it:** Each wave generates learnings that improve the next one. Seller feedback from early waves informed changes to communication cadence, data presentation, and training materials.

---

## 60/30 Day Split

**Decision:** Give sellers 60 days of seller-led outreach before triggering a 30-day customer countdown, totaling 90 days per customer.

**Why:** Sellers need time to have genuine conversations with customers about upsells. Rushing to enforcement would generate complaints instead of revenue. The 30-day countdown creates urgency without feeling sudden.

**Tradeoff:** 90 days per customer extends the overall migration timeline significantly. Some customers will procrastinate because they know they have time.

**Why it was worth it:** The seller-led period is where upsell revenue is generated. Cutting it short would sacrifice the revenue opportunity that makes the migration financially positive for the business.

---

[Back to EMS Transition](../README.md)
