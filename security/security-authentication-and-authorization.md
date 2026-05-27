---
id: security-authentication-and-authorization
version: "1.0.0"
title: Security Authentication and Authorization Rules
scope: project
status: active
---

:::rule id="AA-001" mandatory="false" category="security" tags="security, authentication"
When a request targets a protected capability and authentication is missing, invalid, expired, or revoked, the system shall reject it with 401 and shall not execute the protected handler.
:::

:::rule id="AA-002" mandatory="false" category="security" tags="security, authorization"
When an authenticated caller lacks required permission for an operation, the system shall reject the operation with 403 and shall not execute business logic for that operation.
:::

:::rule id="AA-003" mandatory="false" category="security" tags="security, authz, object-level"
For each protected operation on a target resource, the system shall evaluate authorization using the requested action and target resource attributes before performing the operation.
:::

:::rule id="AA-004" mandatory="false" category="security" tags="security, identity, propagation"
When downstream authorization depends on caller context, the upstream service shall propagate caller identity, tenant context, and authorization claims, and the downstream service shall validate them before authorizing.
:::

:::rule id="AA-005" mandatory="false" category="security" tags="security, delegation, impersonation"
When end-to-end user authorization is required across services, the call context shall include both user identity and calling-service identity for downstream authorization decisions.
:::

:::rule id="AA-006" mandatory="false" category="security" tags="security, machine-identity"
For service-to-service communication, each service shall authenticate with its own distinct runtime identity, and shared identities across services shall not be used.
:::

:::rule id="AA-007" mandatory="false" category="security" tags="security, mfa, step-up-authentication"
When an operation is classified as high-risk or high-impact, the system shall require step-up authentication in the same session before executing the operation.
:::

:::rule id="AA-008" mandatory="false" category="security" tags="security, feature-flags, admin"
For administrative, diagnostic, and dangerous feature paths, the system shall enforce an explicit admin policy that is stricter than standard user policy and deny access by default.
:::
