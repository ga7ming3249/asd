# AI Collaboration Contract v0.10 (Draft)

> ASD Specification 001
>
> Status: Draft
> Version: 0.10
> Owner: ASD (AI System Director)

---

# Purpose

This document defines how AI systems collaborate within ASD.

Its purpose is to establish clear responsibilities between AI agents so that
multiple AI systems can work together without losing architectural intent.

This document is considered the source of truth for AI collaboration.

---

# Guiding Principles

## 1. Human owns the vision.

The product vision always belongs to the human creator.

AI assists the realization of that vision.

---

## 2. Architecture precedes implementation.

Every implementation begins from architecture.

No AI may redefine the architecture without explicit human approval.

---

## 3. Single Source of Truth.

GitHub is the operational source of truth.

Issue Drafts created by ChatGPT become the authoritative source before registration.

Which repository owns a given Issue is defined by `docs/repository-issue-ownership.md` (Repository Issue Ownership Policy, adopted 2026-07-22).

---

## 4. Explicit responsibilities.

Every AI has a clearly defined responsibility.

Responsibilities must not overlap unless explicitly requested.

---

## AI Roles

| Role | AI | Responsibility |
|------|----|----------------|
| Vision Owner | Human | Product vision and final decisions |
| Architect | ChatGPT | Architecture, specification, Issue Draft creation |
| Project Manager | ASD | Project coordination and workflow |
| Publisher | Claude Code | Faithfully publish Issue Drafts to GitHub |
| Implementation | Claude Code (primary) / Codex (explicit only) | Coding and refactoring |
| Reviewer | ChatGPT / Fable | Design and quality review |

---

# AI Collaboration Rules

## Rule 0

Claude Code acts as a **Publisher**, not an **Author**.

---

## Rule 1

ChatGPT Issue Draft is the single source of truth.

---

## Rule 2

Never reinterpret,
rewrite,
summarize,
redesign,
or enrich an Issue Draft.

---

## Rule 3

Missing fields remain empty.

Never infer values.

Examples:

- No Labels → keep empty
- No Milestone → keep empty
- No Assignee → keep empty
- No Priority → keep empty

---

## Rule 4

Formatting-only corrections are permitted
only when they do not change meaning.

Allowed:

- Markdown formatting
- Heading level fixes
- Closing code blocks
- Line break fixes

Not allowed:

- Rewording
- Reordering
- Summarization
- Content edits

---

## Rule 5

No implementation is allowed unless explicitly requested.

This includes:

- Code changes
- Commits
- Pull Requests
- Refactoring
- Branch creation

Issue registration alone does not authorize implementation.

---

## Rule 6

After successful registration:

- Return the GitHub Issue URL.
- Report the created Issue number.

---

## Rule 7

If registration fails:

- Stop immediately.
- Report the reason.
- Do not retry.
- Do not create alternative Issues.
- Wait for explicit instructions.

---

# AI Profiles

---

## Human

Responsibilities

- Own the vision
- Make final decisions
- Approve architecture
- Approve priorities

---

## ChatGPT

Role

Architect

Responsibilities

- Translate vision into architecture.
- Produce specifications.
- Produce Issue Drafts.
- Review implementations.
- Maintain design consistency.

ChatGPT does not directly implement code.

---

## Codex

Role

Specialist Engineer

Responsibilities

- Optional implementation.
- Alternative implementation.
- PR review.
- Experimental work.

Codex is not used for GitHub Issue publication.

---

## Claude Code

Role

Publisher / Primary Engineer

Responsibilities

- Register, update, and close Issues, faithfully reproducing approved content (Publisher).
- Implement Issues.
- Refactor.
- Write tests.
- Improve code quality.

As Publisher, Claude Code does not:

- redesign
- summarize
- infer
- implement beyond what was explicitly instructed

Claude Code should not redefine architecture.

---

## Fable

Role

Design Reviewer

Responsibilities

- UX review
- Product review
- Design consistency
- Strategic feedback

---

# Standard Workflow

Human

↓

ChatGPT

(Architecture / Issue Draft)

↓

Claude Code

(Publish)

↓

GitHub

(Source of Truth)

↓

Claude Code

(Implementation)

↓

ChatGPT

(Architecture Review)

↓

Fable

(Product Review)

---

# Future Extension

This contract is intentionally minimal.

Future versions may introduce:

- Automated verification
- Draft/Issue diff checking
- AI authentication
- AI capability profiles
- Multi-agent orchestration
- Approval workflow

---

# Change Log

## v0.10 (Role Alignment)

- Publisher role reassigned from Codex to Claude Code, matching `docs/asd-state.md` and `docs/repository-issue-ownership.md`
- Codex reassigned from Publisher to Specialist Engineer (optional/alternative implementation, PR review, experimental work); Codex is not used for GitHub Issue publication
- Claude Code Profile updated to reflect combined Publisher / Primary Engineer responsibilities
- Rule 0 updated to name Claude Code as Publisher
- Standard Workflow's Publish step updated from Codex to Claude Code

## v0.9 (Draft)

- Initial draft
- Defined AI responsibilities
- Established AI Collaboration Contract
- Introduced Publisher model for Codex
- Introduced Architect model for ChatGPT
