---
id: performance-io-serialization-and-fail-fast
version: "1.0.0"
title: Performance IO Serialization and Fail Fast Rules
scope: project
status: active
---

:::rule id="PIS-001" mandatory="true" category="performance" tags="performance, serialization"
Serialization and deserialization paths shall minimize allocation, copying, and intermediate materialization.
:::

:::rule id="PIS-002" mandatory="true" category="performance" tags="performance, io"
When full buffering is unnecessary for large payloads, data shall be streamed or piped instead of fully materialized.
:::

:::rule id="PIS-003" mandatory="true" category="performance" tags="performance, logging"
Structured logging shall be used, and expensive log message construction shall be skipped when the log level is disabled.
:::

:::rule id="PIS-004" mandatory="true" category="performance" tags="performance, exceptions"
Exceptions shall not be used as normal control flow on hot paths.
:::

:::rule id="PIS-005" mandatory="true" category="performance" tags="performance, exceptions, validation"
Arguments and preconditions shall be validated before expensive work begins.
:::
