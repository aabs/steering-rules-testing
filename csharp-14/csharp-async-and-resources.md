---
id: csharp-async-and-resources
version: "1.0.0"
title: C# Async and Resource Rules for .NET 10
scope: project
status: active
---

:::rule id="CAR-01" mandatory="true" category="development" tags="csharp, async, tasks"
Use `async` and `await` for naturally asynchronous operations and return `Task` or `Task<T>` by default.
:::

:::rule id="CAR-02" mandatory="true" category="development" tags="csharp, async, cancellation"
Accept a `CancellationToken` in cancellable async APIs and pass it through to all cancellable downstream calls.
:::

:::rule id="CAR-03" mandatory="true" category="development" tags="csharp, async, blocking"
Do not block async flows with `.Result`, `.Wait()`, or `.GetAwaiter().GetResult()`; await tasks instead.
:::

:::rule id="CAR-04" mandatory="false" category="development" tags="csharp, valuetask, performance"
Use `ValueTask` only in measured hot paths where synchronous completion is common and allocation reduction is proven.
:::

:::rule id="CAR-05" mandatory="true" category="development" tags="csharp, collections, linq"
Use clear LINQ and collection code by default, but materialize sequences when needed to avoid hidden multiple enumeration (for example, `ToList()` before multiple passes).
:::

:::rule id="CAR-06" mandatory="true" category="development" tags="csharp, disposal, resources"
Dispose owned resources deterministically with `using` or `await using`.
:::

:::rule id="CAR-07" mandatory="true" category="development" tags="csharp, disposal, ownership"
Never dispose dependencies resolved from the DI container; disposal is owned by the container lifecycle.
:::

:::rule id="CAR-08" mandatory="false" category="development" tags="csharp, spans, performance"
Use `Span<T>` and `ReadOnlySpan<T>` only in measured hot paths where they clearly reduce allocations without harming maintainability.
:::
