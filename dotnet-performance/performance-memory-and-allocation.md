---
id: performance-memory-and-allocation
version: "1.0.0"
title: Performance Memory and Allocation Rules
scope: project
status: active
---

:::rule id="PMA-001" mandatory="true" category="performance" tags="performance, allocations, gc"
Hot-path code shall avoid unnecessary allocations and shall keep allocation rate low enough to prevent avoidable GC pressure.
:::

:::rule id="PMA-002" mandatory="true" category="performance" tags="performance, boxing"
Hot-path code shall avoid hidden boxing.
:::

:::rule id="PMA-003" mandatory="true" category="performance" tags="performance, linq"
When a hot path is allocation-sensitive, allocation-heavy LINQ or iterator chains shall be replaced with materially cheaper loops.
:::

:::rule id="PMA-004" mandatory="true" category="performance" tags="performance, strings"
Hot-path code shall minimize transient string allocation.
:::

:::rule id="PMA-005" mandatory="true" category="performance" tags="performance, parsing, formatting, spans"
When parsing or formatting on hot paths, span-based APIs shall be used when they measurably reduce copying or allocation.
:::

:::rule id="PMA-006" mandatory="false" category="performance" tags="performance, spans"
Span<T> and ReadOnlySpan<T> shall be used only when ownership and lifetime remain safe and clear.
:::

:::rule id="PMA-007" mandatory="false" category="performance" tags="performance, memory"
Memory<T> and ReadOnlyMemory<T> shall be used when buffer lifetime must cross async or heap boundaries.
:::

:::rule id="PMA-008" mandatory="true" category="performance" tags="performance, copying"
Large buffers and collections shall not be copied when a safe slice, view, or reference is sufficient.
:::

:::rule id="PMA-009" mandatory="false" category="performance" tags="performance, stackalloc"
stackalloc shall be used only for small, bounded, short-lived buffers.
:::

:::rule id="PMA-010" mandatory="false" category="performance" tags="performance, pooling, arraypool"
ArrayPool<T> shall be used when measured allocation patterns show frequent buffer churn causing GC pressure.
:::

:::rule id="PMA-011" mandatory="false" category="performance" tags="performance, pooling, objectpool"
Object pooling shall be used only for objects that are expensive to create or reset and are used at predictable high frequency.
:::

:::rule id="PMA-012" mandatory="true" category="performance" tags="performance, pooling, ownership, safety"
Rented or pooled resources shall be returned promptly exactly once and shall not be used or exposed after return.
:::

:::rule id="PMA-013" mandatory="true" category="performance" tags="performance, gc"
GC.Collect shall not be used in production as a performance strategy.
:::
