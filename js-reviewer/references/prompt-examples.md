# JS Reviewer — Prompt Examples

When invoking the `js-reviewer` agent, include the following context for best results.

## 1. Post-Feature Review
*Goal:* Review code written for a new feature.
*Prompt Content:* `Review the recently written code in [file paths]. This is a [React component / Node.js service / Vue composable] that [brief description of what it does]. Pay special attention to [TypeScript types / async error handling / security]. The project uses [framework + version] with [state management library].`

## 2. Security-Focused Review
*Goal:* Verify a security fix or audit for vulnerabilities.
*Prompt Content:* `Perform a security-focused review of [file path]. We just fixed an XSS vulnerability in the comments component. Verify the fix is correct, check for any remaining attack vectors, and ensure input is properly sanitized before rendering.`

## 3. Refactor Quality Check
*Goal:* Ensure a refactor didn't introduce regressions.
*Prompt Content:* `Review the refactored code in [file path]. We migrated from Vue Options API to Composition API. Check for: reactivity loss from props destructuring, missing onUnmounted cleanups, and proper ref vs reactive usage.`

## 4. Performance Review
*Goal:* Identify re-render or memory issues.
*Prompt Content:* `Review [file path] for performance issues. Focus on: unnecessary re-renders (missing useMemo/useCallback), useEffect dependency arrays, and memory leaks from missing cleanup functions. The component renders inside a large list.`

## 5. TypeScript Strictness Audit
*Goal:* Harden TypeScript types.
*Prompt Content:* `Audit [file path] for TypeScript type safety. Flag all uses of 'any', unsafe type assertions (as SomeType), and missing return type annotations on exported functions. Suggest proper generic types or discriminated unions where applicable.`
