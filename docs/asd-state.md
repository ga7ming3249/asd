# ASD State

- Version: 16
- Date: 2026-07-21
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

## Independent Reviewer

- Current primary model: GPT-5.6 Sol
- Environment: Claude Code
- Role: implementation supervision and independent technical review

Responsibilities

- Third-party review of specifications and design
- Technical validity check of the implementation approach
- Flagging oversights, contradictions, and future risks
- Proposing alternatives
- Additional verification prior to Accept Review

The Independent Reviewer is not the final decision-maker. Product decisions remain with the Owner; architecture and ASD governance decisions go through Architect Review.

**Reviewer model is not fixed.** The Owner selects the reviewer model based on availability, cost, fit for the task, context capacity, technical review capability, and independence from the Architect and implementation roles. Fable5 remains the preferred reviewer when available; GPT-5.6 Sol (run in Claude Code) is the current primary reviewer while Fable5's usage conditions make daily use impractical. This is an availability-based reviewer selection, not a permanent replacement — Fable5 may return, exclusively or alongside GPT-5.6 Sol, once its access conditions improve. See `owner-rules.md` for the full policy.

---

## Operational Note — Reviewer Availability (2026-07-20〜)

- 2026年7月20日以降、Fable5は利用条件上、日常的な監修への使用が困難になる見込み。
- 当面はGPT-5.6 SolをClaude Code上で独立レビュー担当（Independent Reviewer）として使用する。
- これは恒久的なFable5の廃止ではない。Temporary operational replacement であり、Fable5をGPT-5.6 Solへ完全移管したものではない。
- 将来Fable5が再び実用的な条件で利用可能になった場合、Owner判断で優先的または併用で復帰できる。
- レビューワーの切り替えはASDの基本責務やAccept権限を変更しない。Owner・Claude Code・Architectの役割分担はそのまま維持される。

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

# Current State

## Current Project Overview

- Type Adjuster Vertical Layout Foundation Completed ([asd#27](https://github.com/ga7ming3249/asd/issues/27), Architect Final Review: Accept, rev8).
- Typography Knowledge Base — Japanese Vertical Typography & Latin Kerning ([asd#28](https://github.com/ga7ming3249/asd/issues/28)) and OpenType Typography Features ([asd#29](https://github.com/ga7ming3249/asd/issues/29)) knowledge deliverables completed.
- Japanese Vertical — Standard implementation proceeding as an Architecture-gated scoped exception ([asd#30](https://github.com/ga7ming3249/asd/issues/30)) — Gate 1 Closed / Gate 2 Ready.

## Project Phase

Previous: Knowledge Review Phase

↓

Current: **Architecture-gated Implementation Phase**

Current Position: Gate 1 Closed / Gate 2 Ready

Typography Knowledge Base（asd#28, asd#29）を基盤として、Japanese Vertical — Standard の実装を Architecture-gated scoped exception（asd#30）として進行中。

## Active Issues

| Issue | Plugin | Priority | Status | Summary |
|---|---|---|---|---|
| [#28](https://github.com/ga7ming3249/asd/issues/28) | Type Adjuster / Type Polish | - | Open | Knowledge Review deliverables completed — Japanese Vertical Typography & Latin Kerning knowledge foundation |
| [#29](https://github.com/ga7ming3249/asd/issues/29) | Type Adjuster / Type Polish | - | Open | Knowledge Review deliverables completed — OpenType Typography Features |
| [#30](https://github.com/ga7ming3249/asd/issues/30) | Type Polish / Type Adjuster | - | Active | Japanese Vertical — Standard — Architecture-gated scoped exception. Gate 1 Closed / Gate 2 Ready |

## Architecture Notes

- Vertical Layout Foundation established by Issue #27; Wrapper / Outer responsibility separation and `relayoutVerticalWrapper()` as the single layout entry point are the current design principles.
- Type Polish owns analysis, candidate generation, rule evaluation, recommendation, and decision ownership.
- Type Adjuster owns explicit Local Fix execution and final manual adjustment; it never becomes an automatic composition engine.

## Knowledge Roadmap

Conceptual map of the Typography Knowledge Base — not an implementation plan.

```
Typography Knowledge Base

├── Issue #28
│   Typography Theory
│   ├── Japanese Typography
│   ├── Vertical Writing
│   ├── Latin Kerning
│   └── CSS Writing Modes
│
└── Issue #29
    OpenType Capabilities
    ├── GSUB
    ├── GPOS
    ├── kern
    ├── palt
    ├── pwid
    ├── vert
    ├── liga
    └── OpenType Feature Research
```

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

**Documentation Migration = Knowledge Reconstruction** (revised 2026-07-17, per Issue #25 follow-up): Documentation Migration is not a transcription task that ports Issue text and Git history into files. Its purpose is **Product Knowledge Reconstruction** — recovering and preserving product knowledge regardless of where it originated. Type Adjuster's and Type Polish's first-pass `HISTORY.md`/`ROADMAP.md` were both superseded once pre-Issue chat context was reviewed and found to hold design rationale, rejected approaches, boundary decisions, and field experience that Issue/Git history alone could not reconstruct. The same gap likely exists for other plugins.

When authoring or updating `HISTORY.md`/`ROADMAP.md`, treat the following as primary sources, in priority order (high to low):

1. The product's current design principles (e.g. `PRINCIPLES.md`)
2. Product Review / Architecture Review records
3. Pre-Issue chat (design rationale, judgment reasoning, trial and error)
4. GitHub Issues
5. Git history

Design rationale, judgment reasoning, boundary decisions, rejected ideas, field-derived insight, and the product's self-definition over time are all in scope for inclusion whenever they have documentation value — even when they exist nowhere in Issues or Git. GitHub remains where documentation outcomes are written and read from, but it is not treated as the sole source of truth for what that documentation should contain; product knowledge as a whole is.

**Living documents, not one-time migration output**: `HISTORY.md`/`ROADMAP.md` are never a fixed, completed artifact once a Migration Issue closes. Whenever earlier primary material (past chat, Product Review notes, pre-Issue design history) surfaces, they should be updated to incorporate it — regardless of whether that plugin's Documentation Migration Issue is already closed. Type Adjuster and Type Polish (both revised 2026-07-17) are the first applied instances of this policy; the same retroactive treatment applies to any other already-migrated plugin (Guide Stamp, Instance Checker, Margin Preflight, Pocket Preview, Type Inventory, Status Stamp, Color Inventory, Component Package, Design Style Sheet) if pre-Issue primary sources for it are later found.

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
```

---

# Review Workflow

```
Owner
  ↓
Specification / Scope
  ↓
Claude Code Implementation
  ↓
Independent Technical Review
  - Currently GPT-5.6 Sol
  - Fable5 may be used when available
  ↓
Architect Review
  ↓
Owner Accept / Close
```

Independent Technical Review and Architect Review are distinct responsibilities:

- **Independent Technical Review** — third-party verification of the implementation and specification.
- **Architect Review** — consistency with ASD as a whole, separation of responsibilities, long-term architecture, and the Accept / Request changes decision.

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
