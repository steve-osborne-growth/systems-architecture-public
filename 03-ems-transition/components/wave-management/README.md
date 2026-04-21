# Component: Wave Management

## Purpose

The wave management system controls which customers receive communication and when, ensuring the migration does not overwhelm sellers, support, or customers by happening all at once.

---

## How It Works

Customers are grouped into cohorts based on factors including product type, overage severity, and account size. Each cohort enters the 90-day migration timeline as a wave.

The system pushes Salesforce DX IDs for each wave into the MailChimp API, which triggers the correct email sequence for that cohort's stage. As customers progress through the seller-led period and into the countdown phase, the system automatically routes them into the appropriate communication track.

---

## Design Notes

Wave-based execution was chosen over a single mass rollout because the support burden of 5,500 customers entering the migration simultaneously would have been unmanageable. Staggering waves also allows each cohort to inform improvements for the next one.

---

[Back to EMS Transition](../../README.md)
