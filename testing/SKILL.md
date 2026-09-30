---
name: testing
description: Design or update automated tests for code changes, bug fixes, APIs, and regressions. Use to test observable behavior and avoid vacuous, brittle, or implementation-coupled test cases.
---

# Testing

A useful test can fail for a plausible consumer-visible defect and pass when the contract is correctly implemented.

1. State the behavior or invariant under test in user-visible terms. Identify the input, action, and expected observable result.
2. Choose the narrowest layer that can prove it. Use unit tests for isolated rules, integration tests for collaborating components, and end-to-end tests only for behavior that requires the full path.
3. Cover meaningful boundaries and failure paths: empty and minimum/maximum values, invalid input, authorization, timeouts, partial state, and repeated operations as applicable.
4. Keep tests deterministic and isolated. Control clocks, randomness, network, filesystem, and concurrency only where the scenario requires it.
5. Assert meaningful outputs and state transitions. Reject tests that only assert no exception, non-empty output, a call count, mock forwarding, copied input, or that an implementation detail was invoked unless that is itself the public contract.
6. Avoid duplicating the implementation's algorithm in expected values. Derive expectations from the contract, an independent oracle, or a known regression case.
7. For a bug fix, reproduce the defect before changing code when practical, then retain a focused regression test that fails on the old behavior.
8. Remove tests that only pin incidental wording, internal structure, or a behavior intentionally removed. Do not chase coverage percentages by adding low-signal assertions.
9. Run the focused test and observe the changed path. Report what passed and what important flow remains untested.

Before keeping a test, ask: what realistic defect would make this assertion fail? If the answer is none, strengthen or delete it.