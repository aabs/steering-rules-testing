---
id: designing-for-testability
version: "1.0.0"
title: Designing for testability
scope: project
status: active
---

:::rule id="TD-001" mandatory="false" category="testability" 
Inject dependencies that can be mocked. 
:::

:::rule id="TD-002" mandatory="false" category="testability" 
Prefer Interface registration in DI containers, rather than registering concrete types.
:::

:::rule id="TD-003" mandatory="false" category="testability"
When registering complex objects for injection elsewhere, create an Interface for the behaviour being injected so that the interface can be the point of dependency.
:::
