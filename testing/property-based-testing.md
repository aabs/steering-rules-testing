---
id: property-based-testing
version: "1.0.0"
title: Property Based Testing Rules
scope: project
status: active
---

:::rule id="PBT-01" mandatory="true" category="testing"
The standard property based testing (PBT) stack is:
- `FsCheck` for property based testing
- `FsCheck.XUnit` for property based testing integration into xunit
:::

:::rule id="PBT-02" mandatory="true" category="testing"
Always default to Property Based Tests rather than Unit tests.
:::

:::rule id="PBT-03" mandatory="true" category="testing"
Property Based Tests should be the default approach for testing that a SUT is broadly correct,
:::

:::rule id="PBT-04" mandatory="true" category="testing"
Unit tests should be reserved for regression cases, to test a specific case that is known to have previously caused issues.
:::

:::rule id="PBT-05" mandatory="true" category="testing"
Never just test single-point scenarios and  happy paths, instead use a Property Based Tests that will test all positive, negative and edge cases.
:::

:::rule id="PBT-06" mandatory="true" category="testing"
Define properties as universal rules that must hold for all valid inputs, rather than relying on specific example cases.
:::

:::rule id="PBT-07" mandatory="true" category="testing"
Design generators to produce diverse, realistic, and edge-case inputs across the full input space.
:::

:::rule id="PBT-08" mandatory="true" category="testing"
Ensure failing cases can be minimized automatically through shrinking to aid debugging.
:::

:::rule id="PBT-09" mandatory="true" category="testing"
Specify preconditions clearly or constrain generators so properties are only evaluated in valid domains.
:::

:::rule id="PBT-10" mandatory="true" category="testing"
Keep tests deterministic and reproducible by controlling randomness and eliminating hidden state or side effects.
:::

:::rule id="PBT-11" mandatory="true" category="testing"
Use strong oracles, models, or metamorphic relationships to validate correctness beyond simple assertions.

- Every property must have an oracle: a mechanical way to decide pass/fail that is stronger than “doesn’t throw” or “looks plausible”.
- Prefer a reference (spec) model oracle when you can: compute expected behaviour using a simpler, obviously-correct implementation and compare.
- If you can’t compute the exact expected output, use a metamorphic oracle: apply a transformation to inputs and assert a predictable relationship between outputs.
- Use multiple weak oracles together (invariants + metamorphic + cross-check) rather than one weak check.
- Fail with evidence: when a property fails, ensure the counterexample is informative (shrinks well; includes classification/labels).
:::


:::rule id="PBT-12" mandatory="true" category="testing"
When making significant changes to a pre-existing unit test, convert it to a Property based test that tests a whole class of invariants and pre and post conditions. 
:::
