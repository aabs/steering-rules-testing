---
id: error-retries-and-resilience
version: "1.0.0"
title: Error Retries and Resilience Rules
scope: project
status: active
---

:::rule id="ERRR-001" mandatory="true" category="error-handling" tags="error-handling, idempotency, retries"
When an operation can be retried, the operation shall be idempotent or duplicate-safe.
:::

:::rule id="ERRR-002" mandatory="true" category="error-handling" tags="error-handling, retries, classification"
Each failure shall be classified as validation, business, transient, dependency, concurrency, or unknown before retry policy is applied.
:::

:::rule id="ERRR-003" mandatory="true" category="error-handling" tags="error-handling, retries, transient"
Retries shall be applied only to failures classified as transient and safe to retry.
:::

:::rule id="ERRR-004" mandatory="true" category="error-handling" tags="error-handling, retries, non-transient"
Failures classified as validation, authorization, or deterministic business-rule violations shall not be retried.
:::

:::rule id="ERRR-005" mandatory="false" category="error-handling" tags="error-handling, backoff, resilience"
When retry is enabled, retry count and delay shall be bounded and shall use delay or backoff.
:::

:::rule id="ERRR-006" mandatory="false" category="error-handling" tags="error-handling, dead-letter, messaging"
When message processing exceeds retry limits, the message shall be moved to explicit quarantine or dead-letter handling.
:::

:::rule id="ERRR-007" mandatory="true" category="error-handling" tags="error-handling, timeout,dependencies"
Timeouts shall be treated as explicit failure modes with defined caller behavior.
:::

:::rule id="ERRR-008" mandatory="true" category="error-handling" tags="error-handling, dependencies,trust-boundary"
Remote dependency failures shall be handled as expected conditions and shall not be treated as impossible faults.
:::

:::rule id="ERRR-009" mandatory="false" category="error-handling" tags="error-handling, fallback,degradation"
Fallback or degraded behavior shall be used only when correctness is preserved and data loss or inconsistency is not hidden.
:::
