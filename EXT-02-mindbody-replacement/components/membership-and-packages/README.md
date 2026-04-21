# Component: Membership and Packages

## Purpose

Handle all purchasing, subscription management, and package tracking for every product the business sells.

---

## Product Types Supported

- **Monthly memberships:** Recurring Stripe subscription with a fixed session allotment per month. Resets at the start of each billing cycle.
- **Punch cards:** Fixed session count with a 60-day expiry from date of purchase.
- **Group class packages:** Prepaid access to a set number of group class sessions.
- **One-on-one sessions:** Single or multi-session purchases for individual training.
- **Virtual training:** Same structure as one-on-one but flagged for remote delivery.

---

## How It Works

WooCommerce manages all products, pricing, and Stripe payment processing. Each product is configured with custom metadata that defines the session allotment rules: how many sessions are included, whether they expire, and what service type they apply to.

When a purchase completes, a WooCommerce webhook triggers custom PHP that reads the product metadata and writes the session balance to the database with the customer's Amelia ID attached. This is the link that allows the booking system to read remaining sessions at the point of booking.

---

## Design Notes

WooCommerce was chosen because it is fully configurable, integrates with Stripe out of the box, and runs on WordPress where the rest of the site lives. The alternative was building a custom e-commerce layer from scratch, which would have taken significantly longer and introduced more maintenance burden.

---

[Back to MindBody Replacement](../../README.md)
