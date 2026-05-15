# Go Tester — Prompt Examples

When invoking the `golang-tester` agent, include the following context for best results.

## 1. New Service — Unit Tests

*Goal:* Write table-driven unit tests for a newly written service.
*Prompt Content:* `Write unit tests for the OrderService in [file path]. The service depends on an OrderRepository interface. Mock the repository at the interface boundary. Cover: happy path, repository error, validation error. The project uses testify v1.10 and Go 1.22.`

## 2. HTTP Handler Tests

*Goal:* Test a new or modified HTTP handler with httptest.
*Prompt Content:* `Write httptest-based tests for the [HandlerName] in [file path]. The handler calls [ServiceInterface]. Mock the service. Cover: 200 success, 400 bad request (invalid body), 404 not found, 500 service error. Use chi URL params if applicable.`

## 3. Integration Tests with Real DB

*Goal:* Write integration tests that hit a real database.
*Prompt Content:* `Write integration tests for the UserRepository in [file path]. These tests require a real Postgres database. Tag them with //go:build integration. Use testcontainers-go to spin up a Postgres container. Cover: insert, find by ID, find returns ErrNotFound, delete cascade.`

## 4. Goroutine Leak Detection

*Goal:* Add goleak-guarded tests to a package that spawns goroutines.
*Prompt Content:* `Add goleak.VerifyTestMain to the [package name] package and write tests for the WorkerPool in [file path]. The pool spawns goroutines that must be cleaned up when Stop() is called. Verify the goroutines are fully terminated using goleak.`

## 5. Benchmark

*Goal:* Add benchmarks for a performance-critical function.
*Prompt Content:* `Write benchmarks for the [FunctionName] in [file path]. It processes a slice of orders and applies discount rules. Use b.ReportAllocs() and b.ResetTimer(). Add both a small (10 items) and large (10,000 items) case.`

## 6. Existing Test Refactor

*Goal:* Migrate non-table-driven tests to idiomatic Go table-driven style.
*Prompt Content:* `Refactor the tests in [file path] from repeated TestX_CaseA / TestX_CaseB functions into a single table-driven TestX with t.Run subtests. Preserve all existing test cases. Add t.Parallel() to independent subtests. The project uses testify.`
