---
id: api-centric-development
version: "1.0.0"
title: API Development and API-Centric Architecture Rules
scope: project
status: active
---

:::rule id="API-01" mandatory="true" category="api-design" tags="api, contracts"
Define API contracts explicitly before implementing behavior.
:::

:::rule id="API-02" mandatory="true" category="api-design" tags="api, contract-first"
Treat API contracts as the authoritative definition of system behavior at the boundary.
:::

:::rule id="API-03" mandatory="true" category="api-design" tags="api, stability"
Do not expose internal domain models directly as external API contracts.
:::

:::rule id="API-04" mandatory="true" category="api-design" tags="api, versioning"
API contracts must evolve in a backward-compatible manner whenever feasible.
:::

:::rule id="API-05" mandatory="true" category="api-design" tags="api, versioning"
Do not introduce breaking changes without explicit versioning or negotiation strategy.
:::

:::rule id="API-06" mandatory="true" category="api-design" tags="api, semantics"
Define both data schema and behavioral semantics for every API operation.
:::

:::rule id="API-07" mandatory="true" category="api-design" tags="api, naming"
Use consistent, domain-aligned naming across endpoints, operations, and contracts.
:::

:::rule id="API-08" mandatory="true" category="api-design" tags="api, resources"
Model APIs around business capabilities, not database tables or CRUD exposure.
:::

:::rule id="API-09" mandatory="true" category="api-design" tags="api, boundaries"
API boundaries must align with service ownership and responsibility boundaries.
:::

:::rule id="API-10" mandatory="true" category="api-design" tags="api, validation"
Validate all inputs at the API boundary before invoking application logic.
:::

:::rule id="API-11" mandatory="true" category="api-design" tags="api, contracts, strictness"
Reject requests that violate contract expectations rather than attempting implicit correction.
:::

:::rule id="API-12" mandatory="true" category="api-design" tags="api, idempotency"
Operations that may be retried must be idempotent or explicitly duplicate-safe.
:::

:::rule id="API-13" mandatory="false" category="api-design" tags="api, http, idempotency"
Use HTTP method semantics (GET, PUT, POST, DELETE) to reflect idempotency and intent where applicable.
:::

:::rule id="API-14" mandatory="true" category="api-design" tags="api, side-effects"
Do not perform irreversible side effects before validating and authorizing the request.
:::

:::rule id="API-15" mandatory="true" category="api-design" tags="api, consistency"
Define consistency guarantees for each API operation, including eventual or strong consistency where relevant.
:::

:::rule id="API-16" mandatory="true" category="api-design" tags="api, async"
Explicitly define whether an operation is synchronous or asynchronous.
:::

:::rule id="API-17" mandatory="false" category="api-design" tags="api, async, long-running"
Use asynchronous patterns for long-running operations rather than blocking clients.
:::

:::rule id="API-18" mandatory="true" category="api-design" tags="api, errors"
Define a consistent and explicit error contract for all APIs.
:::

:::rule id="API-19" mandatory="true" category="api-design" tags="api, error-codes"
Error responses must distinguish validation, business, and infrastructure failures.
:::

:::rule id="API-20" mandatory="true" category="api-design" tags="api, security"
Do not expose internal details, stack traces, or sensitive information through API responses.
:::

:::rule id="API-21" mandatory="true" category="api-design" tags="api, schema"
API schemas must be explicit, strongly typed, and versionable.
:::

:::rule id="API-22" mandatory="true" category="api-design" tags="api, schema-evolution"
Additive changes must not break existing consumers.
:::

:::rule id="API-23" mandatory="true" category="api-design" tags="api, schema-tolerance"
Consumers must tolerate unknown fields unless explicitly forbidden.
:::

:::rule id="API-24" mandatory="true" category="api-design" tags="api, pagination"
Do not return unbounded collections; define pagination or streaming for large result sets.
:::

:::rule id="API-25" mandatory="true" category="api-design" tags="api, filtering"
Provide explicit filtering, sorting, or selection mechanisms rather than over-fetching data.
:::

:::rule id="API-26" mandatory="true" category="api-design" tags="api, performance"
Design APIs so efficient usage is the default and expensive usage is explicit.
:::

:::rule id="API-27" mandatory="true" category="api-design" tags="api, observability"
Attach correlation identifiers to every API request and response.
:::

:::rule id="API-28" mandatory="true" category="api-design" tags="api, logging"
Log API requests, responses, and failures at the appropriate boundary with structured data.
:::

:::rule id="API-29" mandatory="true" category="api-design" tags="api, retries"
Define whether clients may safely retry each API operation.
:::

:::rule id="API-30" mandatory="true" category="api-design" tags="api, timeouts"
Define expected latency and timeout behavior for each API operation.
:::

:::rule id="API-31" mandatory="true" category="api-centric" tags="api, architecture"
Design services to communicate primarily through well-defined APIs rather than shared code or databases.
:::

:::rule id="API-32" mandatory="true" category="api-centric" tags="api, dependency"
All inter-service communication must occur through explicit API contracts or messaging contracts.
:::

:::rule id="API-33" mandatory="true" category="api-centric" tags="api, autonomy"
Services must be independently deployable without requiring changes to unrelated API consumers.
:::

:::rule id="API-34" mandatory="true" category="api-centric" tags="api, compatibility"
API producers must maintain compatibility with existing consumers for supported versions.
:::

:::rule id="API-35" mandatory="true" category="api-centric" tags="api, ownership"
Each API contract must have a clearly defined owning team or service.
:::

:::rule id="API-36" mandatory="true" category="api-centric" tags="api, contracts, review"
Changes to API contracts must be reviewed with respect to consumers and compatibility impact.
:::

:::rule id="API-37" mandatory="false" category="api-centric" tags="api, api-first, design"
Adopt API-first or contract-first development where multiple teams depend on the API.
:::

:::rule id="API-38" mandatory="true" category="api-centric" tags="api, documentation"
Every public API must be documented with its purpose, inputs, outputs, error cases, and usage constraints.
:::

:::rule id="API-39" mandatory="true" category="api-centric" tags="api, discoverability"
APIs must be discoverable through consistent documentation, schemas, or metadata descriptions.
:::

:::rule id="API-40" mandatory="true" category="api-centric" tags="api, consistency"
Maintain consistent patterns across APIs for naming, errors, pagination, and authentication.
:::

:::rule id="API-41" mandatory="true" category="api-centric" tags="api, security, auth"
All protected APIs must enforce authentication and authorization at the boundary.
:::

:::rule id="API-42" mandatory="true" category="api-centric" tags="api, rate-limiting"
Define usage limits or expectations for externally exposed APIs.
:::

:::rule id="API-43" mandatory="false" category="api-centric" tags="api, rate-limiting, protection"
Apply throttling or rate limiting where APIs are exposed to untrusted or high-volume callers.
:::

:::rule id="API-44" mandatory="true" category="api-centric" tags="api, evolution"
Deprecation and removal of APIs must follow a defined lifecycle with consumer notice.
:::

:::rule id="API-45" mandatory="true" category="api-centric" tags="api, testing"
Test APIs for both success and failure cases against their contract.
:::

:::rule id="API-46" mandatory="true" category="api-centric" tags="api, contract-tests"
Use contract or integration tests to verify producer-consumer compatibility.
:::

:::rule id="API-47" mandatory="true" category="api-centric" tags="api, independence"
Do not require synchronous coordination across multiple APIs to complete a single business action unless explicitly designed.
:::

:::rule id="API-48" mandatory="false" category="api-centric" tags="api, aggregation"
Use aggregation layers or composition APIs when clients require data from multiple services.
:::

:::rule id="API-49" mandatory="true" category="api-centric" tags="api, side-effects, boundaries"
Do not couple unrelated business operations in a single API endpoint.
:::

:::rule id="API-50" mandatory="true" category="api-centric" tags="api, simplicity"
Prefer the simplest API surface that satisfies the required use cases.
:::