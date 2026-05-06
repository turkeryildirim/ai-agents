# AI Agents Workspace

This repository contains a collection of specially configured **AI Agents** designed to automate end-to-end software development processes, enhance code quality, and maintain architectural standards.

Each agent acts as a Senior Engineer specialized in its respective field and learns your project's context through a "Dual-Memory" architecture.

## 🚀 Agent Directory

| Agent | Expertise | Core Capabilities |
| :--- | :--- | :--- |
| **api-docs** | API Documentation | Automatically generates **Postman v2.1.0** collections from source code (PHP/Node.js). |
| **arch-advisor** | Architectural Consulting | Provides system design, technology stack evaluation, and scalability strategies (Advisory only). |
| **db-optimizer** | Database Optimization | Analyzes SQL and ORM (Eloquent/Prisma) queries, resolves N+1 issues, and develops indexing strategies. |
| **devops** | Infrastructure & CI/CD | Configures Docker (multi-stage), docker-compose, GitHub Actions, and Nginx/Apache setups. |
| **js-reviewer** | JS/TS Code Review | Audits modern ES6+, React, Vue, and Node.js code for security (XSS/Injection) and performance. |
| **js-tester** | JS/TS Test Writing | Creates Unit, Integration, and Component tests (Testing Library) using Jest and Vitest. |
| **php-reviewer** | PHP Code Review | Performs deep code reviews focused on PHP 8.x, PSR standards, and OWASP security. |
| **php-tester** | PHP Test Writing | Writes modern tests with PHP 8 attributes using PHPUnit and Pest, including Mockery/WP_Mock support. |
| **ui-ux** | Frontend & UI/UX | Specializes in custom SCSS architectures (BEM), accessibility (WCAG), and converting Tailwind to clean SCSS. |
| **gemini** | CLI Wrapper | Specialized bridge for Gemini CLI, handling complex codebase analysis and expert persona integration. |
| **codex** | CLI Wrapper | Specialized bridge for Gemini CLI, managing large-scale analysis and pattern detection. |
| **opencode** | CLI Wrapper | Specialized bridge for Gemini CLI, supporting multi-model sessions and complex queries. |

## 🧠 Core Principles

### 🔄 Dual-Memory Architecture (CRITICAL)
Agents base their decisions on a two-layer memory system:

1.  **Global Memory (`~/.gemini/memory/`):** Your general coding preferences, preferred libraries, and global standards.
2.  **Project Memory (`./.gemini/memory/`):** Project-specific technical debt, framework versions, custom namespace structures, and constraints.

### 🛡️ Security and Quality Standards
- **Security:** All reviewer agents automatically scan for vulnerabilities like SQLi, XSS, and CSRF based on OWASP Top 10 principles.
- **Modern Techniques:** PHP 8+ features, TypeScript strict typing, modern CSS (Grid/Flexbox), and current testing best practices are applied by default.
- **Language Awareness:** Architectural recommendations are tailored to the language's nature (e.g., PHP's statelessness vs. Node.js's event-loop).

## 🛠️ How to Use

To employ an agent, you can provide the instructions from the respective `.md` file as a system prompt to your AI model or invoke it by name through an integrated tool.

**Example Scenarios:**
- *"Why is this query slow?"* -> Triggers **db-optimizer**.
- *"Review this new PHP service class."* -> Triggers **php-reviewer**.
- *"Dockerize this project and set up a CI/CD pipeline."* -> Triggers **devops**.
- *"Convert this Figma design into accessible HTML/SCSS."* -> Triggers **ui-ux**.

---
*This workspace is a living environment that continuously learns. Remember to update the agents' memory files whenever new project rules or global preferences are established.*
