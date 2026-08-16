# JS Pro — Prompt Examples

When invoking the `js-pro` agent, include the following context for best results.

## 1. Post-Implementation Review
*Goal:* Review a diff before it ships.
*Prompt Content:* `Review the TypeScript I just wrote in [files]. Focus on the diff. Check async correctness (floating promises, sequential awaits, cancellation), type safety at boundaries, error handling, and the security checklist. Cite rule ids, give fix code with file:line, and end with the validation command.`

## 2. Async Bug Hunt
*Goal:* Find the race in a promise chain.
*Prompt Content:* `This code sometimes [symptom]: [files]. Trace every async path, find unawaited promises, missing cancellation, and ordering assumptions that the event loop does not guarantee. Explain the exact interleaving that produces the bug and give the fix.`

## 3. Type Tightening
*Goal:* Replace `any` with real modeling.
*Prompt Content:* `Tighten the types in [files]. Replace `any` and unjustified `as` with discriminated unions, generics with real constraints, and type guards. Derive types from the runtime schemas instead of duplicating them. Our tsconfig strictness is [flags]. Show before/after.`

## 4. Backend Service Build
*Goal:* Write a layered Node service.
*Prompt Content:* `Build a [purpose] service using [Fastify/Express/NestJS]. Include layered structure, dependency injection, Zod validation at the boundary, a custom error hierarchy with centralized handling, structured logging, and graceful shutdown. Do not write tests — list the behaviors for js-tester.`

## 5. Security Audit
*Goal:* Check the JS/TS attack surface.
*Prompt Content:* `Security-audit [module]. Check input validation at every boundary, injection surfaces, error responses leaking internals, secrets in code or logs, prototype pollution, and dependency risk. Give pass/fail with code evidence and the fix for each failure.`
