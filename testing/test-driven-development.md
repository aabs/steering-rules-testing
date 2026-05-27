---
id: test-driven-development
version: "1.0.0"
title: Test-Driven Development Rules
scope: project
status: active
---


:::rule id="TDD-001" category="testing"  mandatory="true"
The development workflow shall follow test-first Red-Green-Refactor.
:::

:::rule id="TDD-005" category="testing"  mandatory="true"
At the start of each cycle, the developer shall create a failing property-based test.
:::

:::rule id="TDD-006" category="testing"  mandatory="true"
In the Green step, the developer shall make the smallest functional code change that makes the failing test pass.
:::

:::rule id="TDD-007" category="testing"  mandatory="true"
In each cycle, the developer shall limit changes to a single concern.
:::

:::rule id="TDD-008" category="testing"  mandatory="true"
When moving from red to green, the implementation shall not mask failures; it shall pass by adding valid functionality.
:::

:::rule id="TDD-002" category="testing"  mandatory="true"
Before writing production code for a behavior, the developer shall write the test code for that behavior.
:::

:::rule id="TDD-003" category="testing"  mandatory="true"
Before implementing code for a behavior, the developer shall execute the corresponding test and observe it fail.
:::

:::rule id="TDD-004" category="testing"  mandatory="true"
When the test passes, the developer shall refactor the changed code while preserving test pass status.
:::

:::rule id="TDD-009" category="testing"  mandatory="true"
After refactoring, the changed code shall satisfy the project cleanliness and technical-debt standards.
:::

