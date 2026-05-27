---
id: concurrency-threading-and-runtime-scheduling
version: "1.0.0"
title: Concurrency Threading and Runtime Scheduling Rules
scope: project
status: active
---

:::rule id="CTR-001" mandatory="true" category="concurrency" tags="concurrency, threads, threadpool"
In concurrent data processing pipelines, routine asynchronous or short-lived background work shall not create dedicated Thread instances.
:::

:::rule id="CTR-002" mandatory="false" category="concurrency" tags="concurrency, dedicated-threads, affinity"
In concurrent data processing pipelines, a dedicated thread should be used only when the workload has long-running affinity that is not suitable for ThreadPool scheduling.
:::

:::rule id="CTR-003" mandatory="true" category="concurrency" tags="concurrency, thread-abort"
In concurrent data processing pipelines, Thread.Abort shall not be used.
:::

:::rule id="CTR-004" mandatory="true" category="concurrency" tags="concurrency, cooperative-cancellation, control"
In concurrent data processing pipelines, concurrent work shall be stopped cooperatively through CancellationToken or equivalent explicit control.
:::

:::rule id="CTR-005" mandatory="false" category="concurrency" tags="concurrency, threadpool, tuning"
In concurrent data processing pipelines, ThreadPool minimum or maximum thread settings should not be changed unless measurements show the default behavior is the bottleneck.
:::

:::rule id="CTR-006" mandatory="false" category="concurrency" tags="concurrency, runtime-config, cpu-groups"
In concurrent data processing pipelines, runtime threading configuration, including CPU group settings, should be changed only when deployment constraints and measurements justify the change.
:::

:::rule id="CTR-007" mandatory="true" category="concurrency" tags="concurrency, starvation, design"
In concurrent data processing pipelines, if thread-pool starvation is detected, the design shall remove the starvation cause instead of adding arbitrary threads.
:::