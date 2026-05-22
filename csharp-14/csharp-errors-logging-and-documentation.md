---
id: csharp-errors-logging-and-documentation
version: "1.0.0"
title: C# Errors, Logging, and Documentation Rules for .NET 10
scope: project
status: active
---

:::rule id="CEL-01" mandatory="true" category="development" tags="csharp, exceptions, guard-clauses"
Validate method arguments at the boundary with guard clauses (for example, `ArgumentNullException.ThrowIfNull`) and fail fast on invalid inputs.
:::

:::rule id="CEL-02" mandatory="true" category="development" tags="csharp, exceptions"
Throw exceptions only for exceptional conditions; use explicit return results for expected control flow outcomes.
:::

:::rule id="CEL-03" mandatory="true" category="development" tags="csharp, exceptions, diagnostics"
Preserve diagnostic context when propagating exceptions: use `throw;` to rethrow and include the original exception as `InnerException` when wrapping.
:::

:::rule id="CEL-04" mandatory="true" category="development" tags="csharp, logging, diagnostics"
Use structured logging with message templates and named properties (for example, `logger.LogInformation("Processed {OrderId}", orderId)`).
:::

:::rule id="CEL-05" mandatory="true" category="development" tags="csharp, logging, pii"
Never log secrets, credentials, tokens, or other sensitive values; log redacted or hashed identifiers where traceability is required.
:::

:::rule id="CEL-06" mandatory="true" category="development" tags="csharp, comments, documentation"
Write comments only for intent, invariants, and non-obvious decisions; do not restate what the code already expresses clearly.
:::

:::rule id="CEL-07" mandatory="true" category="development" tags="csharp, documentation, public-api"
Document public APIs with XML documentation when intent, contracts, or failure behavior are not obvious from the signature.
:::

:::rule id="CEL-08" mandatory="true" category="development" tags="csharp, partial, source-generators"
Keep source-generated and hand-written code clearly separated (for example, generated files under a dedicated generated path, with partial types used only at intentional boundaries).
:::

:::rule id="CEL-09" mandatory="true" category="development" tags="exceptions"
Do work that may fail off to the side before changing committed state. First prepare all risky work using temporary state; then commit using steps that cannot fail or are tightly controlled.
:::


:::rule id="CEL-10" mandatory="true" category="development" tags="exceptions"
Prefer commit-or-rollback behavior when practical. A failed operation should ideally leave the observable state exactly as it was before the operation began
:::