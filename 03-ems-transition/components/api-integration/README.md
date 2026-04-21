# Component: API Integration

## Purpose

The API integration component connects the transition system to the EMS platform, enabling automated enforcement of license caps at scale.

---

## How It Works

When a customer reaches compliance, either through seller-led conversion or after the 90-day timeline expires, the system calls the EMS API to flip the customer from a soft limit to a hard limit. This is done in bulk for each wave rather than one customer at a time.

The API call includes logic to preserve admin access so that customer administrators are not locked out during the transition. It also handles edge cases where a customer has multiple products at different compliance stages.

---

## Design Notes

Automating the enforcement step was critical. Manual flipping of 5,500 customers would introduce errors and create an unsustainable operational burden. The API integration ensures that once the data confirms compliance, the enforcement happens reliably and at scale.

---

[Back to EMS Transition](../../README.md)
