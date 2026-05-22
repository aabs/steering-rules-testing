---
id: clean-architecture
version: "1.0.0"
title: Clean Architecture Rules
scope: project
status: active
---

:::rule id="CA-01" mandatory="true" category="architecture" tags="architecture, clean-architecture, dependencies"
Dependencies must point inward toward more stable and more policy-rich code.
:::

:::rule id="CA-02" mandatory="true" category="architecture" tags="architecture, clean-architecture, domain"
The domain model must not depend on application, infrastructure, or presentation concerns.
:::

:::rule id="CA-03" mandatory="true" category="architecture" tags="architecture, clean-architecture, application"
Application use cases must not depend on infrastructure or UI implementation details.
:::

:::rule id="CA-04" mandatory="true" category="architecture" tags="architecture, clean-architecture, framework"
Frameworks and external libraries must be treated as replaceable details at the boundary.
:::

:::rule id="CA-05" mandatory="true" category="architecture" tags="architecture, clean-architecture, separation"
Separate domain logic, application orchestration, infrastructure concerns, and presentation concerns explicitly.
:::

:::rule id="CA-06" mandatory="true" category="architecture" tags="architecture, clean-architecture, business-rules"
Keep enterprise or domain business rules in the innermost architectural layers.
:::

:::rule id="CA-07" mandatory="true" category="architecture" tags="architecture, clean-architecture, use-cases"
Model application behavior as explicit use cases or application services.
:::

:::rule id="CA-08" mandatory="true" category="architecture" tags="architecture, clean-architecture, orchestration"
Use cases must orchestrate work and enforce application flow, not implement infrastructure details.
:::

:::rule id="CA-09" mandatory="true" category="architecture" tags="architecture, clean-architecture, entities"
Entities and value objects must encode core business invariants.
:::

:::rule id="CA-10" mandatory="true" category="architecture" tags="architecture, clean-architecture, invariants"
Enforce business invariants in the layer that owns the relevant business concepts.
:::

:::rule id="CA-11" mandatory="true" category="architecture" tags="architecture, clean-architecture, interfaces"
Define interfaces at the inner layer that needs the capability, not at the outer layer that implements it.
:::

:::rule id="CA-12" mandatory="true" category="architecture" tags="architecture, clean-architecture, ports-adapters"
Cross-layer interaction must occur through explicit ports, contracts, or interfaces.
:::

:::rule id="CA-13" mandatory="true" category="architecture" tags="architecture, clean-architecture, adapters"
Adapters must translate between external representations and internal models.
:::

:::rule id="CA-14" mandatory="true" category="architecture" tags="architecture, clean-architecture, dto"
Do not pass transport or persistence models directly into the domain model.
:::

:::rule id="CA-15" mandatory="true" category="architecture" tags="architecture, clean-architecture, persistence"
Persistence must be an implementation detail behind an application-facing abstraction.
:::

:::rule id="CA-16" mandatory="true" category="architecture" tags="architecture, clean-architecture, repositories"
Repositories must expose domain-meaningful access patterns rather than generic data-table operations.
:::

:::rule id="CA-17" mandatory="true" category="architecture" tags="architecture, clean-architecture, side-effects"
Keep side effects at architectural boundaries and out of core business logic where possible.
:::

:::rule id="CA-18" mandatory="true" category="architecture" tags="architecture, clean-architecture, purity"
Keep decision-making logic deterministic and independent of I/O until a boundary interaction is required.
:::

:::rule id="CA-19" mandatory="true" category="architecture" tags="architecture, clean-architecture, time"
Do not read time, randomness, or environment state directly inside core business logic when they can be abstracted.
:::

:::rule id="CA-20" mandatory="true" category="architecture" tags="architecture, clean-architecture, framework-independence"
Core application and domain code must be runnable without the web framework, UI framework, or database runtime.
:::

:::rule id="CA-21" mandatory="true" category="architecture" tags="architecture, clean-architecture, use-case-input"
Each use case must define explicit input data and explicit output data.
:::

:::rule id="CA-22" mandatory="true" category="architecture" tags="architecture, clean-architecture, contracts"
Use case contracts must not expose infrastructure-specific types.
:::

:::rule id="CA-23" mandatory="true" category="architecture" tags="architecture, clean-architecture, validation"
Validate boundary inputs before invoking core business behavior.
:::

:::rule id="CA-24" mandatory="true" category="architecture" tags="architecture, clean-architecture, authorization"
Perform authorization at the application boundary or use-case boundary, not deep inside infrastructure code.
:::

:::rule id="CA-25" mandatory="true" category="architecture" tags="architecture, clean-architecture, transactions"
Application services must define the transactional or consistency boundary of a use case.
:::

:::rule id="CA-26" mandatory="false" category="architecture" tags="architecture, clean-architecture, unit-of-work"
Use an explicit unit-of-work abstraction when a use case spans multiple repository operations within one consistency boundary.
:::

:::rule id="CA-27" mandatory="true" category="architecture" tags="architecture, clean-architecture, dependencies"
Do not let inner layers reference outer-layer packages, namespaces, or assemblies.
:::

:::rule id="CA-28" mandatory="true" category="architecture" tags="architecture, clean-architecture, package-structure"
Package and project structure must reinforce architectural boundaries rather than obscure them.
:::

:::rule id="CA-29" mandatory="true" category="architecture" tags="architecture, clean-architecture, coupling"
Minimize coupling between use cases so they can evolve independently.
:::

:::rule id="CA-30" mandatory="true" category="architecture" tags="architecture, clean-architecture, cohesion"
Keep each architectural component cohesive and responsible for one clear purpose.
:::

:::rule id="CA-31" mandatory="true" category="architecture" tags="architecture, clean-architecture, errors"
Translate external or infrastructure failures into boundary-appropriate application outcomes.
:::

:::rule id="CA-32" mandatory="true" category="architecture" tags="architecture, clean-architecture, exceptions"
Do not leak infrastructure exception types across architectural boundaries into core policy layers.
:::

:::rule id="CA-33" mandatory="true" category="architecture" tags="architecture, clean-architecture, presentation"
Presentation code must format, validate, and map requests and responses, not implement business policy.
:::

:::rule id="CA-34" mandatory="true" category="architecture" tags="architecture, clean-architecture, controllers"
Controllers, endpoints, handlers, and UI actions must delegate to use cases rather than contain orchestration logic.
:::

:::rule id="CA-35" mandatory="true" category="architecture" tags="architecture, clean-architecture, infrastructure"
Infrastructure code must implement ports and policies defined by inner layers.
:::

:::rule id="CA-36" mandatory="true" category="architecture" tags="architecture, clean-architecture, mapping"
Mapping between layers must be explicit and local to the boundary that needs it.
:::

:::rule id="CA-37" mandatory="true" category="architecture" tags="architecture, clean-architecture, state"
Do not let application state leak implicitly through globals, static mutable state, or ambient context.
:::

:::rule id="CA-38" mandatory="true" category="architecture" tags="architecture, clean-architecture, testing"
Core business logic must be testable without external systems.
:::

:::rule id="CA-39" mandatory="true" category="architecture" tags="architecture, clean-architecture, testability"
Use architecture to make side-effect-free logic easy to test and boundary logic easy to substitute.
:::

:::rule id="CA-40" mandatory="true" category="architecture" tags="architecture, clean-architecture, policies"
Business policies must be expressed in code that is independent of delivery mechanism.
:::

:::rule id="CA-41" mandatory="false" category="architecture" tags="architecture, clean-architecture, cqrs"
Separate command and query models when doing so materially improves clarity, performance, or independence.
:::

:::rule id="CA-42" mandatory="false" category="architecture" tags="architecture, clean-architecture, domain-events"
Use domain events to decouple reactions within the application boundary when the resulting flow remains explicit and understandable.
:::

:::rule id="CA-43" mandatory="true" category="architecture" tags="architecture, clean-architecture, external-systems"
Treat databases, message brokers, file systems, and third-party services as external actors outside the core architecture.
:::

:::rule id="CA-44" mandatory="true" category="architecture" tags="architecture, clean-architecture, anti-corruption"
Use translation or anti-corruption boundaries when integrating incompatible external models.
:::

:::rule id="CA-45" mandatory="true" category="architecture" tags="architecture, clean-architecture, naming"
Use consistent business language across entities, use cases, ports, and adapters.
:::

:::rule id="CA-46" mandatory="true" category="architecture" tags="architecture, clean-architecture, change-isolation"
Changes to frameworks, transport, or persistence should not require changes to domain rules.
:::

:::rule id="CA-47" mandatory="true" category="architecture" tags="architecture, clean-architecture, boundaries"
Architectural boundaries must be visible in code, not only described in documentation.
:::

:::rule id="CA-48" mandatory="false" category="architecture" tags="architecture, clean-architecture, modularity"
Split architectural layers into separate projects or assemblies when physical separation materially improves boundary enforcement.
:::

:::rule id="CA-49" mandatory="true" category="architecture" tags="architecture, clean-architecture, dependency-injection"
Composition root code must wire implementations to abstractions at the outermost boundary.
:::

:::rule id="CA-50" mandatory="true" category="architecture" tags="architecture, clean-architecture, simplicity"
Prefer the simplest boundary structure that preserves dependency direction, testability, and separation of concerns.
:::
