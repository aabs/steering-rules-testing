---
id: concurrency-parallelism-state-and-synchronization
version: "1.0.0"
title: Concurrency Parallelism, State, and Synchronization Rules
scope: project
status: active
---

:::rule id="CPS-001" mandatory="false" category="concurrency" tags="concurrency, cpu-bound, taskrun"
In concurrent data processing pipelines, Task.Run should be used only to move CPU-bound work off a caller thread when that separation is required.
:::

:::rule id="CPS-002" mandatory="false" category="concurrency" tags="concurrency, data-parallelism, cpu"
In concurrent data processing pipelines, Parallel.For, Parallel.ForEach, or equivalent data parallelism should be used only for CPU-bound workloads with enough work per item to amortize scheduling overhead.
:::

:::rule id="CPS-003" mandatory="true" category="concurrency" tags="concurrency, partitioning, shared-state"
In concurrent data processing pipelines, CPU-bound work shall be partitioned into independent units that avoid shared mutable state.
:::

:::rule id="CPS-004" mandatory="true" category="concurrency" tags="concurrency, ownership, immutability"
In concurrent data processing pipelines, concurrency designs shall prefer message passing, ownership transfer, or immutable data over shared mutable state.
:::

:::rule id="CPS-005" mandatory="true" category="concurrency" tags="concurrency, synchronization, minimality"
In concurrent data processing pipelines, the weakest synchronization mechanism that preserves correctness shall be selected.
:::

:::rule id="CPS-006" mandatory="true" category="concurrency" tags="concurrency, atomic, interlocked"
In concurrent data processing pipelines, simple counters, flags, and state transitions shall use Interlocked or equivalent atomic primitives instead of coarse locks.
:::

:::rule id="CPS-007" mandatory="true" category="concurrency" tags="concurrency, locks, critical-sections"
In concurrent data processing pipelines, lock scope shall be minimal and shall not include I/O, blocking waits, or long-running computation.
:::

:::rule id="CPS-008" mandatory="true" category="concurrency" tags="concurrency, locks, await"
In concurrent data processing pipelines, code shall not await inside a monitor lock.
:::

:::rule id="CPS-009" mandatory="true" category="concurrency" tags="concurrency, deadlocks, lock-order"
In concurrent data processing pipelines, when a workflow can acquire more than one lock, a consistent lock acquisition order shall be defined and enforced.
:::

:::rule id="CPS-010" mandatory="true" category="concurrency" tags="concurrency, contention, tuning"
In concurrent data processing pipelines, hot-path lock contention shall be removed before thread count or parallelism is increased.
:::

:::rule id="CPS-011" mandatory="true" category="concurrency" tags="concurrency, collections, thread-safe"
In concurrent data processing pipelines, shared multi-threaded collection access shall use concurrent collections instead of externally locked non-thread-safe collections.
:::

:::rule id="CPS-012" mandatory="true" category="concurrency" tags="concurrency, collections, protocol"
In concurrent data processing pipelines, external locking shall not be combined with concurrent collections unless the combined protocol is documented and covered by concurrency tests.
:::