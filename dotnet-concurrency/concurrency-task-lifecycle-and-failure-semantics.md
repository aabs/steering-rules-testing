---
id: concurrency-task-lifecycle-and-failure-semantics
version: "1.0.0"
title: Concurrency Task Lifecycle and Failure Semantics Rules
scope: project
status: active
---

:::rule id="CLF-001" mandatory="true" category="concurrency" tags="concurrency, task-lifecycle, observability"
In concurrent data processing pipelines, every started Task shall be awaited, explicitly observed, or deliberately detached with explicit exception handling and completion logging.
:::

:::rule id="CLF-002" mandatory="true" category="concurrency" tags="concurrency, exceptions, ownership"
In concurrent data processing pipelines, the boundary that owns a concurrent operation or work queue shall handle and classify exceptions produced by that operation.
:::

:::rule id="CLF-003" mandatory="true" category="concurrency" tags="concurrency, aggregation, failure-policy"
In concurrent data processing pipelines, when multiple tasks run concurrently, the operation shall define and implement one explicit failure policy: cancel siblings on first failure, wait for all, or collect all outcomes.
:::

:::rule id="CLF-004" mandatory="true" category="concurrency" tags="concurrency, idempotency, duplicates"
In concurrent data processing pipelines, queued or retryable work shall be idempotent or duplicate-safe.
:::

:::rule id="CLF-005" mandatory="true" category="concurrency" tags="concurrency, retries, classification"
In concurrent data processing pipelines, retries shall be applied only after failure classification and shall use bounded retry counts and delays.
:::