---
id: performance-measurement-and-governance
version: "1.0.0"
title: Performance Measurement and Governance Rules
scope: project
status: active
---

:::rule id="PMG-001" mandatory="true" category="performance" tags="performance, measurement"
Before implementing a non-trivial optimization, baseline metrics shall be captured, and the same metrics shall be re-measured after the change.
:::

:::rule id="PMG-002" mandatory="true" category="performance" tags="performance, hot-paths"
Optimization work shall target only paths proven hot in profiling data or paths with material user-visible latency.
:::

:::rule id="PMG-003" mandatory="true" category="performance" tags="performance, correctness"
Performance optimizations shall preserve correctness, deterministic behavior, and required observability.
:::

:::rule id="PMG-004" mandatory="true" category="performance" tags="performance, profiling, observability"
Performance investigations shall use profiling and production-safe telemetry to identify CPU, memory, allocation, and latency bottlenecks.
:::

:::rule id="PMG-005" mandatory="true" category="performance" tags="performance, regression"
Critical performance characteristics shall be protected by repeatable benchmarks or automated regression checks.
:::

:::rule id="PMG-006" mandatory="true" category="performance" tags="performance, simplicity"
When multiple designs meet performance targets, the simplest maintainable design shall be selected.
:::
