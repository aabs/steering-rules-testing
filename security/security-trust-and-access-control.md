---
id: security-trust-and-access-control
version: "1.0.0"
title: Security Trust and Access Control Rules
scope: project
status: active
---

:::rule id="TAC-001" mandatory="true" category="security" tags="security, trust-boundary"
When data or requests cross a service, user, or external boundary, the receiving boundary shall apply authentication, authorization, and input validation before side effects.
:::

:::rule id="TAC-002" mandatory="true" category="security" tags="security, least-privilege"
For each user, service, and runtime identity, the access policy shall grant only explicitly required permissions and shall deny all undeclared permissions.
:::

:::rule id="TAC-003" mandatory="true" category="security" tags="security, deny-by-default"
When no explicit allow rule matches an access request, the system shall deny the request and shall not execute protected logic.
:::

:::rule id="TAC-004" mandatory="true" category="security" tags="security, business-logic"
Before executing a business action that reads or changes protected state, the system shall evaluate action-level authorization for that action.
:::

:::rule id="TAC-005" mandatory="true" category="security" tags="security, defaults, secure-by-default"
The system configuration shall default to the most restrictive supported security mode, and weaker behavior shall require explicit per-environment opt-in.
:::

:::rule id="TAC-006" mandatory="true" category="security" tags="security, fail-safe"
When a required security dependency or check is unavailable or indeterminate, the system shall deny the operation and shall not apply state changes.
:::

:::rule id="TAC-007" mandatory="true" category="security" tags="security, trust, external-data"
Data from internal services shall be treated as untrusted input at the receiving boundary and shall be validated against the consumer contract before use.
:::
