# Design Decisions

Key architectural tradeoffs made in building the Google Business Profile automation system.

---

## Variation Rules Over True Generation

**Decision:** Build a phrase variation and combination system rather than attempting true content generation.

**Why:** True content generation without AI was not feasible. The alternative was structured variation: a large enough library of phrase fragments combined with rules that prevented obvious repetition. This produced output that was distinct enough post to post that clients and readers would not notice the pattern.

**Tradeoff:** The variation system required significant upfront investment in building the phrase libraries. Each new property type or amenity category had to be added manually. The system could not handle something it had not been explicitly programmed for.

**Why it was worth it:** Once built for a property type, the library applied to every client with similar properties. The investment amortized quickly across a growing client base.

---

## Google Sheets as the Control Interface

**Decision:** Build the entire language database and scheduling workflow in Google Sheets rather than a custom application.

**Why:** The SEO team using the system was already comfortable in Google Sheets. A custom application would have required training, maintenance, and a developer to update. Sheets was accessible to everyone on the team immediately.

**Tradeoff:** Google Sheets has real limitations as a production system. Formula complexity, row limits, and performance constraints became more noticeable as the client list grew.

**Why it was worth it:** The system reached $24,000 in monthly recurring revenue using Google Sheets as its interface. It did not need to be more sophisticated than that to accomplish its goal.

---

## Manual Quality Review as a Feature

**Decision:** Keep a human review step before every batch of posts was scheduled rather than attempting to fully automate quality assurance.

**Why:** The natural language quality of the posts was the core differentiator. A post that sounded like a robot wrote it would undermine the service. A brief human review caught edge cases that the variation rules missed.

**Tradeoff:** The review step meant the system was not fully automated. Someone had to touch it each month.

**Why it was worth it:** 30 minutes of review per property per month against 16 hours of manual writing is a 97% reduction in labor. The review step was not a cost; it was what made the output trustworthy.

---

## Choosing Not to Rebuild With AI

**Reflection:** This system would be trivially simple to rebuild with a language model today. Feed property data into a prompt and generate hundreds of unique posts in seconds. The photo matching, scheduling, and API integration would remain the same.

The decision not to rebuild it was not made. The business continued running the original system until LLMs made it obsolete naturally.

The more interesting question is what this project demonstrated about the problem before AI existed: content variation at scale, natural language quality control, API-based distribution, and bulk scheduling. All of those problems are still real. The language generation layer is now solved by AI. Everything else still has to be built.

---

[Back to GBP Automation](../README.md)
