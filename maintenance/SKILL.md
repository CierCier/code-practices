---
name: maintenance
description: Refactor, simplify, remove obsolete code, reduce technical debt, or update aging systems. Use when accumulated complexity or drift is making safe changes harder.
---

# Maintenance

- Name the concrete maintenance pain: a repeated defect, costly change, flaky check, obsolete dependency, growing coupling, or warning that hides real problems.
- Trace the full affected surface before editing. Preserve behavior that callers still rely on; do not preserve removed behavior through compatibility shims without a required support window.
- Subtract first: remove dead code, duplicate logic, unused dependencies, stale comments, and obsolete configuration before adding a new abstraction.
- Refactor in small behavior-preserving units. Use a behavior test or observable check to distinguish structural cleanup from behavior changes.
- Fix flaky tests at their nondeterministic source. Do not retry until green or broadly increase timeouts to mask it.
- Address warnings and technical debt deliberately. Avoid broad opportunistic cleanup that obscures the change or increases regression surface.
- Keep dependencies and build configuration current according to project policy. Verify migrations against supported versions.
- Revisit whether a new helper or layer reduces total concepts and call hops. Delete it if it merely moves complexity.

Leave the system measurably easier to understand or change. Explain the benefit through the concrete maintenance cost removed, not a claim that the code is cleaner.