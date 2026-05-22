---
id: solid-design-guidelines
version: "1.0.0"
title: SOLID Design Guidelines
scope: project
status: active
---

:::rule id="SOLID-01" mandatory="true" category="design" tags="solid, srp, responsibility"
Each class, component, or module must have one clear reason to change.
:::

:::rule id="SOLID-02" mandatory="true" category="design" tags="solid, srp, cohesion"
Keep each class or component focused on one cohesive responsibility.
:::

:::rule id="SOLID-03" mandatory="true" category="design" tags="solid, srp, size"
When a class accumulates unrelated responsibilities, split it along responsibility boundaries.
:::

:::rule id="SOLID-04" mandatory="true" category="design" tags="solid, srp, orchestration"
Keep orchestration responsibilities separate from domain decision-making responsibilities.
:::

:::rule id="SOLID-05" mandatory="true" category="design" tags="solid, ocp, extension"
Design modules to be extended by adding new code rather than modifying stable existing code.
:::

:::rule id="SOLID-06" mandatory="true" category="design" tags="solid, ocp, variation"
Isolate anticipated variation points behind explicit abstractions or extension seams.
:::

:::rule id="SOLID-07" mandatory="true" category="design" tags="solid, ocp, branching"
Do not centralize growing behavior variation in large conditional trees when polymorphism or composition can localize it.
:::

:::rule id="SOLID-08" mandatory="true" category="design" tags="solid, ocp, policy"
Keep stable business policy separate from replaceable implementation detail.
:::

:::rule id="SOLID-09" mandatory="true" category="design" tags="solid, lsp, substitutability"
Any subtype must preserve the observable behavioral contract of the base type.
:::

:::rule id="SOLID-10" mandatory="true" category="design" tags="solid, lsp, preconditions"
A subtype must not strengthen preconditions beyond those of the base contract.
:::

:::rule id="SOLID-11" mandatory="true" category="design" tags="solid, lsp, postconditions"
A subtype must not weaken the postconditions guaranteed by the base contract.
:::

:::rule id="SOLID-12" mandatory="true" category="design" tags="solid, lsp, invariants"
A subtype must preserve the invariants of the base abstraction.
:::

:::rule id="SOLID-13" mandatory="true" category="design" tags="solid, lsp, exceptions"
A subtype must not introduce failure modes that violate reasonable caller expectations of the base contract.
:::

:::rule id="SOLID-14" mandatory="true" category="design" tags="solid, lsp, null-object"
Do not model absence or unsupported behavior as a subtype unless that subtype still satisfies the parent contract.
:::

:::rule id="SOLID-15" mandatory="true" category="design" tags="solid, isp, interfaces"
Clients must not be forced to depend on members they do not use.
:::

:::rule id="SOLID-16" mandatory="true" category="design" tags="solid, isp, cohesion"
Keep interfaces small, role-focused, and cohesive.
:::

:::rule id="SOLID-17" mandatory="true" category="design" tags="solid, isp, segregation"
Split broad interfaces when different clients depend on disjoint subsets of behavior.
:::

:::rule id="SOLID-18" mandatory="true" category="design" tags="solid, isp, leakage"
Do not expose implementation convenience methods through public interfaces unless they are part of the client-facing role.
:::

:::rule id="SOLID-19" mandatory="true" category="design" tags="solid, dip, abstractions"
High-level policy must depend on abstractions, not on low-level details.
:::

:::rule id="SOLID-20" mandatory="true" category="design" tags="solid, dip, ownership"
Define abstractions at the layer that owns the policy or use case that needs them.
:::

:::rule id="SOLID-21" mandatory="true" category="design" tags="solid, dip, direction"
Low-level details must implement abstractions required by higher-level policy.
:::

:::rule id="SOLID-22" mandatory="true" category="design" tags="solid, dip, boundaries"
Cross-boundary dependencies must flow through explicit contracts rather than concrete implementations.
:::

:::rule id="SOLID-23" mandatory="true" category="design" tags="solid, composition, dependency-injection"
Compose concrete implementations at the application boundary rather than inside business logic.
:::

:::rule id="SOLID-24" mandatory="true" category="design" tags="solid, testability"
Use SOLID boundaries to make policy code testable without external systems.
:::

:::rule id="SOLID-25" mandatory="true" category="design" tags="solid, srp, state"
Do not combine state management, I/O, validation, and business rules in the same class when they can change independently.
:::

:::rule id="SOLID-26" mandatory="true" category="design" tags="solid, cohesion, naming"
Name classes and interfaces according to their responsibility or role, not their implementation mechanism.
:::

:::rule id="SOLID-27" mandatory="true" category="design" tags="solid, abstraction, semantics"
Every abstraction must represent a meaningful role, capability, or policy boundary.
:::

:::rule id="SOLID-28" mandatory="true" category="design" tags="solid, abstraction, minimality"
Do not introduce abstractions that have only one foreseeable implementation and no independent policy boundary.
:::

:::rule id="SOLID-29" mandatory="false" category="design" tags="solid, abstraction, variability"
Introduce an abstraction when a dependency is expected to vary independently of the policy that uses it.
:::

:::rule id="SOLID-30" mandatory="true" category="design" tags="solid, composition, inheritance"
Prefer composition over inheritance when reuse does not require subtype substitutability.
:::

:::rule id="SOLID-31" mandatory="true" category="design" tags="solid, inheritance, hierarchy"
Use inheritance only when the child is truly substitutable for the parent.
:::

:::rule id="SOLID-32" mandatory="true" category="design" tags="solid, inheritance, reuse"
Do not use inheritance only to reuse implementation.
:::

:::rule id="SOLID-33" mandatory="true" category="design" tags="solid, domain, invariants"
Place business invariants in the type that owns the business concept they protect.
:::

:::rule id="SOLID-34" mandatory="true" category="design" tags="solid, commands, queries"
Separate mutation responsibilities from pure query responsibilities when combining them obscures intent or invariants.
:::

:::rule id="SOLID-35" mandatory="true" category="design" tags="solid, coupling"
Minimize knowledge of concrete collaborators, construction details, and hidden global state.
:::

:::rule id="SOLID-36" mandatory="true" category="design" tags="solid, globals, state"
Do not hide dependencies in static mutable state, service locators, or ambient context when they can be explicit.
:::

:::rule id="SOLID-37" mandatory="true" category="design" tags="solid, constructors, dependencies"
Require mandatory collaborators explicitly through construction or equivalent boundary composition.
:::

:::rule id="SOLID-38" mandatory="true" category="design" tags="solid, optional-dependencies"
Do not make a dependency optional if the type cannot fulfill its contract correctly without it.
:::

:::rule id="SOLID-39" mandatory="true" category="design" tags="solid, interface-contracts, documentation"
Document or encode the behavioral expectations of abstractions that have non-obvious preconditions, postconditions, or invariants.
:::

:::rule id="SOLID-40" mandatory="true" category="design" tags="solid, side-effects, purity"
Keep pure decision logic separate from side-effecting detail where practical.
:::

:::rule id="SOLID-41" mandatory="false" category="design" tags="solid, patterns, strategy"
Use strategy, policy, or plug-in style composition when behavior families vary independently and must remain open for extension.
:::

:::rule id="SOLID-42" mandatory="false" category="design" tags="solid, patterns, decorator"
Use decorator-style composition when behavior must be extended transparently without changing the core contract.
:::

:::rule id="SOLID-43" mandatory="true" category="design" tags="solid, refactoring, smells"
Treat large classes, large interfaces, feature envy, and repeated type-switching as refactoring triggers.
:::

:::rule id="SOLID-44" mandatory="true" category="design" tags="solid, change-isolation"
A change in low-level implementation detail should not require changes in high-level policy code.
:::

:::rule id="SOLID-45" mandatory="true" category="design" tags="solid, persistence, transport"
Do not let persistence, transport, or framework concerns shape core domain abstractions.
:::

:::rule id="SOLID-46" mandatory="true" category="design" tags="solid, boundaries, translation"
Translate between external models and internal abstractions at the boundary that receives the external model.
:::

:::rule id="SOLID-47" mandatory="true" category="design" tags="solid, error-handling, contracts"
Error behavior must be consistent with the abstraction contract and must not leak irrelevant implementation details.
:::

:::rule id="SOLID-48" mandatory="true" category="design" tags="solid, modularity, packages"
Package and project structure must reinforce responsibility boundaries and dependency direction.
:::

:::rule id="SOLID-49" mandatory="true" category="design" tags="solid, reviews, reasoning"
Evaluate SOLID compliance in terms of change isolation, substitutability, cohesion, and dependency direction rather than class count alone.
:::

:::rule id="SOLID-50" mandatory="true" category="design" tags="solid, simplicity"
Prefer the simplest design that preserves clear responsibilities, substitutable contracts, cohesive interfaces, and dependency inversion.
:::
