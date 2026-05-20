---
type: orchestration
project: [project-name]
date: [YYYY-MM-DD]
created_by: [orchestrate | manual]
episode: [YYYY-MM-DD-slug]            # matches the filename; durable id for this episode
status: [open | closed | abandoned]
---
# [[<project>-home|<Project Name>]] — Orchestration: [Episode Title]

*[[dev-hub|Hub]]*

> Per-episode ledger for parallel session fan-out. One file per episode.
> Status: `open` while any handoff is non-terminal; `closed` after the
> orchestrator runs `/end` for the episode; `abandoned` if the operator
> garbage-collects an episode that stalled.

---

## Sessions

| Label | Tool | Worktree | Handoff | Dispatched | Returned | Outcome | Commits | Pushed | Next |
|---|---|---|---|---|---|---|---|---|---|
| A | claude-code | `<worktree>` | `[[handoff-...-YYYY-MM-DD]]` | YYYY-MM-DD HH:MM | — | running | — | — | ingest |
| B | codex       | `<worktree>` | `[[handoff-...-YYYY-MM-DD]]` | YYYY-MM-DD HH:MM | YYYY-MM-DD HH:MM | accepted | `abc1234, def5678` | no | — |
| C | manual      | —            | `[[handoff-...-YYYY-MM-DD]]` | YYYY-MM-DD HH:MM | YYYY-MM-DD HH:MM | rejected | — | — | re-dispatch |

**Outcome vocabulary:** `running` · `returned` · `accepted` · `rejected` · `abandoned`

**Pushed vocabulary:** `no` · `yes (operator approved YYYY-MM-DD)` · `n/a` (worker scope is specs-only or read-only)

## Notes

[Free-form. Decisions taken during the episode, friction observed,
follow-up handoffs queued, ADRs that emerged and need `/architect`,
anything that doesn't fit a table column.]

## Episode Close

- [ ] All handoffs in terminal state (`accepted` / `rejected` / `abandoned`)
- [ ] Specs reconciled (`status.md`, `pipeline.md`, `decisions.md` if applicable)
- [ ] Orchestrator session runs `/end` (this is the episode close)
- [ ] Set frontmatter `status: closed`

---

> **Schema reference:** This template is the canonical orchestration
> ledger shape. See `~/.claude/rules/orchestration.md` (and the codex
> mirror) for the protocol.
