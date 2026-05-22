---
id: messaging-processing-and-consistency
version: "1.0.0"
title: Messaging Processing and Consistency Rules
scope: project
status: active
---

:::rule id="MPC-01" mandatory="false" category="messaging" tags="messaging, workflows, boundaries"
Keep message handlers responsible for one clear business action or reaction.
:::

:::rule id="MPC-02" mandatory="false" category="messaging" tags="messaging, workflows, orchestration"
Model long-running message-driven workflows with explicit states and transitions.
:::

:::rule id="MPC-03" mandatory="false" category="messaging" tags="messaging, workflows, compensation"
Use compensation when a multi-step message-driven workflow cannot be made atomic.
:::

:::rule id="MPC-04" mandatory="false" category="messaging" tags="messaging, side-effects, safety"
Do not perform irreversible side effects from a message unless duplicate execution is prevented or harmless.
:::

:::rule id="MPC-05" mandatory="false" category="messaging" tags="messaging, side-effects, ordering"
Perform external side effects only after validation and commit preconditions succeed.
:::

:::rule id="MPC-06" mandatory="false" category="messaging" tags="messaging, consistency, state"
Do not let partial failure leave owned business state ambiguous or corrupted.
:::

:::rule id="MPC-07" mandatory="false" category="messaging" tags="messaging, consistency, local-boundary"
Within the handler's local consistency boundary, processing a message must be atomic: either all intended state changes for that message commit, or none commit.
:::