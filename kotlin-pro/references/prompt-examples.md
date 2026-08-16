# Kotlin Pro — Prompt Examples

When invoking the `kotlin-pro` agent, include the following context for best results.

## 1. Compose Screen
*Goal:* Build a screen with correct state handling.
*Prompt Content:* `Build the [screen] in Compose. minSdk [n], Kotlin [version], pattern [MVVM/MVI]. Produce a single immutable UiState, a ViewModel with injected dispatchers and lifecycle-aware Flow collection, hoisted Compose state, and Material 3 components. Include the accessibility checklist with measured contrast. Do not write tests — list behaviors for kotlin-tester.`

## 2. Coroutine Audit
*Goal:* Fix unstructured concurrency.
*Prompt Content:* `Audit coroutine usage in [directory]. Find GlobalScope, hardcoded dispatchers, swallowed CancellationException, runBlocking in production code, and non-lifecycle-aware Flow collection. Give before/after per file with line numbers and cite rule ids.`

## 3. Recomposition Performance
*Goal:* Stop a screen from recomposing constantly.
*Prompt Content:* `The [screen] recomposes on every interaction: [files]. Find the unstable parameters, missing lazy layout keys, and state read too high in the tree. Show the fix and explain which recomposition scope each change narrows.`

## 4. Architecture Review
*Goal:* Check layering against the stated pattern.
*Prompt Content:* `Review the architecture of [module]. Our stated pattern is [Clean/MVVM/MVI]. Check layer boundaries, dependency direction, UseCase and Repository responsibilities, and whether the pattern is actually followed. Report findings by file with severity.`

## 5. Gradle Modernization
*Goal:* Move to catalogs and convention plugins.
*Prompt Content:* `Modernize our Gradle setup: [current structure]. Introduce a version catalog in libs.versions.toml, extract shared config into convention plugins, and remove duplicated build logic across [n] modules. Show the resulting build files and what each module's build script shrinks to.`
