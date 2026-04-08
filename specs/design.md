---
type: design
project: dev-setup
date: 2026-04-08
created_by: architect
---
# Dev Setup - Design

Living description of what this repo is, what it includes, and how it should evolve.

## Purpose

`dev-setup` is a small public starter pack for document-driven AI work. It packages the portable core of a local workflow system in the same on-disk shape it actually uses: a root `CLAUDE.md`, a small skill set, spec templates, and a starter macro library.

## Actors

- solo builder setting up a local AI workflow
- curious reader cloning the repo after the Post F essay

## Current Scope

- **Root instruction surface**: a trimmed `CLAUDE.md` that explains how the setup is meant to be used.
- **Portable skill set**: public versions of `/start`, `/end`, and `/brainstorm`.
- **Kickoff reference**: the guided kickoff flow stored where it actually belongs under `.claude/skills/brainstorm/references/`.
- **Local spec templates**: starter markdown templates for `design`, `status`, `pipeline`, `decisions`, `brief`, and `CLAUDE.md`.
- **Starter macro set**: a small macro library split into separate markdown files.

## Architecture

```text
README + CLAUDE.md -> explain workflow
.claude/skills/ -> named behavior
_templates/ -> instantiate local project specs
prompt-macros/ -> reusable reasoning cues
```

**Key files**
- `README.md` - public-facing explanation of the starter pack
- `CLAUDE.md` - root instruction surface
- `.claude/skills/start/SKILL.md` - session startup behavior
- `.claude/skills/end/SKILL.md` - session closeout behavior
- `.claude/skills/brainstorm/SKILL.md` - discovery and kickoff behavior
- `_templates/` - starter templates for local project state
- `prompt-macros/` - split macro docs

**Data flow**
- A user clones the repo and copies the setup into a working environment.
- Local `specs/` files carry project continuity across sessions.
- Skills define reusable workflows that operate on those visible files.
- Macros capture recurring reasoning moves that may later become skills.

## Constraints

- **Technical:** Markdown-first, local-first, no hidden infrastructure required.
- **Workflow:** The public repo should preserve real local structure rather than flattening everything into docs.
- **Scope:** No hooks, agents, MCP, sync systems, or private knowledge layers in v1.

## Future Ideas

- [ ] Add more public-ready skills once they are cleanly portable.
- [ ] Add examples showing a real project using the setup.
- [ ] Add a lighter non-Claude-specific variant if the repo grows beyond its current audience.

## References

- `specs/status.md`
- `specs/pipeline.md`
- `specs/decisions.md`
- `README.md`
