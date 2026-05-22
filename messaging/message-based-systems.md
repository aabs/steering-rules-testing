---
id: message-based-systems
version: "1.0.0"
title: Message-Based Systems Rules
scope: project
status: active
---

:::rule id="MBS-01" mandatory="true" category="messaging" tags="messaging, architecture, contracts"
Define every message type with an explicit contract and clear business meaning.
:::

:::rule id="MBS-02" mandatory="true" category="messaging" tags="messaging, architecture, ownership"
Assign each message type a single owning producer.
:::

:::rule id="MBS-03" mandatory="true" category="messaging" tags="messaging, architecture, semantics"
Use events to communicate facts that have already happened.
:::

:::rule id="MBS-04" mandatory="true" category="messaging" tags="messaging, architecture, semantics"
Use commands to request a specific action from one responsible handler.
:::

:::rule id="MBS-05" mandatory="true" category="messaging" tags="messaging, architecture, boundaries"
Do not use messages to expose internal implementation details.
:::

:::rule id="MBS-06" mandatory="true" category="messaging" tags="messaging, contracts, versioning"
Evolve message contracts in a backward-compatible way whenever feasible.
:::

:::rule id="MBS-07" mandatory="true" category="messaging" tags="messaging, contracts, validation"
Validate every inbound message before executing business logic.
:::

:::rule id="MBS-08" mandatory="true" category="messaging" tags="messaging, contracts, trust"
Treat every inbound message as untrusted until validation and authorization succeed.
:::

:::rule id="MBS-09" mandatory="true" category="messaging" tags="messaging, reliability, delivery"
Assume messages may be delayed, duplicated, reordered, or redelivered.
:::

:::rule id="MBS-10" mandatory="true" category="messaging" tags="messaging, reliability, idempotency"
Make every message handler idempotent or duplicate-safe.
:::

:::rule id="MBS-11" mandatory="true" category="messaging" tags="messaging, reliability, producers"
Make every message producer safe to retry without creating duplicate business effects.
:::

:::rule id="MBS-12" mandatory="true" category="messaging" tags="messaging, reliability, acknowledgements"
Do not acknowledge successful processing before the owned state change is committed.
:::

:::rule id="MBS-13" mandatory="true" category="messaging" tags="messaging, reliability, consistency"
Do not publish a message until the state change or durable intent that justifies it is secured.
:::

:::rule id="MBS-14" mandatory="false" category="messaging" tags="messaging, reliability, outbox"
Use an outbox or equivalent durable intent pattern when state change and publication must not diverge.
:::

:::rule id="MBS-15" mandatory="false" category="messaging" tags="messaging, reliability, inbox"
Use an inbox or equivalent processed-message record when deduplication must survive restarts and failover.
:::

:::rule id="MBS-16" mandatory="true" category="messaging" tags="messaging, ordering, streams"
Do not assume global ordering across unrelated streams, topics, queues, or partitions.
:::

:::rule id="MBS-17" mandatory="true" category="messaging" tags="messaging, ordering, keys"
Rely only on ordering guarantees that are explicit for the relevant stream or key.
:::

:::rule id="MBS-18" mandatory="true" category="messaging" tags="messaging, workflows, boundaries"
Keep message handlers responsible for one clear business action or reaction.
:::

:::rule id="MBS-19" mandatory="true" category="messaging" tags="messaging, workflows, orchestration"
Model long-running message-driven workflows with explicit states and transitions.
:::

:::rule id="MBS-20" mandatory="false" category="messaging" tags="messaging, workflows, compensation"
Use compensation when a multi-step message-driven workflow cannot be made atomic.
:::

:::rule id="MBS-21" mandatory="true" category="messaging" tags="messaging, retries, classification"
Classify message handling failures explicitly before deciding whether to retry.
:::

:::rule id="MBS-22" mandatory="true" category="messaging" tags="messaging, retries, transient"
Retry only failures that are known to be transient and safe to retry.
:::

:::rule id="MBS-23" mandatory="true" category="messaging" tags="messaging, retries, non-transient"
Do not retry validation, authorization, schema, or business rule failures indefinitely.
:::

:::rule id="MBS-24" mandatory="true" category="messaging" tags="messaging, poison-messages"
Do not retry the same failing message indefinitely without quarantine or escalation.
:::

:::rule id="MBS-25" mandatory="false" category="messaging" tags="messaging, dead-letter"
Move repeatedly failing messages to explicit dead-letter or quarantine handling.
:::

:::rule id="MBS-26" mandatory="true" category="messaging" tags="messaging, side-effects, safety"
Do not perform irreversible side effects from a message unless duplicate execution is prevented or harmless.
:::

:::rule id="MBS-27" mandatory="true" category="messaging" tags="messaging, side-effects, ordering"
Perform external side effects only after validation and commit preconditions succeed.
:::

:::rule id="MBS-28" mandatory="true" category="messaging" tags="messaging, consistency, state"
Do not let partial failure leave owned business state ambiguous or corrupted.
:::

:::rule id="MBS-29" mandatory="true" category="messaging" tags="messaging, concurrency, handlers"
Do not process the same logical message concurrently when that could violate invariants or duplicate side effects.
:::

:::rule id="MBS-30" mandatory="true" category="messaging" tags="messaging, throughput, backpressure"
Apply back-pressure or throttling when consumers cannot process more messages safely.
:::

:::rule id="MBS-31" mandatory="true" category="messaging" tags="messaging, throughput, queues"
Do not allow unbounded backlog growth without explicit retention, expiry, or operator-visible consequences.
:::

:::rule id="MBS-32" mandatory="false" category="messaging" tags="messaging, expiry, ttl"
Use explicit expiry when late processing can no longer produce a correct business outcome.
:::

:::rule id="MBS-33" mandatory="true" category="messaging" tags="messaging, observability, identifiers"
Attach a stable message identifier to every message.
:::

:::rule id="MBS-34" mandatory="true" category="messaging" tags="messaging, observability, correlation"
Attach causation or correlation identifiers to support tracing across workflows.
:::

:::rule id="MBS-35" mandatory="true" category="messaging" tags="messaging, observability, telemetry"
Record message receipt, retry attempts, final disposition, and failure classification as structured telemetry.
:::

:::rule id="MBS-36" mandatory="true" category="messaging" tags="messaging, ownership, recovery"
Report handling failure at the boundary that owns the recovery decision.
:::

:::rule id="MBS-37" mandatory="true" category="messaging" tags="messaging, security, provenance"
Preserve provenance and authorization-relevant context where downstream decisions depend on it.
:::

:::rule id="MBS-38" mandatory="true" category="messaging" tags="messaging, security, data"
Do not place secrets or sensitive data in messages unless explicitly required and protected.
:::

:::rule id="MBS-39" mandatory="true" category="messaging" tags="messaging, schema, compatibility"
Do not break existing consumers with incompatible schema changes inside a supported contract version.
:::

:::rule id="MBS-40" mandatory="true" category="messaging" tags="messaging, schema, tolerance"
Consumers must ignore unknown forward-compatible fields unless the contract explicitly forbids them.
:::

:::rule id="MBS-41" mandatory="false" category="messaging" tags="messaging, schema, transformation"
Use explicit version-aware transformation when historical messages cannot be consumed natively after schema evolution.
:::

:::rule id="MBS-42" mandatory="true" category="messaging" tags="messaging, replay, semantics"
Replay must not create new business meaning beyond reprocessing the original intent or fact.
:::

:::rule id="MBS-43" mandatory="true" category="messaging" tags="messaging, replay, safety"
Reprocessing or replay must be safe with respect to durable state and external effects.
:::

:::rule id="MBS-44" mandatory="true" category="messaging" tags="messaging, routing, determinism"
Message routing rules must be explicit and deterministic.
:::

:::rule id="MBS-45" mandatory="true" category="messaging" tags="messaging, autonomy, integration"
Use messaging contracts for inter-system integration rather than shared databases or shared internal code.
:::

:::rule id="MBS-46" mandatory="true" category="messaging" tags="messaging, boundaries, autonomy"
Each consuming service must own its own processing state, retries, and recovery decisions.
:::

:::rule id="MBS-47" mandatory="true" category="messaging" tags="messaging, consistency, local-boundary"
Keep each handler atomic within its own consistency boundary.
:::

:::rule id="MBS-48" mandatory="true" category="messaging" tags="messaging, testing, reliability"
Test duplicate delivery, redelivery, delay, reordering, poison messages, and replay deliberately.
:::

:::rule id="MBS-49" mandatory="true" category="messaging" tags="messaging, architecture, explicitness"
Prefer designs that make delivery guarantees, retry behavior, and recovery behavior explicit by construction.
:::

:::rule id="MBS-50" mandatory="true" category="messaging" tags="messaging, simplicity"
Prefer the simplest messaging topology and contract set that satisfies the required integration needs.
:::