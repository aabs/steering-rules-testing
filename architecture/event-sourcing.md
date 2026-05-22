---
id: event-sourcing-architecture
version: "1.0.0"
title: Event Sourcing Architecture Rules
scope: project
status: active
---

:::rule id="ES-01" mandatory="true" category="architecture" tags="architecture, event-sourcing, source-of-truth"
In an event-sourced aggregate, the event stream is the authoritative record of state.
:::

:::rule id="ES-02" mandatory="true" category="architecture" tags="architecture, event-sourcing, state"
Current aggregate state must be derived solely by applying its committed events.
:::

:::rule id="ES-03" mandatory="true" category="architecture" tags="architecture, events, immutability"
Committed events are immutable and must never be updated or deleted in place.
:::

:::rule id="ES-04" mandatory="true" category="architecture" tags="architecture, events, facts"
Events must record facts that have already happened, not intentions or requests.
:::

:::rule id="ES-05" mandatory="true" category="architecture" tags="architecture, events, naming"
Name events in the past tense to reflect completed domain facts.
:::

:::rule id="ES-06" mandatory="true" category="architecture" tags="architecture, aggregates, invariants"
All business invariants for an aggregate must be enforced before emitting new events.
:::

:::rule id="ES-07" mandatory="true" category="architecture" tags="architecture, aggregates, consistency"
Each event stream must belong to exactly one consistency boundary.
:::

:::rule id="ES-08" mandatory="true" category="architecture" tags="architecture, aggregates"
An aggregate must only emit events for state that it owns.
:::

:::rule id="ES-09" mandatory="true" category="architecture" tags="architecture, commands, events"
Commands request decisions; events record decisions already made.
:::

:::rule id="ES-10" mandatory="true" category="architecture" tags="architecture, determinism, replay"
Applying the same ordered event stream must always produce the same aggregate state.
:::

:::rule id="ES-11" mandatory="true" category="architecture" tags="architecture, ordering, streams"
Preserve event order within each aggregate stream.
:::

:::rule id="ES-12" mandatory="true" category="architecture" tags="architecture, versioning, concurrency"
Use expected stream or aggregate version checks to prevent conflicting writes.
:::

:::rule id="ES-13" mandatory="true" category="architecture" tags="architecture, events, minimality"
Each event must capture the minimal domain fact needed to explain the state transition.
:::

:::rule id="ES-14" mandatory="true" category="architecture" tags="architecture, events, semantics"
Event schemas must express domain meaning clearly and independently of storage concerns.
:::

:::rule id="ES-15" mandatory="true" category="architecture" tags="architecture, contracts, evolution"
Event contracts must be designed for long-term compatibility and evolution.
:::

:::rule id="ES-16" mandatory="true" category="architecture" tags="architecture, replay, side-effects"
Rebuilding state from events must not trigger external side effects.
:::

:::rule id="ES-17" mandatory="true" category="architecture" tags="architecture, projections, separation"
Separate write-side decision logic from read-side projections.
:::

:::rule id="ES-18" mandatory="true" category="architecture" tags="architecture, projections, derivation"
Read models must be derived from events rather than treated as the primary source of truth.
:::

:::rule id="ES-19" mandatory="true" category="architecture" tags="architecture, projections, rebuild"
Projections must be rebuildable from the event history.
:::

:::rule id="ES-20" mandatory="true" category="architecture" tags="architecture, events, completeness"
Emit an event for every domain-significant state transition.
:::

:::rule id="ES-21" mandatory="true" category="architecture" tags="architecture, events, noise"
Do not emit events for changes that have no domain significance.
:::

:::rule id="ES-22" mandatory="true" category="architecture" tags="architecture, events, granularity"
Model events at business-fact granularity, not persistence-update granularity.
:::

:::rule id="ES-23" mandatory="true" category="architecture" tags="architecture, idempotency, projections"
Projection handlers must tolerate duplicate event delivery.
:::

:::rule id="ES-24" mandatory="true" category="architecture" tags="architecture, ordering, projections"
Projection correctness must not assume global ordering across unrelated streams.
:::

:::rule id="ES-25" mandatory="false" category="architecture" tags="architecture, snapshots, performance"
Use snapshots only when replay cost materially affects correctness, latency, or operability.
:::

:::rule id="ES-26" mandatory="true" category="architecture" tags="architecture, snapshots, derivation"
A snapshot is a cache of derived state and must never replace the authoritative event stream.
:::

:::rule id="ES-27" mandatory="true" category="architecture" tags="architecture, metadata"
Store technical metadata separately from domain event meaning.
:::

:::rule id="ES-28" mandatory="true" category="architecture" tags="architecture, metadata, traceability"
Attach sufficient metadata to support causation, correlation, versioning, and replay diagnostics.
:::

:::rule id="ES-29" mandatory="true" category="architecture" tags="architecture, schema, upcasting"
When historical event formats evolve, preserve replayability through explicit version-aware transformation.
:::

:::rule id="ES-30" mandatory="false" category="architecture" tags="architecture, upcasting, migration"
Use upcasting or equivalent translation only when event contract evolution cannot remain natively compatible.
:::

:::rule id="ES-31" mandatory="true" category="architecture" tags="architecture, deletion, audit"
Never remove historical events solely to simplify current-state modelling.
:::

:::rule id="ES-32" mandatory="true" category="architecture" tags="architecture, time, history"
Model history as an ordered sequence of domain facts, not as overwriteable rows.
:::

:::rule id="ES-33" mandatory="true" category="architecture" tags="architecture, process, reactions"
Cross-aggregate or cross-service reactions to events must occur outside the originating aggregate.
:::

:::rule id="ES-34" mandatory="false" category="architecture" tags="architecture, process-managers, sagas"
Use process managers or sagas when business flow spans multiple aggregates or services.
:::

:::rule id="ES-35" mandatory="true" category="architecture" tags="architecture, boundaries, autonomy"
An aggregate must make decisions using only its command input, its current state, and domain rules within its boundary.
:::

:::rule id="ES-36" mandatory="true" category="architecture" tags="architecture, external-data, consistency"
Do not require synchronous external reads to decide aggregate invariants unless that dependency is part of the aggregate boundary.
:::

:::rule id="ES-37" mandatory="true" category="architecture" tags="architecture, replay, determinism"
Aggregate rehydration logic must be deterministic, side-effect free, and independent of wall-clock time.
:::

:::rule id="ES-38" mandatory="true" category="architecture" tags="architecture, timestamps, decisions"
Do not derive business decisions from event store append time alone.
:::

:::rule id="ES-39" mandatory="false" category="architecture" tags="architecture, temporal, bi-temporal"
Model effective business time separately from recording time when the domain requires temporal correctness.
:::

:::rule id="ES-40" mandatory="true" category="architecture" tags="architecture, ubiquitous-language, domain"
Use ubiquitous domain language consistently in commands, events, aggregates, and projections.
:::
