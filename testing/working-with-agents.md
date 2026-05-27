---
id: working-with-agents
version: "1.0.0"
title: Working With Agents Rules
scope: project
status: active
---


:::rule id="AI-002" mandatory="false" category="agentic" 
When diagnostic, experimental, or temporary test code is required, it shall be created and run outside the source repository.
:::

:::rule id="AI-003" mandatory="false" category="agentic"
When requirements are ambiguous, at least one clarifying question shall be asked before implementation.
:::

:::rule id="AI-004" mandatory="false" category="agentic"
Before implementation starts, explicit acceptance criteria shall be defined and used as the completion gate.
:::

:::rule id="AI-005" mandatory="false" category="agentic"
Each behavior claim in the completion report shall be backed by code evidence, test output, or documentation evidence.
:::

:::rule id="AI-006" mandatory="false" category="agentic"
When information is uncertain, uncertainty shall be stated explicitly and assumptions shall not be presented as facts.
:::

:::rule id="AI-007" mandatory="false" category="agentic"
When an API, file, symbol, or command cannot be verified, it shall not be asserted as existing.
:::

:::rule id="AI-008" mandatory="false" category="agentic"
For each requested change, only the smallest set of edits required to satisfy the request shall be applied.
:::

:::rule id="AI-009" mandatory="false" category="agentic"
When editing existing code, established project conventions and architecture boundaries shall be preserved.
:::

:::rule id="AI-010" mandatory="false" category="agentic"
After code changes, relevant tests, lint checks, or build checks shall be executed and results shall be reported.
:::

:::rule id="AI-011" mandatory="false" category="agentic"
When checks fail, the failure cause and next corrective action shall be reported, and no additional feature work shall be performed.
:::

:::rule id="AI-012" mandatory="false" category="agentic"
Final code output shall not include dead code, placeholder logic, or commented-out alternatives.
:::
