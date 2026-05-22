---
id: distributed-microservice-security
version: "1.0.0"
title: Distributed Microservice Security Rules
scope: project
status: active
---

:::rule id="SEC-01" mandatory="true" category="security" tags="security, trust-boundary"
Treat every service boundary, user boundary, and external system boundary as untrusted by default.
:::

:::rule id="SEC-02" mandatory="true" category="security" tags="security, least-privilege"
Grant the minimum privileges required for each user, service, and runtime identity.
:::

:::rule id="SEC-03" mandatory="true" category="security" tags="security, deny-by-default"
Default to deny unless access is explicitly allowed.
:::

:::rule id="SEC-04" mandatory="true" category="security" tags="security, authentication"
Authenticate every externally initiated request before granting access to protected capabilities.
:::

:::rule id="SEC-05" mandatory="true" category="security" tags="security, authorization"
Authorize every operation against the caller's identity, role, claims, or policy.
:::

:::rule id="SEC-06" mandatory="true" category="security" tags="security, authz, object-level"
Enforce authorization on the specific resource or business action being accessed, not only at endpoint level.
:::

:::rule id="SEC-07" mandatory="true" category="security" tags="security, identity, propagation"
Preserve caller identity and security context explicitly across service boundaries where downstream authorization depends on it.
:::

:::rule id="SEC-08" mandatory="false" category="security" tags="security, delegation, impersonation"
Use delegated user context across services only when end-to-end user authorization is required.
:::

:::rule id="SEC-09" mandatory="true" category="security" tags="security, machine-identity"
Use distinct service identities for service-to-service communication.
:::

:::rule id="SEC-10" mandatory="true" category="security" tags="security, secrets"
Never hardcode secrets, credentials, tokens, or keys in source code or configuration files committed to source control.
:::

:::rule id="SEC-11" mandatory="true" category="security" tags="security, secret-management"
Load secrets from approved secret-management mechanisms at runtime.
:::

:::rule id="SEC-12" mandatory="true" category="security" tags="security, token-handling"
Treat access tokens, refresh tokens, API keys, and session identifiers as secrets.
:::

:::rule id="SEC-13" mandatory="true" category="security" tags="security, encryption, transport"
Encrypt sensitive data in transit across all untrusted networks.
:::

:::rule id="SEC-14" mandatory="true" category="security" tags="security, encryption, storage"
Encrypt sensitive data at rest when its exposure would create material risk.
:::

:::rule id="SEC-15" mandatory="true" category="security" tags="security, input-validation"
Validate all untrusted input at the system boundary before using it.
:::

:::rule id="SEC-16" mandatory="true" category="security" tags="security, validation, allow-list"
Prefer allow-list validation over deny-list filtering for constrained inputs.
:::

:::rule id="SEC-17" mandatory="true" category="security" tags="security, canonicalization"
Normalize and canonicalize untrusted input before applying security decisions that depend on its form.
:::

:::rule id="SEC-18" mandatory="true" category="security" tags="security, output-encoding"
Encode or safely serialize untrusted data before rendering or embedding it in downstream consumers.
:::

:::rule id="SEC-19" mandatory="true" category="security" tags="security, injection"
Never concatenate untrusted input into commands, queries, templates, or interpretable expressions.
:::

:::rule id="SEC-20" mandatory="true" category="security" tags="security, deserialization"
Do not deserialize untrusted data into privileged or behavior-rich types without explicit validation and constraints.
:::

:::rule id="SEC-21" mandatory="true" category="security" tags="security, ssrf, outbound"
Treat outbound calls derived from untrusted input as a security-sensitive operation.
:::

:::rule id="SEC-22" mandatory="true" category="security" tags="security, file-handling"
Treat uploaded files and externally supplied binary content as untrusted input.
:::

:::rule id="SEC-23" mandatory="true" category="security" tags="security, error-handling, information-disclosure"
Do not expose internal implementation details, secrets, or security-sensitive diagnostics in client-visible errors.
:::

:::rule id="SEC-24" mandatory="true" category="security" tags="security, logging, audit"
Log security-relevant events with enough context to support detection, investigation, and audit.
:::

:::rule id="SEC-25" mandatory="true" category="security" tags="security, logging, privacy"
Never log secrets, credentials, token contents, or sensitive personal data unless explicitly required and protected.
:::

:::rule id="SEC-26" mandatory="true" category="security" tags="security, audit-integrity"
Security audit records must be tamper-evident or otherwise protected from unauthorized modification.
:::

:::rule id="SEC-27" mandatory="true" category="security" tags="security, session-management"
Session, token, and credential lifetimes must be bounded and no longer than necessary.
:::

:::rule id="SEC-28" mandatory="false" category="security" tags="security, mfa, step-up-authentication"
Require step-up authentication for high-risk or high-impact operations.
:::

:::rule id="SEC-29" mandatory="true" category="security" tags="security, replay-protection"
Protect security-sensitive operations against replay where repeated submission could cause harm.
:::

:::rule id="SEC-30" mandatory="true" category="security" tags="security, idempotency, duplicates"
Do not assume duplicate delivery or repeated requests are benign for security-sensitive actions.
:::

:::rule id="SEC-31" mandatory="true" category="security" tags="security, state-changes, csrf"
Protect user-initiated state-changing operations against cross-origin or cross-site request abuse where relevant.
:::

:::rule id="SEC-32" mandatory="true" category="security" tags="security, cors, browser"
Cross-origin access rules must be explicit and restricted to approved origins, methods, and headers.
:::

:::rule id="SEC-33" mandatory="true" category="security" tags="security, data-minimization"
Collect, expose, and retain only the minimum sensitive data required for the business capability.
:::

:::rule id="SEC-34" mandatory="true" category="security" tags="security, pii, classification"
Classify sensitive data and apply handling rules based on its sensitivity and regulatory impact.
:::

:::rule id="SEC-35" mandatory="true" category="security" tags="security, masking, redaction"
Redact or mask sensitive data whenever full-value exposure is not required.
:::

:::rule id="SEC-36" mandatory="true" category="security" tags="security, segregation, tenancy"
Enforce tenant and customer isolation in every data access path where multi-tenancy exists.
:::

:::rule id="SEC-37" mandatory="false" category="security" tags="security, row-level-security, multi-tenancy"
Use explicit tenant-scoping guards in queries, commands, and events when the system is multi-tenant.
:::

:::rule id="SEC-38" mandatory="true" category="security" tags="security, dependencies, supply-chain"
Use only approved and maintained third-party dependencies.
:::

:::rule id="SEC-39" mandatory="true" category="security" tags="security, vulnerabilities, patching"
Remediate known exploitable dependency vulnerabilities within defined risk-based timeframes.
:::

:::rule id="SEC-40" mandatory="true" category="security" tags="security, unsafe-features"
Do not enable dangerous framework, runtime, or parser features unless their use is explicitly justified and constrained.
:::

:::rule id="SEC-41" mandatory="true" category="security" tags="security, feature-flags, admin"
Protect administrative, diagnostic, and dangerous feature paths with stronger access controls than standard user features.
:::

:::rule id="SEC-42" mandatory="true" category="security" tags="security, rate-limits, abuse"
Apply abuse controls to unauthenticated, authentication, and other security-sensitive endpoints.
:::

:::rule id="SEC-43" mandatory="false" category="security" tags="security, throttling, public-apis"
Use rate limiting, quotas, or back-pressure controls when an interface is exposed to untrusted or high-volume callers.
:::

:::rule id="SEC-44" mandatory="true" category="security" tags="security, workflows, approval"
High-impact security actions must require explicit intent and must not be triggered implicitly by passive reads.
:::

:::rule id="SEC-45" mandatory="true" category="security" tags="security, business-logic"
Model security controls at the business-action level, not only at transport or framework level.
:::

:::rule id="SEC-46" mandatory="true" category="security" tags="security, defaults, secure-by-default"
Choose secure defaults and require explicit opt-in for weaker behavior.
:::

:::rule id="SEC-47" mandatory="true" category="security" tags="security, fail-safe"
When security checks cannot be completed reliably, fail in a safe and restrictive manner.
:::

:::rule id="SEC-48" mandatory="true" category="security" tags="security, trust, external-data"
Never trust data solely because it originated from another internal service.
:::

:::rule id="SEC-49" mandatory="true" category="security" tags="security, provenance, events"
Preserve provenance, identity, and authorization-relevant context for security-sensitive commands and events.
:::

:::rule id="SEC-50" mandatory="false" category="security" tags="security, cryptography, signatures"
Use digital signatures or equivalent integrity protection when message authenticity or non-repudiation is required.
:::