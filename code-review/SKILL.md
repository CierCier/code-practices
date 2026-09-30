---
name: code-review
description: Review a patch, pull request, or proposed implementation for defects. Use to prioritize correctness, security, data integrity, and maintainability over style preferences.
---

# Code review

Review the changed behavior against its callers, contracts, and failure paths. Verify each finding in source before reporting it.

1. Read the diff and enough surrounding code to understand ownership, invariants, and existing conventions.
2. Check correctness first: wrong results, broken boundaries, state corruption, missing failure handling, and compatibility changes.
3. Check security and privacy next: untrusted input, authorization, secret exposure, injection, and unsafe persistence.
4. Check maintainability: unnecessary abstraction, unsafe casts, duplicated policy, dead code, hidden state, brittle tests, and unclear contracts.
5. Check performance only where the patch plausibly changes a measured or material hot path.
6. Follow control flow and data flow through all relevant callers and reverse paths. A change is incomplete if one applicable entry point still uses the old behavior.
7. Report only actionable findings. Include severity, affected location, a concrete failure scenario, and the smallest defensible remedy. Distinguish confirmed defects from questions or risks.
8. Do not report formatting preferences, speculative concerns, or issues that the source disproves. Do not rewrite the patch during a read-only review.

Lead with blocking findings. If none are supported, say so plainly and state the important surfaces you did not inspect.