---
id: test-driven-development
version: "1.0.0"
title: Test-Driven Development Rules
scope: project
status: active
---


:::rule id="TDD-001" category="testing"  mandatory="true"
You MUST practice test-first development.  Follow the process of "Red-Green-Refactor"

The Rules of TDD are:
- Start with a PBT test that fails.
- Make the smallest change needed to make that test pass.
- Keep each step tiny so you focus on one thing at a time.

Never get a failing test to pass by masking its failure.  Only a valid addition of functionality counts.
:::

:::rule id="TDD-002" category="testing"  mandatory="true"
Test code should be developed first, NEVER in retrospect.
:::

:::rule id="TDD-003" category="testing"  mandatory="true"
Observe a test failing first, before implementing the application code that makes it pass.
:::

:::rule id="TDD-004" category="testing"  mandatory="true"
When a test finally passes, refactor the new code to ensure it is clean and has no technical debt.
:::

