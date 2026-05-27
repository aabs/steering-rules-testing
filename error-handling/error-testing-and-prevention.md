---
id: error-testing-and-prevention
version: "1.0.0"
title: Error Testing and Prevention Rules
scope: project
status: active
---

:::rule id="ETP-001" mandatory="true" category="error-handling" tags="error-handling, testing,negative-paths"
Tests shall verify failure paths, boundary cases, and recovery behavior with the same rigor as success paths.
:::

:::rule id="ETP-002" mandatory="true" category="error-handling" tags="error-handling, prevention,design"
APIs and state models shall be designed so illegal states and invalid operations are difficult to represent.
:::

:::rule id="ETP-003" mandatory="true" category="error-handling" tags="error-handling, exceptions,diagnostics"
Failure-path tests shall verify that diagnostic context is sufficient for troubleshooting and excludes secrets.
:::
