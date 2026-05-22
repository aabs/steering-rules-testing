---
id: csharp-foundations-and-tooling
version: "1.0.0"
title: C# Foundations and Tooling Rules for .NET 10
scope: project
status: active
---

:::rule id="CFT-01" mandatory="true" category="development" tags="csharp, dotnet, language-version"
Set `TargetFramework` to `net10.0` in every production `.csproj` unless a documented compatibility constraint requires a different target.
:::

:::rule id="CFT-02" mandatory="true" category="development" tags="csharp, dotnet, nullable"
Enable nullable reference types in every C# project by setting `<Nullable>enable</Nullable>` in the project file.
:::

:::rule id="CFT-03" mandatory="true" category="development" tags="csharp, dotnet, warnings"
Set `<TreatWarningsAsErrors>true</TreatWarningsAsErrors>` and allow suppression only for explicitly documented warning IDs.
:::

:::rule id="CFT-04" mandatory="true" category="development" tags="csharp, analyzers, editorconfig"
Enable .NET analyzers in all projects and define analyzer severity centrally in a source-controlled root `.editorconfig`.
:::

:::rule id="CFT-05" mandatory="true" category="development" tags="csharp, style, consistency"
Define repository-wide C# style in a root `.editorconfig` and enforce it in CI (for example, `dotnet format --verify-no-changes`).
:::

:::rule id="CFT-06" mandatory="true" category="development" tags="csharp, naming"
Apply consistent naming conventions through `.editorconfig` naming rules and use intention-revealing names for types, members, parameters, and locals.
:::

:::rule id="CFT-07" mandatory="true" category="development" tags="csharp, nullability, contracts"
Express nullability intent explicitly in API signatures using nullable annotations (for example, `string?`) and related nullability attributes where needed.
:::

:::rule id="CFT-08" mandatory="true" category="development" tags="csharp, nullability"
Do not suppress nullable warnings (for example, with `!` or pragma directives) unless the exact reason is documented at the call site.
:::

:::rule id="CFT-09" mandatory="true" category="development" tags="csharp, api-design, visibility"
Default to the narrowest visibility (`private` or `internal`) and widen to `public` only when a real consumer requires it.
:::
