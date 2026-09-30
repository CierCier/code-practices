---
name: thinking
description: Scope coding work, clarify behavior and constraints, compare implementation options, and avoid solving the wrong problem. Use before nontrivial changes or when requirements are ambiguous.
---

# Thinking

Before implementation, turn the request into a checkable outcome:

- Identify the actor, inputs, observable output, state transitions, constraints, and failure behavior.
- Inspect current behavior and the code path that owns it. Separate stated requirements from assumptions; test assumptions in the repository when possible.
- List relevant boundaries and edge cases, especially empty, invalid, repeated, partial, and failure inputs.
- Consider the simplest viable design first. Compare alternatives only when a real tradeoff changes behavior, risk, or maintainability.
- Name the invariant that makes the solution correct. Keep it visible in types, data structures, or a focused check rather than restating it across branches.
- Estimate complexity and likely bottlenecks. Preserve correctness first; measure before optimizing.
- Define how success will be observed at the nearest real boundary. A passing compilation or a test that merely mirrors implementation is not proof of behavior.

Stop exploring once evidence selects a sound approach. Do not grow the scope to address imagined future requirements. When an unresolved choice is genuinely a user preference, explain the tradeoff and ask only for that choice.