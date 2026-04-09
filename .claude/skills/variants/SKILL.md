---
name: variants
description: Use when multiple approaches are plausible and you want distinct options with tradeoffs before committing.
---

# Variants

Generate 3 or more genuinely different ways to solve the problem, then recommend one.

## Process

1. Restate the problem in one sentence.
2. Name the 2-3 criteria that matter most for this decision.
3. Generate 3-4 variants that differ in strategy, not just detail.
4. For each variant, include:
   - approach
   - pros
   - cons
   - best when
   - complexity
5. Compare the variants against the criteria.
6. Recommend one. If the answer depends on a missing fact, name the question that decides it.

## Rules

- Make the variants meaningfully different in tradeoff, abstraction level, or implementation style.
- Include a minimal option when the best move might be to do less.
- Do not hide behind "it depends" without naming what it depends on.

## Output Format

```markdown
## Problem
[one-sentence restatement]

## Criteria
1. [criterion]
2. [criterion]

## Variant 1: [name]
**Approach:** ...
**Pros:** ...
**Cons:** ...
**Best when:** ...
**Complexity:** ...

## Variant 2: [name]
...

## Comparison

| Criterion | V1 | V2 | V3 |
|-----------|----|----|----|

## Recommendation
[which variant to choose and why]
```

## When to Use

- multiple approaches seem plausible
- choosing between build, buy, or defer
- architecture or workflow decisions
- naming or framing decisions that need real alternatives
