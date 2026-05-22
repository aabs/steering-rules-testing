---
id: universal-testing-rules
version: "1.0.0"
title: Universal Testing Rules
scope: global
status: active
---


:::rule id="TR-001" category="completion" 
A feature is not complete until integration tests prove it:

1. Runs as intended in situ
2. Executes successfully at runtime rather than merely compiling
3. Produces results that are accessible and correct
4. Exercises the major code paths and result types involved

Features with only compilation tests or with failing runtime tests are incomplete.
:::


:::rule id="TR-002" mandatory="false" category="testing" 
Avoid testing internal implementation details and avoid depending on concrete implementations where looser behavioral validation is possible.
:::

:::rule id="TR-003" mandatory="false" category="testing" 
Never mask failing tests with broad `try` or `catch` blocks or "success assertions".
:::

:::rule id="TR-003" mandatory="false" category="testing" 
Failing tests indentify outstanding work and should never be suppressed
:::