# PHP Pro — Prompt Examples

When invoking the `php-pro` agent, include the following context for best results.

## 1. Post-Implementation Review
*Goal:* Review freshly written code before it ships.
*Prompt Content:* `Review the PHP code I just wrote in [files]. Focus on the diff, not the whole codebase. Check type safety, SOLID, the OWASP checklist, and performance. Cite rule ids, give concrete fix code with file:line, and end with the validation command.`

## 2. Security Audit
*Goal:* Harden a module against the OWASP checklist.
*Prompt Content:* `Security-audit [file/module]. Walk the full checklist: SQL injection, XSS, CSRF, authorization, input validation, mass assignment, deserialization, secrets, and file uploads. For each, state pass/fail with evidence from the code and give the fix. This is a [Laravel/WordPress/plain PHP] project.`

## 3. Legacy Modernization
*Goal:* Bring old PHP up to the current version floor.
*Prompt Content:* `Modernize [file] to PHP [version from composer.json]. Apply strict types, constructor promotion, readonly, enums instead of class constants, match instead of switch, and first-class callables where they help. Do not use features above our version floor. Show before/after and cite rule ids.`

## 4. New Service Class
*Goal:* Write a typed, testable service from scratch.
*Prompt Content:* `Write a [purpose] service class in namespace [namespace]. Requirements: [list]. Use declare(strict_types=1), constructor promotion, typed properties, a specific exception hierarchy, and dependency injection. Do not write tests — list the behaviors php-tester should cover.`

## 5. Static Analysis Cleanup
*Goal:* Fix a class of PHPStan errors, not just instances.
*Prompt Content:* `PHPStan at level [n] reports these errors: [paste]. Group them by root cause, fix the underlying type-modeling problem rather than adding ignores, and tell me which (if any) genuinely belong in the baseline and why.`
