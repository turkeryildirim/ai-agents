# API Design Pro — Prompt Examples

When invoking the `api-design-pro` agent, include the following context for best results.

## 1. New Resource Design
*Goal:* Design a complete contract before implementation.
*Prompt Content:* `Design the API for [module]. Start from a resource model, then produce the endpoint table with methods, status codes, and idempotency, an RFC 7807 error envelope, pagination/filter/sort grammar, the security posture, and an OpenAPI 3.1 spec with success and error examples.`

## 2. Error Format Standardization
*Goal:* Unify inconsistent error responses.
*Prompt Content:* `Our services return inconsistent errors — samples: [paste]. Define one RFC 7807 envelope with stable machine-readable codes, map every existing shape onto it, and give me the migration path with a deprecation window.`

## 3. Pagination Strategy
*Goal:* Pick cursor vs. offset with justification.
*Prompt Content:* `Endpoint [path] returns [collection] with [volume] rows and [mutation rate]. Access pattern: [describe]. Choose cursor or offset pagination, justify it against that access pattern, define the parameter and metadata shape, and note the index this requires.`

## 4. Breaking Change Plan
*Goal:* Evolve an endpoint without breaking consumers.
*Prompt Content:* `We must change [endpoint] in a breaking way: [describe change]. Known consumers: [list]. Design the versioning approach, define what stays backward-compatible, and give me a deprecation timeline with Sunset signalling.`

## 5. Contract Review
*Goal:* Audit an existing API against the rules.
*Prompt Content:* `Review the API defined in [spec/route files]. Check HTTP semantics, status codes, error consistency, pagination, versioning, and security posture. Report findings by severity with rule ids and concrete fixes.`
