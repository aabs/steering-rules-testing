---
id: messaging-contracts-and-semantics
version: "1.0.0"
title: Messaging Contracts and Semantics Rules
scope: project
status: active
---

:::rule id="MCS-01" mandatory="false" category="messaging" tags="messaging, architecture, contracts"
Define every message type with an explicit contract and clear business meaning.
:::

:::rule id="MCS-02" mandatory="false" category="messaging" tags="messaging, architecture, ownership"
Assign each message type a single owning producer.
:::

:::rule id="MCS-03" mandatory="false" category="messaging" tags="messaging, architecture, semantics"
Use events to communicate facts that have already happened.
:::

:::rule id="MCS-04" mandatory="false" category="messaging" tags="messaging, architecture, semantics"
Use commands to request a specific action from one responsible handler.
:::

:::rule id="MCS-05" mandatory="false" category="messaging" tags="messaging, architecture, boundaries"
Do not use messages to expose internal implementation details.
:::

:::rule id="MCS-06" mandatory="false" category="messaging" tags="messaging, contracts, versioning"
Evolve message contracts in a backward-compatible way whenever feasible.
:::

:::rule id="MCS-07" mandatory="false" category="messaging" tags="messaging, contracts, validation"
Validate every inbound message before executing business logic.
:::

:::rule id="MCS-08" mandatory="false" category="messaging" tags="messaging, contracts, trust"
Treat every inbound message as untrusted until validation and authorization succeed.
:::

:::rule id="MCS-09" mandatory="false" category="messaging" tags="messaging, schema, compatibility"
Do not break existing consumers with incompatible schema changes inside a supported contract version.
:::

:::rule id="MCS-10" mandatory="false" category="messaging" tags="messaging, schema, tolerance"
Consumers must ignore unknown forward-compatible fields unless the contract explicitly forbids them.
:::

:::rule id="MCS-11" mandatory="false" category="messaging" tags="messaging, schema, transformation"
Use explicit version-aware transformation when historical messages cannot be consumed natively after schema evolution.
:::

:::rule id="MCS-12" mandatory="false" category="messaging" tags="messaging, routing, determinism"
Message routing rules must be explicit and deterministic.
:::