---
id: security-workflow-and-provenance-integrity
version: "1.0.0"
title: Security Workflow and Provenance Integrity Rules
scope: project
status: active
---

:::rule id="WPI-001" mandatory="true" category="security" tags="security, workflows, approval"
High-impact security actions shall require explicit user confirmation and shall not be invocable through passive read operations.
:::

:::rule id="WPI-002" mandatory="true" category="security" tags="security, provenance, events"
For security-sensitive commands and events, the system shall record and propagate actor identity, tenant context, authorization context, and correlation identifiers.
:::
