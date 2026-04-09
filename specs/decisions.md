---
type: decisions
project: dev-setup
date: 2026-04-08
created_by: architect
---
# Dev Setup - Decisions

Append-only record of non-obvious choices for the public starter-pack repo.

## Decision Log

### Public repo identity

**Date:** 2026-04-08
**Context:** The older `claude-code-setup` repo name and structure no longer fit the role of a public starter pack.
**Options:** Reuse `claude-code-setup`, mirror the private workflow repo directly, or create a cleaner public identity.
**Choice:** Use `dev-setup` as the public repo name and starter-pack identity.
**Tradeoffs:** The name is broader and more extensible, but the immediate contents remain Claude-first.
**Affects:** Repo naming, public references in Post F, README framing

### Preserve real local structure

**Date:** 2026-04-08
**Context:** The starter pack could have been flattened into a docs-only export for readability.
**Options:** Flatten the repo into explanation docs, or preserve the actual local file layout.
**Choice:** Preserve the real local structure.
**Tradeoffs:** Slightly more opinionated and less generic, but much more honest and directly usable.
**Affects:** `.claude/skills/`, `_templates/`, reference file placement

### Split macros into separate files

**Date:** 2026-04-08
**Context:** The internal macro library exists as a larger consolidated document.
**Options:** Publish one monolithic macro doc or split the starter set into separate files.
**Choice:** Split the public macro set into one file per macro.
**Tradeoffs:** More files, but cleaner reuse and easier selective expansion later.
**Affects:** `prompt-macros/`

### Add only portable reasoning skills

**Date:** 2026-04-09
**Context:** The public starter pack already mentioned `variants` and `pushback` in the surrounding post framing, but the repo only shipped them as macros.
**Options:** Keep the public repo limited to `/start`, `/end`, and `/brainstorm`; add `variants` and `pushback`; or expose a much larger skill bundle.
**Choice:** Add cleaned public versions of `/variants` and `/pushback`, but stop short of heavier skills that depend on private infrastructure or repo-specific context.
**Tradeoffs:** The starter pack becomes more complete and better aligned with Post F, but the public surface area grows slightly.
**Affects:** `.claude/skills/`, `README.md`, public skill-set framing
