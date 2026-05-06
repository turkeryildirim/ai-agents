# PHP Reviewer — Prompt Examples

When invoking the `php-reviewer` agent, include the following context for best results.

## 1. Post-Feature Review
*Goal:* Review a newly written PHP class or module.
*Prompt Content:* `Review the recently written code in [file path]. This is a [Service / Controller / Repository] class for [brief description]. The project is [Laravel/WordPress/Symfony]. Check for SOLID adherence, proper type declarations, and security issues.`

## 2. Security Audit
*Goal:* Verify SQL injection or XSS fixes.
*Prompt Content:* `Perform a security audit of [file path]. We recently modified database query logic. Verify that all queries use prepared statements or the ORM correctly. Project uses [Laravel Eloquent / $wpdb / PDO].`

## 3. WordPress-Specific Review
*Goal:* Review hooks, sanitization, and nonce usage.
*Prompt Content:* `Review [file path] for WordPress best practices. Check: nonce verification on all AJAX handlers, proper use of sanitize_* and esc_* functions, correct current_user_can() capability checks, and hook priority/timing issues.`

## 4. Laravel API Review
*Goal:* Review a new API controller.
*Prompt Content:* `Review [file path] — a new Laravel API controller. Check: FormRequest validation completeness, proper use of Policies/Gates for authorization, Eloquent query optimization (no N+1), and correct HTTP status codes in responses.`

## 5. Refactor Architecture Review
*Goal:* Evaluate a refactored class for SOLID compliance.
*Prompt Content:* `Review the refactored [file path]. We extracted business logic from a Controller into a Service class. Verify Single Responsibility is maintained, dependencies are injected via constructor, and the Service is not aware of HTTP layer concerns.`
