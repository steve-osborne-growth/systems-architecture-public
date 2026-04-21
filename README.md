# Growth Systems Architect Portfolio

I come from growth. Every system I have built has been in service of revenue, speed, or scale.

I am not a traditional engineer. I am not a traditional product manager. I sit at the overlap. I identify what needs to exist, design it, build it, and own the outcome. I use AI as an execution layer. I make architectural tradeoffs under real constraints. I move from a vague problem statement to a working system faster than most teams move from a problem statement to a meeting about the problem.

This portfolio documents that work across nine years, three companies, one business I owned, and projects I built on nights and weekends because I could not leave the problem on the table.

---

## Core Work at Trimble

These are the large systems I architected inside Trimble's AECO organization. Each one started from nothing: no template, no roadmap, no team handed to me. I identified the gap, designed the system, and drove it to production.

| Project | Domain | Problem Solved | Key Tech | Outcome |
|---|---|---|---|---|
| [01 · Project Crosstalk](./01-project-crosstalk/) | Customer Intelligence / AI | Strategic insight trapped inside thousands of hours of customer conversations | Python, Gong API, Salesforce API, Azure OpenAI, Google Colab | $3M in estimated sales influence. Spawned Project Higgs. Won 2023 Innovation Award. |
| [02 · Project Higgs](./02-project-higgs/) | AI / Executive Intelligence | Board narratives lacked customer evidence and "so what" context | Python, Gong API, Salesforce API, OpenAI, Google Colab | Real customer evidence in board materials every quarter. Reuses Crosstalk engine. |
| [03 · EMS Transition](./03-ems-transition/) | Systems Architecture / Migration | 5,500 customers need guided migration to unified licensing with no existing playbook | Domo, SQL, EMS API, Salesforce CLI, MailChimp API, Apps Script | Expected $5-7M in license revenue. Unblocked migration by building internal user filter no one else solved. |
| [04 · On-Demand Program](./04-on-demand-program/) | Revenue Operations | A fragmented, manual billing program with unreliable data and no path to scale | Domo, SQL, Google Apps Script, JavaScript, Google Sites | Grew from $3.5M to $15M per year. Now powering the org-wide EMS transition. |
| [05 · MD&A Workflow](./05-mda-workflow-(aspirational)/) | Agentic AI / Automation | Quarterly management analysis is manual, inconsistent, and always late | n8n, OpenAI API, Salesforce, Gong, Domo APIs, Google Docs API | Aspirational. Full agentic workflow designed with atomic findings, bias review, and NotebookLM delivery. |

---

## Micro Systems

Small tools built fast to solve specific problems. Each one removed friction, saved time, or unlocked revenue. MVPs measured in hours, not weeks.

| System | Problem | Tech | Impact |
|---|---|---|---|
| [License Assignment Validation](./06-micro-systems/license-assignment-validation/) | No way to audit which users counted toward billing without manual PDF review | Google Apps Script, JavaScript | Eliminated daily manual review requests for 18 months |
| [Customer Communication Library](./06-micro-systems/customer-communication-library/) | Years of customer history scattered across Gmail and Gong with no way to consolidate | Gmail API, Gong API, Google Apps Script | Full queryable customer knowledge base buildable in minutes |
| [Operational Contact Gathering](./06-micro-systems/operational-contact-gathering/) | Gathering contacts for 5,500 accounts required six hours of nonstop manual work | Salesforce CLI, SOQL, Google Apps Script, PowerShell | Six hours reduced to five minutes. 20,000+ contacts on demand. |
| [Marketo/Mailchimp Stopgap](./06-micro-systems/marketo-mailchimp-stopgap/) | Zero ability to contact customers at scale for six months after a platform was decommissioned | Google Apps Script, Gmail API, JavaScript | Restored bulk communication during a critical gap. Reduced billing disputes. |
| [Seller Email Generator](./06-micro-systems/seller-email-generator/) | Sellers manually drafting outreach one account at a time from raw dashboard data | Google Sheets, Google Apps Script, Gmail API, Domo | Bulk personalized drafts in seconds. 45-minute MVP. |

---

## External Projects

Work built outside of Trimble: a business I owned and operated, and freelance systems built for clients.

| Project | Context | Domain | Problem Solved | Key Tech | Outcome |
|---|---|---|---|---|---|
| [EXT-01 · King's Escape Room](./EXT-01-escape-room/) | Owner / Operator | Business Systems | Owner-dependent business with no path to autonomous operation | Arduino, C++, CCTV, SEO, PHP, JavaScript, process systems | $300K+ annual revenue. Transitioned from owner-operator to absent owner. Sold in full. |
| [EXT-02 · MindBody Replacement](./EXT-02-mindbody-replacement/) | Freelance | Full-Stack / SaaS Replacement | $900/month SaaS that never fit how the business actually ran | WordPress, WooCommerce, Amelia, PHP, JavaScript, Stripe | Full SaaS replacement at hosting cost only. Session cap enforcement across all booking types. |
| [EXT-03 · GBP Automation (Pre-AI)](./EXT-03-gbp-automation-pre-ai/) | Freelance | Content Automation | SEO team spending 16 hours per person per month on manual Google Business Profile posts | JavaScript, Google Sheets, regex, third-party posting API | Reduced to 30 minutes per month. $24K in monthly recurring revenue within six months. |

---

## Presentations

I have led four company-wide sessions on prompt engineering and AI systems, each delivered multiple times across different teams. Spreading knowledge is a core part of how I work.

| Talk | Audience | Date |
|---|---|---|
| Project Crosstalk: Building Customer Intelligence with AI | Trimble Tech Talk | October 2023 |
| Prompt Engineering for Your Everyday Work | Prompt Engineering Guild | March 2024 |
| Understanding Prompt Engineering: Shaping AI Outputs | Trimble Tech Talk | October 2024 |
| Using AI Prompting to Enhance Your Workflows | AECO Strategy Team | April 2025 |

---

## Awards

| Award | Year |
|---|---|
| Trimble Innovation Award — Project Crosstalk | 2023 |
| Global DreamerHack Winner — Project Compass | 2023 |

---

## How I Think About Systems

Every system in this portfolio started the same way: someone was doing something manually that should not have required a human, or a signal was being lost that should have been captured, or a process existed that only worked because a specific person was in the room.

I look for those gaps. Then I build the thing that closes them.

The systems I am most proud of are not the most technically complex. They are the ones that kept running after I stepped away. Project Crosstalk is still generating intelligence three years later. The On-Demand program infrastructure is now powering a 5,500-customer licensing migration I never planned for when I built it. The escape room business ran without me for over a year before I sold it. A content automation system I built before LLMs existed generated $24K in monthly recurring revenue until AI made it obsolete.

That is what good systems architecture looks like to me: not a system that requires its architect to operate, but one designed for the problem to stay solved.

When I approach a new problem I ask:

- What signal is being ignored or lost right now, and why?
- What would have to be true for this to run without me?
- Where does this connect to revenue, speed, or strategic leverage?
- What am I trading off by building it this way, and what does that tradeoff reveal?
- Where does AI add genuine signal here, and where would it just add noise?

The last question matters more now than it ever has. I have been building AI-assisted systems since before most teams had a policy about it. I know where the leverage is and where the hallucinations are. Both are important to understand.

---

[About Me](./ABOUT.md)
