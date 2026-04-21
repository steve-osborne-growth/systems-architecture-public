# Component: Booking System

## Purpose

Handle all session scheduling, calendar management, staff assignment, and customer-facing booking for every service type the business offers.

---

## What It Does

Amelia Booking is the scheduling layer of the platform. It manages the booking calendar for all service types including group classes, one-on-one sessions, and virtual training. Customers see available slots, pick times, and confirm bookings through a front-end interface embedded in the WordPress site.

Amelia handles:
- Staff calendars and availability per service type
- Group class capacity limits
- Booking confirmations and reminders via email
- Customer-facing account view showing upcoming and past bookings

---

## Integration Point

Amelia operates as an independent system with its own database. The session cap enforcement component sits on top of Amelia and intercepts bookings before they complete. Amelia itself does not know about package balances. That logic lives in the custom PHP and JavaScript layer.

---

[Back to MindBody Replacement](../../README.md)
