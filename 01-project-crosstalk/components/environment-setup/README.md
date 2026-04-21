# Component: Environment Setup

## Purpose

The environment setup component initializes the runtime before any data is touched. It ensures every dependency is in place and every credential is loaded before the pipeline begins.

---

## What It Does

- Installs required Python libraries including openai, python-docx, and torch
- Mounts Google Drive to provide persistent file access across sessions
- Loads API credentials for Gong, Salesforce, and OpenAI
- Defines global variables including analysis logs and session configuration
- Validates that required permissions are active before proceeding

---

## Why It Exists as a Separate Stage

Running setup as an isolated first step means the rest of the pipeline can assume a clean, consistent environment. If a dependency is missing or a credential is invalid, the system fails here rather than partway through an analysis run. This makes errors easy to diagnose and fix.

---

## Design Notes

Google Colab was chosen as the runtime environment because it allowed two developers to work in the same live environment simultaneously without local setup overhead. The tradeoff is that the system cannot run on a schedule or trigger automatically. Every run requires a human to initiate it.

---

[Back to Project Crosstalk](../../README.md)
