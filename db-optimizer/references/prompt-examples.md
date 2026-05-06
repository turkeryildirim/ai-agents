# DB Optimizer — Prompt Examples

When invoking the `db-optimizer` agent, include the following context for best results.

## 1. Slow Query Optimization
*Goal:* Optimize a specific slow query.
*Prompt Content:* `This Eloquent query takes 3+ seconds on our [table name] table (currently [X] rows): [paste query]. The table has these existing indexes: [list indexes]. Identify the bottleneck, suggest the optimized ORM and raw SQL version, and provide the required CREATE INDEX statement.`

## 2. N+1 Detection and Fix
*Goal:* Resolve N+1 query problems in ORM code.
*Prompt Content:* `Review [file path] for N+1 query problems. The [OrderController / ProductListService] loads [orders with items / users with roles]. We suspect each loop iteration triggers a new query. Identify the N+1 locations and provide the correct eager loading fix using [Eloquent with() / Prisma include].`

## 3. Schema & Index Audit
*Goal:* Audit a database schema for missing indexes.
*Prompt Content:* `Analyze this MySQL schema [paste CREATE TABLE statements or migration files]. The most common query patterns are: [WHERE user_id = ? AND status = ?, ORDER BY created_at DESC, GROUP BY category_id]. Suggest composite indexes using the left-most prefix rule. Explain which queries each index serves.`

## 4. NoSQL Schema Design
*Goal:* Design an optimal NoSQL document structure.
*Prompt Content:* `We're designing a MongoDB collection for [orders / activity logs / product catalog]. Access patterns: [list the 3 most common read queries]. Current normalized approach causes [X] lookups per request. Suggest an embedded document structure that optimizes for reads, with trade-offs for write complexity.`

## 5. Migration Performance
*Goal:* Plan a large table migration safely.
*Prompt Content:* `We need to add a [NOT NULL column / composite index / rename column] to the [table name] table which has [X million] rows in production. Suggest a safe migration strategy that minimizes downtime: batched updates, pt-online-schema-change, shadow table approach, or zero-downtime migration pattern.`
