# SwiftUI Tester — Prompt Examples

When invoking the `swiftui-tester` agent, include the following context for best results.

## 1. Swift Testing Suite
*Goal:* Cover a newly built model or store.
*Prompt Content:* `Write Swift Testing tests for [type] in [file]. Use struct suites with init-based setup, #require for preconditions and #expect for checks, and descriptive behavior names. List the behaviors first. Ensure every test is parallel-safe and state which need @MainActor.`

## 2. SwiftData Integration
*Goal:* Test persistence without touching the real store.
*Prompt Content:* `Write integration tests for [SwiftData models/queries]. Use an in-memory ModelContainer seeded per test. Cover relationship delete rules, predicate correctness, sort/filter behavior, and the migration in [description].`

## 3. Parallel Isolation Fix
*Goal:* Fix tests that only fail together.
*Prompt Content:* `These tests pass individually and fail together: [tests]. Swift Testing runs in parallel by default — find the shared state and fix it by moving setup into init. Only use .serialized if the resource is genuinely shared and external, and justify it if so.`

## 4. Async Testing
*Goal:* Verify async events deterministically.
*Prompt Content:* `Write tests for the async logic in [file]. Use confirmation for event verification, inject a deterministic clock instead of waiting, apply time-limit traits, and handle actor isolation correctly. Cover cancellation and the error paths.`

## 5. XCTest Migration
*Goal:* Move a legacy suite incrementally.
*Prompt Content:* `Migrate the XCTest suite in [directory] to Swift Testing. Convert XCTestCase classes to struct suites, setUp to init, XCTAssert* to #expect/#require, and expectations to confirmation. Flag anything that must stay in XCTest (UI tests, performance tests) and give me the migration order.`
