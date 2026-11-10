---
name: verification-orchestrator
description: Orchestrate post-implementation quality flow: dispatch code review, dispatch verification-writer, request user approval on the generated HTML plan, then run verifier-runner in Chrome DevTools MCP. Use after coding is complete.
disable-model-invocation: true
---

# Verification Orchestrator

## Goal

Enforce a consistent, approval-gated verification flow.

## Workflow

1. **Code Review Stage**
   - Dispatch code-review agent on current changes.
   - Collect key risks and probable regression areas.

2. **Verification Plan Stage**
   - Dispatch `verification-writer`.
   - Require compact `VERIFICATION.html` output.
   - Ensure it includes both core and regression-derived cases.

3. **Approval Gate (Mandatory)**
   - Present plan to user.
   - Ask for explicit approval before execution.
   - If edits requested, revise and re-present.

4. **Execution Stage**
   - Dispatch `verifier-runner`.
   - Execute all approved cases in Chrome DevTools MCP.
   - Capture screenshots and update report statuses.

5. **Closeout**
   - Share verdict summary with pass/fail/skipped counts.
   - Highlight regressions or open decisions.

## Non-Negotiables

- No browser execution before approval.
- No silent skipping.
- Verification steps must be agent-followable, deterministic, and concise.
