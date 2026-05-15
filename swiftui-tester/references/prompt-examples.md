# SwiftUI Tester — Prompt Examples

When invoking the `swiftui-tester` agent, include the following context for best results.

## 1. New ViewModel — Unit Tests

*Goal:* Write Swift Testing unit tests for a newly written ViewModel.
*Prompt Content:* `Write Swift Testing unit tests for the OrderListViewModel in [file path]. The ViewModel is @Observable and @MainActor. It depends on an OrderServiceProtocol. Use a mock service. Cover: successful load, loading state during fetch, service error propagation, filter logic. The project targets Xcode 16 / iOS 17.`

## 2. SwiftData Model — Integration Tests

*Goal:* Write in-memory SwiftData tests for a new @Model class.
*Prompt Content:* `Write Swift Testing integration tests for the Order @Model in [file path]. Use an in-memory ModelContainer. Cover: insert and fetch, relationship cascade delete (order → items), #Predicate filtering by status, and that a delete rule violation throws. The project targets iOS 17.`

## 3. Async ViewModel Tests

*Goal:* Test async loading and cancellation behavior.
*Prompt Content:* `Write async Swift Testing tests for [ViewModelName] in [file path]. The ViewModel uses .task {} lifecycle. Cover: successful async load, isLoading flag during fetch, cancellation via task context, and error handling. Mark the test suite @MainActor. Use confirmation() to verify async events.`

## 4. UI Test — Critical User Flow

*Goal:* Add an XCTest UI test for a key user flow.
*Prompt Content:* `Write an XCTest UI test for the checkout flow starting from [ScreenName]. The app has accessibility identifiers on all interactive elements. Use the Page Object pattern — create a CheckoutScreen helper. Cover: happy path to order confirmation, validation error when required field is empty. Use launch arguments to put the app in test mode.`

## 5. Parameterized Tests

*Goal:* Replace repetitive test functions with Swift Testing parameterized tests.
*Prompt Content:* `Refactor the tests in [file path] to use parameterized @Test with arguments. The current tests repeat similar logic for multiple OrderStatus values. Consolidate into a single parameterized test covering all status transitions.`

## 6. Known Issue / Flaky Test Handling

*Goal:* Handle a known failing test that maps to a tracked issue.
*Prompt Content:* `The test [testName] in [file path] is failing because of a known bug tracked in issue #[number]. Wrap the failing assertions with withKnownIssue("Tracked in #[number]") { } so the test suite passes in CI but the issue remains visible. Do not remove the test.`
