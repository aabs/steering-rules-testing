---
id: error-boundary-contracts-and-reporting
version: "1.0.0"
title: Error Boundary Contracts and Reporting Rules
scope: project
status: active
---

:::rule id="EBC-001" mandatory="true" category="error-handling" tags="error-handling, exceptions,boundaries"
Exceptions shall be caught only at boundaries that can translate, compensate, retry, or report correctly.
:::

:::rule id="EBC-002" mandatory="true" category="error-handling" tags="error-handling, exceptions,scope"
Broad exception categories shall not be caught unless boundary behavior is identical for all captured types.
:::

:::rule id="EBC-003" mandatory="true" category="error-handling" tags="error-handling, translation,boundaries"
Before crossing a process or API boundary, internal exceptions shall be translated to boundary-defined error contracts.
:::

:::rule id="EBC-004" mandatory="true" category="error-handling" tags="error-handling, contracts,api"
Public error contracts shall be explicit, version-stable, and independent of internal implementation types.
:::

:::rule id="EBC-005" mandatory="true" category="error-handling" tags="error-handling, security,information-disclosure"
User-visible errors shall not expose stack traces, secrets, or internal infrastructure details.
:::

:::rule id="EBC-006" mandatory="true" category="error-handling" tags="error-handling, reporting,observability"
Each reported failure shall include structured diagnostic data, correlation or causation identifiers, and an owning boundary for remediation.
:::

:::rule id="EBC-007" mandatory="true" category="error-handling" tags="error-handling, logging,duplication"
Each propagated failure shall be logged once at the owning reporting boundary; additional logs are allowed only when adding new diagnostic information.
:::
