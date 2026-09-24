# Applying Engineering Principles

An Agent Skill that applies a compact set of production-engineering principles as **engineering policy**, while remaining orthogonal to process frameworks such as [Superpowers](https://github.com/obra/superpowers).

## Purpose

This skill defines **what qualities an acceptable engineering result should preserve**:

- architecture and domain boundaries
- module cohesion and dependency direction
- protocol/domain/persistence/view-model separation
- security, authorization, and tenant isolation
- concurrency and failure semantics
- complete frontend state handling
- dependency discipline
- maintainability and durable engineering context
- observability, diagnosability, compatibility, and rollback

It intentionally does **not** prescribe a development workflow.

When Superpowers or another process skill is active:

- **The process skill owns how the work proceeds**: discovery, brainstorming, planning, TDD, debugging, execution, review, worktrees, commits, and completion verification.
- **This skill owns engineering policy**: the architectural and operational properties the resulting design and implementation must preserve.

## Structure

```text
.
├── SKILL.md
├── references/
│   └── core-engineering-principles.md
├── CLAUDE.md-snippet.md
├── INSTALL.md
└── LICENSE
```

`SKILL.md` is intentionally small. The complete ten principles live in `references/core-engineering-principles.md` and are required reading when the skill is invoked.

## Installation

Claude Code:

```text
~/.claude/skills/applying-engineering-principles/
```

Cross-runtime Agent Skills alias:

```text
~/.agents/skills/applying-engineering-principles/
```

Copy the whole repository contents so the reference file remains available beside `SKILL.md`.

To make the policy mandatory for relevant engineering work, merge `CLAUDE.md-snippet.md` into the repository's root `CLAUDE.md`, or adapt the same rule to the top-level agent instruction file used by your runtime.

## Design relationship with Superpowers

This skill is designed to compose with Superpowers rather than compete with it.

```text
Superpowers
  └─ How should the work proceed?
     brainstorming
     planning
     TDD
     debugging
     review
     verification
     ...

applying-engineering-principles
  └─ What qualities must the result preserve?
     architecture
     boundaries
     isolation/security
     concurrency/failure
     UX completeness
     dependency discipline
     maintainability
     observability
     compatibility
     rollback
```

## Origin and attribution

The ten core principles are an English adaptation of the **核心工程原则 / Core Engineering Principles** section of [HuangPuStar/FenixAgent](https://github.com/HuangPuStar/FenixAgent/blob/main/CLAUDE.md), which is distributed under the Apache License 2.0.

This repository modifies that source material by translating it into English and restructuring it for use as a standalone Agent Skill. The Skill wrapper, Superpowers composition guidance, trigger metadata, and installation guidance are specific to this repository.

## License

Apache License 2.0. See [LICENSE](LICENSE).
