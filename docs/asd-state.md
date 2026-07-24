# ASD State

- Version: 30
- Date: 2026-07-25
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

Status: Draft v0.10

**Current ADR**

ADR-001

Publisher Role Assignment

Status: Accepted

**Current Architecture Proposal**

Documentation Architecture v1.0

Issue: [ga7ming3249/asd#12](https://github.com/ga7ming3249/asd/issues/12)

Status: Approved — adopted as ASD's official documentation policy (2026-07-17)

**Repository Issue Ownership Policy**

`docs/repository-issue-ownership.md`

Status: Adopted (2026-07-22) — defines which repository (`asd`, `figma-os`, or a future Product Repository) owns and tracks a given GitHub Issue, based on the Primary Deliverable's Canonical Source.

---

# Current State

## Current Project Overview

- Type Adjuster Vertical Layout Foundation Completed ([asd#27](https://github.com/ga7ming3249/asd/issues/27), Architect Final Review: Accept, rev8).
- Typography Knowledge Base — Japanese Vertical Typography & Latin Kerning ([asd#28](https://github.com/ga7ming3249/asd/issues/28)) and OpenType Typography Features ([asd#29](https://github.com/ga7ming3249/asd/issues/29)) knowledge deliverables completed.
- Vision Owner priority decision (2026-07-23): [figma-os#2](https://github.com/ga7ming3249/figma-os/issues/2) is prioritized ahead of Gate 5 Desktop Acceptance; this decision governed figma-os#2's implementation through to completion below.
- Nightly Canonical State Synchronization (2026-07-25): [figma-os#2](https://github.com/ga7ming3249/figma-os/issues/2) is **Completed / Accepted / Closed** (closed 2026-07-24). Findings A/B/C from the prior Changes-Required review were corrected, PR [figma-os#7](https://github.com/ga7ming3249/figma-os/pull/7) merged to `figma-os/main` at `2838450c91429e9bc9c312103e0741c64e0068d2` (implementation commit `874d94dbfa4336ab064822e1ccc07ece12795149`), verified: Build Success, Typecheck Success, Tests 138/138 passed, Desktop Verification All Pass. Verified `figma-os/main` HEAD is `2838450c91429e9bc9c312103e0741c64e0068d2`. figma-os#2's isolated worktree/feature-branch cleanup (`feature/issue-2-scale-state-sync`) is optional maintenance only, not required for Issue closure. A Dedicated Main Worktree is recorded as the canonical verification environment for the latest Type Adjuster builds; the Protected Gate 4 checkout remains a separate, intentionally isolated development environment and is unaffected by this merge.
- Japanese Vertical — Standard implementation proceeding as an Architecture-gated scoped exception ([asd#30](https://github.com/ga7ming3249/asd/issues/30)) — Gate 5 remains authorized and its Primary Implementation Issue [figma-os#6](https://github.com/ga7ming3249/figma-os/issues/6) remains Open. figma-os#2's completion resolves the Gate 5 hold's stated dependency, but per existing policy Gate 5 "resumes only after an explicit Owner priority decision" — no such decision is included in this synchronization, so Gate 5 remains Open / Owner Priority Hold. Gate 4 remains accepted only at `dc6361157345ebb8b17264f63aef8fa0e265c5eb` on `feature/issue-30-gate4-safe-local-fix` ([figma-os#5](https://github.com/ga7ming3249/figma-os/issues/5), Closed) and is not merged to `figma-os/main`.
- Type Adjuster Scale UI synchronization Issue ([figma-os#2](https://github.com/ga7ming3249/figma-os/issues/2)) — Completed / Accepted / Closed (see Nightly Canonical State Synchronization note above); independent Product Improvement, no Gate dependency.
- Type Polish Utility ownership consolidation decision Issue registered ([figma-os#3](https://github.com/ga7ming3249/figma-os/issues/3)) — Product Architecture Decision, remains Open / not started, downstream of figma-os#2 completion before any Utility removal is considered.
- Repository Issue Ownership Reorganization Phase 2 executed (2026-07-22): [asd#3](https://github.com/ga7ming3249/asd/issues/3) transferred to [figma-os#4](https://github.com/ga7ming3249/figma-os/issues/4) (Type Inventory multiline support — not started, Successor Issue method) and closed; [figma-os#2](https://github.com/ga7ming3249/figma-os/issues/2)'s bare `#30` cross-repository references corrected to `ga7ming3249/asd#30`; Repository Issue Ownership Policy adopted (`docs/repository-issue-ownership.md`). See `docs/ASD-Issues-17-24-Architecture-Review-Bundle-2026-07-22.md` for the #17–#24 review bundle.
- Repository Issue Ownership Reorganization Phase 3 executed (2026-07-22): Documentation Migration Epic #13's remaining 8 child Issues (asd#17–#24) received Architecture Review and were Closed — #17, #18, #21, #24 after a limited Product Documentation correction (`figma-os` commit `c9def97`), #19, #20, #22, #23 without correction. `docs/ai-collaboration-contract.md` updated to v0.10 (Publisher role: Codex → Claude Code; Codex: Publisher → Specialist Engineer).
- Reference Assistant established as an independent private repository (2026-07-23): `ga7ming3249/reference-assistant`, baseline `main` commit `f0025cb30acd25948b92abd9e06ff93b4974a15c`, CI baseline verified, stable local clone `/Users/atsushitogami/Developer/reference-assistant`. `asd#4` and `asd#6` migrated to that repository by the Successor Issue method after explicit Vision Owner approval; `asd#5` is retained, unchanged, as closed history.
- Reference Assistant Daily Operation Guide completed (2026-07-23): [reference-assistant#2](https://github.com/ga7ming3249/reference-assistant/issues/2) is Closed / Completed; `docs/daily-operation-guide.md` is merged into `reference-assistant/main` at `9ef507480de209e4910b9e42c38326c47d30890c`.
- Reference Assistant Issue #5 — Japan-first Collection Gate and Always-on Content Safety ([reference-assistant#5](https://github.com/ga7ming3249/reference-assistant/issues/5)): **In Progress — Review / Validation transition**, not Accepted, not Closed. Current reviewed commit `541a74e113d8ebe96175228c4627151f3f007e50`. Draft PR [reference-assistant#6](https://github.com/ga7ming3249/reference-assistant/pull/6) remains **Draft / Open**. Daily Preview remains disabled. Outstanding work: Acceptance Criteria audit, Manual Live Validation, Independent Technical Review, Architect Review, and Vision Owner restart approval.
- [reference-assistant#1](https://github.com/ga7ming3249/reference-assistant/issues/1) (Daily Preview Operation) remains Open; Daily Preview stays stopped until a safe promotion path for `reference-assistant#5` is established.
- Human-reviewed Safety Promotion is a proposed approach only — not yet approved by the Vision Owner, and not recorded as Accepted Architecture. Whether it becomes a Phase B addendum to Issue #5 or a separate Issue awaits Vision Owner decision.
- Dropbox repository migration (2026-07-25): the Dropbox repository is now the canonical local development repository for `reference-assistant`, superseding the prior `/Users/atsushitogami/Developer/reference-assistant` clone referenced above.
- Reference Assistant Issue #7 — Post-migration Cleanup After Dropbox Development Directory Migration ([reference-assistant#7](https://github.com/ga7ming3249/reference-assistant/issues/7)): Open, independent maintenance issue. Does not block Issue #5 completion.

## Project Phase

Previous: Knowledge Review Phase

↓

Current: **Architecture-gated Implementation Phase**

Current Position: figma-os#2 Completed / Accepted / Closed — Issue #30 Gate 5 (Desktop Acceptance) dependency resolved but remains on Owner Priority Hold pending an explicit Vision Owner decision to resume

Typography Knowledge Base（asd#28, asd#29）を基盤として、Japanese Vertical — Standard の実装を Architecture-gated scoped exception（asd#30）として進行中。

## Active Issues

| Issue | Plugin | Priority | Status | Summary |
|---|---|---|---|---|
| [#28](https://github.com/ga7ming3249/asd/issues/28) | Type Adjuster / Type Polish | - | Open | Knowledge Review deliverables completed — Japanese Vertical Typography & Latin Kerning knowledge foundation |
| [#29](https://github.com/ga7ming3249/asd/issues/29) | Type Adjuster / Type Polish | - | Open | Knowledge Review deliverables completed — OpenType Typography Features |
| [#30](https://github.com/ga7ming3249/asd/issues/30) | Type Polish / Type Adjuster | - | Active / Open Parent | Japanese Vertical — Standard — Parent Coordination Issue for Gate 5 Desktop Acceptance. figma-os#2 dependency resolved; Gate 5 remains on Owner Priority Hold pending an explicit Vision Owner decision to resume |
| [figma-os#6](https://github.com/ga7ming3249/figma-os/issues/6) | Type Adjuster / Type Polish | - | Open / Owner Priority Hold | Gate 5 — Desktop Acceptance. Architect-verified and authorized; inherited baseline `dc636115...` (unmerged, `figma-os` feature branch). Desktop Acceptance not started; figma-os#2 dependency resolved (Closed 2026-07-24), but Owner Priority Hold remains pending an explicit Vision Owner decision. Product code changes, PR, and main merge remain unauthorized |
| [figma-os#3](https://github.com/ga7ming3249/figma-os/issues/3) | Type Polish / Type Adjuster | Medium | Open / Downstream of #2 | Product Architecture Decision — canonical ownership of Utility (Scale/Baseline/Tracking). Depends on figma-os#2 completion before any Utility removal |
| [reference-assistant#1](https://github.com/ga7ming3249/reference-assistant/issues/1) | Reference Assistant | P1 | Open / Daily Preview Stopped | Daily Preview Operation — Primary Issue, Successor to asd#4. Daily Preview stopped pending a safe promotion path for reference-assistant#5 |
| [reference-assistant#5](https://github.com/ga7ming3249/reference-assistant/issues/5) | Reference Assistant | P1 | Open / In Progress — Review / Validation transition | Implement Japan-first Collection Gate and Always-on Content Safety. Draft PR [reference-assistant#6](https://github.com/ga7ming3249/reference-assistant/pull/6) remains Draft/Open, reviewed commit `541a74e...`; not Accepted, not Closed. Outstanding: Acceptance Criteria audit, Manual Live Validation, Independent Technical Review, Architect Review, Vision Owner restart approval |
| [reference-assistant#7](https://github.com/ga7ming3249/reference-assistant/issues/7) | Reference Assistant | - | Open / Maintenance | Post-migration Cleanup After Dropbox Development Directory Migration. Independent maintenance issue; does not block reference-assistant#5 completion |
| [reference-assistant#3](https://github.com/ga7ming3249/reference-assistant/issues/3) | Reference Assistant | P2 | Open | Design Library Location Selection and Safe Relocation Model — Architecture Issue |

## Architecture Notes

- Vertical Layout Foundation established by Issue #27; Wrapper / Outer responsibility separation and `relayoutVerticalWrapper()` as the single layout entry point are the current design principles.
- Type Polish owns Analysis, Recommendation, User Decision, and Manual Handoff production. Gate 4 adds current-selection-only applied-marker recognition and preserves zero document mutation.
- Type Adjuster owns current-selection validation, explicit Local Fix execution, and final manual adjustment. Gate 4 delivered `LF-UPRIGHT-001`, `LF-ROTATE-RUN-001`, group-member Nudge, and conflict-safe structural Reset. It remains non-judgmental and never becomes an automatic composition engine.
- Transport and execution status: Manual Handoff Transport is Adopted; Safe Local Fix consumption and explicit execution are implemented and accepted on `feature/issue-30-gate4-safe-local-fix` at `dc6361157345ebb8b17264f63aef8fa0e265c5eb`. Real Figma Desktop acceptance remains Gate 5.
- Gate 4 implementation is not present on verified `figma-os/main@2838450c91429e9bc9c312103e0741c64e0068d2` (figma-os#2 merged 2026-07-24); downstream work must inherit the accepted feature-branch commit explicitly.
- `figma-os#2` was implemented against canonical `main@c9def9785e86272c8d21d61f14a500cd8b45793c` and merged via PR [figma-os#7](https://github.com/ga7ming3249/figma-os/pull/7) at `2838450c91429e9bc9c312103e0741c64e0068d2`; Gate 4 and Gate 5 use the accepted, unmerged `dc6361157345ebb8b17264f63aef8fa0e265c5eb`. The two lineages still overlap in Type Adjuster UI, backend/message flow, generated output, tests, and documentation, and require a future explicit integration/reconciliation scope — reviewing overlapping files and rerunning both regression suites — before they are combined. No rebase, cherry-pick, or merge between the lineages is authorized until then.
- Reference Assistant product work belongs in its own Product Repository (`ga7ming3249/reference-assistant`). ASD is used only for cross-product/global governance, not for tracking that product's day-to-day Issues.

## Current main

Verified ASD base main before this State update: `a510a6eb0312fbcb4ad3b14faaa01bfbcbcd2253`

Verified figma-os main: `2838450c91429e9bc9c312103e0741c64e0068d2` (figma-os#2 / PR #7 merged, 2026-07-24)

Accepted, unmerged Gate 4 feature head: `dc6361157345ebb8b17264f63aef8fa0e265c5eb`

Verified Reference Assistant main: `9ef507480de209e4910b9e42c38326c47d30890c`

## Outstanding Work

**figma-os#2 — Completed / Accepted / Closed**

Findings A/B/C from the prior Changes-Required review were corrected. PR [figma-os#7](https://github.com/ga7ming3249/figma-os/pull/7) merged to `figma-os/main` at `2838450c91429e9bc9c312103e0741c64e0068d2` (implementation commit `874d94dbfa4336ab064822e1ccc07ece12795149`), closing figma-os#2. Verified: Build Success, Typecheck Success, Tests 138/138 passed, Desktop Verification All Pass. Gate 4 / Gate 5 lineage (`dc6361157345ebb8b17264f63aef8fa0e265c5eb`) remains separate and unmerged; a future explicit integration/reconciliation scope is still required before combining it with `figma-os/main`. Cleanup of the isolated worktree/feature branch used during implementation (`feature/issue-2-scale-state-sync`) is optional maintenance only.

**Current work: Resume Issue #30 Gate 5 — Desktop Acceptance**

figma-os#2's completion resolves the dependency that Gate 5's Owner Priority Hold was conditioned on. Per existing policy, Gate 5 "resumes only after an explicit Owner priority decision" (see Outstanding Work → Issue #30 below); no such decision is included in this synchronization, so Gate 5 remains Open / Owner Priority Hold pending that explicit decision.

**reference-assistant#5 — Japan-first Collection Gate and Always-on Content Safety**

Open, **In Progress — Review / Validation transition**; not Accepted, not Closed. Draft PR [reference-assistant#6](https://github.com/ga7ming3249/reference-assistant/pull/6) remains Draft/Open, current reviewed commit `541a74e113d8ebe96175228c4627151f3f007e50`. Daily Preview ([reference-assistant#1](https://github.com/ga7ming3249/reference-assistant/issues/1)) remains disabled/stopped. Outstanding work: Acceptance Criteria audit, Manual Live Validation, Independent Technical Review, Architect Review, and Vision Owner restart approval. Human-reviewed Safety Promotion is a proposed approach only, not yet approved by the Vision Owner; it is not recorded as Accepted Architecture.

**reference-assistant#7 — Post-migration Cleanup After Dropbox Development Directory Migration**

Open, independent maintenance issue. The Dropbox repository is now the canonical local development repository for `reference-assistant`. Does not block reference-assistant#5 completion.

**Issue #30**

Completed Gates:

- Gate 0 — Current implementation / transport review
- Gate 1 — Shared Rules + analyzer
- Gate 2 — Type Polish result UI
- Gate 3 — Manual Handoff Transport
- Gate 4 — Safe Local Fix MVP ([figma-os#5](https://github.com/ga7ming3249/figma-os/issues/5), Closed / Completed, accepted at `dc6361157345ebb8b17264f63aef8fa0e265c5eb`)

Remaining Gate:

- Gate 5 — Desktop Acceptance ([figma-os#6](https://github.com/ga7ming3249/figma-os/issues/6), Open / Owner Priority Hold)

Issue remains Open. `asd#30` remains the Parent Coordination Issue for Architecture Gates, Global Architect Review, completion judgment, and State Synchronization.

Gate 5 remains authorized (Architect verified the Issue URL and exact specification on 2026-07-23), but the Vision Owner placed Desktop Acceptance on Owner Priority Hold on 2026-07-23 pending `figma-os#2`. This is not a defect, architecture blocker, rejection, or cancellation. Gate 5 resumes only after an explicit Owner priority decision. Product code changes, PR creation, and merge to `figma-os/main` remain unauthorized.

Gate 5 must inherit `dc6361157345ebb8b17264f63aef8fa0e265c5eb` directly. It must not assume `figma-os/main@2838450c9...` contains Gate 4.

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

*Deliverable migration (成果物移行状態)* — ✅ Complete, evidence-verified 2026-07-22:

- `docs/ASD_HISTORY.md`, `docs/ROADMAP.md` (this repo)
- All 11 figma-os plugins' `HISTORY.md` + `ROADMAP.md` exist in `figma-os/<plugin>/` alongside each plugin's code (Guide Stamp, Instance Checker, Margin Preflight, Pocket Preview, Type Inventory, Status Stamp, Color Inventory, Component Package, Type Adjuster, Type Polish, Design Style Sheet), and the commit that added each file is reachable on `figma-os` `main`.

*GitHub Issue lifecycle (Issue管理状態)* — ✅ Complete, reconciled 2026-07-22: all 13 child Issues (#14–#26) are Closed. #14, #15, #16, #25, #26 closed at first pass; #17–#24 received Architecture Review (Accepted) and were closed in the Phase 3 reconciliation — #17, #18, #21, #24 required a limited Product Documentation correction first (see `figma-os` commit `c9def97`), #19, #20, #22, #23 were accepted without correction. `docs/ASD-Issues-17-24-Architecture-Review-Bundle-2026-07-22.md` remains available as the historical evidence record for that review.

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

## State Synchronization Policy

### 1. Milestone Synchronization

ASD State is synchronized whenever the project's current state materially changes.

Examples:

- Project Phase changes
- Gate completion
- Architecture decisions
- Major Issue transitions
- Beta → Stable
- Release milestones

ASD State represents the current project state only. Historical progress remains in GitHub history rather than accumulating inside the state document.

### 2. Context Handoff Synchronization

ASD State is synchronized before intentionally starting a new Architect session when the current conversation is no longer an efficient working context.

Examples:

- Conversation becomes excessively long
- Context quality begins to degrade
- Performance decreases
- A fresh Architect chat is intentionally created
- Work is handed over between Architect sessions

The purpose of this synchronization is not to preserve chat history. The purpose is to ensure that the next Architect session can reconstruct the current project state directly from ASD State without relying on conversational memory.

### Design Principle

Chat conversations are temporary working spaces.

ASD State is the canonical project memory.

Architect sessions may change.

Project state must remain continuous.

---

# Notes

This file is the single initialization document for every new ASD conversation.

There is always only one current version.

It is updated in place.

Historical state is preserved through Git history, not by creating multiple State Update documents.
