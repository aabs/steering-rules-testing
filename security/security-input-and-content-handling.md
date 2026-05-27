---
id: security-input-and-content-handling
version: "1.0.0"
title: Security Input and Content Handling Rules
scope: project
status: active
---

:::rule id="ICH-001" mandatory="true" category="security" tags="security, input-validation"
When untrusted input fails boundary validation, the system shall reject it before domain logic executes.
:::

:::rule id="ICH-002" mandatory="true" category="security" tags="security, validation, allow-list"
For constrained inputs, validation shall enforce an explicit allow-list of accepted values or patterns.
:::

:::rule id="ICH-003" mandatory="true" category="security" tags="security, canonicalization"
Before applying validation or authorization decisions that depend on input form, the system shall canonicalize untrusted input.
:::

:::rule id="ICH-004" mandatory="true" category="security" tags="security, output-encoding"
Before rendering or embedding untrusted data, the system shall apply output encoding or safe serialization for the target sink context.
:::

:::rule id="ICH-005" mandatory="true" category="security" tags="security, injection"
The system shall execute commands, queries, templates, and interpretable expressions using parameterized or structured APIs, not string concatenation of untrusted input.
:::

:::rule id="ICH-006" mandatory="true" category="security" tags="security, deserialization"
Before deserializing untrusted data, the system shall enforce explicit schema/type constraints and shall reject payloads targeting privileged or behavior-rich types.
:::

:::rule id="ICH-007" mandatory="true" category="security" tags="security, ssrf, outbound"
When an outbound call target is derived from untrusted input, the system shall enforce destination allow-list checks and shall block unauthorized destinations before making the call.
:::

:::rule id="ICH-008" mandatory="true" category="security" tags="security, file-handling"
For uploaded files and externally supplied binary content, the system shall enforce file type and size checks before processing or storage.
:::
