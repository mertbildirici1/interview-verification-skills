---
name: verifier-runner
description: Execute an approved HTML verification plan in Chrome DevTools MCP, capture screenshots, and update case statuses and evidence paths. Use after user approval of verification steps.
disable-model-invocation: true
---

# Verifier Runner

## Goal

Run all approved verification cases and attach evidence.

## Inputs

- Approved `VERIFICATION.html`
- Base URL
- Evidence folder name (for example `review-run-4`)

## Execution Checklist

```text
- [ ] Read approved cases from HTML
- [ ] Execute each case in Chrome DevTools MCP
- [ ] Capture screenshot evidence per case
- [ ] Mark pass/fail/skipped with short note
- [ ] Update VERIFICATION.html verdict and evidence list
```

## Browser Execution Rules

1. Run cases in listed order unless dependencies force reordering.
2. Validate expected outcome using visible UI state.
3. If screenshot direct-write is blocked:
   - write to MCP temp path
   - copy into evidence folder
4. Never skip silently; mark `SKIPPED` with reason.

## Status Policy

- `PASS`: expected result observed
- `FAIL`: expected result not observed
- `SKIPPED`: blocked by env/data/approval
- `NEEDS DECISION`: behavior ambiguous and needs product call

## Output Requirements

- Updated `VERIFICATION.html` with case statuses
- Evidence filenames linked in the report
- Short final verdict summary
