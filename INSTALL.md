# Installation

Install the whole directory so `SKILL.md` and `references/core-engineering-principles.md` remain together.

Claude Code:

```text
~/.claude/skills/applying-engineering-principles/
```

Cross-runtime Agent Skills alias:

```text
~/.agents/skills/applying-engineering-principles/
```

## With Superpowers

This skill is intentionally orthogonal to Superpowers:

- **Superpowers owns process:** discovery, brainstorming, planning, TDD, debugging, execution, review, worktrees, and verification.
- **This skill owns engineering policy:** architecture, boundaries, isolation, concurrency/failure semantics, UX completeness, dependency discipline, maintainability, observability, compatibility, and rollback characteristics.

Do not chain a second workflow from this skill. Superpowers determines *how the work proceeds*; this skill constrains *what an acceptable engineering result preserves*.

To make the policy mandatory in a repository, merge `CLAUDE.md-snippet.md` into the root `CLAUDE.md` (or the equivalent top-level agent instruction file for your runtime).
