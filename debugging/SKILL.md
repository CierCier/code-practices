---
name: debugging
description: Diagnose incorrect behavior, crashes, flaky tests, or runtime failures. Use to reproduce the symptom, trace evidence to its root cause, and verify the repair.
---

# Debugging

- Preserve the reported failure as an observation. Reproduce it with the smallest reliable input before changing code when possible.
- Read the full error and trace. Identify the first relevant failure boundary, not just the last visible symptom.
- Check the assumptions the failing path relies on: input shape, ownership, ordering, environment, state, and error propagation.
- Inspect actual state at the failure point with the debugger, logs, traces, or a focused diagnostic. Avoid broad print statements and unrelated rewrites.
- Change one causal factor at a time. Trace how the failure arose and why the proposed fix prevents it rather than suppressing the error or special-casing one example.
- Add or update a regression test for the externally observable behavior when a deterministic test can capture it.
- Rerun the original reproduction and the focused test. Observe the result; do not treat compilation as proof.

If the problem cannot be reproduced, record what evidence is missing and narrow the next diagnostic step. Do not claim a root cause from correlation alone.