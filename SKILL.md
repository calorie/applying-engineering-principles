---
name: applying-engineering-principles
description: Use when production engineering work can affect architecture, domain boundaries, module responsibilities, data flow, security or tenant isolation, concurrency or failure behavior, frontend state handling, dependency choices, maintainability, observability, compatibility, or rollback characteristics.
---

# Applying Engineering Principles

## Role

This is an **engineering policy skill**, not a development-process skill. It defines the qualities and invariants a sound production design must preserve.

When a process skill such as Superpowers is active, that skill owns sequencing, exploration, approvals, planning, TDD, debugging, review, worktrees, and completion verification. Apply this skill as a design and implementation constraint **inside** that process; do not duplicate or replace the process.

Read `references/core-engineering-principles.md` in full whenever this skill is invoked. Do not substitute a remembered summary for the reference.

More specific project-local rules take precedence when they intentionally specialize these principles. If documentation and code disagree, verify the intended design rather than silently treating either as authoritative.

## Engineering Lens

Use the principles to evaluate substantive engineering decisions across these dimensions:

| Dimension | Questions to preserve |
|---|---|
| Architecture & domain | Are responsibilities, boundaries, dependency direction, and data flow explicit? Is short-term convenience distorting the design? |
| Boundaries & isolation | Are protocol, domain, persistence, and view models separated? Are authentication, authorization, tenant isolation, and trust boundaries explicit? |
| Concurrency & failure | Are races, idempotency, transactions, timeouts, cancellation, retry, backpressure, and cleanup handled deliberately where relevant? |
| Product & module quality | Are modules cohesive with narrow interfaces? Are frontend loading, empty, error, retry, feedback, and accessibility states complete? |
| Evolution & operations | Are reuse and dependencies justified? Is context preserved for maintainers? Is the change testable, observable, diagnosable, reversible, and compatible where contractually required? |

## Non-Goals

This skill does **not** choose a workflow, require an approval sequence, prescribe TDD mechanics, manage worktrees or commits, define debugging procedure, or specify verification commands. Use the applicable process skill for those concerns.

## Red Flags

Re-evaluate the engineering decision when you see convenience-driven architecture, a one-use speculative abstraction, model leakage across boundaries, implicit tenant or authorization rules, swallowed errors, unbounded retries, hidden shared state, unchecked dependencies, context-free `TODO`s, incomplete frontend states, unobservable behavior, missing rollback thinking, or internal compatibility code retained only to avoid deletion.
