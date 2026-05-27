---
id: security-data-protection-and-tenant-isolation
version: "1.0.0"
title: Security Data Protection and Tenant Isolation Rules
scope: project
status: active
---

:::rule id="DPT-001" mandatory="true" category="security" tags="security, data-minimization"
For each business capability, the system shall collect, expose, and retain only sensitive data fields that are explicitly required.
:::

:::rule id="DPT-002" mandatory="true" category="security" tags="security, pii, classification"
Each sensitive data field shall have a defined classification, and handling controls shall be enforced according to that classification.
:::

:::rule id="DPT-003" mandatory="true" category="security" tags="security, masking, redaction"
When full sensitive values are not required for a response or log, the system shall redact or mask them before output.
:::

:::rule id="DPT-004" mandatory="true" category="security" tags="security, segregation, tenancy"
When multi-tenancy exists, each data read and write shall be scoped to the caller's tenant and shall reject cross-tenant access.
:::

:::rule id="DPT-005" mandatory="false" category="security" tags="security, row-level-security, multi-tenancy"
When the system is multi-tenant, queries, commands, and events shall include explicit tenant-scoping constraints, and requests missing tenant scope shall be rejected.
:::
