# System Overview

The MindBody replacement is a custom platform built on WordPress, WooCommerce, and Amelia Booking. It connects three systems that were not designed to talk to each other and adds custom logic on top to enforce session caps based on what a customer has purchased.

---

## Core Design Principles

**The customer must own their account.** Customers create a login, manage their bookings, view their package balances, and self-serve their scheduling. No staff intervention required for routine booking activity.

**Purchases must govern what can be booked.** A customer who buys a five-session punch card cannot book a sixth session. A customer on a monthly membership cannot book more sessions than their plan allows. Enforcement happens automatically at the point of booking.

**The system must match how the business actually operates.** MindBody imposed a structure the business had to adapt to. This system was built around the business's existing products, pricing, and workflows.

---

## System Components

| Component | Purpose |
|---|---|
| Booking System | Amelia handles all session scheduling, calendar management, and availability |
| Membership and Packages | WooCommerce manages all purchases including memberships, packages, and punch cards |
| Session Cap Enforcement | Custom PHP and JavaScript logic bridges Amelia and WooCommerce to enforce booking limits |

---

## How the Three Systems Connect

Amelia and WooCommerce are independent platforms with separate databases. Neither was designed to enforce booking limits based on purchases made in the other. Connecting them required custom code at multiple layers.

When a customer makes a purchase in WooCommerce, a custom integration creates a corresponding record in the Amelia database tied to the customer's WooCommerce account. When the customer attempts to book a session, the system checks their remaining session balance by querying both databases. A JavaScript hook on the booking page reads the exposed balance data and blocks the booking interaction if the customer has no sessions remaining.

The result is a seamless customer experience where the booking form simply does not allow overbooking, without revealing any of the underlying logic.

---

[Back to MindBody Replacement](../README.md)
