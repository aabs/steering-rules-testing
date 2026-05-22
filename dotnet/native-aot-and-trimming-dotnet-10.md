---
id: native-aot-and-trimming-dotnet-10
version: "1.0.0"
title: Native AOT and Trimming Rules for .NET 10
scope: project
status: active
---

:::rule id="AOT-01" mandatory="true" category="deployment-compatibility" tags="aot, trimming, compatibility"
Decide per project whether it must support trimming, Native AOT, both, or neither, and record that decision in the project file.
:::

:::rule id="AOT-02" mandatory="false" category="deployment-compatibility" tags="aot, trimming, publish"
For any project that must support trimmed deployment, enable trim analysis in the project file rather than only on the publish command line.
:::

:::rule id="AOT-03" mandatory="false" category="deployment-compatibility" tags="aot, native-aot, publish"
For any project that must support Native AOT, enable AOT analysis in the project file rather than only on the publish command line.
:::

:::rule id="AOT-04" mandatory="false" category="deployment-compatibility" tags="aot, trimming, warnings"
Treat trim analysis warnings as build failures for projects that are declared trim-compatible.
:::

:::rule id="AOT-05" mandatory="false" category="deployment-compatibility" tags="aot, native-aot, warnings"
Treat AOT analysis warnings as build failures for projects that are declared AOT-compatible.
:::

:::rule id="AOT-06" mandatory="true" category="api-design" tags="aot, trimming, public-api"
Do not introduce public APIs that require unrestricted runtime reflection to function.
:::

:::rule id="AOT-07" mandatory="true" category="api-design" tags="aot, dynamic-code"
Do not require runtime code generation for core application behavior unless the project is explicitly exempt from Native AOT support.
:::

:::rule id="AOT-08" mandatory="true" category="api-design" tags="aot, serialization, source-generation"
Use source-generated serializers or equivalent compile-time metadata generation when serialization participates in trimmed or AOT-critical paths.
:::

:::rule id="AOT-09" mandatory="true" category="api-design" tags="aot, dependency-injection, registration"
Prefer explicit service registration over assembly scanning in projects that must support trimming or Native AOT.
:::

:::rule id="AOT-10" mandatory="true" category="api-design" tags="aot, reflection, activation"
Do not activate application types by string name or unconstrained reflection in trimmed or AOT-critical paths.
:::

:::rule id="AOT-11" mandatory="true" category="api-design" tags="aot, reflection, members"
Do not depend on discovering constructors, methods, properties, or fields dynamically unless those members are explicitly preserved.
:::

:::rule id="AOT-12" mandatory="true" category="api-design" tags="aot, generics, closed-types"
Ensure all generic types used in AOT-critical runtime paths are reachable through statically analyzable code paths.
:::

:::rule id="AOT-13" mandatory="true" category="api-design" tags="aot, plugins, extensibility"
Do not design plugin or extension mechanisms around arbitrary runtime type discovery if the host must support Native AOT.
:::

:::rule id="AOT-14" mandatory="false" category="api-design" tags="aot, plugins, manifests"
For trimmed or AOT-compatible extensibility, load extensions through explicit manifests, generated registries, or other statically declared contracts.
:::

:::rule id="AOT-15" mandatory="true" category="code-design" tags="aot, reflection, hotspots"
Isolate any unavoidable reflection behind a small, explicitly documented boundary.
:::

:::rule id="AOT-16" mandatory="true" category="code-design" tags="aot, annotations, contracts"
When reflection is required, annotate the exact member requirements on the API boundary that demands them.
:::

:::rule id="AOT-17" mandatory="true" category="code-design" tags="aot, annotations, minimality"
Do not preserve more types or members than the reflective code path actually requires.
:::

:::rule id="AOT-18" mandatory="true" category="code-design" tags="aot, suppression, warnings"
Do not suppress trim or AOT warnings without documenting the specific code path, reason, and safety argument.
:::

:::rule id="AOT-19" mandatory="true" category="code-design" tags="aot, suppression, scope"
Keep every trim or AOT suppression local to the smallest possible member or call site.
:::

:::rule id="AOT-20" mandatory="true" category="code-design" tags="aot, dynamic-dependencies"
Use explicit preservation metadata only for members that are proven necessary at runtime.
:::

:::rule id="AOT-21" mandatory="true" category="code-design" tags="aot, dependencies, libraries"
Do not depend on third-party libraries in trimmed or AOT-targeted projects unless their compatibility has been verified.
:::

:::rule id="AOT-22" mandatory="false" category="code-design" tags="aot, libraries, metadata"
Mark libraries as trim-compatible or AOT-compatible only after their warnings are resolved and their supported scenarios are documented.
:::

:::rule id="AOT-23" mandatory="true" category="configuration" tags="aot, configuration, binding"
Use compile-time-supported configuration binding patterns in projects that must support trimming.
:::

:::rule id="AOT-24" mandatory="true" category="configuration" tags="aot, options, models"
Keep configuration models simple, concrete, and statically analyzable in trimmed or AOT-targeted code paths.
:::

:::rule id="AOT-25" mandatory="true" category="serialization" tags="aot, json, contracts"
Define serialization contracts explicitly and do not rely on incidental runtime discovery of serializable members.
:::

:::rule id="AOT-26" mandatory="true" category="serialization" tags="aot, polymorphism"
Do not use open-ended runtime polymorphic serialization in trimmed or AOT-targeted code paths unless all runtime types are explicitly declared.
:::

:::rule id="AOT-27" mandatory="true" category="serialization" tags="aot, duplicate-properties, strictness"
Use explicit serializer settings and contract metadata rather than relying on permissive runtime defaults in trimmed or AOT-targeted systems.
:::

:::rule id="AOT-28" mandatory="true" category="dependency-injection" tags="aot, di, factories"
Prefer constructor injection and explicit factories over container-driven reflection-heavy activation in AOT-targeted projects.
:::

:::rule id="AOT-29" mandatory="true" category="dependency-injection" tags="aot, di, open-generics"
Do not register or resolve service patterns whose runtime activation depends on unbounded type discovery.
:::

:::rule id="AOT-30" mandatory="false" category="build" tags="aot, publish, rid"
Publish Native AOT artifacts for explicit runtime identifiers in CI for every supported deployment target.
:::

:::rule id="AOT-31" mandatory="false" category="build" tags="aot, trimming, publish-validation"
Publish trimmed artifacts in CI for every project that declares trimmed deployment support.
:::

:::rule id="AOT-32" mandatory="false" category="build" tags="aot, smoke-test, ci"
Run a smoke test against the published trimmed or AOT artifact rather than relying only on normal debug builds.
:::

:::rule id="AOT-33" mandatory="true" category="build" tags="aot, debug, release"
Do not assume Debug build behavior proves trimmed or Native AOT compatibility.
:::

:::rule id="AOT-34" mandatory="true" category="build" tags="aot, analyzers, source-control"
Keep all AOT and trimming compatibility settings under source control in the project file or repository build configuration.
:::

:::rule id="AOT-35" mandatory="false" category="build" tags="aot, optimization-preference"
Set Native AOT optimization preference explicitly only when startup, size, or throughput goals have been measured.
:::

:::rule id="AOT-36" mandatory="true" category="runtime-behavior" tags="aot, feature-gating"
Guard unsupported dynamic features behind explicit feature boundaries so they cannot execute in trimmed or AOT deployments accidentally.
:::

:::rule id="AOT-37" mandatory="true" category="runtime-behavior" tags="aot, fallbacks, semantics"
Do not silently fall back to reflection-heavy or non-AOT-safe behavior in a deployment that claims AOT or trim compatibility.
:::

:::rule id="AOT-38" mandatory="true" category="runtime-behavior" tags="aot, diagnostics, startup"
Fail fast with a clear startup or initialization error when a required preserved member or generated artifact is missing.
:::

:::rule id="AOT-39" mandatory="true" category="testing" tags="aot, tests, coverage"
Test the exact code paths that use serialization, configuration binding, dependency injection, and activation in published trimmed or AOT artifacts.
:::

:::rule id="AOT-40" mandatory="false" category="testing" tags="aot, tests, reflection"
Add targeted tests for every intentionally preserved reflective code path.
:::

:::rule id="AOT-41" mandatory="true" category="testing" tags="aot, regression, warnings"
Add regression checks that fail the build if new trim or AOT warnings are introduced in compatible projects.
:::

:::rule id="AOT-42" mandatory="true" category="design" tags="aot, architecture, boundaries"
Keep trim-sensitive and AOT-sensitive code paths near the application boundary rather than scattered through core domain logic.
:::

:::rule id="AOT-43" mandatory="true" category="design" tags="aot, domain, purity"
Keep core business logic free of runtime type discovery, dynamic loading, and runtime code emission.
:::

:::rule id="AOT-44" mandatory="true" category="design" tags="aot, ownership, documentation"
Document which projects, assemblies, or binaries are expected to be trim-compatible, AOT-compatible, or exempt.
:::

:::rule id="AOT-45" mandatory="false" category="design" tags="aot, migration, incremental-adoption"
Adopt trimming and Native AOT incrementally by first making leaf libraries and executables warning-clean.
:::

:::rule id="AOT-46" mandatory="true" category="design" tags="aot, compatibility, contracts"
If a project claims trim or AOT compatibility, treat that claim as a supported contract that must be preserved by future changes.
:::

:::rule id="AOT-47" mandatory="true" category="dependencies" tags="aot, packages, review"
Review new package dependencies for reflection, dynamic loading, source generation support, and published trim or AOT guidance before adoption.
:::

:::rule id="AOT-48" mandatory="true" category="dependencies" tags="aot, package-upgrades, verification"
Re-run trim and AOT publish validation after upgrading any package that participates in startup, serialization, dependency injection, or activation.
:::

:::rule id="AOT-49" mandatory="true" category="design" tags="aot, explicitness, defaults"
Prefer explicit metadata, explicit registrations, and explicit contracts over convention-based runtime discovery.
:::

:::rule id="AOT-50" mandatory="true" category="design" tags="aot, simplicity"
Prefer the simplest AOT-safe and trim-safe design that satisfies the measured deployment goals.
:::