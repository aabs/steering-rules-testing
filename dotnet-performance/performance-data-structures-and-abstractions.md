---
id: performance-data-structures-and-abstractions
version: "1.0.0"
title: Performance Data Structures and Abstractions Rules
scope: project
status: active
---

:::rule id="PDA-001" mandatory="true" category="performance" tags="performance, collections"
Collection types shall be selected according to required lookup, iteration, mutation, and allocation characteristics.
:::

:::rule id="PDA-002" mandatory="true" category="performance" tags="performance, enumeration"
Hot-path logic shall not enumerate the same sequence multiple times.
:::

:::rule id="PDA-003" mandatory="true" category="performance" tags="performance, data-structures"
When measurements show cache-locality benefit, contiguous data-access patterns shall be preferred.
:::

:::rule id="PDA-004" mandatory="false" category="performance" tags="performance, structs, readonly-struct"
Structs shall be used only when value semantics and measured allocation or locality benefits justify them; immutable frequently copied value types shall be readonly struct.
:::

:::rule id="PDA-005" mandatory="true" category="performance" tags="performance, mutability"
Immutability shall be the default design, and defensive copying on hot paths shall be used only when required for correctness.
:::

:::rule id="PDA-006" mandatory="true" category="performance" tags="performance, generics"
Generic type-safe implementations shall be preferred over object-based abstractions when object-based designs materially increase boxing or allocation.
:::

:::rule id="PDA-007" mandatory="true" category="performance" tags="performance, virtual-dispatch"
Hot paths shall avoid unnecessary virtual dispatch when an equally maintainable lower-overhead alternative exists.
:::

:::rule id="PDA-008" mandatory="true" category="performance" tags="performance, api-design"
Public APIs shall make efficient usage the default path and expensive behavior explicit.
:::
