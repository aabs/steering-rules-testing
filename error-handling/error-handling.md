---
id: error-handling
version: "1.0.0"
title: Error Handling Rules
scope: project
status: active
---

:::rule id="ERR-01" mandatory="true" category="error-handling" tags="error-handling, invariants, consistency"
Preserve valid domain invariants even when an operation fails.
:::

:::rule id="ERR-02" mandatory="true" category="error-handling" tags="error-handling, consistency, state"
Do not leave persistent state partially updated after a failed operation.
:::

:::rule id="ERR-03" mandatory="true" category="error-handling" tags="error-handling, atomicity"
Make each state-changing operation atomic within its own consistency boundary.
:::

:::rule id="ERR-04" mandatory="false" category="error-handling" tags="error-handling, compensation, distributed-systems"
Use compensation when a multi-step distributed operation cannot be made atomic.
:::

:::rule id="ERR-05" mandatory="true" category="error-handling" tags="error-handling, boundaries, validation"
Validate inputs at system and application boundaries before performing business work.
:::

:::rule id="ERR-06" mandatory="true" category="error-handling" tags="error-handling, fail-fast, validation"
Fail fast on invalid input, invalid state, or violated preconditions.
:::

:::rule id="ERR-07" mandatory="true" category="error-handling" tags="error-handling, preconditions, contracts"
Check preconditions before mutating state or performing irreversible side effects.
:::

:::rule id="ERR-08" mandatory="true" category="error-handling" tags="error-handling, side-effects, ordering"
Do not perform external side effects before all required validation and authorization checks succeed.
:::

:::rule id="ERR-09" mandatory="true" category="error-handling" tags="error-handling, idempotency, retries"
State-changing operations that may be retried must be idempotent or duplicate-safe.
:::

:::rule id="ERR-10" mandatory="true" category="error-handling" tags="error-handling, retries, classification"
Classify failures explicitly as validation, business, transient, dependency, concurrency, or unknown.
:::

:::rule id="ERR-11" mandatory="true" category="error-handling" tags="error-handling, retries, transient"
Retry only failures that are known to be transient.
:::

:::rule id="ERR-12" mandatory="true" category="error-handling" tags="error-handling, retries, non-transient"
Do not retry validation, authorization, or deterministic business rule failures.
:::

:::rule id="ERR-13" mandatory="false" category="error-handling" tags="error-handling, backoff, resilience"
Use bounded retry with delay or backoff for transient failures that are safe to retry.
:::

:::rule id="ERR-14" mandatory="false" category="error-handling" tags="error-handling, dead-letter, messaging"
Move repeatedly failing messages or commands to explicit quarantine or dead-letter handling.
:::

:::rule id="ERR-15" mandatory="true" category="error-handling" tags="error-handling, exceptions, usage"
Use exceptions for exceptional failures, not for normal control flow.
:::

:::rule id="ERR-16" mandatory="true" category="error-handling" tags="error-handling, exceptions, types"
Throw the most specific exception or error type that accurately describes the failure.
:::

:::rule id="ERR-17" mandatory="true" category="error-handling" tags="error-handling, exceptions, semantics"
Exception and error types must represent distinct failure semantics, not vague categories.
:::

:::rule id="ERR-18" mandatory="true" category="error-handling" tags="error-handling, exceptions,messages"
Error messages must state what failed, why it failed, and what context is relevant.
:::

:::rule id="ERR-19" mandatory="true" category="error-handling" tags="error-handling, exceptions,diagnostics"
Include enough structured context with an error to support diagnosis without exposing secrets.
:::

:::rule id="ERR-20" mandatory="true" category="error-handling" tags="error-handling, exceptions,stack-trace"
Preserve the original stack trace and causal chain when propagating an exception.
:::

:::rule id="ERR-21" mandatory="true" category="error-handling" tags="error-handling, exceptions,wrapping"
Wrap a lower-level exception only when adding meaningful domain or boundary context.
:::

:::rule id="ERR-22" mandatory="true" category="error-handling" tags="error-handling, exceptions,swallowing"
Never swallow an exception without explicitly handling its consequences.
:::

:::rule id="ERR-23" mandatory="true" category="error-handling" tags="error-handling, exceptions,boundaries"
Catch exceptions at boundaries where they can be translated, compensated, retried, or reported correctly.
:::

:::rule id="ERR-24" mandatory="true" category="error-handling" tags="error-handling, exceptions,scope"
Do not catch broad exception categories unless the boundary genuinely requires it.
:::

:::rule id="ERR-25" mandatory="true" category="error-handling" tags="error-handling, translation,boundaries"
Translate internal exceptions to boundary-appropriate error contracts before crossing process or API boundaries.
:::

:::rule id="ERR-26" mandatory="true" category="error-handling" tags="error-handling, contracts,api"
Public error contracts must be stable, explicit, and independent of internal implementation details.
:::

:::rule id="ERR-27" mandatory="true" category="error-handling" tags="error-handling, security,information-disclosure"
Do not expose internal stack traces, secrets, or infrastructure details in user-visible errors.
:::

:::rule id="ERR-28" mandatory="true" category="error-handling" tags="error-handling, reporting,observability"
Report failures with enough structured data to support correlation, diagnosis, and remediation.
:::

:::rule id="ERR-29" mandatory="true" category="error-handling" tags="error-handling, correlation,traceability"
Attach correlation or causation identifiers to error reports for multi-step or distributed flows.
:::

:::rule id="ERR-30" mandatory="true" category="error-handling" tags="error-handling, logging,duplication"
Record each failure once at the boundary that owns the reporting responsibility.
:::

:::rule id="ERR-31" mandatory="true" category="error-handling" tags="error-handling, logging,signal"
Do not log and rethrow the same failure repeatedly at multiple layers without adding new information.
:::

:::rule id="ERR-32" mandatory="true" category="error-handling" tags="error-handling, cleanup,resources"
Release or roll back owned resources deterministically when an operation fails.
:::

:::rule id="ERR-33" mandatory="true" category="error-handling" tags="error-handling, cleanup,finally"
Put mandatory cleanup in explicit cleanup paths that run on both success and failure.
:::

:::rule id="ERR-34" mandatory="true" category="error-handling" tags="error-handling, cancellation"
Treat cancellation as a distinct outcome and do not report it as an unexpected fault.
:::

:::rule id="ERR-35" mandatory="true" category="error-handling" tags="error-handling, concurrency,optimistic-concurrency"
Handle concurrency conflicts explicitly and do not treat them as generic internal errors.
:::

:::rule id="ERR-36" mandatory="true" category="error-handling" tags="error-handling, timeout,dependencies"
Treat timeouts as explicit failure modes with defined caller behavior.
:::

:::rule id="ERR-37" mandatory="true" category="error-handling" tags="error-handling, dependencies,trust-boundary"
Treat remote dependency failures as expected conditions, not impossible exceptions.
:::

:::rule id="ERR-38" mandatory="false" category="error-handling" tags="error-handling, fallback,degradation"
Use fallback or degraded behavior only when it preserves correctness and does not hide data loss or inconsistency.
:::

:::rule id="ERR-39" mandatory="true" category="error-handling" tags="error-handling, defaults,correctness"
Do not substitute default values for missing or invalid data unless the default is explicitly correct for the domain.
:::

:::rule id="ERR-40" mandatory="true" category="error-handling" tags="error-handling, nullability,totality"
Make invalid or absent states explicit rather than relying on implicit nulls or magic values.
:::

:::rule id="ERR-41" mandatory="true" category="error-handling" tags="error-handling, domain,results"
Represent expected business rule rejections with explicit domain outcomes where possible.
:::

:::rule id="ERR-42" mandatory="false" category="error-handling" tags="error-handling, result-types,functional"
Use explicit result types instead of exceptions when failure is an expected and frequent outcome.
:::

:::rule id="ERR-43" mandatory="true" category="error-handling" tags="error-handling, branching,exhaustiveness"
Handle all known error cases explicitly where exhaustive handling is possible.
:::

:::rule id="ERR-44" mandatory="true" category="error-handling" tags="error-handling, determinism,side-effects"
Keep decision logic deterministic and side-effect free until the point a commit or external effect is required.
:::

:::rule id="ERR-45" mandatory="true" category="error-handling" tags="error-handling, defensive-programming"
Assume external inputs, dependencies, and timing can fail in ways the happy path does not model.
:::

:::rule id="ERR-46" mandatory="true" category="error-handling" tags="error-handling, simplicity,correctness"
Prefer simple control flow and explicit state transitions over clever error-handling logic.
:::

:::rule id="ERR-47" mandatory="true" category="error-handling" tags="error-handling, state-machines,invariants"
Model long-running or multi-step workflows with explicit states and failure transitions.
:::

:::rule id="ERR-48" mandatory="true" category="error-handling" tags="error-handling, observability,ownership"
Every reported error must have a clear owning boundary responsible for handling, translation, or escalation.
:::

:::rule id="ERR-49" mandatory="true" category="error-handling" tags="error-handling, testing,negative-paths"
Test failure paths, boundary cases, and recovery behavior as deliberately as success paths.
:::

:::rule id="ERR-50" mandatory="true" category="error-handling" tags="error-handling, prevention,design"
Design APIs and state models so that illegal states and invalid operations are hard to represent.
:::

:::rule id="ERR-51" mandatory="true" category="error-handling" tags="exceptions, state-management"
Do work that may fail off to the side before changing committed state. First prepare all risky work using temporary state; then commit using steps that cannot fail or are tightly controlled.
:::

:::rule id="ERR-52" mandatory="true" category="error-handling" tags="exceptions, state-management"
Prefer commit-or-rollback behavior when practical. A failed operation should ideally leave the observable state exactly as it was before the operation began
:::