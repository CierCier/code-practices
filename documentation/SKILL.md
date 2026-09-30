---
name: documentation
description: Write or update READMEs, API references, setup guides, architecture notes, and operational instructions. Use when behavior, interfaces, setup, or deployment changes.
---

# Documentation

- Identify the reader and the task they need to complete. Put prerequisites and the shortest working path first.
- Document public contracts, non-obvious decisions, setup, deployment, and limitations that a user or maintainer cannot infer safely from code.
- Prefer a tested example over broad claims. Keep commands, paths, names, and outputs aligned with the current implementation.
- Update documentation with behavior and API changes in the same change. Remove instructions for obsolete flows.
- Keep durable explanation near the code or interface it explains. Use architecture docs for cross-module decisions, not as a duplicate source of implementation truth.
- Explain why a surprising constraint exists; do not narrate obvious code or add comments that merely restate a symbol name.
- Keep prose concise and scannable. Split separate tasks into headings, use consistent terminology, and avoid promises the system does not guarantee.

Verify commands and examples at the nearest practical boundary. If a limitation is not confirmed, label it rather than presenting it as fact.