---
id: performance-async-and-concurrency
version: "1.0.0"
title: Performance Async and Concurrency Rules
scope: project
status: active
---

:::rule id="PAC-001" mandatory="true" category="performance" tags="performance, async"
For naturally asynchronous I/O-bound work, asynchronous APIs with async/await shall be used.
:::

:::rule id="PAC-002" mandatory="true" category="performance" tags="performance, blocking"
Throughput-sensitive code paths shall not block threads while waiting for asynchronous operations.
:::

:::rule id="PAC-003" mandatory="false" category="performance" tags="performance, valuetask"
ValueTask shall be used only when measurements show material allocation benefit and usage semantics are correct for ValueTask consumption.
:::

:::rule id="PAC-004" mandatory="true" category="performance" tags="performance, cancellation"
Long-running or potentially blocking operations shall accept and propagate CancellationToken.
:::

:::rule id="PAC-005" mandatory="true" category="performance" tags="performance, concurrency"
Parallelism shall be introduced only when the workload is thread-safe, partitionable, and measurably faster under realistic contention.
:::

:::rule id="PAC-006" mandatory="true" category="performance" tags="performance, contention"
Throughput-sensitive code shall minimize shared mutable state and lock contention.
:::
