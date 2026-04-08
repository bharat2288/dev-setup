---
name: end
description: Use when wrapping up a session. Updates local spec files so the next session can resume cleanly.
---

# End

Close a session by recording what changed and what should happen next.

## Quick Mode: `/end skip`

Run without prompts:

1. Update `specs/status.md` with a short session entry
2. Update `specs/pipeline.md` if items were completed or newly discovered
3. Update `specs/decisions.md` only if a real decision was made
4. Return a short closeout summary

## Full Mode

### Step 1: Review the session

Scan the conversation and recent file changes for:

- what was accomplished
- what changed in project state
- any decisions that should be remembered
- what the next session should focus on

### Step 2: Update local specs

Use the local `specs/` folder only.

- `specs/status.md`
  - add a new session entry
  - keep the current state section accurate
- `specs/pipeline.md`
  - mark finished items done
  - add new follow-up work if it emerged
- `specs/decisions.md`
  - append decisions with context, choice, and tradeoffs
  - skip if nothing non-obvious was decided

If `specs/` does not exist, say so and provide a short textual closeout instead of fabricating files.

### Step 3: Capture next-session focus

Prefer one or two concrete next steps over a broad backlog dump.

## Output

```markdown
## End: [project-name]

### Accomplished
- [item]
- [item]

### Recorded
- Status updated
- Pipeline updated
- Decisions: [count or none]

### Next Session
1. [focus]
2. [focus]
```

## Recording Rules

Record:

- changes in direction
- non-obvious tradeoffs
- newly discovered follow-up work

Do not record:

- obvious typos
- trivial renames
- temporary dead ends that taught nothing

## When to Use

- session end
- before a long break
- before switching to another project
