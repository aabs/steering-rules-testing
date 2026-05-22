---
id: csharp-dotnet-10-development
version: "1.0.0"
title: C# Development Rules for .NET 10
scope: project
status: active
---

:::rule id="CS10-01" mandatory="true" category="development" tags="csharp, dotnet, language-version"
Target .NET 10 for all production C# projects unless an explicit compatibility constraint requires otherwise.
:::

:::rule id="CS10-02" mandatory="true" category="development" tags="csharp, dotnet, nullable"
Enable nullable reference types for every C# project.
:::

:::rule id="CS10-03" mandatory="true" category="development" tags="csharp, dotnet, warnings"
Treat compiler warnings as errors unless a specific warning is intentionally documented and suppressed.
:::

:::rule id="CS10-04" mandatory="true" category="development" tags="csharp, analyzers, editorconfig"
Enable .NET analyzers and configure rule severity centrally in source-controlled analyzer configuration.
:::

:::rule id="CS10-05" mandatory="true" category="development" tags="csharp, style, consistency"
Use one consistent coding style across the repository and enforce it automatically.
:::

:::rule id="CS10-06" mandatory="true" category="development" tags="csharp, naming"
Use clear, intention-revealing names for types, members, parameters, and locals.
:::

:::rule id="CS10-07" mandatory="true" category="development" tags="csharp, immutability"
Prefer immutable types and immutable state by default.
:::

:::rule id="CS10-08" mandatory="true" category="development" tags="csharp, records, value-objects"
Use records for value-like models where value semantics are intended.
:::

:::rule id="CS10-09" mandatory="false" category="development" tags="csharp, structs, performance"
Use structs only when value semantics and measured performance characteristics justify them.
:::

:::rule id="CS10-10" mandatory="true" category="development" tags="csharp, nullability, contracts"
Express nullability intent explicitly in public and internal APIs.
:::

:::rule id="CS10-11" mandatory="true" category="development" tags="csharp, nullability"
Do not suppress nullable warnings without a specific and justified reason.
:::

:::rule id="CS10-12" mandatory="true" category="development" tags="csharp, exceptions, guard-clauses"
Validate method arguments at the boundary and fail fast on invalid inputs.
:::

:::rule id="CS10-13" mandatory="true" category="development" tags="csharp, exceptions"
Throw exceptions only for exceptional conditions, not for normal control flow.
:::

:::rule id="CS10-14" mandatory="true" category="development" tags="csharp, exceptions, diagnostics"
Preserve useful diagnostic context when throwing or rethrowing exceptions.
:::

:::rule id="CS10-15" mandatory="true" category="development" tags="csharp, async, tasks"
Use async and await for naturally asynchronous operations.
:::

:::rule id="CS10-16" mandatory="true" category="development" tags="csharp, async, cancellation"
Accept and propagate CancellationToken in cancellable asynchronous operations.
:::

:::rule id="CS10-17" mandatory="true" category="development" tags="csharp, async, blocking"
Do not block on Task or ValueTask in asynchronous code paths.
:::

:::rule id="CS10-18" mandatory="false" category="development" tags="csharp, valuetask, performance"
Use ValueTask only when measurement shows it materially reduces allocation or overhead.
:::

:::rule id="CS10-19" mandatory="true" category="development" tags="csharp, collections, linq"
Prefer clear collection and LINQ expressions, but avoid hidden multiple enumeration and unnecessary allocation.
:::

:::rule id="CS10-20" mandatory="true" category="development" tags="csharp, api, interfaces"
Program against abstractions at boundaries where substitution or testability is required.
:::

:::rule id="CS10-21" mandatory="true" category="development" tags="csharp, dependency-injection, di"
Use constructor injection for required dependencies.
:::

:::rule id="CS10-22" mandatory="true" category="development" tags="csharp, dependency-injection, lifetimes"
Choose dependency lifetimes deliberately and keep lifetime usage valid.
:::

:::rule id="CS10-23" mandatory="true" category="development" tags="csharp, dependency-injection, design"
Do not instantiate service dependencies directly inside business logic when dependency injection is appropriate.
:::

:::rule id="CS10-24" mandatory="true" category="development" tags="csharp, srp, cohesion"
Keep classes small, cohesive, and responsible for one clear purpose.
:::

:::rule id="CS10-25" mandatory="true" category="development" tags="csharp, methods, readability"
Keep methods focused on one operation and one level of abstraction.
:::

:::rule id="CS10-26" mandatory="true" category="development" tags="csharp, configuration, options"
Bind configuration to typed options instead of scattering raw configuration access.
:::

:::rule id="CS10-27" mandatory="true" category="development" tags="csharp, logging, diagnostics"
Use structured logging with named properties instead of interpolated log strings.
:::

:::rule id="CS10-28" mandatory="true" category="development" tags="csharp, logging, pii"
Never log secrets, credentials, or other sensitive values.
:::

:::rule id="CS10-29" mandatory="true" category="development" tags="csharp, disposal, resources"
Dispose owned IDisposable and IAsyncDisposable resources correctly.
:::

:::rule id="CS10-30" mandatory="true" category="development" tags="csharp, disposal, ownership"
Do not dispose dependencies that are owned by the dependency injection container.
:::

:::rule id="CS10-31" mandatory="true" category="development" tags="csharp, serialization, contracts"
Keep serialization contracts explicit and decoupled from internal behavior-rich domain types.
:::

:::rule id="CS10-32" mandatory="true" category="development" tags="csharp, generics, reuse"
Use generics to encode reusable type-safe behavior rather than duplicating logic across types.
:::

:::rule id="CS10-33" mandatory="true" category="development" tags="csharp, pattern-matching, clarity"
Prefer pattern matching when it makes type and state handling clearer and safer.
:::

:::rule id="CS10-34" mandatory="true" category="development" tags="csharp, extension-methods"
Use extension members only to add cohesive, discoverable behavior that does not obscure ownership or intent.
:::

:::rule id="CS10-35" mandatory="true" category="development" tags="csharp, time, determinism"
Do not read wall-clock time directly inside business logic when time can be injected or abstracted.
:::

:::rule id="CS10-36" mandatory="true" category="development" tags="csharp, randomness, determinism"
Do not create hidden randomness inside business logic when deterministic behavior is required.
:::

:::rule id="CS10-37" mandatory="true" category="development" tags="csharp, concurrency, thread-safety"
Assume shared mutable state is unsafe unless its concurrency model is explicit.
:::

:::rule id="CS10-43" mandatory="false" category="development" tags="csharp, spans, performance"
Use Span<T> and ReadOnlySpan<T> only where they improve performance without reducing clarity unacceptably.
:::

:::rule id="CS10-44" mandatory="true" category="development" tags="csharp, api-design, visibility"
Expose the narrowest visibility that satisfies the intended usage.
:::

:::rule id="CS10-45" mandatory="true" category="development" tags="csharp, comments, documentation"
Use comments to explain intent, invariants, or non-obvious decisions, not to restate the code.
:::

:::rule id="CS10-46" mandatory="true" category="development" tags="csharp, documentation, public-api"
Document public APIs whose intent, contracts, or failure behavior are not obvious from their signature.
:::

:::rule id="CS10-47" mandatory="true" category="development" tags="csharp, partial, source-generators"
Use partial types and source-generator patterns deliberately and keep generated and hand-written code clearly separated.
:::

:::rule id="CS10-48" mandatory="true" category="development" tags="csharp, interoperability, boundaries"
Keep framework-specific code at the edges and keep core logic framework-agnostic where practical.
:::
