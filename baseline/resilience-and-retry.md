---
id: resilience-and-retry
version: "1.0.0"
title: Resilience and Retry Rules
scope: project
status: active
---

:::rule id="RES-01" mandatory="true" category="resilience" tags="resilience, failure-model"
Treat remote calls, storage operations, and message delivery as fallible by default.
:::

:::rule id="RES-02" mandatory="true" category="resilience" tags="resilience, failure-classification"
Classify failures explicitly as transient, persistent, concurrency, cancellation, timeout, or unknown.
:::

:::rule id="RES-03" mandatory="true" category="resilience" tags="resilience, retry, safety"
Retry only operations that are known to be safe to retry.
:::

:::rule id="RES-04" mandatory="true" category="resilience" tags="resilience, retry, transient"
Retry only failures that are classified as transient.
:::

:::rule id="RES-05" mandatory="true" category="resilience" tags="resilience, retry, non-transient"
Do not retry validation, authorization, business rule, or deterministic application errors.
:::

:::rule id="RES-06" mandatory="true" category="resilience" tags="resilience, idempotency, retries"
Any operation that may be retried must be idempotent or duplicate-safe.
:::

:::rule id="RES-07" mandatory="true" category="resilience" tags="resilience, side-effects, retries"
Do not retry non-idempotent side effects unless duplicate consequences are explicitly prevented.
:::

:::rule id="RES-08" mandatory="true" category="resilience" tags="resilience, boundaries, policy"
Define retry behavior at the boundary that owns the dependency interaction.
:::

:::rule id="RES-09" mandatory="true" category="resilience" tags="resilience, backoff"
Use bounded retry with delay between attempts.
:::

:::rule id="RES-10" mandatory="false" category="resilience" tags="resilience, jitter, contention"
Add jitter to retry delays when many callers may retry the same dependency concurrently.
:::

:::rule id="RES-11" mandatory="true" category="resilience" tags="resilience, retries, limits"
Set an explicit maximum retry count or retry duration for every retrying operation.
:::

:::rule id="RES-12" mandatory="true" category="resilience" tags="resilience, timeout"
Set explicit timeouts for all remote and potentially blocking operations.
:::

:::rule id="RES-13" mandatory="true" category="resilience" tags="resilience, timeout, retries"
A retry policy must respect the overall operation timeout or deadline.
:::

:::rule id="RES-14" mandatory="true" category="resilience" tags="resilience, cancellation"
Propagate cancellation and stop retrying when cancellation is requested.
:::

:::rule id="RES-15" mandatory="true" category="resilience" tags="resilience, cancellation, semantics"
Treat cancellation as a distinct outcome, not as a retryable fault.
:::

:::rule id="RES-16" mandatory="true" category="resilience" tags="resilience, timeout, semantics"
Treat timeouts as explicit failure modes with defined caller behavior.
:::

:::rule id="RES-17" mandatory="true" category="resilience" tags="resilience, circuit-breaker"
Do not continue sending traffic indefinitely to a dependency that is repeatedly failing.
:::

:::rule id="RES-18" mandatory="false" category="resilience" tags="resilience, circuit-breaker, bulkhead"
Use circuit breaking or equivalent isolation when repeated dependency failure would amplify system instability.
:::

:::rule id="RES-19" mandatory="true" category="resilience" tags="resilience, fallback, correctness"
Use fallback behavior only when it preserves correctness and makes failure semantics explicit.
:::

:::rule id="RES-20" mandatory="true" category="resilience" tags="resilience, fallback, data-loss"
Do not hide failed writes, lost messages, or inconsistent state behind fallback behavior.
:::

:::rule id="RES-21" mandatory="true" category="resilience" tags="resilience, degradation"
Graceful degradation must reduce capability explicitly rather than silently changing business meaning.
:::

:::rule id="RES-22" mandatory="true" category="resilience" tags="resilience, consistency, partial-failure"
Design workflows to tolerate partial failure without corrupting business state.
:::

:::rule id="RES-23" mandatory="false" category="resilience" tags="resilience, compensation, distributed-workflows"
Use compensation when a multi-step distributed operation cannot be made atomic.
:::

:::rule id="RES-24" mandatory="true" category="resilience" tags="resilience, state, commit-order"
Do not acknowledge success before the owned state change or durable intent is committed.
:::

:::rule id="RES-25" mandatory="true" category="resilience" tags="resilience, messaging, at-least-once"
Assume messages may be delivered more than once unless stronger guarantees are explicit.
:::

:::rule id="RES-26" mandatory="true" category="resilience" tags="resilience, messaging, deduplication"
Consumers of retryable or redeliverable messages must be duplicate-tolerant.
:::

:::rule id="RES-27" mandatory="true" category="resilience" tags="resilience, ordering, messaging"
Do not assume global message ordering across unrelated streams or partitions.
:::

:::rule id="RES-28" mandatory="true" category="resilience" tags="resilience, poison-messages"
Do not retry the same failing message indefinitely without quarantine or escalation.
:::

:::rule id="RES-29" mandatory="false" category="resilience" tags="resilience, dead-letter, quarantine"
Move repeatedly failing messages or commands to explicit dead-letter or quarantine handling.
:::

:::rule id="RES-30" mandatory="true" category="resilience" tags="resilience, observability, retries"
Record retry attempts, final outcomes, and failure classification as structured telemetry.
:::

:::rule id="RES-31" mandatory="true" category="resilience" tags="resilience, correlation, tracing"
Attach correlation or causation identifiers to retries and cross-service recovery flows.
:::

:::rule id="RES-32" mandatory="true" category="resilience" tags="resilience, ownership, reporting"
Report a failure once at the boundary that owns the recovery decision.
:::

:::rule id="RES-33" mandatory="true" category="resilience" tags="resilience, concurrency, optimistic-concurrency"
Handle concurrency conflicts explicitly and do not treat them as generic transient faults.
:::

:::rule id="RES-34" mandatory="false" category="resilience" tags="resilience, retry, concurrency"
Retry concurrency conflicts only when the business operation is safe to re-evaluate on fresh state.
:::

:::rule id="RES-35" mandatory="true" category="resilience" tags="resilience, resource-protection"
Do not let retry behavior exhaust threads, connections, memory, or queues.
:::

:::rule id="RES-36" mandatory="false" category="resilience" tags="resilience, bulkhead, isolation"
Use isolation boundaries when one failing dependency could consume resources needed by unrelated work.
:::

:::rule id="RES-37" mandatory="true" category="resilience" tags="resilience, backpressure"
Apply back-pressure or rejection when the system cannot process more work safely.
:::

:::rule id="RES-38" mandatory="true" category="resilience" tags="resilience, queueing, overload"
Do not accept unbounded work when downstream capacity is degraded or unavailable.
:::

:::rule id="RES-39" mandatory="true" category="resilience" tags="resilience, startup, readiness"
Do not assume a dependency is healthy solely because it is configured or reachable.
:::

:::rule id="RES-40" mandatory="true" category="resilience" tags="resilience, health, semantics"
Health signals must distinguish readiness, liveness, and dependency degradation where relevant.
:::

:::rule id="RES-41" mandatory="true" category="resilience" tags="resilience, determinism, side-effects"
Keep decision logic deterministic and side-effect free until the commit or external effect boundary.
:::

:::rule id="RES-42" mandatory="true" category="resilience" tags="resilience, external-effects, ordering"
Perform irreversible external effects only after all required validation and commit preconditions succeed.
:::

:::rule id="RES-43" mandatory="true" category="resilience" tags="resilience, persistence, outbox"
Do not publish or acknowledge externally visible outcomes unless their durable source-of-truth state is secured.
:::

:::rule id="RES-44" mandatory="false" category="resilience" tags="resilience, outbox, messaging"
Use durable intent patterns such as outbox or equivalent when state change and message publication must not diverge.
:::

:::rule id="RES-45" mandatory="true" category="resilience" tags="resilience, defaults, correctness"
Do not substitute default data for missing dependency responses unless that default is explicitly correct for the domain.
:::

:::rule id="RES-46" mandatory="true" category="resilience" tags="resilience, contracts, degradation"
Recovery and degradation behavior must be explicit in service contracts where callers depend on it.
:::

:::rule id="RES-47" mandatory="true" category="resilience" tags="resilience, workflows, failure-transitions"
Long-running workflows must model timeout, retry, failure, and compensation transitions explicitly.
:::

:::rule id="RES-48" mandatory="true" category="resilience" tags="resilience, testing, fault-injection"
Test retry, timeout, duplicate delivery, partial failure, and degraded dependency paths deliberately.
:::

:::rule id="RES-49" mandatory="true" category="resilience" tags="resilience, prevention,design"
Prefer designs that remove the need for retries over designs that depend on retries for correctness.
:::

:::rule id="RES-50" mandatory="true" category="resilience" tags="resilience, recovery, ownership"
Every resilience mechanism must have a clearly owned recovery decision and stopping condition.
:::
