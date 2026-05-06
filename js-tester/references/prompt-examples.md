# JS Tester — Prompt Examples

When invoking the `js-tester` agent, include the following context for best results.

## 1. React Component Tests
*Goal:* Write tests for a new React component.
*Prompt Content:* `Write tests for the newly created [ComponentName] in [file path]. It [fetches user data / handles form submission / renders a list]. The project uses Vitest + React Testing Library. Test the happy path, loading state, error state, and user interaction.`

## 2. Custom Hook Tests
*Goal:* Test a new React hook.
*Prompt Content:* `Write unit tests for the [useHookName] hook in [file path]. It manages [cart state / authentication / pagination]. Use renderHook from @testing-library/react. Cover: initial state, state updates, cleanup on unmount, and edge cases with empty data.`

## 3. Next.js API Route Tests
*Goal:* Test a new API route handler.
*Prompt Content:* `Write integration tests for the POST /api/orders route in [file path]. It validates input with Zod, creates a DB record, and returns 201. Use node-mocks-http or supertest. Test: valid payload success, validation failure (422), and DB error handling (500).`

## 4. Utility Function Tests
*Goal:* Test pure utility functions.
*Prompt Content:* `Write unit tests for the utility functions in [file path]. Functions: [list function names]. Use data-driven tests (test.each / describe.each) for multiple input/output cases. Cover boundary values and type edge cases.`

## 5. Vue Composable Tests
*Goal:* Test a Vue 3 composable.
*Prompt Content:* `Write tests for the [useComposableName] composable in [file path]. The project uses Vitest + Vue Test Utils. Test: reactive state changes, computed values, async data fetching (mock the API call), and cleanup. Mock the Pinia store using createTestingPinia.`
