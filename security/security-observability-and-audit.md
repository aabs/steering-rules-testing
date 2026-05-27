---
id: security-observability-and-audit
version: "1.0.0"
title: Security Observability and Audit Rules
scope: project
status: active
---

:::rule id="OA-001" mandatory="true" category="security" tags="security, error-handling, information-disclosure"
Client-visible error responses shall not include stack traces, internal implementation details, secrets, or security-sensitive diagnostics.
:::

:::rule id="OA-002" mandatory="true" category="security" tags="security, logging, audit"
The system shall log security-relevant events with timestamp, actor identity, action, target, and outcome fields.
:::

:::rule id="OA-003" mandatory="true" category="security" tags="security, logging, privacy"
Before log persistence, log records shall redact or remove secrets, credentials, token contents, and sensitive personal data unless explicitly required and protected.
:::

:::rule id="OA-004" mandatory="true" category="security" tags="security, audit-integrity"
Security audit records shall be append-only or tamper-evident, and write access shall be restricted to authorized audit writers.
:::
