# Vindicta Documentation Constitution

**Version**: 1.0.0 | **Ratified**: 2026-02-01

## Purpose

This constitution governs agentic development within the mkdocs documentation repository.

---

## Core Principles

### I. Documentation Scope
This repository hosts **platform-wide public documentation only**. Repository-specific documentation belongs in individual repos.

### II. Spec-Driven Content
All significant documentation changes should be traceable to platform specifications or ADRs.

### III. Quality Standards
- All pages must render without errors
- Links must be validated before merge
- Code examples must be tested

### IV. Contribution Flow
1. Branch from `main`
2. Make changes in `docs/`
3. Test with `mkdocs serve`
4. Submit PR for review

### V. Agentic Guidelines
Agents working in this repository:
- MUST NOT duplicate content that belongs in individual repos
- MUST validate all links before committing
- MUST follow MkDocs syntax conventions
- SHOULD prefer Mermaid for diagrams

---

## Governance

This constitution is subordinate to the main platform-core constitution. Amendments require platform maintainer approval.
