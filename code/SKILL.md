---
name: code
description: Write or edit application code, APIs, scripts, or refactors. Use to keep implementations idiomatic, explicit, scoped, strongly typed, and easy to change without speculative abstraction.
---

# Code

When writing or changing code:

1. Read the relevant implementation and nearby conventions first. Reuse the source of truth; do not add a parallel pattern.
2. Name the inputs, outputs, state, and invariants before building logic. Use types that reflect the domain and validate untrusted values once at the boundary.
3. Write the smallest complete implementation. Keep control flow visible, mutable state local, and each function responsible for one coherent operation.
4. Prefer direct code over one-use wrappers, generic helpers, speculative extension points, clever chaining, or repeated type conversions. An abstraction earns its cost only when it removes real duplication or makes a meaningful invariant explicit.
5. Avoid `any`, unchecked casts, non-null assertions, and broad error suppression. Find the missing invariant, narrow the type at the boundary, or handle the genuine exceptional case. If a cast is unavoidable, localize it and state the concrete reason.
6. Follow the language and project idioms. Use compiler, formatter, linter, and warnings as feedback; do not silence them to hide a flaw.
7. Keep names precise; comments explain non-obvious constraints or why a surprising choice is necessary, not what the next line does.
8. Remove dead code made obsolete by the change. Do not preserve compatibility paths the task removes.

Before finishing, trace the changed path from caller to observable result. Check that the code solves the requested behavior and that a future maintainer can follow it without reconstructing hidden state.