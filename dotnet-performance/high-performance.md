---
id: high-performance-dotnet-10
version: "1.0.0"
title: High Performance Code Rules for .NET 10
scope: project
status: active
---

:::rule id="PERF-01" mandatory="true" category="performance" tags="performance, measurement"
Measure before and after every non-trivial performance optimization.
:::

:::rule id="PERF-02" mandatory="true" category="performance" tags="performance, hot-paths"
Optimize only code paths that are proven hot or materially user-visible.
:::

:::rule id="PERF-03" mandatory="true" category="performance" tags="performance, correctness"
Never trade away correctness, determinism, or observability for performance.
:::

:::rule id="PERF-04" mandatory="true" category="performance" tags="performance, allocations"
Avoid unnecessary allocations in hot paths.
:::

:::rule id="PERF-05" mandatory="true" category="performance" tags="performance, boxing"
Avoid hidden boxing in hot paths.
:::

:::rule id="PERF-06" mandatory="true" category="performance" tags="performance, linq"
Do not use allocation-heavy LINQ or iterator chains in hot paths when a simpler loop is materially cheaper.
:::

:::rule id="PERF-07" mandatory="true" category="performance" tags="performance, strings"
Minimize transient string creation in hot paths.
:::

:::rule id="PERF-08" mandatory="true" category="performance" tags="performance, parsing, formatting"
Use span-based parsing and formatting APIs where they materially reduce copying or allocation.
:::

:::rule id="PERF-09" mandatory="false" category="performance" tags="performance, spans"
Use Span<T> and ReadOnlySpan<T> only where they improve performance without making ownership or lifetime unsafe or unclear.
:::

:::rule id="PERF-10" mandatory="false" category="performance" tags="performance, memory"
Use Memory<T> and ReadOnlyMemory<T> only where buffer lifetime must cross async or heap boundaries.
:::

:::rule id="PERF-11" mandatory="true" category="performance" tags="performance, copying"
Avoid copying large buffers or collections when a safe slice, view, or reference is sufficient.
:::

:::rule id="PERF-12" mandatory="false" category="performance" tags="performance, stackalloc"
Use stackalloc only for small, bounded, short-lived buffers.
:::

:::rule id="PERF-13" mandatory="false" category="performance" tags="performance, pooling, arraypool"
Use ArrayPool<T> when frequent buffer allocation creates measurable GC pressure.
:::

:::rule id="PERF-14" mandatory="false" category="performance" tags="performance, pooling, objectpool"
Use object pooling only for objects that are expensive to create or reset and are used predictably at high frequency.
:::

:::rule id="PERF-15" mandatory="true" category="performance" tags="performance, pooling, ownership"
Always return rented or pooled resources promptly and exactly once.
:::

:::rule id="PERF-16" mandatory="true" category="performance" tags="performance, pooling, safety"
Do not expose pooled buffers or objects beyond the lifetime in which they are valid to use.
:::

:::rule id="PERF-17" mandatory="true" category="performance" tags="performance, async"
Use async and await for naturally asynchronous I/O-bound operations.
:::

:::rule id="PERF-18" mandatory="true" category="performance" tags="performance, blocking"
Do not block threads on asynchronous work in throughput-sensitive code paths.
:::

:::rule id="PERF-19" mandatory="false" category="performance" tags="performance, valuetask"
Use ValueTask only when measurement shows that avoiding Task allocation is materially beneficial.
:::

:::rule id="PERF-20" mandatory="true" category="performance" tags="performance, cancellation"
Propagate CancellationToken in long-running or potentially blocking operations to avoid wasted work.
:::

:::rule id="PERF-21" mandatory="true" category="performance" tags="performance, logging"
Use structured logging and avoid expensive log message construction when the log level is disabled.
:::

:::rule id="PERF-22" mandatory="true" category="performance" tags="performance, exceptions"
Do not use exceptions for normal control flow in hot paths.
:::

:::rule id="PERF-23" mandatory="true" category="performance" tags="performance, exceptions, validation"
Validate arguments and fail early before expensive work begins.
:::

:::rule id="PERF-24" mandatory="true" category="performance" tags="performance, collections"
Choose collection types based on required lookup, iteration, mutation, and allocation characteristics.
:::

:::rule id="PERF-25" mandatory="true" category="performance" tags="performance, enumeration"
Avoid multiple enumeration of the same sequence in hot paths.
:::

:::rule id="PERF-26" mandatory="true" category="performance" tags="performance, data-structures"
Prefer contiguous data access patterns when they materially improve cache locality.
:::

:::rule id="PERF-27" mandatory="false" category="performance" tags="performance, structs"
Use structs only when value semantics and measured allocation or locality benefits justify them.
:::

:::rule id="PERF-28" mandatory="false" category="performance" tags="performance, readonly-struct"
Use readonly struct for immutable value types that are frequently copied or passed by reference.
:::

:::rule id="PERF-29" mandatory="true" category="performance" tags="performance, mutability"
Prefer immutability by default, but avoid defensive copying in hot paths unless correctness requires it.
:::

:::rule id="PERF-30" mandatory="true" category="performance" tags="performance, generics"
Prefer generic, type-safe code over object-based abstractions when object-based code would box or allocate materially more.
:::

:::rule id="PERF-31" mandatory="true" category="performance" tags="performance, virtual-dispatch"
Avoid unnecessary virtual dispatch in hot paths when a simpler and equally maintainable alternative exists.
:::

:::rule id="PERF-32" mandatory="true" category="performance" tags="performance, reflection"
Avoid runtime reflection in hot paths.
:::

:::rule id="PERF-33" mandatory="false" category="performance" tags="performance, source-generators"
Prefer source generation over runtime reflection or runtime code discovery where it materially improves startup or throughput.
:::

:::rule id="PERF-34" mandatory="true" category="performance" tags="performance, serialization"
Choose serialization and deserialization paths that minimize allocation, copying, and intermediate materialization.
:::

:::rule id="PERF-35" mandatory="true" category="performance" tags="performance, io"
Stream or pipe large payloads instead of fully materializing them when full buffering is unnecessary.
:::

:::rule id="PERF-36" mandatory="true" category="performance" tags="performance, memory, gc"
Design hot-path code to reduce GC pressure rather than relying on forced collection.
:::

:::rule id="PERF-37" mandatory="true" category="performance" tags="performance, gc"
Do not call GC.Collect in production code as a performance strategy.
:::

:::rule id="PERF-38" mandatory="true" category="performance" tags="performance, concurrency"
Do not introduce parallelism unless the workload is safe, partitionable, and measurably faster under realistic contention.
:::

:::rule id="PERF-39" mandatory="true" category="performance" tags="performance, contention"
Avoid shared mutable state and lock contention in throughput-sensitive code.
:::

:::rule id="PERF-40" mandatory="false" category="performance" tags="performance, simd, intrinsics"
Use SIMD, hardware intrinsics, or vectorized APIs only when measurement shows a clear benefit and portability remains acceptable.
:::

:::rule id="PERF-41" mandatory="true" category="performance" tags="performance, loops"
Keep hot loops simple, branch-light, and allocation-free where practical.
:::

:::rule id="PERF-42" mandatory="true" category="performance" tags="performance, bounds"
Keep hot-path assumptions explicit and validate them outside the hot loop where possible.
:::

:::rule id="PERF-43" mandatory="false" category="performance" tags="performance, tiered-compilation"
Change tiered compilation, quick JIT, or compilation settings only when benchmark evidence justifies it.
:::

:::rule id="PERF-44" mandatory="false" category="performance" tags="performance, trimming"
Make libraries trimming-compatible when they are intended for trimmed deployments.
:::

:::rule id="PERF-45" mandatory="false" category="performance" tags="performance, native-aot"
Use Native AOT only when startup time, memory footprint, deployment model, or scale characteristics justify its constraints.
:::

:::rule id="PERF-46" mandatory="false" category="performance" tags="performance, aot, compatibility"
Avoid dynamic code paths that prevent trimming or Native AOT where those deployment modes are required.
:::

:::rule id="PERF-47" mandatory="true" category="performance" tags="performance, profiling, observability"
Use profiling and production-safe telemetry to locate CPU, memory, allocation, and latency bottlenecks.
:::

:::rule id="PERF-48" mandatory="true" category="performance" tags="performance, regression"
Protect important performance characteristics with repeatable benchmarks or regression checks.
:::

:::rule id="PERF-49" mandatory="true" category="performance" tags="performance, api-design"
Design APIs so efficient usage is the default and expensive usage is explicit.
:::

:::rule id="PERF-50" mandatory="true" category="performance" tags="performance, simplicity"
Prefer the simplest implementation that meets measured performance goals.
:::