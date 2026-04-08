# STEPS

## Purpose

Break a complex task into a clear ordered sequence.

## Trigger

- `STEPS`
- `STEPS: [request]`

## Behavior

1. Parse the goal.
2. Split it into major steps.
3. Order them by dependency.
4. Flag tool needs or decision points.
5. Return a numbered plan.

## Good for

- implementation planning
- research workflows
- multi-stage content or code tasks

## Pairs well with

- `OPTIMIZE`
- `SNAPSHOT`
