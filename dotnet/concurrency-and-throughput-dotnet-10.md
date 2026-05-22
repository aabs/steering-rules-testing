---
id: concurrency-and-throughput-dotnet-10
version: "1.0.0"
title: Concurrency and Throughput Rules for .NET 10
scope: project
status: active
---

:::rule id="CONC-01" mandatory="true" category="concurrency" tags="concurrency, throughput, measurement"
Measure throughput, latency, queue depth, allocation rate, and thread usage before changing concurrency design.
:::

:::rule id="CONC-02" mandatory="true" category="concurrency" tags="concurrency, work-classification"
Classify each hot operation explicitly as I/O-bound, CPU-bound, or coordination-bound before choosing a concurrency model.
:::

:::rule id="CONC-03" mandatory="true" category="concurrency" tags="concurrency, async, io"
Use async and await for naturally asynchronous I/O-bound work.
:::

:::rule id="CONC-04" mandatory="true" category="concurrency" tags="concurrency, blocking, async"
Do not block on Task, ValueTask, or async waits in throughput-sensitive code paths.
:::

:::rule id="CONC-05" mandatory="true" category="concurrency" tags="concurrency, cancellation"
Accept and propagate CancellationToken in long-running, queued, or potentially blocking operations.
:::

:::rule id="CONC-06" mandatory="true" category="concurrency" tags="concurrency, cancellation, semantics"
Treat cancellation as a normal control outcome, not as an unexpected fault.
:::

:::rule id="CONC-07" mandatory="true" category="concurrency" tags="concurrency, timeouts"
Apply explicit timeouts or deadlines to remote, queued, or potentially blocking work.
:::

:::rule id="CONC-08" mandatory="true" category="concurrency" tags="concurrency, admission-control"
Set an explicit concurrency limit for every fan-out, queue consumer pool, or parallel work stage.
:::

:::rule id="CONC-09" mandatory="true" category="concurrency" tags="concurrency, backpressure"
When consumers have finite capacity, use bounded queues or bounded channels rather than unbounded buffering.
:::

:::rule id="CONC-10" mandatory="false" category="concurrency" tags="concurrency, channels, producer-consumer"
Use Channel<T> for asynchronous producer-consumer pipelines that require explicit bounding or backpressure.
:::

:::rule id="CONC-11" mandatory="true" category="concurrency" tags="concurrency, queues"
Do not allow unbounded queue growth in steady-state production workloads.
:::

:::rule id="CONC-12" mandatory="true" category="concurrency" tags="concurrency, overload"
Reject, defer, shed, or throttle work when the system cannot process more safely.
:::

:::rule id="CONC-13" mandatory="true" category="concurrency" tags="concurrency, task-lifecycle"
Every started Task must be awaited, observed, or deliberately detached with explicit error handling.
:::

:::rule id="CONC-14" mandatory="true" category="concurrency" tags="concurrency, exceptions"
Handle exceptions at the boundary that owns the concurrent operation or work queue.
:::

:::rule id="CONC-15" mandatory="true" category="concurrency" tags="concurrency, aggregation"
When running multiple tasks concurrently, define whether partial failure cancels siblings, waits for all, or collects all results.
:::

:::rule id="CONC-16" mandatory="true" category="concurrency" tags="concurrency, work-creation"
Do not create more concurrent work items than the stage can complete within its latency and memory budget.
:::

:::rule id="CONC-17" mandatory="false" category="concurrency" tags="concurrency, cpu-bound, taskrun"
Use Task.Run only to move CPU-bound work off a caller thread when that separation is required.
:::

:::rule id="CONC-18" mandatory="true" category="concurrency" tags="concurrency, io-bound, taskrun"
Do not wrap naturally asynchronous I/O in Task.Run.
:::

:::rule id="CONC-19" mandatory="true" category="concurrency" tags="concurrency, sync-over-async"
Do not use Task.Wait, Result, or GetAwaiter().GetResult() in throughput-sensitive code paths.
:::

:::rule id="CONC-20" mandatory="false" category="concurrency" tags="concurrency, parallelism, cpu"
Use Parallel.For, Parallel.ForEach, or equivalent data parallelism only for CPU-bound work with enough work per item to amortize scheduling overhead.
:::

:::rule id="CONC-21" mandatory="true" category="concurrency" tags="concurrency, partitioning"
Partition CPU-bound work explicitly so that independent units can run without shared mutable state.
:::

:::rule id="CONC-22" mandatory="true" category="concurrency" tags="concurrency, shared-state"
Prefer message passing, ownership transfer, or immutable data over shared mutable state.
:::

:::rule id="CONC-23" mandatory="true" category="concurrency" tags="concurrency, synchronization"
Choose the weakest synchronization mechanism that preserves correctness.
:::

:::rule id="CONC-24" mandatory="true" category="concurrency" tags="concurrency, interlocked"
Use Interlocked or other atomic primitives for simple counters, flags, and state transitions instead of coarse locks.
:::

:::rule id="CONC-25" mandatory="true" category="concurrency" tags="concurrency, locks"
Keep lock scope minimal and free of I/O, blocking waits, and long-running work.
:::

:::rule id="CONC-26" mandatory="true" category="concurrency" tags="concurrency, locks, await"
Do not await inside a monitor lock.
:::

:::rule id="CONC-27" mandatory="true" category="concurrency" tags="concurrency, deadlocks"
Design lock acquisition order explicitly whenever more than one lock can be taken in the same workflow.
:::

:::rule id="CONC-28" mandatory="true" category="concurrency" tags="concurrency, contention"
Remove hot-path lock contention before increasing thread count or parallelism.
:::

:::rule id="CONC-29" mandatory="true" category="concurrency" tags="concurrency, collections"
Use concurrent collections for shared multi-threaded collection access instead of manually locking non-thread-safe collections.
:::

:::rule id="CONC-30" mandatory="true" category="concurrency" tags="concurrency, ownership, collections"
Do not mix external locking with concurrent collections unless the combined protocol is explicitly documented and tested.
:::

:::rule id="CONC-31" mandatory="true" category="concurrency" tags="concurrency, pipeline-stages"
Give each pipeline stage one clear responsibility, one input contract, and one output contract.
:::

:::rule id="CONC-32" mandatory="true" category="concurrency" tags="concurrency, ordering"
Do not assume completion order matches submission order unless the design enforces it.
:::

:::rule id="CONC-33" mandatory="true" category="concurrency" tags="concurrency, idempotency"
Queued or retryable work must be idempotent or duplicate-safe.
:::

:::rule id="CONC-34" mandatory="true" category="concurrency" tags="concurrency, retries"
Do not increase throughput by blind retry; classify failure and apply bounded retry only where safe.
:::

:::rule id="CONC-35" mandatory="true" category="concurrency" tags="concurrency, threads"
Do not create dedicated Thread instances for routine asynchronous or short-lived background work.
:::

:::rule id="CONC-36" mandatory="false" category="concurrency" tags="concurrency, dedicated-threads"
Use a dedicated thread only when a workload has a clear long-running affinity that is not appropriate for ThreadPool scheduling.
:::

:::rule id="CONC-37" mandatory="true" category="concurrency" tags="concurrency, thread-abort"
Do not use Thread.Abort.
:::

:::rule id="CONC-38" mandatory="true" category="concurrency" tags="concurrency, cooperative-cancellation"
Stop concurrent work cooperatively through CancellationToken or equivalent explicit control.
:::

:::rule id="CONC-39" mandatory="false" category="concurrency" tags="concurrency, threadpool, tuning"
Do not change ThreadPool minimum or maximum thread settings unless measurement shows the default behavior is the bottleneck.
:::

:::rule id="CONC-40" mandatory="false" category="concurrency" tags="concurrency, cpu-groups, windows"
Change .NET threading runtime configuration such as CPU group settings only when the deployment environment and measurements justify it.
:::

:::rule id="CONC-41" mandatory="true" category="concurrency" tags="concurrency, starvation"
Treat thread-pool starvation as a design bug to remove, not as a reason to add arbitrary threads.
:::

:::rule id="CONC-42" mandatory="true" category="concurrency" tags="concurrency, async-all-the-way"
Keep the full call path asynchronous when the entry operation is asynchronous.
:::

:::rule id="CONC-43" mandatory="true" category="concurrency" tags="concurrency, batching"
Batch small independent units of work when per-item scheduling overhead materially limits throughput.
:::

:::rule id="CONC-44" mandatory="true" category="concurrency" tags="concurrency, granularity"
Do not split work so finely that scheduling, synchronization, or queue overhead dominates useful work.
:::

:::rule id="CONC-45" mandatory="true" category="concurrency" tags="concurrency, memory"
Keep per-work-item memory bounded so that concurrency does not turn latency pressure into GC pressure.
:::

:::rule id="CONC-46" mandatory="true" category="concurrency" tags="concurrency, channels, completion"
Complete or close producer-consumer pipelines explicitly so consumers can terminate deterministically.
:::

:::rule id="CONC-47" mandatory="true" category="concurrency" tags="concurrency, observability"
Record queue length, active work count, throughput, latency, failure rate, cancellation rate, and timeout rate for each concurrent stage.
:::

:::rule id="CONC-48" mandatory="true" category="concurrency" tags="concurrency, diagnostics"
Use runtime metrics, tracing, and profiling to confirm whether bottlenecks are CPU saturation, blocking, contention, queueing, or allocation.
:::

:::rule id="CONC-49" mandatory="true" category="concurrency" tags="concurrency, regression"
Protect important concurrency and throughput characteristics with repeatable stress, soak, and benchmark tests.
:::

:::rule id="CONC-50" mandatory="true" category="concurrency" tags="concurrency, simplicity"
Prefer the simplest concurrency model that meets measured throughput and latency goals.
:::