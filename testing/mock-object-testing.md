---
id: mock-object-testing
version: "1.0.0"
title: Unit Testing With Mock Objects
scope: project
status: active
---

:::rule id="TM-001" mandatory="false" category="mocking" 
When Injecting complex objects into a system under test (SUT), use Mock object frameworks to control the dependencies so that only the SUT is being tested.
:::

:::rule id="TM-002" mandatory="false" category="mocking" 
Create Mock objects for the interface defining the behaviour of a dependency. Don't depend on concrete implementation details of your dependencies.
:::
