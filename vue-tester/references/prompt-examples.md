# Vue Tester — Prompt Examples

When invoking the `vue-tester` agent, include the following context for best results.

## 1. Component Test Suite
*Goal:* Cover a newly built component.
*Prompt Content:* `Write tests for [component]. State the test surface and why first, then list the behaviors — props, emits, slots, user interaction, error and empty states — then write complete runnable tests using accessible queries. Use the project's MSW setup for HTTP. End with the run command.`

## 2. Black-Box Rewrite
*Goal:* Decouple tests from internals.
*Prompt Content:* `These tests use wrapper.vm and class selectors: [test file]. Rewrite them against the public contract — rendered output, emitted events, observable side effects — using role/label/text queries. Show before/after and cite rule ids.`

## 3. Composable Testing
*Goal:* Test a lifecycle-bound composable properly.
*Prompt Content:* `Write tests for the composable [file]. Use a withSetup() host component so lifecycle hooks and effectScope disposal are exercised, cover the provide/inject dependencies, and assert cleanup on unmount.`

## 4. Store & Router Tests
*Goal:* Cover state and navigation.
*Prompt Content:* `Write tests for the Pinia store [file] using real Pinia, and for the route component [file] using memory history with createTestingPinia. Cover guards, param-change reactivity, and redirect termination.`

## 5. Flaky Async Test
*Goal:* Make an async test deterministic.
*Prompt Content:* `This test is flaky: [test]. Failure: [paste]. Find the missing await, the unresolved promise, or the timer leak. Replace any sleep with flushPromises or vi.waitFor, ensure fresh mocks and store per test, and show the afterEach cleanup.`
