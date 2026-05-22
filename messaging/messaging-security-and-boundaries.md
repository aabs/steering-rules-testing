---
id: messaging-security-and-boundaries
version: "1.0.0"
title: Messaging Security and Boundaries Rules
scope: project
status: active
---

:::rule id="MSB-01" mandatory="false" category="messaging" tags="messaging, security, provenance"
Preserve provenance and authorization-relevant context where downstream decisions depend on it.
:::

:::rule id="MSB-02" mandatory="false" category="messaging" tags="messaging, security, data"
Do not place secrets or sensitive data in messages unless explicitly required and protected.
:::

:::rule id="MSB-03" mandatory="false" category="messaging" tags="messaging, autonomy, integration"
Use messaging contracts for inter-system integration rather than shared databases or shared internal code.
:::

:::rule id="MSB-04" mandatory="false" category="messaging" tags="messaging, boundaries, autonomy"
Each consuming service must own its own processing state, retries, and recovery decisions.
:::