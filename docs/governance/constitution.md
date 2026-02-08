<!--
Sync Impact Report:
- Version change: 1.0.0 -> 1.1.0
- Principles: Unchanged (5 core principles)
- Additions:
  1. Pre-commit & CI Standards (Quality Gates)
  2. PR Hygiene Policy (Development Workflow)
  3. Architecture Documentation (Quality Gates)
  4. Session Memory requirement (Agent Context)
- Validated against: 20 active conversations, 37 open PRs, Week 1 Sprint completed
-->
# Vindicta Platform Constitution (Ratified v1.1.0)

## Core Principles

1. **MCP-First Mandate**: Always check for available MCP servers (GitHub, Firebase, etc.) before using CLI tools or manual scripts. **Agents MUST use MCP tools for all File Explorer (filesystem) and GitHub operations** to ensure alignment with platform state. Manual CLI usage is a fallback only when MCP capabilities are exhausted.
2. **Spec-Driven Development (SDD)**: Every feature implementation MUST start with an SDD bundle in `.specify/specs/[ID]-[name]/`. Implementation cannot proceed until the SDD bundle is approved and merged into the main branch.
3. **Economic Prime Directive**: All platform architecture and implementation must strictly comply with the GCP Free Tier. Scaling beyond free tier limits requires an explicit architectural review.
4. **Zero-Issue Stability**: System stability and technical debt resolution take precedence over new feature development. Maintain a "Zero-Issue State" at all times.
5. **Vanilla-Forward & Modern Tooling**: Favor vanilla JavaScript (ES2020+) and modern build systems (Vite 7+) over heavy frameworks. Maintain compatibility with modern SDKs and leverage GitHub Actions for CI/CD.

## Development Workflow

1. **Specify**: Tech-agnostic user stories and acceptance criteria.
2. **Clarify**: Three-cycle clarification (Ambiguity, Component Impact, Failure Mode).
3. **Plan**: Technical architecture, file changes, and risk assessment.
4. **Tasks**: Dependency-ordered (MODELS -> SERVICES -> ENDPOINTS) task list.
5. **Implement**: Atomic TDD commits (Red-Green-Refactor).
6. **Verify**: Verification checklist with evidence.

### PR Hygiene Policy

- **Org-wide rollout PRs** (cross-references, pre-commit configs) MUST be batch-merged or closed within 48 hours of creation.
- **Batch sync PRs** should be merged or rebased promptly; do not let them accumulate.
- PRs that remain open without activity for >7 days should be reviewed for closure or draft conversion.
- Feature branches MUST follow the naming convention: `feat/`, `fix/`, `chore/`, `ci/`, `docs/`.

## Quality Gates

1. **Linting & Formatting**: All commits must pass pre-commit hooks and linting checks.
2. **Test Coverage**: Critical paths must have associated unit or integration tests (>80%).
3. **Link Integrity**: Documentation must pass markdown link validation at all tiers.
4. **Agent Context**: Every repository must contain up-to-date `.antigravity/` context artifacts (`ARCHITECTURE.md`, `CONSTRAINTS.md`).
5. **Pre-commit Standards**: Python repos use Ruff for linting/formatting, commitizen for conventional commits, and gitleaks for secret scanning. Frontend repos use markdownlint-cli2 for docs.
6. **Architecture Documentation**: All cross-cutting architectural decisions MUST be recorded in Platform-Docs (`docs/adr/`) before implementation. The C4 workspace DSL in `c4/workspace.dsl` is the canonical source of truth for system architecture.

## Implementation Hubs

- **Governance & Spec Hub**: [`.specify`](https://github.com/vindicta-platform/.specify) — Authoritative hub for Spec-Driven Development, templates, and the 100-Spec Campaign.
- **Agent & Automation Hub**: [`.agent`](https://github.com/vindicta-platform/.agent) — Canonical hub for agent workflows, skills, and platform memory. Provides the master Repository Registry.

## Session Memory Protocol

Agents MUST update `.specify/memory/session-log.md` at the end of each working session with:
- Decisions made and their rationale
- Active workstreams and their status
- Blockers and open questions
- Key file paths and artifact locations

**Version**: 1.1.0 | **Ratified**: 2026-02-06 | **Last Amended**: 2026-02-08
