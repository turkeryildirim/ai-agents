# JS Tester — Prompt Examples

When invoking the `js-tester` agent, include the following context for best results.

## 1. New Test Suite
*Goal:* Cover a freshly implemented module.
*Prompt Content:* `Write Vitest tests for [module] in [file]. First list the behaviors — happy path, error paths, boundaries — then write complete runnable tests. Match the conventions in [existing test file]. State the isolation strategy per dependency and end with the run command.`

## 2. Flake Diagnosis
*Goal:* Find why a test only fails in CI.
*Prompt Content:* `This test passes locally and fails in CI: [test]. Output: [paste]. Diagnose the root cause — leaked timers, shared module state, ordering dependency, unhandled rejection, or real I/O — and give the fix. Do not add a retry.`

## 3. Mocking Strategy Review
*Goal:* Replace over-mocking with real coverage.
*Prompt Content:* `Review the mocks in [test file]. Flag module mocks that should be dependency injection, stubbed HTTP clients that should be MSW handlers, and assertions on internals. Rewrite the worst offenders around observable behavior and cite rule ids.`

## 4. Async & Timer Tests
*Goal:* Test time-dependent logic deterministically.
*Prompt Content:* `Write tests for [time-dependent logic] in [file]. Use fake timers with explicit advancement, inject the clock, and cover the debounce/retry/timeout boundaries. No arbitrary sleeps. Show the cleanup in afterEach.`

## 5. Coverage Gap Audit
*Goal:* Find what the coverage number hides.
*Prompt Content:* `Coverage reports [n]% for [directory] but regressions still ship. Analyze branch coverage rather than line coverage, list every untested error path and boundary, and give me the tests that would actually catch regressions — ordered by risk.`
