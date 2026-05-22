---
id: messaging-delivery-and-reliability
version: "1.0.0"
title: Messaging Delivery and Reliability Rules
scope: project
status: active
---

:::rule id="MDR-01" mandatory="false" category="messaging" tags="messaging, reliability, delivery"
Assume messages may be delayed, duplicated, reordered, or redelivered.
:::

:::rule id="MDR-02" mandatory="false" category="messaging" tags="messaging, reliability, idempotency"
Make every message handler idempotent or duplicate-safe.
:::

:::rule id="MDR-03" mandatory="false" category="messaging" tags="messaging, reliability, producers"
Make every message producer safe to retry without creating duplicate business effects.
:::

:::rule id="MDR-04" mandatory="false" category="messaging" tags="messaging, reliability, acknowledgements"
Do not acknowledge successful processing before the owned state change is committed.
:::

:::rule id="MDR-05" mandatory="false" category="messaging" tags="messaging, reliability, consistency"
Do not publish a message until the state change or durable intent that justifies it is secured.
:::

:::rule id="MDR-06" mandatory="false" category="messaging" tags="messaging, reliability, outbox"
Use an outbox or equivalent durable intent pattern when state change and publication must not diverge.
:::

:::rule id="MDR-07" mandatory="false" category="messaging" tags="messaging, reliability, inbox"
Use an inbox or equivalent processed-message record when deduplication must survive restarts and failover.
:::

:::rule id="MDR-08" mandatory="false" category="messaging" tags="messaging, ordering, streams"
Do not assume global ordering across unrelated streams, topics, queues, or partitions.
:::

:::rule id="MDR-09" mandatory="false" category="messaging" tags="messaging, ordering, keys"
Rely only on ordering guarantees that are explicit for the relevant stream or key.
:::

:::rule id="MDR-10" mandatory="false" category="messaging" tags="messaging, retries, classification"
Classify message handling failures explicitly before deciding whether to retry.
:::

:::rule id="MDR-11" mandatory="false" category="messaging" tags="messaging, retries, transient"
Retry only failures that are known to be transient and safe to retry.
:::

:::rule id="MDR-12" mandatory="false" category="messaging" tags="messaging, retries, non-transient"
Do not retry validation, authorization, schema, or business rule failures indefinitely.
:::

:::rule id="MDR-13" mandatory="false" category="messaging" tags="messaging, poison-messages"
Do not retry the same failing message indefinitely without quarantine or escalation.
:::

:::rule id="MDR-14" mandatory="false" category="messaging" tags="messaging, dead-letter"
Move repeatedly failing messages to explicit dead-letter or quarantine handling.
:::

:::rule id="MDR-15" mandatory="false" category="messaging" tags="messaging, concurrency, handlers"
Do not process the same logical message concurrently when that could violate invariants or duplicate side effects.
:::

:::rule id="MDR-16" mandatory="false" category="messaging" tags="messaging, throughput, backpressure"
Apply back-pressure or throttling when consumers cannot process more messages safely.
:::

:::rule id="MDR-17" mandatory="false" category="messaging" tags="messaging, throughput, queues"
Do not allow unbounded backlog growth without explicit retention, expiry, or operator-visible consequences.
:::

:::rule id="MDR-18" mandatory="false" category="messaging" tags="messaging, expiry, ttl"
Use explicit expiry when late processing can no longer produce a correct business outcome.
:::

:::rule id="MDR-19" mandatory="false" category="messaging" tags="messaging, replay, semantics"
Replay must not create new business meaning beyond reprocessing the original intent or fact.
:::

:::rule id="MDR-20" mandatory="false" category="messaging" tags="messaging, replay, safety"
Reprocessing or replay must be safe with respect to durable state and external effects.
:::