# PHP Tester — Prompt Examples

When invoking the `php-tester` agent, include the following context for best results.

## 1. Laravel Service Unit Tests
*Goal:* Write unit tests for a new service class.
*Prompt Content:* `Write unit tests for [ServiceClass] in [file path]. It handles [payment processing / currency conversion / email sending]. Mock external dependencies (Stripe SDK, Mailer). Use Pest with the Expectations API. Cover: success path, validation failure, and exception handling.`

## 2. Laravel Feature Tests (HTTP)
*Goal:* Write HTTP feature tests for a new API endpoint.
*Prompt Content:* `Write feature tests for the POST /api/[resource] endpoint in [Controller file]. Use RefreshDatabase. Test: authenticated success (201), unauthenticated (401), validation errors (422), and forbidden access (403). Use actingAs() for auth.`

## 3. WordPress Unit Tests
*Goal:* Test a WordPress plugin class.
*Prompt Content:* `Write unit tests for [ClassName] in [file path]. It's a WordPress plugin class that [registers hooks / processes AJAX / queries $wpdb]. Use WP_Mock to mock WordPress functions. Test: hook registration, sanitization logic, and early returns on capability checks.`

## 4. PHPUnit Data Provider Tests
*Goal:* Test multiple input variations cleanly.
*Prompt Content:* `Write PHPUnit tests for [ClassName::methodName] in [file path]. This method [converts currencies / validates phone numbers / calculates discounts]. Use #[DataProvider] with a dataset covering: valid inputs, boundary values, zero/null edge cases, and invalid format inputs.`

## 5. Repository / Eloquent Tests
*Goal:* Test database query logic.
*Prompt Content:* `Write tests for [RepositoryClass] in [file path]. It queries the [orders / users / products] table with Eloquent. Use RefreshDatabase with model factories. Test: correct records returned, scopes applied, relationships eager-loaded, and empty result handling.`
