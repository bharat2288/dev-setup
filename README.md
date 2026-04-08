# dev-setup

A small public starter pack for document-driven AI work.

This repo ships the portable core of my local setup in the same shape it actually lives on disk: a `CLAUDE.md`, a small skill set, spec templates, and a starter macro library.

It is intentionally not the full private system. There are no hooks, agents, MCP servers, sync scripts, or hidden databases here.

## What is here

- `CLAUDE.md` - the root instruction surface
- `.claude/skills/start/` - session startup skill
- `.claude/skills/end/` - session closeout skill
- `.claude/skills/brainstorm/` - discovery and kickoff skill
- `.claude/skills/brainstorm/references/kickoff-flow.md` - the guided kickoff reference
- `_templates/` - local spec templates
- `prompt-macros/` - a small macro library, one file per macro

## Mental model

The workflow progression is:

1. `specs/` keep state across sessions.
2. Prompt macros compress repeated reasoning moves.
3. Skills turn repeated routines into named workflow behaviors.

## Suggested local shape

```text
my-project/
|- CLAUDE.md
|- .claude/
|  `- skills/
|- specs/
|  |- design.md
|  |- status.md
|  |- pipeline.md
|  `- decisions.md
|- _templates/
`- prompt-macros/
```

## How to use it

1. Copy `CLAUDE.md`, `.claude/`, `_templates/`, and `prompt-macros/` into the place you want to work from.
2. Create a local `specs/` folder for each project.
3. Instantiate the templates you need:
   - `design-template.md` -> `specs/design.md`
   - `status-template.md` -> `specs/status.md`
   - `pipeline-template.md` -> `specs/pipeline.md`
   - `decisions-template.md` -> `specs/decisions.md`
4. Use `/brainstorm` when the idea is still soft.
5. Use `/start` at session start and `/end` at session end.

## Design choices

- Local-first: everything assumes a local `specs/` folder.
- Plain markdown: continuity lives in visible files, not hidden memory.
- Small surface area: only the parts that travel well are included.
- Real structure: the files are stored where they actually belong, not flattened into docs.

## Not included

- hooks
- MCP
- agent orchestration
- global knowledge search
- cloud sync
- project hub surfaces
- the full private skill and rule library

## Notes

This starter pack is meant to grow slowly. Add things because they survive repeated use, not because they sound comprehensive.
