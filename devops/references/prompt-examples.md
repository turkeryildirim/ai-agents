# DevOps — Prompt Examples

When invoking the `devops` agent, include the following context for best results.

## 1. New Docker Setup
*Goal:* Create a complete Docker environment for a project.
*Prompt Content:* `Create a production-ready Docker setup for our [Laravel/Next.js] application. Stack: [PHP 8.3 + Nginx + MySQL 8 + Redis / Node 20 + Nginx]. Requirements: [list specific PHP extensions needed, env variables, exposed ports]. Use multi-stage builds where applicable. Non-root user required.`

## 2. Docker Image Size Optimization
*Goal:* Reduce an oversized Docker image.
*Prompt Content:* `Our [Next.js / Laravel] Docker image is [X]GB. Current Dockerfile: [paste Dockerfile]. Analyze the layers, identify what's inflating the size (devDependencies, source files, unnecessary packages), and provide an optimized multi-stage Dockerfile targeting under [target size].`

## 3. CI/CD Pipeline
*Goal:* Write a GitHub Actions or GitLab CI pipeline.
*Prompt Content:* `Write a [GitHub Actions / GitLab CI] pipeline for our [Laravel/Node.js] project. Stages needed: [lint, test, build Docker image, push to registry, deploy to VPS via SSH]. Caching: [npm/composer dependencies]. Environment: [staging on push to develop, production on push to main].`

## 4. Nginx Configuration
*Goal:* Configure Nginx for a specific application.
*Prompt Content:* `Write an Nginx server block configuration for [Laravel/Next.js]. Requirements: [HTTPS with SSL cert paths, gzip compression, static asset caching headers, rate limiting on /api routes, reverse proxy to PHP-FPM on port 9000 / Node on port 3000, correct try_files for SPA routing].`

## 5. Docker Compose for Local Dev
*Goal:* Create a local development docker-compose.yml.
*Prompt Content:* `Create a docker-compose.yml for local development. Services: [app (Laravel/Node), nginx, mysql:8, redis, mailpit for email testing]. Requirements: volume mounts for hot reload, .env file binding, healthchecks, service dependency order. Expose: [app on 8080, mysql on 3306, mailpit UI on 8025].`
