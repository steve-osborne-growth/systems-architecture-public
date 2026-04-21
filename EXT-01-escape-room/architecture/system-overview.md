# System Overview

King's Escape Room was built twice. The first time, it was built as a business. The second time, it was rebuilt as an operating system.

The first version required the owner to be present for the business to function. The owner designed the rooms, ran the sessions, trained employees, handled problems, and drove all customer acquisition. That version generated revenue but had no leverage. If the owner was not there, nothing worked.

The second version was designed to run without the owner. Every customer interaction was scripted and trained. Every technical system was documented with failure protocols. Every marketing process was handed off or automated. Every employee decision was either covered by documentation or explicitly delegated.

The transition between those two versions is the real system. This documentation covers both the individual systems built and the architectural thinking behind how they connected.

---

## How the Systems Fit Together

The business had five core operating layers. Each had to work independently and hand off cleanly to the others.

**Customer Experience Layer**
Puzzle design and game flow controlled what customers encountered from the moment they entered a room to the moment they finished. This was the product. Everything else served it.

**Technology Layer**
Arduino-based clue systems and CCTV monitoring handled the in-room electronics. These systems had to be reliable under repeated use and physical stress. A failing puzzle mid-session broke the customer experience immediately.

**Operations Layer**
Employee systems and process manuals governed everything staff touched: room resets, session starts, clue delivery, corporate event management, and multi-room simultaneous operation. This was the hardest layer to systematize because it involved human behavior.

**Customer Acquisition Layer**
SEO-driven marketing brought customers in the door. This ran entirely in-house and was eventually handed off to trained staff. It was the revenue engine that made everything else financially viable.

**Management Layer**
The general manager sat on top of all other layers. The GM role was only viable because the four layers beneath it were fully documented and systematized. Without that foundation, the GM would have needed the owner constantly.

---

## The Principle

The insight from E-Myth Revisited shaped the entire approach: most small business owners build a job for themselves, not a business. A business can run without its owner. A job cannot.

Every system in this project was built with that distinction in mind.

---

[Back to King's Escape Room](../README.md)
