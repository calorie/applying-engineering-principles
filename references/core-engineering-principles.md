# Core Engineering Principles

> **Modified work notice:** This file is an English translation and standalone-skill adaptation of the **核心工程原则 / Core Engineering Principles** section in [HuangPuStar/FenixAgent `CLAUDE.md`](https://github.com/HuangPuStar/FenixAgent/blob/main/CLAUDE.md). The upstream project is licensed under Apache License 2.0. The wording here has been translated and edited for clarity and independent reuse.

1. **Architecture and domain first.** Aim for the ideal architecture at design time. Make the business goal, domain boundaries, module responsibilities, dependency direction, and data flow explicit, and establish a design that follows the domain, supports long-term maintenance, and can evolve sustainably before coding. Do not sacrifice the overall design for short-term implementation convenience. Keep the design complete and the implementation restrained: avoid speculative abstractions. Introduce an abstraction only when a second real use case proves it necessary; implement a single real scenario directly.

2. **Pursue elegant code modules.** Modules should have high cohesion and low coupling. Encapsulate internal complexity behind small, stable interfaces so responsibilities, naming, dependencies, and extension paths remain clear and natural. Split code by single responsibility. No individual file should exceed 500 lines; when a file approaches that limit, revisit module boundaries before adding more code.

3. **Keep boundaries and data flow clear.** Protocol models, domain models, persistence models, and view models must not leak into one another. Validate data and perform independent conversion at boundaries. Avoid mutable state shared across layers.

4. **Enable security and isolation by default.** Design every feature for multi-tenant and multi-user scenarios. Make authentication, authorization, and data-isolation boundaries explicit. Follow least privilege. Treat all external input as untrusted. Never place sensitive information in source code, logs, or responses.

5. **Design for concurrency and failure.** Backend design should proactively account for idempotency, race conditions, transaction boundaries, timeouts, cancellation, retries, backpressure, and resource cleanup. Never mask problems with unbounded retries, swallowed errors, or implicit shared state.

6. **Ensure a complete frontend experience.** Control rendering cost, asynchronous state, and concurrent requests while keeping UI structure clear. User flows must cover loading, empty, error, retry, feedback, and accessibility states.

7. **Reuse stable business semantics.** Prefer existing modules and capabilities, but do not abstract merely because code has a similar shape. When duplication is intentional, document why the paths need to evolve independently or why abstraction is deferred. Before adding a dependency, check whether the project's existing dependencies—including the root `package.json` and `packages/` workspaces—already satisfy the requirement. Do not assume an existing library lacks a capability: inspect its documentation and type definitions first. When a new dependency is genuinely required, prefer a mature, well-maintained library instead of reimplementing generic functionality.

8. **Preserve context for future maintainers.** Code, comments, tests, and architecture documents are collaboration media across time. For non-obvious design decisions, compatibility constraints, known defects, and temporary workarounds, record the reason, affected scope, potential risk, and removal conditions. Link technical debt to a trackable task. Record important, long-lived architectural decisions in ADRs. Do not leave a context-free `TODO`.

9. **Make changes verifiable, observable, and reversible.** Every change should have testable behavior, observable runtime state, diagnosable failures, and a considered path for backward compatibility and rollback. Errors and logs must preserve diagnostic context without exposing sensitive information.

10. **Prefer deletion over internal compatibility.** When refactoring internal paths, delete obsolete implementations directly instead of adding compatibility layers, deprecated shims, or dual-write logic. Evaluate compatibility for external contracts—such as stable `/api/*` interfaces and database migrations—separately as a contractual obligation, not as accommodation for obsolete internal code.
