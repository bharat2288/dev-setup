# OPTIMIZE

## Purpose

Turn a vague request into a tighter, more actionable prompt.

## Trigger

- `OPTIMIZE: [request]`
- `OPTIMIZE[refine-only]: [request]`
- `OPTIMIZE[verbose]: [request]`

## Behavior

1. Identify ambiguity or missing context.
2. Add sensible defaults.
3. Specify output shape and constraints.
4. Rewrite the prompt clearly.
5. Execute it unless the mode is `refine-only`.

## Good for

- underspecified asks
- fuzzy research prompts
- requests that need a stricter output format

## Pairs well with

- `STEPS`
- `VARIANTS`
