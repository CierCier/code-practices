---
name: architecture
description: Design or change module boundaries, APIs, data flow, and state ownership. Use when a feature crosses components or current coupling makes changes difficult.
---

# Architecture

Design from the behavior the system must support, not from a preferred pattern.

- Trace the current request path and identify the actual owner of policy, state, persistence, and side effects.
- Place validation at trust boundaries. Keep internal contracts typed and business rules independent of transport or framework adapters where practical.
- Give each module a cohesive responsibility and explicit dependencies. Avoid cycles, hidden global state, and abstractions that only forward calls.
- Shape APIs around caller use cases. Keep them small; make invalid states difficult to represent and preserve invariants at the owning boundary.
- Prefer composition when it clarifies responsibility; do not add inheritance, registries, plugin points, or layers without a present use case.
- Choose the smallest design that can handle evidenced requirements. Do not add architecture for hypothetical scale or extensibility.
- When replacing an API, migrate all callers and remove the obsolete path in the same change unless an explicitly required compatibility window exists.
- Consider failure, retries, partial completion, and concurrency at the boundary that owns each operation.

Before committing to a new boundary, explain what complexity it removes and which concrete caller benefits. If it only relocates complexity or adds indirection, keep the existing structure.