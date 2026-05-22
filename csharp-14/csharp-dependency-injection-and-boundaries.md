---
id: csharp-dependency-injection-and-boundaries
version: "1.0.0"
title: C# Dependency Injection and Boundaries Rules for .NET 10
scope: project
status: active
---

:::rule id="CDB-01" mandatory="true" category="development" tags="csharp, api, interfaces"
Define and consume abstractions (interfaces or equivalent contracts) at architectural boundaries where substitution or testability is required.
:::

:::rule id="CDB-02" mandatory="true" category="development" tags="csharp, dependency-injection, di"
Use constructor injection for required dependencies; do not hide required dependencies behind property injection.
:::

:::rule id="CDB-03" mandatory="true" category="development" tags="csharp, dependency-injection, lifetimes"
Choose DI lifetimes deliberately (for example, singleton for stateless shared services, scoped for request-bound services, transient for lightweight stateless services) and keep lifetime usage valid.
:::

:::rule id="CDB-04" mandatory="true" category="development" tags="csharp, dependency-injection, design"
Do not instantiate service dependencies with `new` inside business logic when DI should provide them.
:::

:::rule id="CDB-05" mandatory="true" category="development" tags="csharp, configuration, options"
Use the .NET Options pattern (`IOptions<T>`, `IOptionsSnapshot<T>`, or `IOptionsMonitor<T>`) and bind configuration into typed options classes.
:::

:::rule id="CDB-06" mandatory="true" category="development" tags="csharp, serialization, contracts"
Define explicit serialization DTOs and keep them separate from behavior-rich domain types.
:::
