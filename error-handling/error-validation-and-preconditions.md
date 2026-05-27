---
id: error-validation-and-preconditions
version: "1.0.0"
title: Error Validation and Preconditions Rules
scope: project
status: active
---

:::rule id="EVP-001" mandatory="true" category="error-handling" tags="error-handling, boundaries, validation"
Before business logic executes, boundary inputs shall be validated at system and application boundaries.
:::

:::rule id="EVP-002" mandatory="true" category="error-handling" tags="error-handling, fail-fast, validation"
Before mutating state or invoking external side effects, validation, authorization, and precondition checks shall pass; otherwise processing shall fail fast.
:::

:::rule id="EVP-003" mandatory="true" category="error-handling" tags="error-handling, defaults,correctness"
When data is missing or invalid, defaults shall be used only when domain rules explicitly define them as correct.
:::

:::rule id="EVP-004" mandatory="true" category="error-handling" tags="error-handling, nullability,totality"
Invalid or absent states shall be represented explicitly and shall not rely on implicit nulls or magic values.
:::
