---
name: verification-writer
description: Write a compact HTML verification plan for a web change using core test cases plus regression-derived cases from changed code risk areas. Use when the user asks for test steps and expected outcomes before browser execution.
disable-model-invocation: true
---

# Verification Writer

## Goal

Create `VERIFICATION.html` that another agent can execute exactly.

## Inputs

- Base URL
- Changed files/diff
- Optional product acceptance criteria
- Output path (default: `VERIFICATION.html`)

## Method

1. Derive **core test cases** from intended behavior.
2. Derive **regression cases** from changed areas:
   - routing/navigation
   - forms and validation
   - client state transitions
   - direct URL/deep-link loading
   - empty/error states
3. Keep steps deterministic and short.
4. Include expected results that are observable from UI.
5. Assign evidence filenames for each case.

## Required HTML Sections

- Outcome (placeholder before execution)
- Executed Tests table
- Edge/Regression Cases table
- Evidence section with expected filenames
- Agent Flow section (review -> plan -> approval -> verify)

## Table Schema

For each case use:

- Case ID
- Check
- Status (`PENDING` before execution)
- Evidence path

## Rules

- Do not blindly mirror user test list; add likely regressions.
- Prefer fewer high-value cases over long noisy lists.
- Mark assumptions explicitly when behavior is ambiguous.
