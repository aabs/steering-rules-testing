---
id: security-supply-chain-and-runtime-hardening
version: "1.0.0"
title: Security Supply Chain and Runtime Hardening Rules
scope: project
status: active
---

:::rule id="SRH-001" mandatory="true" category="security" tags="security, dependencies, supply-chain"
Builds shall include only dependencies from the approved dependency inventory.
:::

:::rule id="SRH-002" mandatory="true" category="security" tags="security, vulnerabilities, patching"
Known exploitable dependency vulnerabilities shall be remediated before release or within the defined risk-based remediation SLA.
:::

:::rule id="SRH-003" mandatory="true" category="security" tags="security, unsafe-features"
Dangerous framework, runtime, or parser features shall remain disabled by default, and any enabled use shall have documented justification and scoped constraints.
:::
