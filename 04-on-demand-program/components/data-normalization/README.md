# Component: Data Normalization

## Purpose

The data normalization component transforms raw inputs from 11 different product sources into a single unified data structure. This is the most critical component in the program. Everything downstream depends on it being accurate.

---

## What It Does

- Runs hundreds of SQL transformations across all product data sources
- Standardizes field names, data types, and account identifiers across all 11 products
- Merges all normalized records into a single dataset that spans the full product portfolio
- Remaps customer records from the legacy Viewpoint Salesforce instance to the current DX instance

---

## The Salesforce Remapping

One of the most impactful pieces of work in the entire program was remapping customer records from the old Viewpoint Salesforce instance to the new DX instance. Thousands of customers were effectively invisible in the data because their records had never been connected to the new system.

Completing this remapping exposed a large portion of the eligible customer base that had never been billed or tracked. This single piece of work was responsible for a significant portion of the revenue growth from $3.5M to $15M.

---

## Design Notes

Data normalization was identified early as the root cause of most of the program's reliability problems. The original program had no normalization step. Data arrived in different formats from different teams and was manually reconciled, which introduced errors and made auditing nearly impossible.

Building a proper normalization layer before any other system was the architectural decision that made everything else possible.

---

[Back to On-Demand Program](../../README.md)
