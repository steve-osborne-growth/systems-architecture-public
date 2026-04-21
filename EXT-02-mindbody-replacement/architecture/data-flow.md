# Data Flow

This diagram shows how a customer moves through the system from first visit to booking enforcement.

```mermaid
flowchart TD
    A([New Customer\nVisits Website]) --> B[Create Account\nFirst Visit Required]
    B --> C[Amelia Booking\nRecord Created]
    C --> D[WooCommerce API\nLinks Amelia ID to WC Record]

    D --> E{What Does\nCustomer Want?}

    E -- Free consultation --> F[Book Consultation\nNo Purchase Required]
    E -- Buy package --> G[WooCommerce Purchase\nMembership, Package, or Punch Card]

    G --> H[Custom PHP Logic\nWrites Session Balance to DB]
    H --> I[Customer Books\nSession in Amelia]

    I --> J[JavaScript Hook\nReads Session Balance]
    J --> K{Sessions\nRemaining?}

    K -- Yes --> L[Booking Proceeds\nBalance Decremented]
    K -- No --> M[Booking Blocked\nUI Prevents Submission]

    L --> N[Calendar Updated\nConfirmation Sent]
    M --> O([Customer Prompted\nto Purchase More])

    subgraph Package Types
        P[Monthly Membership]
        Q[Punch Card]
        R[Group Class Package]
        S[One-on-One Sessions]
        T[Virtual Training]
    end

    G --> Package Types

    style A fill:#dbeafe,stroke:#93c5fd,color:#1e3a5f
    style L fill:#dcfce7,stroke:#86efac,color:#14532d
    style N fill:#dcfce7,stroke:#86efac,color:#14532d
    style M fill:#fef9c3,stroke:#fde047,color:#713f12
    style O fill:#fef9c3,stroke:#fde047,color:#713f12
```

---

## Stage Descriptions

**Account Creation**
First-time visitors must create an account before booking. This creates records in both Amelia and WooCommerce that are linked by a shared customer identifier.

**Purchase**
Customers purchase whatever service type they want through WooCommerce. Each product type has different session allotment rules configured in the backend. A monthly membership might allow eight sessions per month. A punch card allows a fixed number with a 60-day expiry.

**Custom PHP Logic**
When a purchase completes, custom PHP writes the session balance and expiry rules to the database. This is the bridge between the purchase and the booking system.

**JavaScript Hook at Booking**
When a customer attempts to book a session, a JavaScript hook reads the session balance exposed on the page for the logged-in user. If the balance is zero or the package has expired, the hook prevents the booking form from submitting. The customer sees a prompt to purchase more sessions rather than a booking confirmation.

**Session Decrement**
When a booking is confirmed, the session balance is decremented automatically.

---

[Back to MindBody Replacement](../README.md)
