# Go Reviewer — Prompt Examples

When invoking the `golang-reviewer` agent, include the following context for best results.

## 1. Post-Feature Review

*Goal:* Review code written for a new feature.
*Prompt Content:* `Review the recently written code in [file paths]. This is a [HTTP handler / service / repository / CLI command] that [brief description]. Pay special attention to [error handling / context propagation / interface design]. The project uses Go [version] with [Gin / Chi / Echo / stdlib] and [pgx / sqlx / GORM] for the database.`

## 2. Concurrency & Goroutine Safety Review

*Goal:* Verify goroutine lifecycle and context propagation after a concurrency change.
*Prompt Content:* `Perform a concurrency-focused review of [file path]. We just added a background worker goroutine. Verify the goroutine has a clear termination path via context cancellation, that context is propagated to all downstream calls, and that shared state is properly protected. The project targets Go 1.22.`

## 3. Security-Focused Review

*Goal:* Audit a data-access or input-handling layer for vulnerabilities.
*Prompt Content:* `Perform a security-focused review of [file path]. This is a repository layer that constructs database queries from user input. Verify all queries use parameterized statements, no credentials are hardcoded, and input is validated before use.`

## 4. Refactor Quality Check

*Goal:* Ensure a refactor to idiomatic Go didn't introduce regressions.
*Prompt Content:* `Review the refactored code in [file path]. We migrated from global state to constructor-injected dependencies. Check for: any remaining package-level vars, interfaces defined in the wrong package (should be consumer-side), and proper error wrapping with %w.`

## 5. Interface & Package Design Audit

*Goal:* Audit package boundaries and interface design before a PR.
*Prompt Content:* `Audit the package design of [directory]. Check for: large interfaces (>3 methods) used as dependencies, interfaces defined in the implementation package instead of the consumer, typed nil pointer returns, and proper use of internal/ for unexported packages.`

## 6. Error Handling Audit

*Goal:* Enforce consistent error handling across a package.
*Prompt Content:* `Audit error handling in [file path / package]. Flag: errors ignored with _, errors both logged and returned (single handling rule violation), missing %w wrapping, string comparisons on errors instead of errors.Is/As, and panic used for non-programmer errors.`
