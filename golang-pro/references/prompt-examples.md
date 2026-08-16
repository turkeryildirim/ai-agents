# Golang Pro — Prompt Examples

When invoking the `golang-pro` agent, include the following context for best results.

## 1. Post-Implementation Review
*Goal:* Review a Go diff before merge.
*Prompt Content:* `Review the Go code I just wrote in [files]. Focus on the diff. Check idiom, interface placement, goroutine lifecycles, context propagation, error wrapping and single-handling, and hot-path allocations. Cite rule ids, give fix code with file:line, and end with the validation commands.`

## 2. Goroutine Leak Hunt
*Goal:* Find why goroutines accumulate.
*Prompt Content:* `Our service accumulates goroutines under load: [files]. Produce a goroutine lifecycle audit — where each is started, who owns it, and what guarantees it exits. Find the leak, give the fix, and tell me whether goleak should be added to the test suite.`

## 3. Concurrent Worker Design
*Goal:* Build a bounded, cancellable pipeline.
*Prompt Content:* `Design a [purpose] worker pool in Go [version]. Requirements: bounded concurrency of [n], context cancellation, error aggregation via errgroup, and graceful drain on shutdown. Show the goroutine ownership model explicitly. Do not write tests — list the behaviors for golang-tester.`

## 4. Error Handling Cleanup
*Goal:* Restore context in the error chain.
*Prompt Content:* `Errors lose context between [layer] and [layer]: [files]. Fix the wrapping with %w, introduce sentinel errors or typed errors where callers need to branch, ensure each error is handled exactly once, and keep messages low-cardinality. Show before/after.`

## 5. Performance Pass
*Goal:* Cut allocations in a hot path.
*Prompt Content:* `Profile output for [function]: [paste]. Identify the allocations causing escapes, apply pre-allocation, strings.Builder, and sync.Pool where justified, and tell me which changes need a benchmark to prove. Do not optimize what the profile does not implicate.`
