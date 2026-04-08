---
name: brainstorm
description: Use when the idea is still forming. Turns a vague request into a usable brief, with scope boundaries, decisions, and next steps.
---

# Brainstorm

Conversational discovery for features, projects, and kickoff work.

This skill is for the phase before architecture or implementation, when the user knows they want something but not yet what shape it should take.

## Step 0: Load context

### Existing project

Read local context before asking questions:

1. `specs/design.md`
2. `specs/status.md`
3. `specs/pipeline.md`
4. `specs/decisions.md` if it exists
5. relevant code for the area being discussed

### New project

Read `references/kickoff-flow.md` and use it as the interview guide.

## Step 1: The spark

Start with one question:

`Tell me more about the idea. What are you imagining?`

Probe for:

- what triggered it
- the concrete use case
- the current workaround
- whether it is one feature or several bundled together

One question at a time. Use the user's language, not system jargon.

## Step 2: Scope boundaries

Once the shape is visible, lock the minimum useful version.

Ask:

- What is the smallest version that would still matter?
- What is explicitly out of scope for v1?
- If this had one job, what would it be?

Capture extras as future ideas instead of letting them blur the core request.

## Step 3: Edge cases and tensions

Surface the parts the user has not thought through yet:

- unusual inputs or failure states
- contradictions between earlier answers
- hidden dependencies
- data or UI implications

If the request involves UI, sketch the current and proposed states in ASCII before moving on.

## Step 4: Decision tree

List the unresolved branches and resolve them one by one.

Use this table:

| # | Branch | Code Investigated | Recommendation | Status |
|---|--------|:-:|----------------|--------|
| 1 | [decision topic] | Yes | [what you recommend and why] | Confirmed |
| 2 | [decision topic] | No | [recommendation] | Deferred - [reason] |

Rule: if code can answer a question, read the code before asking the user.

## Step 5: Impact scan

Summarize the likely impact:

- data model
- API surface
- UI surface
- business logic
- new dependencies
- risk level

Classify the work as:

- Additive
- Integrative
- Invasive

## Step 6: Synthesis

Reflect back what you heard, confirm it, then draft a brief using `../../../_templates/brief-template.md`.

Present the brief in chat first. After approval:

1. save it to `specs/brief-[topic].md`
2. if this is a new project, instantiate a starter `CLAUDE.md` from `../../../_templates/claude-md-template.md`
3. recommend the next move:
   - `/brainstorm` is done -> move to architecture or implementation
   - if the idea is still too broad, narrow v1 first

## Conversation style

- curious, not performative
- concrete, not abstract
- gently skeptical when scope starts to sprawl
- concise when the idea is already clear

## When to use

- vague feature requests
- project kickoff
- "what if we built..."
- work that needs scoping before design or code
