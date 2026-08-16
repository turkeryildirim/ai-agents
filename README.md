# AI Agents Workspace

This repository contains a collection of specially configured **AI Agents** designed to automate end-to-end software development processes, enhance code quality, and maintain architectural standards.

Each agent acts as a Senior Engineer specialized in its respective field, pairs with a matching skill pack from the [`ai-skills`](../ai-skills) collection, and learns your project's context through a "Dual-Memory" architecture.

**Contents:** 24 agents · 3 artifacts each (`<name>.md` system prompt, `<name>.json` machine definition, `references/prompt-examples.md`).

## 🚀 Agent Directory

### 🏛️ Architecture & Cross-Cutting

| Agent | Paired Skill | Core Capabilities |
| :--- | :--- | :--- |
| **arch-pro** | `architecture-advisor` | Scans a project, detects the stack, routes to the matching language analysis persona, and produces a severity-rated report with a prioritized action list. Advisory only — writes no implementation code. |
| **code-standards-pro** | `code-standards` | Language-agnostic design review: SOLID, KISS/YAGNI/DRY/TDA, function design, complexity metrics, and testability seams. |
| **microservices-pro** | `microservices` | Service decomposition and bounded contexts, saga/CQRS data consistency, resilience (circuit breaker, retry, bulkhead, timeout), observability, and strangler-fig migration paths. |
| **api-design-pro** | `api-design-patterns` | REST/GraphQL/gRPC contract design: resource modeling, RFC 7807 errors, pagination, versioning, security, and OpenAPI emission. |
| **api-docs** | `api-design-patterns` | Generates **Postman v2.1.0** collections and OpenAPI specs from real source — routes, validation rules, and resource transformers. |

### 🐘 PHP Ecosystem

| Agent | Paired Skill | Core Capabilities |
| :--- | :--- | :--- |
| **php-pro** | `php` | Modern PHP 8.4+ implementation and review — type safety, PSR standards, SOLID, OWASP security, and static analysis. |
| **php-tester** | `phpunit` | PHPUnit 12 and Pest — AAA structure, assertion selection, test doubles, data providers, isolation, and flake diagnosis. |
| **laravel-pro** | `laravel` | Laravel 13 — Eloquent and N+1 elimination, Action classes, form requests, queues, caching, zero-downtime migrations, and Inertia/React security. |
| **wordpress-pro** | `wordpress` | Blocks and `block.json`, plugin architecture, the hooks system, REST API, block themes, WP-CLI, and WP security. |
| **woocommerce-pro** | `woocommerce` | Products, orders, cart/checkout, payment gateways, shipping, emails, HPOS-aware CRUD, and bulk-operation performance. |

### 🌐 JavaScript & Frontend

| Agent | Paired Skill | Core Capabilities |
| :--- | :--- | :--- |
| **js-pro** | `javascript` | Modern JS/TS — async correctness, advanced type systems, Node.js backend architecture, runtime validation, and JS security. |
| **js-tester** | `javascript` | Vitest and Jest — isolation strategy, async and fake-timer patterns, MSW boundaries, fixtures, and branch coverage. |
| **vue-pro** | `vuejs` | Vue 3.5 — SFC structure, component boundaries, reactivity, composables, Pinia and Vue Router 4, SSR safety, and accessibility. |
| **vue-tester** | `vuejs-tester` | Vitest, Vue Test Utils, Testing Library, Pinia/router tests, MSW, Browser Mode, and Playwright E2E. |
| **ui-pro** | *(cross-cutting)* | Custom SCSS architecture (BEM, 7-1), design tokens, CSS Grid/Flexbox, responsive mobile-first layouts, WCAG AA accessibility, and Tailwind → SCSS conversion. |

### 📱 Compiled & Native

| Agent | Paired Skill | Core Capabilities |
| :--- | :--- | :--- |
| **golang-pro** | `golang` | Idiomatic Go — interface placement, goroutine lifecycle, context propagation, error wrapping, performance, and toolchain conventions. |
| **golang-tester** | `golang-tester` | Table-driven suites, parallelism, interface-based mocking, `httptest`, `goleak`, integration tags, benchmarks, and fuzzing. |
| **kotlin-pro** | `kotlin` | Kotlin/Android/KMP — Compose UI and Material 3, coroutines and Flow, Clean Architecture, Hilt/Koin, Room, and Gradle version catalogs. |
| **kotlin-tester** | `kotlin-tester` | JUnit/Kotest, MockK, Coroutines Test, Turbine, Espresso and the Robot pattern, Compose Testing, and Kover. |
| **swiftui-pro** | `swiftui` | SwiftUI for iOS 17–26+ — `@Observable` state, Swift 6.3+ strict concurrency, SwiftData, navigation, HIG compliance, and accessibility. |
| **swiftui-tester** | `swiftui-tester` | Swift Testing (`@Test`/`#expect`/`#require`), XCTest, in-memory SwiftData integration tests, and XCTest migration. |

### 🗄️ Data & Infrastructure

| Agent | Paired Skill | Core Capabilities |
| :--- | :--- | :--- |
| **db-pro** | `sql-expert` | Execution-plan-driven query tuning, composite index design, schema normalization, N+1 elimination across ORMs, and zero-downtime migrations. |
| **docker-pro** | `docker` | Dockerfiles and multi-stage builds, BuildKit mounts, Compose, networking and storage, security hardening, production readiness, and registry/CI publishing. |
| **devops** | `docker` + `microservices` | CI/CD pipelines, Nginx/Apache configuration, zero-downtime deployment and rollback, secret handling, process supervision, and observability wiring. |

## 🧠 Core Principles

### 🔌 Skill Pairing (CRITICAL)

Every agent is paired with one or more skills from the **ai-skills** collection. Agents follow a strict loading protocol:

1. Read the skill's `SKILL.md` first — it carries the core directives, the **category index**, and the **rule index**.
2. Load **only** the reference files the category index names for the task at hand. Never read a whole `references/` directory.
3. Pull concrete guidance from `rules/*.md`.

Several skills ship multiple language personas (`architecture-advisor` has nine, `kotlin`/`swiftui`/`vuejs` have four each). Agents load the persona matching the detected stack rather than reasoning generically.

### 📌 Rule Citation

Every finding, recommendation, and generated block cites the rule id it rests on — `[sec-sql-prepared]`, `[rx-computed-pure]`, `[coro-no-globalscope]`, `[idx-leftmost-prefix]`. A rule id is the `rules/` filename minus `.md`, so feedback is traceable back to its source.

Where no rule covers a point, agents write `[no-rule]` and state the reasoning rather than inventing an id. Where a rule conflicts with **Project Memory**, Project Memory wins and both sides are cited.

### 🔄 Dual-Memory Architecture

Agents base their decisions on a two-layer memory system, namespaced per agent:

1. **Global Memory (`~/.ai-memory/<agent>/`):** Cross-project coding preferences, preferred libraries, and standing review rules.
2. **Project Memory (`./.ai-memory/<agent>/`):** Framework versions, namespace structures, deliberately-tolerated debt, and project constraints.

Each agent has an explicit **initialization step** — the specific files it must read (`composer.json`, `tsconfig.json`, `go.mod`, `build.gradle.kts`, `phpunit.xml`, the deployment target) before it is allowed to give advice. Version floors are load-bearing: an API recommendation above the project's floor is wrong by construction.

### 🎭 Separation of Concerns (Mandatory)

**Implementation agents never write tests.** Once code is produced they name the behaviors that must be covered and hand off explicitly to the matching tester:

| Stack | Implementation | Testing |
| :--- | :--- | :--- |
| PHP / Laravel / WordPress / WooCommerce | `php-pro`, `laravel-pro`, `wordpress-pro`, `woocommerce-pro` | `php-tester` |
| JavaScript / TypeScript | `js-pro` | `js-tester` |
| Vue 3 | `vue-pro` | `vue-tester` |
| Go | `golang-pro` | `golang-tester` |
| Kotlin / Android / KMP | `kotlin-pro` | `kotlin-tester` |
| SwiftUI / iOS | `swiftui-pro` | `swiftui-tester` |

Tester agents are equally constrained in the other direction: they never modify production code. When something cannot be tested without a change, they name the change and hand it back.

### 🛡️ Security and Quality Standards

- **Security:** Every `*-pro` review agent runs an explicit OWASP-derived checklist with pass/fail evidence — not a general impression.
- **Modern techniques:** PHP 8.4+, TypeScript strict mode, Go generics, Kotlin 2.x, Swift 6.3+ concurrency, Vue 3.5, and current testing practice — always gated on the project's actual version floor.
- **Language awareness:** Recommendations respect each runtime's nature (PHP's shared-nothing request model vs. Node's event loop vs. Go's goroutine scheduler).

## 🔀 Delegation Flow

1. **Understand** → `arch-pro` scans, detects the stack, and reports. It writes no code.
2. **Design** → `api-design-pro` for contracts, `microservices-pro` for distributed topology, `db-pro` for schema and indexes.
3. **Implement** → the matching `<domain>-pro` agent.
4. **Test** → never in the same call as implementation; route to the matching tester.
5. **Ship** → `docker-pro` for container assets, `devops` for pipelines, servers, deployment, and rollback.

`code-standards-pro` runs as a second pass on any of these when a design smells wrong but the problem is not language-specific.

## 🗂️ Repository Layout

```
<agent-name>/
├── <agent-name>.md              # System prompt with YAML frontmatter (name, description, model, color)
├── <agent-name>.json            # Machine definition: { name, description, model, system_prompt }
└── references/
    └── prompt-examples.md       # 5 worked invocation examples
```

The `.md` and `.json` are two views of the same definition — the JSON `system_prompt` is the markdown body verbatim.

## 🛠️ How to Use

Provide the instructions from an agent's `.md` file as a system prompt, or invoke the agent by name through an integrated tool. `references/prompt-examples.md` shows the context each agent needs to do its best work.

**Example Scenarios:**

- *"Audit this codebase's architecture."* → **arch-pro**
- *"Why is this query slow?"* → **db-pro**
- *"Review this new PHP service class."* → **php-pro** → hands off to **php-tester**
- *"This Vue component is 700 lines."* → **vue-pro**
- *"Our image is 1.5GB."* → **docker-pro**
- *"Design the endpoints for the billing module."* → **api-design-pro** → **api-docs**
- *"Split the monolith."* → **arch-pro** → **microservices-pro**
- *"Convert this Figma design into accessible HTML/SCSS."* → **ui-pro**

---
*This workspace is a living environment that continuously learns. Remember to update the agents' memory files whenever new project rules or global preferences are established.*
