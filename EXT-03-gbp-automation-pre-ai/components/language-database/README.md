# Component: Language Database

## Purpose

Generate hundreds of natural-sounding post variations per property from structured property data, without writing each post manually.

---

## How It Works

The language database is a structured Google Sheets document with two main sections: property data and phrase libraries.

**Property data** is entered once per client and includes all factual information about the property: amenities, location, community features, pricing tier, nearby highlights, and image library tags.

**Phrase libraries** contain hundreds of pre-written sentence fragments and variations for each attribute type. A library entry for a pool amenity might contain dozens of ways to reference a pool: different words, different sentence structures, different tones. The same pattern applies to every other attribute the system might reference.

A combination engine built with JavaScript and regex formulas pulled from both sections and assembled them into complete post drafts. The engine was designed to minimize repetition by tracking which phrase combinations had already been used for a given property.

---

## The Natural Language Challenge

Getting the posts to sound like natural writing rather than a formula was the hardest part of this component. Early iterations were clearly templated. The variation rules had to be extensive and the phrase libraries had to be written carefully enough that combinations still sounded coherent when assembled automatically.

This required many iterations and manual review cycles before the output quality was consistent enough to reduce review time to 30 minutes per month.

---

## What This Looks Like With AI Today

The entire language database component is now replaceable with a single LLM prompt. Feed in the property data and ask for 200 unique post variations. What took a team weeks to build manually takes seconds today.

The value of having built it the hard way is understanding exactly what the system was doing and why certain approaches produced natural-sounding output while others did not.

---

[Back to GBP Automation](../../README.md)
