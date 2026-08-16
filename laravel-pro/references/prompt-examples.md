# Laravel Pro — Prompt Examples

When invoking the `laravel-pro` agent, include the following context for best results.

## 1. New Feature Module
*Goal:* Build a feature the idiomatic Laravel way.
*Prompt Content:* `Build [feature] in our Laravel app. Requirements: [list]. Match our existing pattern in [directory]. Produce migrations with index justification, models with relationships and casts, Form Requests, an Action class, an API Resource, and queued jobs for side effects. Do not write tests — list the behaviors for php-tester.`

## 2. N+1 Elimination
*Goal:* Cut query count on a hot page.
*Prompt Content:* `The [route/page] fires [n] queries. Code: [files]. Find every N+1, fix it with eager loading, withCount, or subquery selects, and show the before/after query count per endpoint. Tell me which indexes the new queries need.`

## 3. Fat Controller Refactor
*Goal:* Extract logic without breaking behavior.
*Prompt Content:* `Controller [file] is [n] lines. Refactor it into Form Requests plus Action classes matching our existing pattern in [directory]. Keep behavior identical. Show before/after and cite rule ids.`

## 4. Zero-Downtime Migration
*Goal:* Change a large table safely.
*Prompt Content:* `We need to [schema change] on table [name] with [row count] rows in [MySQL 8 / PostgreSQL 17]. Write the zero-downtime migration path, state the lock behavior of each step, give the rollback path, and note any application-side dual-write needed during the transition.`

## 5. Laravel Security Review
*Goal:* Audit a module against the Laravel security rules.
*Prompt Content:* `Security-review [module]. Walk the checklist: mass assignment, broken access control, injection, CSRF, XSS through Inertia/React props, sensitive data in Inertia props, rate limiting, and cryptographic failures. Give pass/fail with code evidence and the fix for each failure.`
