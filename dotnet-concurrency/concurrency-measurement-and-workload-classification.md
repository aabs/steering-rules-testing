---
id: concurrency-measurement-and-workload-classification
version: "1.0.0"
title: Concurrency Measurement and Workload Classification Rules
scope: project
status: active
---

:::rule id="CMW-001" mandatory="true" category="concurrency" tags="concurrency, throughput, latency, measurement"
Before changing concurrency design in concurrent data processing pipelines, the system shall capture baseline throughput, latency, queue depth, allocation rate, and thread usage for the target workload.
:::

:::rule id="CMW-002" mandatory="true" category="concurrency" tags="concurrency, classification, workload"
Before selecting a concurrency model for a hot operation in concurrent data processing pipelines, the operation shall be classified as I/O-bound, CPU-bound, or coordination-bound.
:::

:::rule id="CMW-003" mandatory="true" category="concurrency" tags="concurrency, diagnostics, profiling"
During concurrency investigations for concurrent data processing pipelines, the team shall use metrics, tracing, and profiling to identify whether the dominant bottleneck is CPU saturation, blocking, contention, queueing, or allocation pressure.
:::

:::rule id="CMW-004" mandatory="true" category="concurrency" tags="concurrency, simplicity, governance"
When multiple concurrency designs for concurrent data processing pipelines meet measured throughput and latency targets, the simplest maintainable design shall be selected.
:::