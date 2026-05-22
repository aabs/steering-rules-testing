# C# 14 Rules at a Glance

This rules pack improves delivery confidence for C# 14 and .NET 10 codebases.

It is designed to reduce regressions, improve maintainability, and keep services easier to evolve as complexity grows.

## What You Get

- Fewer nullability, API, and contract defects
- Safer async behavior, cancellation, and resource disposal
- Clearer boundaries through consistent DI and abstraction usage
- Better diagnostics with structured logging and stronger exception hygiene
- More consistent code quality through analyzers, style rules, and focused design guidance

## Rule Set Breakdown

- csharp-foundations-and-tooling.md
	Defines baseline language and tooling discipline: target framework, analyzers, warnings, style, naming, and nullability.
- csharp-design-and-modeling.md
	Defines modeling and design quality rules: cohesion, determinism, domain-friendly types, and framework boundary discipline.
- csharp-async-and-resources.md
	Defines async and resource-safety rules: cancellation, blocking avoidance, allocation-sensitive patterns, and disposal ownership.
- csharp-dependency-injection-and-boundaries.md
	Defines dependency and boundary rules: abstraction-first design, DI lifetimes, configuration binding, and serialization boundaries.
- csharp-errors-logging-and-documentation.md
	Defines operational quality rules: exception usage, diagnostic context, logging hygiene, and API documentation expectations.

## Outcome

Applied together, these rules produce C# services that are more reliable in production, easier to maintain, and safer to change.