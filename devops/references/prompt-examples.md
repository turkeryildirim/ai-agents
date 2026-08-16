# DevOps — Prompt Examples

When invoking the `devops` agent, include the following context for best results.

## 1. CI/CD Pipeline
*Goal:* Build a staged pipeline that is fast and safe.
*Prompt Content:* `Write a [GitHub Actions/GitLab CI] pipeline for our [language/framework] app. Stages: lint, test, build, deploy to [target]. Cache dependencies keyed on the lockfile, run [test suites], gate deployment on all checks, and inject secrets from [source]. Show the expected duration per stage and what each cache key covers.`

## 2. Reverse Proxy Configuration
*Goal:* Configure the server in front of the app.
*Prompt Content:* `Configure Nginx as a reverse proxy for [services on ports]. Include TLS termination with [cert source], HTTP/2, compression, static asset caching, rate limiting on [endpoints], and explicit timeouts at every hop matched to the app's own timeout. Explain why each timeout value was chosen.`

## 3. Zero-Downtime Deployment
*Goal:* Eliminate deploy-time errors.
*Prompt Content:* `Our deploys cause [duration] of 502s. Current process: [describe]. Design a zero-downtime deployment: connection draining, health-gated cutover, migration ordering relative to code, and queue worker restart. Give the full rollback procedure with preconditions and flag anything irreversible.`

## 4. Environment Parameterization
*Goal:* Make one artifact run everywhere.
*Prompt Content:* `Set up [staging] to mirror [production] for [app]. Externalize every environment-specific value, list the full environment variable inventory with source and per-environment values, and ensure the same build artifact runs in both. Tell me what currently prevents that.`

## 5. Observability Wiring
*Goal:* Get signal instead of noise.
*Prompt Content:* `Wire observability for [app] on [platform]. Structured log shipping to [destination], metrics for error rate/latency/saturation, uptime checks, and alerts. Define alert thresholds on user-visible symptoms rather than internal causes, and tell me explicitly which alerts should page a human at 3am and which should not.`
