# Component: Internal User Filter

## Purpose

The internal user filter prevents Trimble employees, partners, and consultants from counting against customer license caps when they log into customer systems.

---

## The Problem It Solves

EMS was designed without accounting for internal users who access customer environments for support, implementation, or consulting. Without a filter, every internal login would consume a customer license slot. For Vista and Spectrum customers, this was a non-starter that would have blocked the entire migration.

---

## How It Works

The filter maintains a database of known internal users, partners, and consultants. When license assignment data is pulled for compliance checking, these users are automatically excluded before any comparison against contracted counts.

The filter runs as a soft cap solution for both Vista and Spectrum until a permanent filtering mechanism is built into EMS itself.

---

## Design Notes

This component was not in the original migration plan. It was identified as a blocker during the build process and required proactive research and cross-team coordination to solve. Building the stopgap allowed the EMS team to continue their roadmap without stopping to build a permanent solution immediately.

---

[Back to EMS Transition](../../README.md)
