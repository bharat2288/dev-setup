---
name: start
description: Use when a session is starting or context needs to be reloaded. Reads local specs, summarizes the current state, and suggests a plan based on the user's opening message.
---

# Start

Initialize a session by loading local project context and detecting intent.

## Step 1: Load Local Context

Read the local `specs/` folder when it exists.

1. Read `specs/design.md`
2. Read `specs/status.md`
3. Read `specs/pipeline.md`
4. Read `specs/decisions.md` if it exists
5. Read any relevant `specs/brief-*.md` files if they exist

If `specs/` does not exist yet:

- vague idea or kickoff request -> suggest `/brainstorm`
- clear scope -> continue directly or instantiate templates first

## Step 2: Detect Intent

Use the opening message to decide the likely workflow.

| Intent | Signal words |
|--------|--------------|
| DEBUG | bug, error, failing, broken, not working |
| FEATURE | add, build, implement, create, kickoff |
| CONTINUE | continue, resume, pick up, back to |
| EXPLORE | explain, understand, where is, how does |
| MAINTENANCE | cleanup, refactor, docs, organize |

If there is no clear intent, infer from the open items in `specs/pipeline.md`.

## Step 3: Present Session Context

Use this format:

```markdown
## Session: [project-name]

**Purpose:** [1 sentence from design.md]
**Last session:** [latest note from status.md]
**Pending:** [top items from pipeline.md]

### Recent Decisions
- [relevant decision]

### Detected: [INTENT]
**Plan:**
1. [step]
2. [step]
3. [step]
```

Keep it short. The point is to restore working context, not narrate everything in the repo.

## Keywords

`handoff`
- Write a short resume prompt with current state, recent work, and which spec files to read next.

## Workflow Hints

### DEBUG
1. Reproduce the problem
2. Read the relevant code and recent decisions
3. Fix and verify

### FEATURE
1. Check fit against `design.md`
2. If the request is still fuzzy, route to `/brainstorm`
3. If clear, implement and update specs afterward

### CONTINUE
1. Read the latest session from `status.md`
2. Check open items in `pipeline.md`
3. Resume the next unfinished step

### EXPLORE
1. Read the relevant files
2. Explain what exists
3. Offer to implement if needed

## When to Use

- start of a session
- after a break
- after context compaction
- whenever the project state feels stale
