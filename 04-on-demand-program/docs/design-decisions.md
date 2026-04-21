# Design Decisions

This document captures the key architectural tradeoffs made in building the On-Demand Program and the reasoning behind each one.

---

## Normalization Before Everything Else

**Decision:** Build the data normalization layer before building any other system component.

**Why:** The original program's core problem was unreliable data. Every other failure in the program, missed customers, incorrect invoices, seller distrust, traced back to this root cause. There was no point building billing tools, seller tools, or dashboards on top of data that could not be trusted.

**Tradeoff:** Normalization took significant time before any visible progress was made. Stakeholders wanted to see revenue growth quickly. The decision to invest in the foundation first delayed short-term wins.

**Why it was worth it:** Every system built after the normalization layer worked correctly the first time because the data underneath it was reliable. The $15M run rate would not have been achievable on a fragmented data foundation.

---

## Self-Serve Seller Tools Over Centralized Support

**Decision:** Build tools that let sellers handle routine actions themselves rather than routing everything through a central support person.

**Why:** The program could not scale if every forgiveness request, do-not-bill flag, and customer inquiry required manual intervention. One person running a program at $15M annual volume cannot also be a help desk.

**Tradeoff:** Building self-serve tools required more upfront design and development time than simply handling requests manually. It also required training sellers to use the tools correctly.

**Why it was worth it:** Seller self-service reduced the operational burden significantly and allowed the program to scale without adding headcount. Sellers also acted faster when they could handle things themselves without waiting.

---

## AI Chatbot with Extensive Validation

**Decision:** Build an AI chatbot to answer program questions rather than relying on documentation alone or routing questions to a person.

**Why:** The program has significant nuance. Sellers, customer success teams, and support agents all interact with it differently and have different questions. A chatbot that could answer questions in natural language 24 hours a day was more scalable than any alternative.

**Tradeoff:** Building a reliable chatbot required hundreds of validation iterations. Shipping a chatbot that gave incorrect answers would spread misinformation across the sales team and directly damage program outcomes. The validation process was time-intensive.

**Why it was worth it:** The chatbot handles a large volume of routine questions that would otherwise require a human response. It also means new sellers onboarding to the program have a resource available immediately.

---

## Treating Enablement as Infrastructure

**Decision:** Build the knowledge base, training materials, and chatbot as first-class system components, not supplementary documentation.

**Why:** Early in the rebuild, the technical systems improved faster than seller awareness and adoption. Revenue growth was constrained by how well sellers understood and trusted the program, not by system capability. This made clear that enablement was not optional. It was part of the system.

**Tradeoff:** Time spent on enablement is time not spent on technical development. This is a real tension that had to be managed throughout the project.

**Why it was worth it:** Seller confidence in the program is directly correlated to conversion rates. A seller who does not understand the program will not prioritize it. A seller who understands it and has the tools to act quickly will.

---

## Manual to Automated Incrementally

**Decision:** Move processes from manual to automated incrementally rather than attempting to automate everything at once.

**Why:** The manual processes had to be understood before they could be automated correctly. Running things manually first revealed edge cases, exceptions, and business rules that would have been missed in an upfront automation design.

**Tradeoff:** The program remained more manual than ideal for longer than was comfortable. This created ongoing operational burden during the transition period.

**Why it was worth it:** Every automation built was based on a real, tested understanding of the process it was replacing. There were no automation failures caused by incomplete process knowledge. The manual work, while a cost, was also the research that made the automation reliable.

---

[Back to On-Demand Program](../README.md)
