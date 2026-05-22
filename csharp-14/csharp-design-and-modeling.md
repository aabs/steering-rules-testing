---
id: csharp-design-and-modeling
version: "1.0.0"
title: C# Design and Modeling Rules for .NET 10
scope: project
status: active
---

:::rule id="CDM-01" mandatory="false" category="development" tags="csharp, immutability"
Default to immutable models by using `init` setters, `readonly` fields, and immutable collections unless mutability is required.
:::

:::rule id="CDM-02" mandatory="false" category="development" tags="csharp, records, value-objects"
Implement value objects as `record` or `record struct` when value-based equality is the intended behavior.
:::

:::rule id="CDM-03" mandatory="false" category="development" tags="csharp, structs, performance"
Use `struct` only for small, immutable value types when profiling shows a measurable allocation or locality benefit.
:::

:::rule id="CDM-04" mandatory="false" category="development" tags="csharp, srp, cohesion"
Keep each class focused on one responsibility; split classes when behavior changes for unrelated reasons.
:::

:::rule id="CDM-05" mandatory="false" category="development" tags="csharp, methods, readability"
Write methods to perform one operation at one abstraction level; extract helper methods when a method mixes high-level flow and low-level detail.
:::

:::rule id="CDM-06" mandatory="false" category="development" tags="csharp, generics, reuse"
Use generic abstractions to share type-safe behavior instead of duplicating equivalent logic per type.
:::

:::rule id="CDM-07" mandatory="false" category="development" tags="csharp, pattern-matching, clarity"
Use pattern matching (`is`, `switch`, `switch` expressions) as the default for type and state branching when it improves clarity and exhaustiveness.
:::

:::rule id="CDM-08" mandatory="false" category="development" tags="csharp, extension-methods"
Place extension members in focused static classes and use them only for cohesive behavior that is naturally discoverable on the extended type.
:::

:::rule id="CDM-09" mandatory="false" category="development" tags="csharp, time, determinism"
Do not call `DateTime.UtcNow` or `DateTime.Now` directly in domain logic; inject time via `TimeProvider` or an equivalent abstraction.
:::

:::rule id="CDM-10" mandatory="false" category="development" tags="csharp, randomness, determinism"
Do not instantiate randomness directly in domain logic (for example, `new Random()`); inject a randomness abstraction where determinism matters.
:::

:::rule id="CDM-11" mandatory="true" category="development" tags="csharp, concurrency, thread-safety"
Treat shared mutable state as unsafe by default and require an explicit concurrency strategy (for example, immutability, locks, or concurrent collections).
:::

:::rule id="CDM-12" mandatory="false" category="development" tags="csharp, interoperability, boundaries"
Keep framework-specific code (for example, ASP.NET Core and EF Core) at boundary layers and keep core domain logic framework-agnostic.
:::
