---
id: concurrency-async-cancellation-and-time-bounds
version: "1.0.0"
title: Concurrency Async, Cancellation, and Time Bound Rules
scope: project
status: active
---

:::rule id="CAT-001" mandatory="true" category="concurrency" tags="concurrency, async, io"
In concurrent data processing pipelines, naturally asynchronous I/O-bound work shall use asynchronous APIs with async/await.
:::

:::rule id="CAT-002" mandatory="true" category="concurrency" tags="concurrency, blocking, sync-over-async"
In concurrent data processing pipelines, in throughput-sensitive code paths, code shall not call Task.Wait, Task.Result, GetAwaiter().GetResult(), or equivalent blocking waits on asynchronous operations.
:::

:::rule id="CAT-003" mandatory="true" category="concurrency" tags="concurrency, cancellation, propagation"
In concurrent data processing pipelines, when an operation can run long, be queued, or block, the operation shall accept a CancellationToken and shall propagate the same token to downstream cancellable operations.
:::

:::rule id="CAT-004" mandatory="true" category="concurrency" tags="concurrency, cancellation, outcomes"
In concurrent data processing pipelines, when cancellation is requested for an operation, the operation shall terminate cooperatively and report cancellation as a defined control outcome rather than as an unexpected fault.
:::

:::rule id="CAT-005" mandatory="true" category="concurrency" tags="concurrency, timeout, deadline"
In concurrent data processing pipelines, remote, queued, or potentially blocking work shall enforce an explicit timeout or deadline.
:::

:::rule id="CAT-006" mandatory="true" category="concurrency" tags="concurrency, async-all-the-way"
In concurrent data processing pipelines, when an entry operation is asynchronous, the full call path to completion shall remain asynchronous.
:::

:::rule id="CAT-007" mandatory="true" category="concurrency" tags="concurrency, io-bound, taskrun"
In concurrent data processing pipelines, naturally asynchronous I/O operations shall not be wrapped in Task.Run.
:::