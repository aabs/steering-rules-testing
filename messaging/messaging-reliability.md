---
id: messaging-reliability
version: "1.0.0"
title: Messaging Reliability Rules
scope: project
status: active
---

:::rule id="MSG-01" mandatory="true" category="messaging" tags="messaging, delivery-semantics"
Assume messages may be delayed, duplicated, reordered, or lost unless stronger guarantees are explicit.
:::

:::rule id="MSG-02" mandatory="true" category="messaging" tags="messaging, contracts, semantics"
Every message contract must define its business meaning, producer intent, and consumer expectations explicitly.
:::

:::rule id="MSG-03" mandatory="true" category="messaging" tags="messaging, boundaries, ownership"
Each message type must have a clearly defined owning producer and clearly defined consumers.
:::

:::rule id="MSG-04" mandatory="true" category="messaging" tags="messaging, events, facts"
Events must describe facts that have happened, not requests for another component to decide.
:::

:::rule id="MSG-05" mandatory="true" category="messaging" tags="messaging, commands, intent"
Commands must express requested intent to one responsible handler.
:::

:::rule id="MSG-06" mandatory="true" category="messaging" tags="messaging, publication, durability"
Do not publish a message until the state change or durable intent that justifies it is secured.
:::

:::rule id="MSG-07" mandatory="false" category="messaging" tags="messaging, outbox, atomicity"
Use an outbox or equivalent durable intent pattern when state change and message publication must not diverge.
:::

:::rule id="MSG-08" mandatory="true" category="messaging" tags="messaging, idempotency, producers"
Message producers must tolerate publish retries without creating duplicate business effects.
:::

:::rule id="MSG-09" mandatory="true" category="messaging" tags="messaging, idempotency, consumers"
Message consumers must be duplicate-tolerant.
:::

:::rule id="MSG-10" mandatory="true" category="messaging" tags="messaging, deduplication"
Do not assume the broker or transport eliminates duplicates.
:::

:::rule id="MSG-11" mandatory="true" category="messaging" tags="messaging, handlers, atomicity"
A message handler must complete its owned state change atomically within its consistency boundary.
:::

:::rule id="MSG-12" mandatory="true" category="messaging" tags="messaging, acknowledgements, commit-order"
Do not acknowledge successful handling before the owned state change or durable processing result is committed.
:::

:::rule id="MSG-13" mandatory="true" category="messaging" tags="messaging, retries, classification"
Classify message handling failures explicitly as transient, persistent, business, concurrency, timeout, cancellation, or unknown.
:::

:::rule id="MSG-14" mandatory="true" category="messaging" tags="messaging, retries, transient"
Retry only transient message handling failures.
:::

:::rule id="MSG-15" mandatory="true" category="messaging" tags="messaging, retries, non-transient"
Do not retry deterministic validation, schema, authorization, or business rule failures indefinitely.
:::

:::rule id="MSG-16" mandatory="true" category="messaging" tags="messaging, poison-messages"
Do not retry the same failing message indefinitely without quarantine, dead-lettering, or escalation.
:::

:::rule id="MSG-17" mandatory="false" category="messaging" tags="messaging, dead-letter, quarantine"
Move repeatedly failing messages to explicit dead-letter or quarantine handling.
:::

:::rule id="MSG-18" mandatory="true" category="messaging" tags="messaging, ordering"
Do not assume global ordering across unrelated streams, topics, partitions, or queues.
:::

:::rule id="MSG-19" mandatory="true" category="messaging" tags="messaging, ordering, partitions"
Preserve and rely only on ordering guarantees that are explicit for the relevant message stream or key.
:::

:::rule id="MSG-20" mandatory="true" category="messaging" tags="messaging, causation, correlation"
Attach stable message identifiers and sufficient causation or correlation metadata to support tracing and deduplication.
:::

:::rule id="MSG-21" mandatory="true" category="messaging" tags="messaging, schema, compatibility"
Message contracts must evolve in a backward-compatible way whenever feasible.
:::

:::rule id="MSG-22" mandatory="true" category="messaging" tags="messaging, schema, validation"
Validate message shape and required invariants before executing business logic.
:::

:::rule id="MSG-23" mandatory="true" category="messaging" tags="messaging, schema, tolerance"
Ignore unknown forward-compatible fields unless the contract explicitly forbids them.
:::

:::rule id="MSG-24" mandatory="false" category="messaging" tags="messaging, upcasting, evolution"
Use explicit version-aware transformation when historical messages cannot be consumed natively after schema evolution.
:::

:::rule id="MSG-25" mandatory="true" category="messaging" tags="messaging, side-effects, idempotency"
Do not perform irreversible side effects from a message unless duplicate execution is prevented or harmless.
:::

:::rule id="MSG-26" mandatory="true" category="messaging" tags="messaging, side-effects, ordering"
Perform external side effects only after required validation and commit preconditions succeed.
:::

:::rule id="MSG-27" mandatory="true" category="messaging" tags="messaging, state, consistency"
Design consumers so partial failure does not leave owned business state ambiguous or corrupted.
:::

:::rule id="MSG-28" mandatory="false" category="messaging" tags="messaging, inbox, deduplication"
Use an inbox or equivalent processed-message record when consumer-side deduplication must be durable.
:::

:::rule id="MSG-29" mandatory="true" category="messaging" tags="messaging, concurrency, handlers"
Do not process the same logical message concurrently when that could violate invariants or duplicate side effects.
:::

:::rule id="MSG-30" mandatory="true" category="messaging" tags="messaging, timeouts, dependencies"
Treat downstream dependency timeouts during message handling as explicit failure modes with defined retry or escalation behavior.
:::

:::rule id="MSG-31" mandatory="true" category="messaging" tags="messaging, cancellation"
Treat cancellation as a distinct outcome and do not report it as an unexpected processing fault.
:::

:::rule id="MSG-32" mandatory="true" category="messaging" tags="messaging, backpressure, overload"
Apply back-pressure, throttling, or controlled rejection when consumers cannot process more messages safely.
:::

:::rule id="MSG-33" mandatory="true" category="messaging" tags="messaging, queues, overload"
Do not allow unbounded backlog growth without explicit retention, expiry, or operator-visible consequences.
:::

:::rule id="MSG-34" mandatory="true" category="messaging" tags="messaging, expiry, staleness"
Define whether a message becomes stale and how stale messages must be handled.
:::

:::rule id="MSG-35" mandatory="false" category="messaging" tags="messaging, ttl, expiration"
Use explicit expiry or time-to-live when late processing can no longer produce a correct business outcome.
:::

:::rule id="MSG-36" mandatory="true" category="messaging" tags="messaging, exactly-once, semantics"
Do not claim exactly-once business processing unless the entire end-to-end effect is proven duplicate-safe.
:::

:::rule id="MSG-37" mandatory="true" category="messaging" tags="messaging, observability, telemetry"
Record message receipt, retry attempts, final disposition, and failure classification as structured telemetry.
:::

:::rule id="MSG-38" mandatory="true" category="messaging" tags="messaging, ownership, reporting"
Report a handling failure once at the boundary that owns the recovery decision.
:::

:::rule id="MSG-39" mandatory="true" category="messaging" tags="messaging, security,provenance"
Preserve message provenance and authorization-relevant context where downstream decisions depend on it.
:::

:::rule id="MSG-40" mandatory="true" category="messaging" tags="messaging, validation, trust-boundary"
Treat every inbound message as untrusted until contract and authorization checks succeed.
:::

:::rule id="MSG-41" mandatory="true" category="messaging" tags="messaging, workflows, state-machines"
Model long-running message-driven workflows with explicit states, retries, timeouts, and failure transitions.
:::

:::rule id="MSG-42" mandatory="false" category="messaging" tags="messaging, compensation, distributed-workflows"
Use compensation when a message-driven multi-step workflow cannot be made atomic and partial completion has business consequences.
:::

:::rule id="MSG-43" mandatory="true" category="messaging" tags="messaging, replay, determinism"
Message replay must not create new business meaning beyond reprocessing the original intent or fact.
:::

:::rule id="MSG-44" mandatory="true" category="messaging" tags="messaging, replay, side-effects"
Reprocessing or replay must be safe with respect to durable state, external effects, and audit history.
:::

:::rule id="MSG-45" mandatory="true" category="messaging" tags="messaging, routing, determinism"
Message routing rules must be explicit, deterministic, and independent of incidental infrastructure state.
:::

:::rule id="MSG-46" mandatory="true" category="messaging" tags="messaging, defaults, correctness"
Do not substitute default data for missing or malformed message content unless that default is explicitly correct for the domain.
:::

:::rule id="MSG-47" mandatory="true" category="messaging" tags="messaging, consumer-design, cohesion"
A message handler must have one clear responsibility and one clear success or failure outcome.
:::

:::rule id="MSG-48" mandatory="true" category="messaging" tags="messaging, testing, fault-injection"
Test duplicate delivery, redelivery, delay, reordering, schema evolution, poison messages, and replay deliberately.
:::

:::rule id="MSG-49" mandatory="true" category="messaging" tags="messaging, prevention, design"
Prefer messaging designs that make duplicate handling, replay safety, and failure recovery explicit by construction.
:::

:::rule id="MSG-50" mandatory="true" category="messaging" tags="messaging, recovery, ownership"
Every messaging reliability mechanism must have a clearly owned recovery decision and stopping condition.
:::