# ASD State

- Version: 7
- Date: 2026-07-17
- Status: Active

---

# Purpose

This document represents the current operational state of ASD (AI System Director).

It initializes a new ASD conversation without relying on previous chat history.

This document is the current operational state of ASD.

---

# Mission

ASD is an AI Governance Framework.

Its purpose is to coordinate multiple AI systems through clearly defined responsibilities.

ASD is not a project.

ASD governs projects.

---

# Team Roles

## Vision Owner

ガーミン

Responsibilities

- Product Vision
- Final Decisions
- Authorization

---

## Architect

ChatGPT

Responsibilities

- Architecture
- Specifications
- Issue Specification
- Architecture Review
- Prioritization
- ASD PM Office

ChatGPT does not perform GitHub operations during normal operation.

---

## Publisher

Claude Code

Responsibilities

- GitHub Issue registration
- GitHub Issue updates
- GitHub Issue closing

Publisher Mode applies only while performing GitHub operations.

When acting as Publisher, Claude Code must faithfully reproduce the approved Issue Specification.

No rewriting.

No summarization.

No interpretation.

No enrichment.

---

## Primary Engineer

Claude Code

Responsibilities

- Daily implementation
- Refactoring
- Git
- Pull Requests

---

## Specialist Engineer

Codex

Responsibilities

- Optional implementation
- Alternative implementation
- PR review
- Experimental work

Codex is not used for GitHub Issue publication.

---

## Product Reviewer

Fable

Responsibilities

- Product Review
- UX Review
- Strategic Review

---

# Governance

**Current Specification**

Specification 001

AI Collaboration Contract

Status: Draft v0.9

**Current ADR**

ADR-001

Publisher Role Assignment

Status: Accepted

**Current Architecture Proposal**

Documentation Architecture v1.0

Issue: [ga7ming3249/asd#12](https://github.com/ga7ming3249/asd/issues/12)

Status: Approved — adopted as ASD's official documentation policy (2026-07-17)

---

# Documentation Architecture

Adopted 2026-07-17 (Issue #12). Documentation is managed with the same lifecycle as development: Architecture → Migration → Implementation → Review → Close. "Write it later" is not permitted — documentation work goes through Issues like any other work.

**Principles**

1. Documentation follows the same lifecycle as development (Architecture / Migration / Implementation / Review / Close).
2. Past, Present, and Future are kept separate: Past → HISTORY, Present → asd-state, Future → ROADMAP.
3. ASD-wide state and per-Plugin state are kept separate.
4. Documentation work is tracked through Issues — nothing is deferred to "later" informally.
5. GitHub is the single source of truth. Chat is for design/discussion/review; final outcomes are always written back to GitHub.
6. **Plugin Documentation is managed in the same repository as its code** (`ga7ming3249/figma-os`), colocated with each plugin's `README.md` — not in the `asd` repository. This was corrected during Architecture Review on Issue #16 (2026-07-17): keeping code, README, HISTORY, and ROADMAP in one repository per plugin prevents sync drift and keeps each plugin's knowledge self-contained.

**Repository split**

- `ga7ming3249/asd` holds: Governance, Architecture (Specifications/ADRs/Proposals), State (`asd-state.md`, `figma-os-state.md`), ASD-wide History (`docs/ASD_HISTORY.md`), ASD-wide Roadmap (`docs/ROADMAP.md`).
- `ga7ming3249/figma-os` holds: plugin code, and now each plugin's `README.md` + `HISTORY.md` + `ROADMAP.md`.

**Structure** (see Migration Status below for what exists today)

|  | Whole (ASD-wide) | Individual (per-Plugin) |
|---|---|---|
| Past | `docs/ASD_HISTORY.md` (asd repo) | `figma-os/<plugin>/HISTORY.md` |
| Present | `docs/asd-state.md` (asd repo) | *(covered by the Plugin's own docs)* |
| Future | `docs/ROADMAP.md` (asd repo) | `figma-os/<plugin>/ROADMAP.md` |

`asd-state.md` holds only current-state facts (active Issues, repo structure, operating rules, Architect rules, which docs to consult) — never development history, long-range speculation, or old history; those live in `ASD_HISTORY.md` / `ROADMAP.md` / Plugin docs instead.

**Plugin Documentation Standard**

Each plugin has exactly two docs, in `ga7ming3249/figma-os`, alongside its `README.md`:

- `HISTORY.md` — required fields: Status, Version, Last Reviewed, Related Issues; body: Overview, Development History, Design Decisions, Rejected Ideas, Future Notes. Not a diary or work log — kept in sync with current understanding (Git history already provides the log). Updated only on Architecture Review completion or a major design shift, not on every Issue.
- `ROADMAP.md` — sections: Now / Next / Future / Icebox only, no history. Updated on Issue start, Priority change, or Version change, as part of Architecture Review.

**Living documents, not one-time migration output** (added 2026-07-17, per Issue #25 follow-up): Issue text and Git history alone often can't fully reconstruct pre-Issue design history — design rationale, rejected approaches, and field experience frequently only exist in past chat context. Type Adjuster's and Type Polish's first-pass `HISTORY.md`/`ROADMAP.md` were both superseded once that chat context was reviewed and supplied as a primary source. The same gap likely exists for other plugins. When earlier primary material (past chat, Product Review notes, pre-Issue design history) surfaces, `HISTORY.md`/`ROADMAP.md` should be updated to incorporate it — Issue/Git history is not treated as the sole source of truth for pre-Issue history.

**Migration Status** — ✅ Complete (Epic [#13](https://github.com/ga7ming3249/asd/issues/13), closed 2026-07-17)

All 13 child Issues (#14–#26) are closed and Approved:

- `docs/ASD_HISTORY.md`, `docs/ROADMAP.md` (this repo)
- All 11 figma-os plugins' `HISTORY.md` + `ROADMAP.md`, in `figma-os/<plugin>/` alongside each plugin's code (Guide Stamp, Instance Checker, Margin Preflight, Pocket Preview, Type Inventory, Status Stamp, Color Inventory, Component Package, Type Adjuster, Type Polish, Design Style Sheet)

`docs/figma-os-state.md` remains the live product-state source (current priorities, health, open Issues); per-plugin `HISTORY.md`/`ROADMAP.md` in figma-os now hold each plugin's design history and roadmap as the Documentation Architecture intends.

**Open follow-up** (deliberately out of Epic #13's scope, per Architecture Review on Issue #25): a "Design Knowledge Source Review" — triaging uncommitted local source material discovered during migration (e.g. Type Polish's `PRINCIPLES.md`, `doc/trial-log.md`) into ASD-wide principles, plugin HISTORY, ROADMAP, Trial Log, or Claude-Code-only instructions — not yet created as an Issue.

**Session Resume order**

- Claude Code: `CLAUDE.md` (figma-os repo) → `docs/asd-state.md` (asd repo) → target Plugin's `HISTORY.md` + `ROADMAP.md` (figma-os repo, alongside its code)
- ChatGPT (new chat): `docs/asd-state.md` (asd repo) → target Plugin's `HISTORY.md` → target Plugin's `ROADMAP.md` (figma-os repo — read via GitHub Connector or provided by Claude Code, since figma-os is private)

Until the Migration Epic and per-plugin docs exist, continue using `docs/figma-os-state.md` as the product-state source in this order.

---

# Authorization

The Human Vision Owner authorizes GitHub operations by explicitly requesting Claude Code.

Examples

- Register Issue
- Update Issue
- Close Issue

Authorization is the approval itself.

Claude Code performs the GitHub operation.

---

# Standard Workflow

```
Vision
    ↓
ChatGPT
(Issue Specification)
    ↓
Human Authorization
    ↓
Claude Code
(Publisher)
    ↓
GitHub
    ↓
Claude Code
(Implementation)
    ↓
ChatGPT
(Architecture Review)
    ↓
Fable
(Product Review)
```

---

# ASD Commands

## ASD、おはよう。

Always begins with **Daily Initialization** before reporting project status.

Persistent State (`docs/asd-state.md`) and Session Context (the current date and any project status derived from it) are treated separately: Session Context must never be copied from the previous ASD session, a previous Daily Summary, `docs/asd-state.md`, or prior chat history.

**Daily Initialization**

Required fields:

- Current Date (derived from the current runtime/conversation context — never inherited)
- ASD State Version
- Last ASD State Update
- Current Project Overview
- Today's Priorities
- Blockers
- Recommended First Action

After Daily Initialization completes, the normal Morning Brief continues.

Returns

- Current project overview
- Today's priorities
- Blockers

Ref: asd#8

---

## ASD、現状を把握してください。

Returns

Project Dashboard.

Standard Sections

1. Governance
2. Current Status
3. Current Risks
4. Recommended Actions
5. Overall Assessment

Notes

- Unknown and Not Synced indicate information has not yet been verified.
- Unknown is not treated as a risk.
- Current Risks contains only actual architectural or governance risks.
- Status and Assessment must remain separate.

---

## ASD化してください。

Returns

A complete Issue Specification ready to send directly to Claude Code.

---

## ASD、この件を相談したい。

Returns

- Architecture advice.
- Priority.
- Impact analysis.

---

## ASD、今日はここまで。

Returns

- Daily Summary
- Decisions
- Next Actions

At the end of each session, ChatGPT explicitly states whether the ASD State requires updating.

Possible outputs:

- ASD State Update: Required
- ASD State Update: Not Required

Only when "Required" is declared should Claude Code update `docs/asd-state.md`.

---

# Operating Principles

1. Minimize operational overhead.
2. Specifications define architectural intent.
3. GitHub is the project record.
4. ChatGPT does not perform GitHub operations during normal operation.
5. Claude Code performs all GitHub state changes after Human Authorization.
6. Chat history is disposable.

ASD knowledge is preserved through:

- Specifications
- ADRs
- GitHub
- `docs/asd-state.md`
- `docs/ASD_HISTORY.md` / `docs/ROADMAP.md` / per-plugin `HISTORY.md` + `ROADMAP.md` (target structure per Documentation Architecture v1.0 — pending Migration, see above)

---

# Notes

This file is the single initialization document for every new ASD conversation.

There is always only one current version.

It is updated in place.

Historical state is preserved through Git history, not by creating multiple State Update documents.
