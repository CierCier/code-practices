---
name: tooling
description: Select or configure formatters, linters, type checkers, tests, CI, build tools, and developer automation. Use to make useful checks reproducible without adding noisy process.
---

# Tooling

- Start from the project's current toolchain and developer workflow. Improve the existing path before adding another tool.
- Automate repetitive checks that catch likely defects: formatting, linting, type checking, tests, builds, or static analysis.
- Add a tool only when its coverage or workflow benefit justifies setup, runtime, maintenance, and configuration cost. Avoid redundant linters and generic scripts that only forward commands.
- Make commands reproducible and failures legible. Keep local and CI commands aligned; use pinned tool versions where the project requires reproducibility.
- Scope checks to changed code only when that preserves correctness. Do not weaken global checks to make a patch pass.
- Keep configuration near the tool and use one source of truth. Delete obsolete scripts and settings after migration.
- Test the actual command in a clean or representative environment. Distinguish a successful check from behavior verified at runtime.

Prefer a small, discoverable command over a framework for command dispatch. A tool earns its place when it makes feedback faster, more reliable, or easier to act on.