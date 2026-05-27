---
id: error-resource-cleanup-and-concurrency
version: "1.0.0"
title: Error Resource Cleanup and Concurrency Rules
scope: project
status: active
---

:::rule id="ERC-001" mandatory="true" category="error-handling" tags="error-handling, cleanup,resources"
Owned resources shall be released deterministically on both success and failure paths, and owned state changes shall be rolled back on failure when rollback is available.
:::

:::rule id="ERC-002" mandatory="true" category="error-handling" tags="error-handling, concurrency,optimistic-concurrency"
Concurrency conflicts shall be detected explicitly and shall not be reported as generic internal errors.
:::
