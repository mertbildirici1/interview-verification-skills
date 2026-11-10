# Interview Verification Skills

Reusable Cursor skills for a 3-agent verification workflow:

1. `verification-writer` drafts a regression-aware HTML verification plan.
2. `verifier-runner` executes approved steps in Chrome DevTools MCP and records evidence.
3. `verification-orchestrator` coordinates code review -> plan -> user approval -> execution.

## Included Skills

- `verification-writer/SKILL.md`
- `verifier-runner/SKILL.md`
- `verification-orchestrator/SKILL.md`

## Local Install

Copy each skill folder into `~/.cursor/skills/`:

- `~/.cursor/skills/verification-writer/`
- `~/.cursor/skills/verifier-runner/`
- `~/.cursor/skills/verification-orchestrator/`

## Suggested Usage

1. Run `verification-orchestrator` after implementing code changes.
2. Review the generated `VERIFICATION.html`.
3. Approve or request edits.
4. Let `verifier-runner` execute all approved cases and update the report with evidence.
