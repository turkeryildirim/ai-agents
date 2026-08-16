# Kotlin Tester — Prompt Examples

When invoking the `kotlin-tester` agent, include the following context for best results.

## 1. ViewModel Test Suite
*Goal:* Cover a ViewModel's state and effects.
*Prompt Content:* `Write tests for [ViewModel]. Use MainDispatcherRule, runTest with an injected TestDispatcher, and Turbine for the StateFlow assertions. Build the GIVEN/WHEN/THEN behavior table first, cover loading/success/error/empty states, and use fakes rather than MockK chains where the dependency is stateful.`

## 2. Flow Testing
*Goal:* Assert on a hot stream correctly.
*Prompt Content:* `Write tests for the Flow logic in [file]. Use Turbine for StateFlow/SharedFlow, cover emission order, distinctUntilChanged behavior, and cancellation. Explain where advanceUntilIdle is needed and why toList() would be wrong here.`

## 3. Compose UI Tests
*Goal:* Make UI tests survive CI.
*Prompt Content:* `Write Compose tests for [screen]. Use createComposeRule, testTag selectors, and the Robot pattern. Cover interaction, state restoration, and the error/empty states. Use waitUntil instead of sleeps and tell me the Orchestrator and animation settings needed.`

## 4. Espresso Flake Fix
*Goal:* Remove nondeterminism from instrumented tests.
*Prompt Content:* `These Espresso tests are flaky: [tests]. Replace Thread.sleep with IdlingResources or waitUntil, move selectors into Robot classes, add Orchestrator isolation, and disable animations. Explain the root cause of each flake — do not just add retries.`

## 5. Coverage & CI Setup
*Goal:* Wire enforcement into the pipeline.
*Prompt Content:* `Set up Kover with a [n]% threshold for [modules], configure Gradle Managed Devices for instrumented tests, and wire it into [CI system]. Tell me which packages should be excluded from coverage and why, and report the current branch gaps.`
