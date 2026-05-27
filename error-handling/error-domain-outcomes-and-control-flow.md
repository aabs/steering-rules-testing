---
id: error-domain-outcomes-and-control-flow
version: "1.0.0"
title: Error Domain Outcomes and Control Flow Rules
scope: project
status: active
---

:::rule id="EDO-001" mandatory="true" category="error-handling" tags="error-handling, domain,results"
Expected business-rule rejections shall be represented as explicit domain outcomes when possible.
:::

:::rule id="EDO-002" mandatory="false" category="error-handling" tags="error-handling, result-types,functional"
When failure is expected and frequent, explicit result types shall be used instead of exceptions.
:::

:::rule id="EDO-003" mandatory="true" category="error-handling" tags="error-handling, branching,exhaustiveness"
Where exhaustive handling is possible, all known error cases shall be handled explicitly.
:::

:::rule id="EDO-004" mandatory="true" category="error-handling" tags="error-handling, state-machines,invariants"
Long-running or multi-step workflows shall be modeled with explicit states and defined failure transitions.
:::

:::rule id="EDO-005" mandatory="true" category="error-handling" tags="error-handling, simplicity,correctness"
Error-handling code shall use explicit control flow and state transitions, and shall keep decision logic side-effect free until commit or external effect is required.
:::

:::rule id="EDO-006" mandatory="true" category="error-handling" tags="error-handling, defensive-programming"
Code interacting with external inputs or dependencies shall model failure as an expected branch.
:::
