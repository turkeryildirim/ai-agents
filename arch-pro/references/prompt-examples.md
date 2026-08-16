# Arch Pro — Prompt Examples

When invoking the `arch-pro` agent, include the following context for best results.

## 1. Full Architecture Audit
*Goal:* Onboard to an unfamiliar codebase with a rated report.
*Prompt Content:* `Audit this repository's architecture. Scan config files and the directory tree first, name the detected stack and version, then produce a severity-rated report with Strengths, Findings, and a prioritized action list. Do not write implementation code.`

## 2. Pattern Decision
*Goal:* Choose between competing structural approaches.
*Prompt Content:* `We are considering moving [module] from [current pattern] to [target pattern]. Current stack: [stack]. Team size: [n]. Traffic: [scale]. Give me Options with Pros/Cons, a Language & Ecosystem Fit section, and a definitive verdict.`

## 3. Coupling Hotspot Review
*Goal:* Find the tightest coupling before a refactor.
*Prompt Content:* `Analyze coupling in [directory]. Identify God classes, framework-internal coupling, static/global state, and leaked domain logic. Rate each finding CRITICAL/HIGH/MEDIUM/LOW and cite the rule id. Give me a migration path, not a rewrite.`

## 4. Scalability Assessment
*Goal:* Pressure-test the design against a growth target.
*Prompt Content:* `Our current setup is [stack + topology] handling [current load]. We expect [target load] in [timeframe]. Where does this architecture break first? Rate each bottleneck and give the smallest change that removes it.`

## 5. Technology Fit Evaluation
*Goal:* Decide whether the standard stack fits a new workload.
*Prompt Content:* `We need to build [workload description]. Our standard stack is [stack]. Evaluate whether it fits, considering the runtime's concurrency model and CPU/IO profile. If it does not fit, recommend an alternative and explain the integration cost.`
