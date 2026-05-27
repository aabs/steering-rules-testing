---
id: universal-testing-rules
version: "1.0.0"
title: Universal Testing Rules
scope: global
status: active
---


:::rule id="UTR-001" category="completion"
A feature shall be marked complete only when integration tests pass at runtime, verify in-situ behavior, verify accessible and correct results, and exercise major code paths and result types.
:::

:::rule id="UTR-002" mandatory="false" category="completion"
When only compilation checks exist, the feature shall be marked incomplete.
:::

:::rule id="UTR-003" mandatory="false" category="completion"
When any runtime test fails, the feature shall be marked incomplete.
:::

:::rule id="UTR-004" mandatory="false" category="testing"
When behavioral validation is possible, tests shall validate externally observable behavior and avoid internal-detail and concrete-implementation assertions.
:::

:::rule id="UTR-005" mandatory="false" category="testing"
Tests shall not mask failures with broad try/catch blocks or unconditional success assertions.
:::

:::rule id="UTR-006" mandatory="false" category="testing"
When a test fails, the team shall treat it as outstanding work and shall not suppress it.
:::