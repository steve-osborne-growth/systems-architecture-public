# Design Decisions

Key architectural tradeoffs made in building the MindBody replacement.

---

## Building on WordPress Instead of a Custom Stack

**Decision:** Build the entire platform on WordPress with WooCommerce and Amelia rather than writing a custom application from scratch.

**Why:** The business needed a reliable, maintainable system that the owner could manage without ongoing developer involvement. WordPress plugins provided a proven foundation for booking and e-commerce. Building from scratch would have taken longer, cost more, and created a system no one could maintain without the original developer.

**Tradeoff:** WordPress and plugins introduce constraints. Not every behavior can be customized easily, and plugin updates can occasionally break custom integrations.

**Why it was worth it:** The system has run with minimal maintenance since launch. The owner can manage products, pricing, and content independently. That was the core requirement.

---

## JavaScript Hook for Booking Enforcement

**Decision:** Use a client-side JavaScript hook to enforce session caps rather than a server-side API rejection.

**Why:** The Amelia API did not provide a reliable server-side endpoint to intercept and reject bookings based on external session balance data. The JavaScript approach was the solution that actually worked.

**Tradeoff:** Client-side enforcement can theoretically be bypassed by disabling JavaScript. It is not as robust as a server-side rejection.

**Why it was worth it:** For a small business with known customers, the risk of bypass is negligible. The system functions correctly for all real-world usage and has required no maintenance or intervention since launch.

---

## Database Mapping as the Critical Path

**Decision:** Invest time upfront in establishing clean database links between Amelia customer records and WooCommerce customer records.

**Why learned in hindsight:** Early in the build, records were not always created correctly or linked cleanly. Existing customers who were migrated to the new system sometimes had mismatched records that caused session balance errors.

**What would be done differently:** The database mapping between the two systems should have been the first thing designed and validated before any other component was built. Every other piece of the system depends on that link being correct. Treating it as an afterthought created more rework than anything else in the project.

---

[Back to MindBody Replacement](../README.md)
