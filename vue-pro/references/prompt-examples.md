# Vue Pro — Prompt Examples

When invoking the `vue-pro` agent, include the following context for best results.

## 1. Mega Component Breakup
*Goal:* Split a component along real boundaries.
*Prompt Content:* `Component [file] is [n] lines. Propose the component boundary FIRST — a table of child components with one-sentence responsibilities and the composables to extract — then show the refactored SFCs. Keep behavior identical. Cite rule ids.`

## 2. State Placement Audit
*Goal:* Move state to the lightest level that works.
*Prompt Content:* `Review state usage in [directory]. Classify every piece as local, lifted, provided, URL, or global with justification. Flag anything in Pinia that has not crossed a feature boundary, and anything ephemeral and shareable that belongs in the URL instead.`

## 3. Reactivity Bug
*Goal:* Fix a re-render or stale-value problem.
*Prompt Content:* `This component [symptom]: [file]. Audit the reactivity — computed purity, watcher source form and flush timing, destructuring that breaks reactivity, and missing effect cleanup. Explain the mechanism causing the bug and give before/after code.`

## 4. SSR / Hydration Fix
*Goal:* Eliminate a hydration mismatch.
*Prompt Content:* `We get a hydration mismatch on [page]. Check for module-scope mutable state, shared store instances across requests, browser APIs called at import time, and non-deterministic render output. Give the fix and the SSR-safety checklist result.`

## 5. New Feature Build
*Goal:* Build a typed Vue feature end to end.
*Prompt Content:* `Build [feature] for our Vue 3 app. Vue [version], SSR [yes/no], TypeScript strict. Propose the component boundary first, then produce typed SFCs with explicit props/emits, the composables, the state classification, and accessibility handling. Do not write tests — list behaviors for vue-tester.`
