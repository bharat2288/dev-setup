---
type: handoff
project: [project-name]
date: [YYYY-MM-DD]
created_by: [orchestrate | manual]
episode: [YYYY-MM-DD-slug]            # ledger filename without prefix/extension; omit for ad-hoc handoffs outside an orchestrated episode
session_label: [A | B | C | ...]      # episode-local; resets per episode; omit if not in an episode
worker_tool: [claude-code | codex | loop-harness | manual]
worker_skill: [tdd | brainstorm | review | sandbox | council | architect | none]
worktree: [relative-path-or-null]
branch: [branch-name]
specs_writer: [orchestrator | worker]      # who writes shared specs (status/pipeline/decisions). Default orchestrator under an episode.
code_commit: [orchestrator | worker]       # who commits project repo code. Default worker (commits own worktree).
code_push: [orchestrator | worker | operator]   # default operator (requires explicit approval at episode close)
expected_return_path: [path-or-null]   # set if worker writes a return artifact instead of pasting a summary
read_first: []
scope: []                              # allowed write paths for the worker; ingest verifies via git diff against this list
dependencies: []                       # other handoff slugs this one waits on
exit_criteria: []
status: [open | dispatched | returned | accepted | rejected | abandoned]
---
# [[<project>-home|<Project Name>]] — Handoff: [Topic]

*[[dev-hub|Hub]]*

> [One-paragraph summary of what this handoff exists to accomplish and the
> context the worker needs immediately.]

---

## Goal

[The single sentence statement of what the worker must achieve.]

## Read First

- [absolute or repo-relative paths the worker must read before starting]
- [...]

## Scope and Boundaries

**In scope:**
- [bullet]

**Out of scope:**
- [bullet]

**Allowed write paths:** (mirrors `scope` field)
- [path]

## Expected Return

The worker reports back with:
- [files changed]
- [tests run + outcome]
- [commit sha(s) on `<branch>`]
- [whether anything is dirty or unpushed]
- [scope-violation notes, if any]

If `expected_return_path` is set: worker writes the return summary to that path
instead of (or in addition to) pasting it back.

## Exit Criteria

- [ ] [concrete, verifiable condition]
- [ ] [...]

## Notes for Operator

[Anything the orchestrator session should remember when ingesting the
return — gotchas, related handoffs, decisions that may need ADR
follow-up, etc.]

---

> **Schema reference:** This template is the canonical handoff shape.
> Frontmatter fields are machine-parseable by `/orchestrate ingest`.
> See `~/.claude/rules/orchestration.md` (and the codex mirror) for the
> protocol.
