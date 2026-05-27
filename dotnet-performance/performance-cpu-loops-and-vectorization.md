---
id: performance-cpu-loops-and-vectorization
version: "1.0.0"
title: Performance CPU Loops and Vectorization Rules
scope: project
status: active
---

:::rule id="PCV-001" mandatory="true" category="performance" tags="performance, loops"
Hot loops shall remain simple, branch-light, and allocation-free where practical.
:::

:::rule id="PCV-002" mandatory="true" category="performance" tags="performance, bounds"
Hot-loop assumptions shall be explicit, and invariant checks shall be validated outside the loop when possible.
:::

:::rule id="PCV-003" mandatory="false" category="performance" tags="performance, simd, intrinsics"
SIMD, hardware intrinsics, or vectorized APIs shall be used only when measurement shows clear benefit and target-platform portability remains acceptable.
:::
