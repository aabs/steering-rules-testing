---
id: property-based-testing
version: "1.0.0"
title: Property Based Testing Rules
scope: project
status: active
---

:::rule id="PBT-01" mandatory="false" category="testing"
When the test project targets .NET 8+, the property-based test suite shall use FsCheck.
:::

:::rule id="PBT-02" mandatory="false" category="testing"
When the test project targets .NET 8+ and uses xUnit, the property-based test suite shall use FsCheck.Xunit integration.
:::

:::rule id="PBT-03" mandatory="true" category="testing"
For broad SUT-correctness testing, the test suite shall use property-based tests as the default test type.
:::

:::rule id="PBT-04" mandatory="true" category="testing"
For regression testing, the test suite shall use unit tests only for specific cases that previously caused issues.
:::

:::rule id="PBT-05" mandatory="true" category="testing"
Each property-based test shall cover positive, negative, and edge-case input classes.
:::

:::rule id="PBT-06" mandatory="true" category="testing"
Each property shall define a universal invariant that holds for all valid inputs.
:::

:::rule id="PBT-07" mandatory="true" category="testing"
Each generator shall produce diverse realistic values, including edge cases, across the input domain.
:::

:::rule id="PBT-08" mandatory="true" category="testing"
When a property fails, the framework shall automatically shrink the failing input to a minimal counterexample.
:::

:::rule id="PBT-09" mandatory="true" category="testing"
For each property, the test shall enforce valid-domain evaluation through explicit preconditions or constrained generators.
:::

:::rule id="PBT-10" mandatory="true" category="testing"
Each property-based test shall be deterministic and reproducible by controlling randomness and eliminating hidden state or side effects.
:::

:::rule id="PBT-11" mandatory="true" category="testing"
Each property shall use a mechanical oracle that decides pass or fail and is stronger than exception-only or plausibility checks.
:::

:::rule id="PBT-13" mandatory="true" category="testing"
When a simpler correct reference model is available, each property shall use it as the oracle.
:::

:::rule id="PBT-14" mandatory="true" category="testing"
When exact expected outputs are not computable, each property shall use a metamorphic oracle with a predictable output relationship.
:::

:::rule id="PBT-15" mandatory="true" category="testing"
When no single strong oracle is available, each property shall combine multiple weak oracles.
:::

:::rule id="PBT-16" mandatory="true" category="testing"
When a property fails, the test output shall include an informative counterexample that shrinks well and includes classification labels.
:::


:::rule id="PBT-12" mandatory="true" category="testing"
When significantly changing a pre-existing unit test, the test suite shall convert it to a property-based test that verifies invariants and pre/postconditions across an input class.
:::
