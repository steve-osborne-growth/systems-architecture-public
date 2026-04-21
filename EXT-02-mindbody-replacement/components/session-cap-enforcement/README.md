# Component: Session Cap Enforcement

## Purpose

Prevent customers from booking more sessions than their active package or membership allows, without requiring staff to manually track or enforce limits.

---

## The Problem It Solves

Amelia and WooCommerce are independent systems. Amelia does not know what a customer has purchased. WooCommerce does not know what a customer has booked. Without a bridge, a customer could theoretically book unlimited sessions regardless of what they paid for.

The Amelia API documentation did not provide a reliable server-side hook to intercept and reject bookings based on external data. A different approach was needed.

---

## How It Works

The solution uses two layers working together.

**PHP layer:** Custom PHP runs on the server and exposes the logged-in customer's remaining session balance as data on the booking page. This is calculated by reading the session balance written when the customer made a purchase and subtracting completed bookings.

**JavaScript layer:** A JavaScript hook reads the exposed session balance on the booking page. If the balance is zero or the package has expired, the hook disables the booking form submission. The customer cannot proceed. They see a message prompting them to purchase additional sessions.

This approach does not use a server-side API rejection. It prevents the customer from interacting with the submit button entirely. The result is functionally identical: the booking cannot proceed.

---

## Design Notes

The JavaScript intercept was the solution arrived at after the Amelia API did not support the needed server-side hook. It is a pragmatic workaround rather than a textbook solution, but it works reliably and has required no maintenance since launch.

The tradeoff is that a technically sophisticated user who disabled JavaScript could theoretically bypass the check. For a small personal training business where customers are known individuals, this is an acceptable risk.

---

[Back to MindBody Replacement](../../README.md)
