---
id: error-consistency-and-atomicity
version: "1.0.0"
title: Error Consistency and Atomicity Rules
scope: project
status: active
---

:::rule id="ECA-001" mandatory="true" category="error-handling" tags="error-handling, invariants, consistency"
When an operation fails, domain invariants shall remain valid.
:::

:::rule id="ECA-002" mandatory="true" category="error-handling" tags="error-handling, atomicity"
Within a consistency boundary, each state-changing operation shall commit all state changes atomically or commit none, leaving observable state unchanged on failure.
:::

:::rule id="ECA-003" mandatory="false" category="error-handling" tags="error-handling, compensation, distributed-systems"
When a distributed multi-step operation cannot be atomic, the workflow shall define and execute compensation for each committed step.
:::

:::rule id="ECA-004" mandatory="true" category="error-handling" tags="error-handling, state-management"
Before applying committed state changes, work that can fail shall be completed using temporary or non-committed state.
:::
