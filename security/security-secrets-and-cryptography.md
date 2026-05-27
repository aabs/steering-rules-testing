---
id: security-secrets-and-cryptography
version: "1.0.0"
title: Security Secrets and Cryptography Rules
scope: project
status: active
---

:::rule id="SC-001" mandatory="true" category="security" tags="security, secrets"
Source code and committed configuration shall not contain plaintext secrets, credentials, tokens, or private keys.
:::

:::rule id="SC-002" mandatory="true" category="security" tags="security, secret-management"
At runtime, the system shall load required secrets only from approved secret-management mechanisms and shall fail startup when required secrets are unavailable.
:::

:::rule id="SC-003" mandatory="true" category="security" tags="security, token-handling"
The system shall protect access tokens, refresh tokens, API keys, and session identifiers with the same controls used for secrets, including no plaintext logging and no URL placement.
:::

:::rule id="SC-004" mandatory="true" category="security" tags="security, encryption, transport"
Across untrusted networks, the system shall transmit sensitive data only over authenticated encrypted transport.
:::

:::rule id="SC-005" mandatory="true" category="security" tags="security, encryption, storage"
When stored sensitive data exposure creates material risk, the system shall encrypt the data at rest and shall manage keys separately from the data store.
:::

:::rule id="SC-006" mandatory="true" category="security" tags="security, session-management"
Sessions, tokens, and credentials shall have explicit expiration and shall be rejected after expiry.
:::

:::rule id="SC-007" mandatory="false" category="security" tags="security, cryptography, signatures"
When authenticity or non-repudiation is required, the system shall sign the payload and shall reject verification failures before processing.
:::
