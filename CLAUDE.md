# CLAUDE.md

This repo is a starter pack for document-driven AI work.

It is not an application codebase. Treat it as a portable setup layer: root instructions, reusable skills, spec templates, and a small macro library.

## Read First

1. `README.md`
2. `.claude/skills/`
3. `_templates/`
4. `prompt-macros/`

## Working Style

- Prefer local `specs/` files over hidden memory.
- Read `specs/design.md`, `specs/status.md`, `specs/pipeline.md`, and `specs/decisions.md` at session start when they exist.
- If the user has a vague idea, use `/brainstorm`.
- If the direction is unclear, use `/variants`.
- If a proposal needs to be challenged, use `/pushback`.
- If the task is clear and scoped, implement directly.
- Update local specs at the end of meaningful sessions.

## Structure

- `.claude/skills/` holds portable workflow and reasoning behaviors.
- `_templates/` holds the starter spec templates.
- `prompt-macros/` holds lightweight reasoning cues.

## Scope

This starter pack deliberately omits:

- hooks
- MCP
- agents
- sync systems
- global knowledge databases

Those can be added later if they prove necessary. They are not required for the core workflow.
