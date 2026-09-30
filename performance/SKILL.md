---
name: performance
description: Investigate or optimize slow, memory-heavy, or high-throughput code. Use to establish a representative baseline, find the measured bottleneck, and verify the improvement.
---

# Performance

- Establish the user-visible target: latency, throughput, memory, startup time, or resource cost. Record a representative baseline and workload.
- Profile or instrument the real path before optimizing. Distinguish CPU, allocation, I/O, lock contention, network, and queueing costs.
- Check algorithmic complexity and data volume. Prefer removing repeated work, unnecessary I/O, and avoidable allocations before low-level tuning.
- Make the smallest change that addresses the measured bottleneck. Keep correctness, predictable behavior, and maintainability intact.
- Re-measure under the same workload and environment. Compare distributions and resource cost, not a single favorable sample.
- Add a performance regression guard only when the metric is stable and meaningful in the project environment; avoid flaky timing assertions.

Do not add a cache, batching layer, concurrency, or specialized data structure based on intuition alone. State the evidence that justifies the tradeoff and confirm that the optimization did not change behavior.