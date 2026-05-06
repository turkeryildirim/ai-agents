# Arch Advisor — Prompt Examples

When invoking the `arch-advisor` agent, include the following context for best results.

## 1. New Feature Architecture
*Goal:* Get architectural guidance before implementing a feature.
*Prompt Content:* `We need to add [real-time notifications / file export / background processing] to our [Laravel/Node.js] application. Current stack: [tech stack]. Expected scale: [concurrent users / request volume]. Evaluate the best architectural approach and provide trade-offs.`

## 2. Folder / Module Structure Review
*Goal:* Evaluate if a folder structure is becoming too coupled or bloated.
*Prompt Content:* `Review the current structure of our [services / modules / domain] folder at [path]. We have [X] classes and suspect tight coupling between [module A] and [module B]. Should we move toward a modular monolith or domain-driven structure? Provide a migration path.`

## 3. Technology Stack Decision
*Goal:* Choose between technology options.
*Prompt Content:* `We are building a [new microservice / background worker / real-time feature]. Current team expertise: [PHP/Laravel]. Should we use [Option A] vs [Option B]? Consider: team ramp-up time, operational complexity, and fit with our existing [PostgreSQL / Redis] infrastructure.`

## 4. Scalability Analysis
*Goal:* Identify bottlenecks before scaling.
*Prompt Content:* `Review the architecture of [module/feature] in our codebase. We expect traffic to grow from [X] to [Y] requests/day. Identify likely bottlenecks (DB, stateful services, synchronous calls), and recommend patterns to handle the scale without a full rewrite.`

## 5. Monolith to Service Extraction
*Goal:* Plan extracting a feature into a separate service.
*Prompt Content:* `We want to extract [billing / notifications / search] from our monolith into a standalone service. Analyze the current coupling in [file/folder paths]. Define the service boundary, the communication pattern (REST / Events / Queue), and the data ownership strategy.`
