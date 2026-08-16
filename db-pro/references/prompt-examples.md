# DB Pro — Prompt Examples

When invoking the `db-pro` agent, include the following context for best results.

## 1. Slow Query Tuning
*Goal:* Fix a query with plan-driven reasoning.
*Prompt Content:* `This query takes [duration]: [paste query or ORM code]. Engine [PostgreSQL 17/MySQL 8.4], table [name] has [n] rows, existing indexes: [list]. Analyze what EXPLAIN ANALYZE would show, identify the root cause, rewrite the query, and design the index with column-order justification and write-cost trade-off.`

## 2. N+1 Elimination
*Goal:* Cut query count in ORM code.
*Prompt Content:* `Find and fix the N+1 problems in [files]. ORM is [Eloquent/Prisma/GORM]. Show the ORM-level fix and the raw SQL it produces, report the before/after query count per endpoint, and tell me which indexes the new query shape needs.`

## 3. Schema Design
*Goal:* Design a schema that will not need rescuing.
*Prompt Content:* `Design the schema for [module]. Requirements: [list]. Engine [name]. Normalize appropriately, use the narrowest correct types, enforce constraints in the database, store timestamps in UTC, and specify the indexes with the query shapes each serves. Note anywhere you deliberately denormalized and why.`

## 4. Zero-Downtime Migration
*Goal:* Change a large table safely.
*Prompt Content:* `We need to [schema change] on [table] with [n] rows in [engine]. Write the multi-step zero-downtime migration: each step's lock behavior, concurrent index creation if supported, the backfill strategy with batch size, the application-side dual-write window, and the rollback path for each step.`

## 5. Index Audit
*Goal:* Find missing and redundant indexes.
*Prompt Content:* `Audit the indexes on [tables]. Given these query patterns: [list], identify missing indexes, redundant indexes (already covered by an existing composite prefix), and unused ones. For each recommendation state the query it serves, the leftmost-prefix implication, and the write cost.`
