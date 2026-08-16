# Microservices Pro — Prompt Examples

When invoking the `microservices-pro` agent, include the following context for best results.

## 1. Monolith Decomposition
*Goal:* Find the seams and get a reversible migration path.
*Prompt Content:* `Our monolith is [stack] with [modules]. Team size: [n]. Deploy cadence: [x]. Map the bounded contexts, tell me honestly whether we should split at all, and if so give me a strangler-fig migration path in reversible steps with the first extraction named.`

## 2. Saga Design
*Goal:* Make a cross-service transaction survive partial failure.
*Prompt Content:* `This flow spans [services]: [describe steps]. Currently it can leave [inconsistent state]. Design a saga — orchestration or choreography with justification — define every compensating action, specify consumer idempotency keys, and tell me whether the outbox pattern is required.`

## 3. Resilience Hardening
*Goal:* Contain a failure that cascades.
*Prompt Content:* `When [service] is slow, [downstream impact] happens. Give me a resilience matrix: timeout, retry policy with backoff and jitter, circuit breaker thresholds, bulkhead isolation, and the exact degraded behavior the user should see. Cite rule ids.`

## 4. Observability Setup
*Goal:* Make a request traceable end to end.
*Prompt Content:* `We cannot trace a request across [services]. Design correlation-id propagation including across the message broker, the trace span structure, the structured log fields every service must emit, and the SLI/SLO for the [critical path] flow.`

## 5. Distributed Review
*Goal:* Audit an existing distributed system.
*Prompt Content:* `Review our service topology: [describe or point to manifests]. Check boundary correctness, shared-database violations, missing timeouts and breakers, consumer idempotency, correlation-id gaps, and health probe semantics. Report by severity with rule ids and concrete fixes.`
