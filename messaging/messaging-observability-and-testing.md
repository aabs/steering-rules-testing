---
id: messaging-observability-and-testing
version: "1.0.0"
title: Messaging Observability and Testing Rules
scope: project
status: active
---

:::rule id="MOT-01" mandatory="false" category="messaging" tags="messaging, observability, identifiers"
Attach a stable message identifier to every message.
:::

:::rule id="MOT-02" mandatory="false" category="messaging" tags="messaging, observability, correlation"
Attach causation or correlation identifiers to support tracing across workflows.
:::

:::rule id="MOT-03" mandatory="false" category="messaging" tags="messaging, observability, telemetry"
Record message receipt, retry attempts, final disposition, and failure classification as structured telemetry.
:::

:::rule id="MOT-04" mandatory="false" category="messaging" tags="messaging, ownership, recovery"
Report handling failure at the boundary that owns the recovery decision.
:::

:::rule id="MOT-05" mandatory="false" category="messaging" tags="messaging, testing, reliability"
Test duplicate delivery, redelivery, delay, reordering, poison messages, and replay deliberately.
:::

:::rule id="MOT-06" mandatory="false" category="messaging" tags="messaging, simplicity"
Prefer the simplest messaging topology and contract set that satisfies the required integration needs.
:::