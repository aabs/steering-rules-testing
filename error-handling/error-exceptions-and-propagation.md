---
id: error-exceptions-and-propagation
version: "1.0.0"
title: Error Exceptions and Propagation Rules
scope: project
status: active
---

:::rule id="EEX-001" mandatory="true" category="error-handling" tags="error-handling, exceptions, usage"
Exceptions shall represent exceptional failures and shall not be used for normal control flow.
:::

:::rule id="EEX-002" mandatory="true" category="error-handling" tags="error-handling, exceptions, types"
When raising a failure, the most specific exception or error type shall be used, and each type shall map to one distinct failure semantic.
:::

:::rule id="EEX-003" mandatory="true" category="error-handling" tags="error-handling, exceptions,messages"
Error details shall state what failed, why it failed, and relevant non-secret context.
:::

:::rule id="EEX-004" mandatory="true" category="error-handling" tags="error-handling, exceptions,stack-trace"
When propagating a failure, original causal chain and stack trace shall be preserved.
:::

:::rule id="EEX-005" mandatory="true" category="error-handling" tags="error-handling, exceptions,wrapping"
A lower-level exception shall be wrapped only when additional boundary or domain context is added.
:::

:::rule id="EEX-006" mandatory="true" category="error-handling" tags="error-handling, exceptions,swallowing"
Exceptions shall not be swallowed unless consequences are explicitly handled.
:::

:::rule id="EEX-007" mandatory="true" category="error-handling" tags="error-handling, cancellation"
Cancellation shall be handled as a distinct non-fault outcome and shall not be reported as an unexpected fault.
:::
