---
name: concurrency
description: Build or modify asynchronous, threaded, distributed, or multi-writer code. Use to reason about ownership, races, ordering, cancellation, and backpressure.
---

# Concurrency

Before adding concurrent work, identify which actors run simultaneously and what data, files, keys, or external effects they share.

- Prefer ownership or message passing that removes sharing. Keep shared mutable state small and give each shared resource an explicit synchronization boundary.
- Define ordering and atomicity requirements. Protect invariants with the narrowest lock, transaction, compare-and-swap, or single-writer design that actually enforces them.
- Treat cancellation, timeouts, task failure, and shutdown as normal control paths. Propagate cancellation; do not leave orphaned work or locks held across unrelated awaits.
- Bound queues and parallelism. Specify what happens under overload: wait, reject, shed, or persist. Avoid unbounded task spawning.
- Make retryable operations idempotent where retries or crashes can repeat them. Separate state before serializing concurrent writers where possible.
- Avoid locks around slow I/O unless required for correctness. Document lock ordering when multiple locks remain.
- Test invariants under contention with controlled barriers or stress tests. Use deterministic schedules for known races where possible; do not rely on sleeping to make a race appear.
- Instrument queue depth, failures, cancellation, and latency where operators need to diagnose production behavior.

Do not introduce concurrency to hide a slow path before measuring it. Explain the shared-state invariant and show the changed behavior under the relevant race or cancellation case.