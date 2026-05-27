---
id: security-web-and-request-abuse-protection
version: "1.0.0"
title: Security Web and Request Abuse Protection Rules
scope: project
status: active
---

:::rule id="WRA-001" mandatory="true" category="security" tags="security, replay-protection"
When repeated submission could cause harm, the system shall enforce replay protection and shall reject reused replay tokens or nonces.
:::

:::rule id="WRA-002" mandatory="true" category="security" tags="security, idempotency, duplicates"
For security-sensitive actions, the system shall detect duplicate delivery and repeated requests and shall prevent duplicate side effects.
:::

:::rule id="WRA-003" mandatory="true" category="security" tags="security, state-changes, csrf"
For browser-exposed state-changing operations, the system shall require CSRF protection and shall reject requests that fail origin or anti-CSRF validation.
:::

:::rule id="WRA-004" mandatory="true" category="security" tags="security, cors, browser"
The system shall allow CORS only for explicitly approved origins, methods, and headers.
:::

:::rule id="WRA-005" mandatory="true" category="security" tags="security, rate-limits, abuse"
The system shall enforce abuse controls on unauthenticated, authentication, and security-sensitive endpoints, including request throttling and lockout or backoff behavior.
:::

:::rule id="WRA-006" mandatory="false" category="security" tags="security, throttling, public-apis"
When an interface is exposed to untrusted or high-volume callers, the system shall enforce configured rate limits, quotas, or back-pressure thresholds.
:::
