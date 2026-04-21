# Design Decisions

Key architectural tradeoffs made in building King's Escape Room as an operating system.

---

## Branching Puzzle Flow Over Linear

**Decision:** Design rooms with parallel, branching puzzle paths rather than a single linear sequence.

**Why:** Early escape rooms were entirely linear. Complete puzzle A to unlock puzzle B. As the industry matured, players who had done other rooms found linear flows predictable and less engaging. Branching flows allowed multiple people in a group to work simultaneously on different puzzles, which better matched how people naturally explore a space.

**Tradeoff:** Branching flows are harder to balance. A puzzle that blocks one path can stall an entire group. Difficulty calibration required more playtesting and iteration than linear designs.

**Why it was worth it:** Repeat customers and differentiation from simpler competitors. Players who finished a branching room felt like they had genuinely solved something complex.

---

## Finishing Over Stopping

**Decision:** Design for every customer to finish the room, even if they exceed the time limit, rather than enforcing a hard stop.

**Why:** Feedback was consistent: customers who were stopped mid-puzzle rated the experience lower than those who finished, even past the time limit. The feeling of incompletion outweighed the time constraint in terms of customer satisfaction.

**Tradeoff:** Sessions occasionally ran long, which could affect the next booking slot.

**Why it was worth it:** Customer satisfaction drove reviews. Reviews drove search rankings. Search rankings drove revenue. Optimizing for satisfaction over strict time enforcement had a direct path to revenue.

---

## Moving to Generation Two Electronics

**Decision:** Replace all padlock-based puzzles with Arduino-driven electronic systems across all rooms.

**Why:** Padlock puzzles had a ceiling. They could only create a certain type of experience. Electronic systems could respond to customer actions in ways that felt genuinely surprising, with doors appearing from nowhere, objects dropping from ceilings, and hidden compartments revealing themselves.

**Tradeoff:** Electronics require maintenance. They fail in ways that physical locks do not. Every electronic puzzle needed a backup plan and a documented reset procedure for failures during a session.

**Why it was worth it:** The Gen Two transition moved the business from a hobbyist-level operation to a genuine entertainment venue with real technical infrastructure. It also created the memorable moments that drove word-of-mouth and reviews.

---

## SEO Over Paid Advertising

**Decision:** Build organic search as the primary acquisition channel rather than running paid advertising.

**Why:** Paid advertising creates a dependency. Stop paying and traffic stops. Organic search compounds. Content published years ago still drives traffic. Building the SEO infrastructure required upfront investment in time and technical skill but produced a durable, low-cost acquisition engine.

**Tradeoff:** SEO takes time to build. Paid advertising produces traffic faster. The business had to survive long enough on early organic results and word-of-mouth before the SEO system reached its full output.

**Why it was worth it:** High profit margins depended on low customer acquisition costs. An escape room running expensive paid advertising is a very different financial model than one generating traffic organically.

---

## Documenting Everything Before Hiring a GM

**Decision:** Fully document all systems and processes before hiring a general manager, rather than hiring first and documenting later.

**Why:** A GM hired into an undocumented business has to learn from the owner directly. That creates dependency and means the owner cannot step away until the GM has accumulated enough informal knowledge. Documentation first meant the GM could learn from the systems, not from the owner.

**Tradeoff:** Documentation took significant time before the owner could step back. The temptation to hire the GM first and figure out documentation later was real.

**Why it was worth it:** The GM was autonomous from the start. The owner was not needed as a trainer or decision-maker. The transition out happened cleanly and quickly.

---

[Back to King's Escape Room](../README.md)
