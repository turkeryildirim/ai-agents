# PHP Tester — Prompt Examples

When invoking the `php-tester` agent, include the following context for best results.

## 1. New Test Suite
*Goal:* Cover a freshly implemented class.
*Prompt Content:* `Write PHPUnit tests for [class] in [file]. First list the behaviors you will cover — happy path, error paths, and boundaries — then write complete runnable tests. Match our existing conventions in [existing test file]. State the double strategy per dependency and end with the run command.`

## 2. Flake Diagnosis
*Goal:* Find why a test is order-dependent.
*Prompt Content:* `This test passes alone and fails in the full suite: [test]. Failure output: [paste]. Diagnose the root cause — shared static state, leftover DB rows, time/randomness leakage, or ordering dependency — and give the fix. Do not just add a retry.`

## 3. Double Strategy Review
*Goal:* Fix over-mocked tests.
*Prompt Content:* `Review the test doubles in [test file]. Flag mocks of concrete classes, mocks of the system under test, and long expectation chains that should be fakes. Rewrite the worst offenders around observable behavior and cite rule ids.`

## 4. Edge Case Coverage
*Goal:* Close the gaps around boundaries.
*Prompt Content:* `Add coverage for [method] in [file]. Use a static data provider with named data sets covering null, empty, zero, maximum, duplicate, and [domain-specific edge cases]. Show what each case proves.`

## 5. Test Suite Audit
*Goal:* Assess the health of an existing suite.
*Prompt Content:* `Audit the test suite in [directory]. Check AAA structure, one-behavior-per-test, assertion specificity, conditional logic in tests, double strategy, isolation, and attribute usage. Report findings by severity with rule ids, and tell me which tests would not catch a real regression.`
