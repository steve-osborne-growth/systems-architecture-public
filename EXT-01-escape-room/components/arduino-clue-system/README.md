# Component: Arduino-Based Digital Clue System

## Purpose

Replace padlock and key-based puzzles with electronic, sensor-driven interactions that respond to customer actions and create immersive reveal moments without staff involvement.

---

## What It Did

Generation One rooms used physical locks and keys. Customers found a key, unlocked a box, found a clue. It was simple and functional but limited in the experiences it could create and increasingly dated as the industry evolved.

Generation Two rooms used Arduino microcontrollers and C++ to create electronic puzzles. When a customer solved a puzzle, something happened in the room: a hidden door opened, an object dropped from the ceiling, a secret compartment was revealed, or a new clue appeared. The mechanism was invisible to the customer. They interacted with the room, and the room responded.

The core hardware pattern was a magnetic lock held closed by an electrical current. When the puzzle was solved, the Arduino cut power to the lock and it released. What happened next depended on what was behind or attached to the lock.

---

## Examples Built

**Torch sequence puzzle:** A cave-themed room with multiple openings in the wall. Customers had to insert a prop torch into the correct openings in the correct order. Each opening had a light sensor inside. When the correct sequence was completed, an Arduino registered the pattern and opened a hidden compartment elsewhere in the room.

**Symbol tree:** A fake tree built into the corner of a room. The actual puzzle was across the room where customers arranged symbols in a specific order based on a prior clue. When the correct combination was entered, the tree opened.

**Ceiling drop:** A sequence of buttons on a wall. When pressed in the correct order, a paddle attached to a mag lock dropped from the ceiling. Customers had no idea it was there until it fell.

---

## Built With

- Arduino microcontrollers
- C++ for all logic and sensor handling
- Magnetic locks as the primary release mechanism
- Light sensors, button arrays, and RFID components depending on puzzle type
- Custom physical construction to house and conceal all electronics

---

## Impact

The Gen Two transition modernized the rooms and moved the business from a basic operation into something with real technical infrastructure. It also created genuine surprise moments that customers talked about and reviewed, which fed directly into the SEO and word-of-mouth acquisition channels.

The durability challenge was significant. Electronics in an environment where customers are encouraged to search, touch, and interact with everything required robust construction and regular maintenance protocols.

---

[Back to King's Escape Room](../../README.md)
