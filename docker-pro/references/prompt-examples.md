# Docker Pro — Prompt Examples

When invoking the `docker-pro` agent, include the following context for best results.

## 1. Containerize a Service
*Goal:* Produce the minimum complete asset set.
*Prompt Content:* `Containerize this [language/framework] service. Runtime [version], listens on [port], needs [dependencies], persists [data]. Target is [production]. Produce a cache-efficient multi-stage Dockerfile with a non-root user and a health check, a language-aware .dockerignore, and Compose plus .env.example only if multi-container orchestration is genuinely needed. Verify with real commands.`

## 2. Image Size Reduction
*Goal:* Cut a bloated image down.
*Prompt Content:* `Our image is [size]: [paste Dockerfile]. Restructure it as a multi-stage build, choose a minimal runtime base, fix the layer ordering for cache efficiency, and add the missing .dockerignore. Show the stage-by-stage size table and what specifically was removed from the runtime image.`

## 3. Security Review
*Goal:* Audit containers before an audit audits you.
*Prompt Content:* `Security-review [Dockerfile(s) and compose.yaml]. Run the full hardening checklist: non-root user, secrets in layers (check docker history reasoning), base image pinning and trust, dropped capabilities, read-only root filesystem, and scanner coverage. Report findings by severity with file:line, risk, and fix — then list the checks that already pass.`

## 4. Container Debugging
*Goal:* Diagnose a failing container.
*Prompt Content:* `Container [name] [symptom — exits with code X / can't reach service Y / health check fails]. Compose file: [paste]. Give me the diagnostic command sequence, tell me what output to look for at each step, then the likely cause and the smallest corrective change.`

## 5. CI Publishing Pipeline
*Goal:* Publish images reproducibly.
*Prompt Content:* `Set up image publishing to [Docker Hub/GHCR] for [service]. Include multi-platform builds for [platforms], a tagging strategy covering semver and git SHA, buildx cache backends for CI speed, vulnerability scanning as a gate, and build attestations. Tell me which secrets the pipeline needs and how they are mounted.`
