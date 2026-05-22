---
id: unit-testing-dotnet
version: "1.0.0"
title: Unit Testing Rules for .NET
scope: project
status: active
---

:::rule id="UT-001" mandatory="false" category="testing" 
The standard unit testing stack for .NET is:

- `xUnit` as the test framework
- `FluentAssertions` for assertions
:::

:::rule id="UT-002" mandatory="true" category="testing" 
All unit tests should be in a dedicated Unit Testing project.  
NEVER put tests in the same project as the code being tested.
:::

:::rule id="UT-003" mandatory="true" category="testing" 
All tests projects should be located under a root folder called `tests/`.
:::

:::rule id="UT-004" mandatory="true" category="testing"
Unit testing should only be used when capturing and testing specific cases that have previously failed under PBT.
:::