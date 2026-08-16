# Golang Tester — Prompt Examples

When invoking the `golang-tester` agent, include the following context for best results.

## 1. Table-Driven Suite
*Goal:* Cover a newly implemented package.
*Prompt Content:* `Write tests for [package/file]. List the behaviors first — happy path, every error path, and edge cases (zero values, empty slices, nil pointers, boundaries) — then write a complete table-driven suite with named cases and t.Run subtests. State the mock strategy per dependency. End with the run command.`

## 2. Concurrency Test
*Goal:* Prove a concurrent component is correct.
*Prompt Content:* `Write tests for [concurrent component]. Cover cancellation via context, bounded concurrency, error aggregation, and graceful drain. Add goleak.VerifyTestMain. Ensure everything passes under -race and -shuffle=on, and explain which subtests can be parallel and why.`

## 3. HTTP Handler Tests
*Goal:* Test the full response contract.
*Prompt Content:* `Write httptest-based tests for the handlers in [file]. Assert status code, headers, and body shape for success, validation failure, and unauthorized. Use httptest.NewRecorder for handlers and httptest.NewServer where the client is under test.`

## 4. Flaky Test Diagnosis
*Goal:* Fix a race instead of hiding it.
*Prompt Content:* `This test fails intermittently under -race: [test]. Output: [paste]. Find the shared mutable state or the ordering assumption. Do not fix it by removing t.Parallel() unless the shared state is genuinely intrinsic — explain either way.`

## 5. Benchmarks
*Goal:* Measure before optimizing.
*Prompt Content:* `Write benchmarks for [function] using b.Loop() (Go [version]) and b.ReportAllocs(). Cover [input sizes]. Guard against compiler elision, and tell me how to compare runs with benchstat.`
