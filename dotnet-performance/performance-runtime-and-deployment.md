---
id: performance-runtime-and-deployment
version: "1.0.0"
title: Performance Runtime and Deployment Rules
scope: project
status: active
---

:::rule id="PRD-001" mandatory="true" category="performance" tags="performance, reflection"
Hot paths shall not use runtime reflection.
:::

:::rule id="PRD-002" mandatory="false" category="performance" tags="performance, source-generators"
When startup or throughput is materially improved, source generation shall be preferred over runtime reflection or runtime code discovery.
:::

:::rule id="PRD-003" mandatory="false" category="performance" tags="performance, tiered-compilation"
Tiered compilation, quick JIT, or compilation settings shall be changed only when benchmark evidence justifies the change.
:::

:::rule id="PRD-004" mandatory="false" category="performance" tags="performance, trimming, aot, compatibility"
When trimmed or Native AOT deployment is required, code paths incompatible with trimming or AOT shall be avoided and library surfaces shall remain trimming-compatible.
:::

:::rule id="PRD-005" mandatory="false" category="performance" tags="performance, native-aot"
Native AOT shall be adopted only when measured startup, memory, deployment, or scale benefits justify its constraints.
:::
