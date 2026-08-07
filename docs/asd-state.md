# ASD State

- Version: 37
- Date: 2026-08-07
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

## Execution Authority and Proxy Handoff

These rules take precedence over fixed role assignments when service capabilities or operating conditions change.

1. **Human Authorization is mandatory.** No AI actor may create, edit, delete, publish, Commit, Push, Close, Merge, or otherwise mutate project state without explicit authorization from the Vision Owner.
2. **Role assignments may change.** Architect, Publisher, Engineer, Director, or Reviewer assignments may be changed to match current AI service capabilities, provided architectural intent, quality standards, decision rationale, and current state remain transferable.
3. **Proxy execution requires mandatory follow-up.** When an actor performs work assigned to another role, the proxy executor must notify and hand off to the originally assigned actor.
4. **The follow-up must include:** the reason for proxy execution; actions and results; Issue, Commit, file, or other references; decisions and unresolved items; requested verification or continuation; and the status of Canonical record updates.
5. **Proxy execution is not synchronized until handoff is possible.** The originally assigned actor must be able to verify the result and resume responsibility. Duplicate execution is not required; audit, acknowledgment, and continuation are the default.
6. **Chat history is not the record.** These rules and any material changes to them must be synchronized to Canonical Documents before an Architect chat is intentionally replaced, so ChatGPT and Claude Code can reconstruct the same current state.

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
- Nightly Canonical State Synchronization (2026-07-29): Japanese Vertical — Standard ([asd#30](https://github.com/ga7ming3249/asd/issues/30)) Gate 5 — Desktop Acceptance, Primary Implementation Issue [figma-os#6](https://github.com/ga7ming3249/figma-os/issues/6), is **Accepted / Completed / Closed** (closed `2026-07-29T11:45:25Z` / 2026-07-29 20:45:25 JST, state reason Completed). PR [figma-os#8](https://github.com/ga7ming3249/figma-os/pull/8) is **Merged** to `figma-os/main` (base `main`, 7 commits, merged `2026-07-29T11:44:32Z`) — accepted implementation commit `9253ce8ce46dbd02225f9bfa73019f4662f575de`, merge commit `d3abd4f46ce89240a22a467bbbf712f4c5e10628`. Gate 4 remains historically accepted at `dc6361157345ebb8b17264f63aef8fa0e265c5eb` on `feature/issue-30-gate4-safe-local-fix` ([figma-os#5](https://github.com/ga7ming3249/figma-os/issues/5), Closed); its lineage is now merged to `figma-os/main` via the Gate 5 accepted implementation commit above. Japanese Vertical — Standard / Safe Local Fix MVP Gate 0 through Gate 5 are now complete, and `asd#30` is Closed / Completed as of this Canonical State Synchronization.
- Gate 5 Accepted verification evidence: Type Adjuster full suite `278/278 PASS`, Scale UI tests `109/109 PASS`, Gate 4 Local Fix tests `163/163 PASS`, G5-DEF-002 generated marker tests `6/6 PASS`, Type Polish full suite `165/165 PASS`, Type Adjuster build PASS, Type Polish build PASS, Pre-rebase Desktop Acceptance `9/9 PASS` (macOS `26.5.2 (25F84)`, Figma Desktop App `126.6.14`), Rebased-head Desktop Acceptance `7/7 PASS` (macOS `26.5.2 (25F84)`, Figma Desktop App `126.7.10`).
- Gate 5 confirmed Local Fix Reset architecture: Reset uses a `retained-original-node` approach — the original TextNode instance is retained and restored rather than reconstructed. Reset resolves the unique, valid Local Fix group from the ancestor/descendant relationship among the Local Fix member, its outer Frame, and the selection container; multiple candidates, corruption, invalidity, or ambiguity fail closed. Reset availability and Nudge availability are independent UI/execution conditions.
- Gate 5 confirmed cross-plugin generated marker contract: Type Adjuster attaches a shared generated marker to the outer Frame on every generation path (horizontal Split, vertical Split, Local Fix Apply). Type Polish reads the ancestor chain of a target TextNode read-only and excludes Type Adjuster-generated output from normal analysis; within a valid Local Fix range, `already-applied` takes priority over `generated-skip`. Type Polish performs no document mutation.
- Scale UI and Local Fix integration regression was Accepted as part of Gate 5. Gate 4 accepted implementation, Gate 4 Integration, Scale UI, and Gate 5 dependencies are resolved. No known unresolved defects remain in Gate 5 scope. Generic Vertical Split Reset and Reset button visual state are not Gate 5 defects or unfinished Gate 5 items; they remain Post-Gate-5 Follow-up Candidates only, not created as Issues by this synchronization.
- Nightly Canonical State Synchronization (2026-07-29, second same-day sync): Two new Issues Architect-Accepted and registered — [asd#31](https://github.com/ga7ming3249/asd/issues/31) (Type Polish — Japanese Horizontal Typography Analysis Track; Open; Product Capability / Parent Coordination Issue; labels `enhancement`, `architecture`, `roadmap`, `product:type-polish`, `priority:P2`) and [figma-os#10](https://github.com/ga7ming3249/figma-os/issues/10) (Type Polish / Type Adjuster User Guide; Open; Documentation / UX Enablement; labels `documentation`, `ux`, `type-polish`, `type-adjuster`, `priority:P1`). `asd#31` begins a new Gate 0–Gate 5 Japanese Horizontal Typography capability track and is not incomplete Gate 5 scope — Gate 5 (Desktop Acceptance) for Japanese Vertical — Standard remains Accepted / Completed / Closed as recorded above. `asd#31` Gate 0 Knowledge Collection may begin before [figma-os#3](https://github.com/ga7ming3249/figma-os/issues/3) is resolved; Utility removal, transfer, or ownership-changing implementation must not begin before figma-os#3 is resolved. Type Polish remains zero-mutation; Type Adjuster retains execution and document-mutation ownership. Architect-Accepted priority order: 1) [figma-os#10](https://github.com/ga7ming3249/figma-os/issues/10) — Type Polish / Type Adjuster User Guide, 2) [figma-os#3](https://github.com/ga7ming3249/figma-os/issues/3) — Type Polish Utility ownership decision, 3) [asd#31](https://github.com/ga7ming3249/asd/issues/31) — Japanese Horizontal Typography Analysis Track. `asd#31` Gate 0 may proceed independently when appropriate, but it is not the current first implementation priority.
- ASD Operations Architecture Improvement — Daily Initialization Workflow v2 ([asd#32](https://github.com/ga7ming3249/asd/issues/32), 2026-08-01): Global Architect initialization is standardized as a five-stage Session Lifecycle (Session Creation → Workspace Validation → Architecture Initialization → Execution → Finalization). GitHub Repository — `docs/asd-state.md`, `docs/figma-os-state.md`, `docs/ROADMAP.md` on the target branch — is now the Canonical Primary Source for Daily Initialization; daily re-upload of Canonical Documents by the Vision Owner is discontinued. Responsibility is split: GitHub Audit (Canonical Documents, Issue/PR state, dependencies, priority) remains a Global Architect responsibility, while Local Synchronization Audit (local branch, local HEAD vs `origin/main`, working tree, staged/unstaged/untracked state) is a Claude Code responsibility — read-only, no auto-remediation, its result passed to the Global Architect as input rather than independently re-verified. Daily Sessions are created inside the ASD Project as new chats named `ASD-YYMMDD`; moving an ordinary chat into the ASD Project afterward is not the standard flow. Start-of-Day status is one of `Ready to Proceed` / `Attention Required` / `Blocked` / `ASD Escalation Required`. The ASD Operations Prompt Library (`asd-prompt-library.html`, a local reference file outside this repository) has been updated accordingly and Accepted in Issue-scoped Architect review; the former separate next-morning-verification prompt is now merged into the ASD Daily Initialization Workflow v2 prompt. `asd#32` remains Open pending Close after this Canonical Documentation Synchronization.
- Gate 0 Completed (2026-07-30): [asd#31](https://github.com/ga7ming3249/asd/issues/31) (Japanese Horizontal Typography Analysis Track) Gate 0 Knowledge Platform is Architecture-Review-Accepted and Finalized. Registered in `ga7ming3249/figma-os` at `references/type-polish/japanese-horizontal-typography/` (commit `8b15f28`, pushed to `figma-os/main`) — `README.md`, `INDEX.md`, `KB-0001` (Illustrator character composition v30.6), Knowledge Base Entry Template v0.2, Rule Catalog v0.1 (Rules HR-001–HR-006, all `Observed`, no `Accepted Rule`) with its template, `architecture-reviews/ARCHITECTURE-REVIEW-GATE0.md`, and `review-records/REVIEW-0001.md`. Original source material (`アキ量設定一覧_2026_v306.pdf`, redistribution/license/official status Unknown/Unconfirmed) stays local-only under `source-local/`, excluded via `.gitignore`, never committed. Result recorded on [asd#31](https://github.com/ga7ming3249/asd/issues/31#issuecomment-5127060715). `asd#31` remains Open as the Parent Coordination Issue. Current Phase: Knowledge Collection. The Knowledge Platform design itself is now Frozen — further work adds Knowledge Base entries (`KB-0002` and later) and accumulates Evidence, not Platform redesign, unless a critical architectural issue is discovered. Next Gate: Gate 1 (Cross-reference & Rule Consolidation).
- Type Adjuster Scale UI synchronization Issue ([figma-os#2](https://github.com/ga7ming3249/figma-os/issues/2)) — Completed / Accepted / Closed (see Nightly Canonical State Synchronization note above); independent Product Improvement, no Gate dependency.
- Type Polish Utility ownership consolidation decision Issue registered ([figma-os#3](https://github.com/ga7ming3249/figma-os/issues/3)) — Product Architecture Decision, remains Open / not started, downstream of figma-os#2 completion before any Utility removal is considered.
- Repository Issue Ownership Reorganization Phase 2 executed (2026-07-22): [asd#3](https://github.com/ga7ming3249/asd/issues/3) transferred to [figma-os#4](https://github.com/ga7ming3249/figma-os/issues/4) (Type Inventory multiline support — not started, Successor Issue method) and closed; [figma-os#2](https://github.com/ga7ming3249/figma-os/issues/2)'s bare `#30` cross-repository references corrected to `ga7ming3249/asd#30`; Repository Issue Ownership Policy adopted (`docs/repository-issue-ownership.md`). See `docs/ASD-Issues-17-24-Architecture-Review-Bundle-2026-07-22.md` for the #17–#24 review bundle.
- Repository Issue Ownership Reorganization Phase 3 executed (2026-07-22): Documentation Migration Epic #13's remaining 8 child Issues (asd#17–#24) received Architecture Review and were Closed — #17, #18, #21, #24 after a limited Product Documentation correction (`figma-os` commit `c9def97`), #19, #20, #22, #23 without correction. `docs/ai-collaboration-contract.md` updated to v0.10 (Publisher role: Codex → Claude Code; Codex: Publisher → Specialist Engineer).
- Reference Assistant established as an independent private repository (2026-07-23): `ga7ming3249/reference-assistant`, baseline `main` commit `f0025cb30acd25948b92abd9e06ff93b4974a15c`, CI baseline verified, stable local clone `/Users/atsushitogami/Developer/reference-assistant`. `asd#4` and `asd#6` migrated to that repository by the Successor Issue method after explicit Vision Owner approval; `asd#5` is retained, unchanged, as closed history.
- Reference Assistant Daily Operation Guide completed (2026-07-23): [reference-assistant#2](https://github.com/ga7ming3249/reference-assistant/issues/2) is Closed / Completed; `docs/daily-operation-guide.md` is merged into `reference-assistant/main` at `9ef507480de209e4910b9e42c38326c47d30890c`.
- Nightly Canonical State Synchronization (2026-07-25, second same-day sync): Reference Assistant Issue #5 — Japan-first Collection Gate and Always-on Content Safety ([reference-assistant#5](https://github.com/ga7ming3249/reference-assistant/issues/5)) is **Completed / Accepted / Closed** (closed 2026-07-25 13:44 JST). PR [reference-assistant#6](https://github.com/ga7ming3249/reference-assistant/pull/6) is **Merged / Closed** — accepted implementation commit `dee933fd2f934314b628f3213025ff8e6efd5bfa`, merged to `reference-assistant/main` at `672cada474240909729d876a882eb455ad44e103`. On 2026-07-25 the implementation passed Architect Review, Independent Technical Review, Delta Review, and Manual Live Validation (using a temporary validation-only Library); automated verification reported `304 passed, 33 warnings, 0 failures`.
- **Canonical Behavior established by reference-assistant#5**: Remote SEARCH's default market is `JP`; Meta Ads uses `country=JP` and Google Ads uses `region=JP` as the default effective market designation, and the Remote Collector no longer implicitly falls back to `US`. Explicit CLI `--market` overrides remain backward-compatible with the existing `country` / `region` settings. Remote SEARCH ingestion now has a collector-independent, shared `Content Safety Boundary`: Content Safety evaluation runs before Dedup (an Architecture Invariant), is **Always-on and Fail Closed**, and cannot be disabled through any supported remote collection option. Fail Closed applies on engine unavailability, initialization failure, evaluation failure, unexpected exception, or an otherwise indeterminate verdict. `unsafe` and unapproved `indeterminate_safety` results do not enter the Canonical Library, and `unsafe` is permanently non-promotable.
- **Human-reviewed Safety Promotion** (adopted as reference-assistant#5's Phase B / Addendum by explicit Vision Owner decision, 2026-07-25) is the formal Promotion Workflow for eligible `indeterminate_safety` results only. A Human Review Approve does not write directly to the Canonical Library — it routes the item back to the Existing Ingest Pipeline, which remains the Canonical Library's sole Single Writer. Market, Safety Counter, and Review Audit History are persisted additively to SQLite; Filesystem as Source of Truth and the existing Single Writer Principle are unchanged. The current `HeuristicSkinRatioEngine` is an `unsafe`-only supplemental signal, not a comprehensive Content Safety Engine — it does not auto-generate `safe` verdicts, and anything it cannot prove safe is classified `indeterminate`.
- **Accepted Limitations** of reference-assistant#5 (not incomplete Issue #5 scope): violence, gore, weapons, contextual harm, advertiser authenticity, semantic understanding, retroactive Safety certification of pre-existing Library content, advanced reviewer authentication, and multi-user permission management. Comprehensive Safety Classification Expansion covering these remains Future Work, not part of Issue #5.
- [reference-assistant#1](https://github.com/ga7ming3249/reference-assistant/issues/1) (Daily Preview Operation) remains Open. Issue #5's completion resolves the safe Collection / Promotion Boundary that was the main recorded Safety Blocker, but Daily Preview resumption is **not automatically decided** by this synchronization — it remains subject to separate Owner-controlled operating conditions.
- Dropbox repository migration (2026-07-25): the Dropbox repository is now the canonical local development repository for `reference-assistant`, superseding the prior `/Users/atsushitogami/Developer/reference-assistant` clone referenced above.
- Reference Assistant Issue #7 — Post-migration Cleanup After Dropbox Development Directory Migration ([reference-assistant#7](https://github.com/ga7ming3249/reference-assistant/issues/7)): Open, independent low-priority maintenance issue. Not remaining Issue #5 work; does not block or gate Issue #5 (now Closed).
- ASD Nightly Canonical Synchronization (2026-08-05): [asd#32](https://github.com/ga7ming3249/asd/issues/32) (Daily Initialization Workflow v2) verified **Closed / Completed** (`2026-08-01T06:31:41Z`). [asd#33](https://github.com/ga7ming3249/asd/issues/33) (Standardize Issue Completion Authority and Operation Directives) registered **Open** (created 2026-08-01) as an Architecture Improvement Issue addressing insufficient separation between Review Decision, Completion, and GitHub Operation. [asd#31](https://github.com/ga7ming3249/asd/issues/31) (Japanese Horizontal Typography Analysis Track) is **Closed** — GitHub's issue timeline shows exactly one close event (`2026-08-05T10:08:05Z`), five seconds after a KB-0005 Knowledge Extraction Complete comment was posted, and **no reopen event exists** anywhere in GitHub's history for this Issue; the original close was not Publisher-verified at the time. Repository verification of Issue #31's stated Knowledge Track scope, against `ga7ming3249/figma-os` `main`, found: KB-0001–KB-0003 registered (commits `8b15f28`, `3d22e8a`, `3f1599e`); **KB-0004 not found** anywhere (no file, no git history on any branch, no Issue comment content); **KB-0005** has an Architecture Review summary posted as an Issue comment claiming Knowledge Extraction Complete, but no corresponding repository file exists. Both KB-0004 and KB-0005 are **Remote Registration Pending** — not registered, no Accepted Commit SHA for either, and Publisher has not created or reconstructed either artifact. Separately, Publisher identified commit `5464a78bf3500475a8855f10cfb8aaa75b9caa39` on `figma-os/main` (2026-08-01, pushed directly with no PR) implementing a read-only Horizontal Analysis Profile — per its commit message: boundary observation (HR-001/HR-002), conflict *detection only* (HR-004, no auto-resolution), and Recommendation generation with execution capability never enabled; no Vertical pipeline, Type Adjuster, Handoff, Marker, or Utility code changed. No Architecture Review record for this commit has been identified. This commit is recorded as **Repository Evidence Identified — Architecture Classification Pending** (not Accepted, not Gate 2/3-satisfying, not Canonical Architecture) and is escalated for Global Architect review. Full detail: Publisher Verification comment on [asd#31](https://github.com/ga7ming3249/asd/issues/31#issuecomment-5190980016) and correction comment on [asd#33](https://github.com/ga7ming3249/asd/issues/33#issuecomment-5190983450). **Nightly Synchronization Final Status: Blocked** — required Canonical Artifacts (KB-0004/KB-0005) for `figma-os` registration are missing, and unclassified repository evidence (commit `5464a78`) requires Global Architect Architecture Classification before full reconciliation.

## Project Phase

Previous: Knowledge Review Phase

↓

Current: **Architecture-gated Implementation Phase**

Current Position: Issue #30 Gate 5 (Desktop Acceptance) — [figma-os#6](https://github.com/ga7ming3249/figma-os/issues/6) Accepted / Completed / Closed (2026-07-29); PR [figma-os#8](https://github.com/ga7ming3249/figma-os/pull/8) merged to `figma-os/main`. Japanese Vertical — Standard / Safe Local Fix MVP Gate 0–Gate 5 are complete; `asd#30` is Closed / Completed as of this Canonical State Synchronization.

Typography Knowledge Base（asd#28, asd#29）を基盤として進行していた Japanese Vertical — Standard の実装（Architecture-gated scoped exception, asd#30）は、Gate 0〜Gate 5をもって完了した。

## Active Issues

| Issue | Plugin | Priority | Status | Summary |
|---|---|---|---|---|
| [#28](https://github.com/ga7ming3249/asd/issues/28) | Type Adjuster / Type Polish | - | Open | Knowledge Review deliverables completed — Japanese Vertical Typography & Latin Kerning knowledge foundation |
| [#29](https://github.com/ga7ming3249/asd/issues/29) | Type Adjuster / Type Polish | - | Open | Knowledge Review deliverables completed — OpenType Typography Features |
| [figma-os#10](https://github.com/ga7ming3249/figma-os/issues/10) | Type Polish / Type Adjuster | `priority:P1` | Open / Architect-Accepted | Type Polish / Type Adjuster User Guide — Documentation / UX Enablement. Canonical source: Markdown in `ga7ming3249/figma-os`. Priority order 1 of 3 |
| [figma-os#3](https://github.com/ga7ming3249/figma-os/issues/3) | Type Polish / Type Adjuster | Medium | Open / Downstream of #2 | Product Architecture Decision — canonical ownership of Utility (Scale/Baseline/Tracking). Depends on figma-os#2 completion before any Utility removal. Priority order 2 of 3 |
| [reference-assistant#1](https://github.com/ga7ming3249/reference-assistant/issues/1) | Reference Assistant | P1 | Open | Daily Preview Operation — Primary Issue, Successor to asd#4. reference-assistant#5's Safety Blocker is resolved (Closed 2026-07-25); Daily Preview resumption is not automatically decided by this synchronization and remains subject to separate Owner-controlled operating conditions |
| [reference-assistant#7](https://github.com/ga7ming3249/reference-assistant/issues/7) | Reference Assistant | - | Open / Maintenance | Post-migration Cleanup After Dropbox Development Directory Migration. Independent low-priority maintenance issue; not remaining reference-assistant#5 work |
| [reference-assistant#3](https://github.com/ga7ming3249/reference-assistant/issues/3) | Reference Assistant | P2 | Open | Design Library Location Selection and Safe Relocation Model — Architecture Issue |
| [asd#33](https://github.com/ga7ming3249/asd/issues/33) | ASD Process | - | Open | Standardize Issue Completion Authority and Operation Directives — Architecture Improvement addressing insufficient separation between Review Decision, Completion, and GitHub Operation, following an unverified KB-0005 review comment that closed asd#31 |

## Architecture Notes

- Vertical Layout Foundation established by Issue #27; Wrapper / Outer responsibility separation and `relayoutVerticalWrapper()` as the single layout entry point are the current design principles.
- Type Polish owns Analysis, Recommendation, User Decision, and Manual Handoff production. Gate 4 adds current-selection-only applied-marker recognition and preserves zero document mutation.
- Type Adjuster owns current-selection validation, explicit Local Fix execution, and final manual adjustment. Gate 4 delivered `LF-UPRIGHT-001`, `LF-ROTATE-RUN-001`, group-member Nudge, and conflict-safe structural Reset. It remains non-judgmental and never becomes an automatic composition engine.
- Transport and execution status: Manual Handoff Transport is Adopted; Safe Local Fix consumption and explicit execution are implemented and accepted on `feature/issue-30-gate4-safe-local-fix` at `dc6361157345ebb8b17264f63aef8fa0e265c5eb`. Real Figma Desktop acceptance (Gate 5) is Accepted / Completed / Closed (2026-07-29, figma-os#6).
- Gate 4 implementation was not present on `figma-os/main@2838450c91429e9bc9c312103e0741c64e0068d2` (figma-os#2 merged 2026-07-24); it is now present on verified `figma-os/main@d3abd4f46ce89240a22a467bbbf712f4c5e10628` via the Gate 5 accepted implementation commit (PR figma-os#8, 2026-07-29).
- `figma-os#2` was implemented against canonical `main@c9def9785e86272c8d21d61f14a500cd8b45793c` and merged via PR [figma-os#7](https://github.com/ga7ming3249/figma-os/pull/7) at `2838450c91429e9bc9c312103e0741c64e0068d2`; Gate 4 was accepted, unmerged, at `dc6361157345ebb8b17264f63aef8fa0e265c5eb`. That lineage and the figma-os#2 `main` lineage were reconciled and combined through the Gate 5 accepted implementation commit `9253ce8ce46dbd02225f9bfa73019f4662f575de`, merged to `figma-os/main` via PR [figma-os#8](https://github.com/ga7ming3249/figma-os/pull/8) at `d3abd4f46ce89240a22a467bbbf712f4c5e10628` (2026-07-29).
- Gate 5 confirmed Local Fix Reset architecture (`retained-original-node`): Reset restores the original TextNode instance rather than reconstructing it, resolves the unique valid Local Fix group from ancestor/descendant relationships among the Local Fix member, outer Frame, and selection container, and fails closed on multiple candidates, corruption, invalidity, or ambiguity. Reset availability and Nudge availability remain independent UI/execution conditions.
- Gate 5 confirmed cross-plugin generated marker contract: Type Adjuster attaches a shared generated marker to the outer Frame on every generation path (horizontal Split, vertical Split, Local Fix Apply); Type Polish reads the ancestor chain read-only and excludes Type Adjuster-generated output from normal analysis, with `already-applied` taking priority over `generated-skip` inside a valid Local Fix range. Type Polish continues to perform zero document mutation.
- Reference Assistant product work belongs in its own Product Repository (`ga7ming3249/reference-assistant`). ASD is used only for cross-product/global governance, not for tracking that product's day-to-day Issues.

## Current main

Verified ASD base main before this State update: `02c5d9ec351ee68fe362e7438bf0e59c9d7569f1`

Verified figma-os main: `5464a78bf3500475a8855f10cfb8aaa75b9caa39` — current `figma-os/main` HEAD as verified 2026-08-05 (Repository fact only; includes commits `8b15f28`/`3d22e8a`/`3f1599e` — KB-0001–KB-0003 registration — and `5464a78` — Horizontal Analysis Profile implementation, **Repository Evidence Identified, Architecture Classification Pending**, see Current Project Overview). Supersedes prior `d3abd4f46ce89240a22a467bbbf712f4c5e10628` (figma-os#6 / PR #8, 2026-07-29), which itself superseded `2838450c91429e9bc9c312103e0741c64e0068d2` (figma-os#2 / PR #7, 2026-07-24).

Gate 4 accepted feature head: `dc6361157345ebb8b17264f63aef8fa0e265c5eb` ([figma-os#5](https://github.com/ga7ming3249/figma-os/issues/5), Closed) — now merged to `figma-os/main` via the Gate 5 accepted implementation commit above

Verified Reference Assistant main: `672cada474240909729d876a882eb455ad44e103` (reference-assistant#5 / PR #6 merged, 2026-07-25; supersedes prior `9ef50748...`)

## Outstanding Work

**figma-os#2 — Completed / Accepted / Closed**

Findings A/B/C from the prior Changes-Required review were corrected. PR [figma-os#7](https://github.com/ga7ming3249/figma-os/pull/7) merged to `figma-os/main` at `2838450c91429e9bc9c312103e0741c64e0068d2` (implementation commit `874d94dbfa4336ab064822e1ccc07ece12795149`), closing figma-os#2. Verified: Build Success, Typecheck Success, Tests 138/138 passed, Desktop Verification All Pass. Gate 4 / Gate 5 lineage (`dc6361157345ebb8b17264f63aef8fa0e265c5eb`) remained separate and unmerged at the time of this record; it was subsequently combined with `figma-os/main` through the Gate 5 accepted implementation commit `9253ce8ce46dbd02225f9bfa73019f4662f575de` (PR [figma-os#8](https://github.com/ga7ming3249/figma-os/pull/8), 2026-07-29 — see Outstanding Work → figma-os#6 below). Cleanup of the isolated worktree/feature branch used during implementation (`feature/issue-2-scale-state-sync`) is optional maintenance only.

**figma-os#6 — Gate 5 Desktop Acceptance — Accepted / Completed / Closed**

Closed `2026-07-29T11:45:25Z` (2026-07-29 20:45:25 JST), state reason Completed. PR [figma-os#8](https://github.com/ga7ming3249/figma-os/pull/8) Merged to `figma-os/main` (base `main`, 7 commits, merged `2026-07-29T11:44:32Z`) — accepted implementation commit `9253ce8ce46dbd02225f9bfa73019f4662f575de`, merge commit `d3abd4f46ce89240a22a467bbbf712f4c5e10628`. Verified: Type Adjuster full suite `278/278 PASS`, Scale UI tests `109/109 PASS`, Gate 4 Local Fix tests `163/163 PASS`, G5-DEF-002 generated marker tests `6/6 PASS`, Type Polish full suite `165/165 PASS`, Type Adjuster build PASS, Type Polish build PASS, Pre-rebase Desktop Acceptance `9/9 PASS` (macOS `26.5.2 (25F84)`, Figma Desktop App `126.6.14`), Rebased-head Desktop Acceptance `7/7 PASS` (macOS `26.5.2 (25F84)`, Figma Desktop App `126.7.10`). Confirms the `retained-original-node` Local Fix Reset architecture and the shared generated marker contract between Type Adjuster and Type Polish (see Architecture Notes above). Scale UI and Local Fix integration regression is Accepted. No known unresolved Gate 5 defects remain; generic Vertical Split Reset and Reset button visual state are not Gate 5 defects and remain Post-Gate-5 Follow-up Candidates only.

**reference-assistant#5 — Completed / Accepted / Closed**

Japan-first Collection Gate and Always-on Content Safety. Closed 2026-07-25 13:44 JST. PR [reference-assistant#6](https://github.com/ga7ming3249/reference-assistant/pull/6) Merged / Closed at `672cada474240909729d876a882eb455ad44e103` (accepted implementation commit `dee933fd2f934314b628f3213025ff8e6efd5bfa`). Passed Architect Review, Independent Technical Review, Delta Review, and Manual Live Validation on 2026-07-25; automated verification `304 passed, 33 warnings, 0 failures`. Establishes JP as the default Remote SEARCH market (Meta Ads `country=JP`, Google Ads `region=JP`, no implicit `US` fallback, explicit `--market` override backward-compatible) and a collector-independent, Always-on / Fail Closed `Content Safety Boundary` evaluated before Dedup. `unsafe` and unapproved `indeterminate_safety` cannot enter the Canonical Library; `unsafe` is permanently non-promotable. Human-reviewed Safety Promotion, adopted as this Issue's Phase B / Addendum by explicit Vision Owner decision (2026-07-25), is the sanctioned Promotion Workflow for eligible `indeterminate_safety` only, and routes Approved items back through the Existing Ingest Pipeline (unchanged Single Writer). Accepted Limitations (violence, gore, weapons, contextual harm, advertiser authenticity, semantic understanding, retroactive Safety certification of the existing Library, advanced reviewer authentication, multi-user permission management) are Future Work, not incomplete Issue #5 scope. Resolves the main recorded Safety Blocker against [reference-assistant#1](https://github.com/ga7ming3249/reference-assistant/issues/1) (Daily Preview Operation), but Daily Preview resumption is not automatically decided by this synchronization.

**reference-assistant#7 — Post-migration Cleanup After Dropbox Development Directory Migration**

Open, independent low-priority maintenance issue. The Dropbox repository is now the canonical local development repository for `reference-assistant`. Not remaining reference-assistant#5 work; does not block or gate reference-assistant#5 (now Closed).

**Issue #30 — Closed / Completed (2026-07-29)**

Completed Gates:

- Gate 0 — Current implementation / transport review
- Gate 1 — Shared Rules + analyzer
- Gate 2 — Type Polish result UI
- Gate 3 — Manual Handoff Transport
- Gate 4 — Safe Local Fix MVP ([figma-os#5](https://github.com/ga7ming3249/figma-os/issues/5), Closed / Completed, accepted at `dc6361157345ebb8b17264f63aef8fa0e265c5eb`)
- Gate 5 — Desktop Acceptance ([figma-os#6](https://github.com/ga7ming3249/figma-os/issues/6), Accepted / Completed / Closed 2026-07-29, PR [figma-os#8](https://github.com/ga7ming3249/figma-os/pull/8) merged at `d3abd4f46ce89240a22a467bbbf712f4c5e10628`)

Japanese Vertical — Standard / Safe Local Fix MVP Gate 0 through Gate 5 are complete. `asd#30` was the Parent Coordination Issue for Architecture Gates, Global Architect Review, completion judgment, and State Synchronization; it is Closed / Completed as of this Canonical State Synchronization, following Gate 5 Vision Owner Acceptance and Issue-scoped Architect Accept recorded on `figma-os#6`. No unresolved Gate blocker remains. Generic Vertical Split Reset and Reset button visual state are not treated as Gate 5 defects or unfinished Gate 5 items; they remain Post-Gate-5 Follow-up Candidates only, pending a future explicit Global Architect or Vision Owner Issue-creation decision.

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

**Daily Initialization Workflow v2** (asd#32, adopted 2026-08-01)

Daily Initialization is not information gathering. It is the step that establishes the Architecture Context the Global Architect uses for the day's decisions.

Session Lifecycle:

```
Session Creation
    ↓
Workspace Validation
    ↓
Architecture Initialization
    ↓
Execution
    ↓
Finalization
```

Daily Session:

- Created inside the ASD Project as a new chat named `ASD-YYMMDD`.
- Moving an ordinary chat into the ASD Project afterward is not the standard flow.

Canonical Primary Source:

- `docs/asd-state.md`, `docs/figma-os-state.md`, `docs/ROADMAP.md` are read directly from GitHub on the target branch.
- Daily re-upload of Canonical Documents by the Vision Owner is discontinued.

Responsibility Boundary:

- Global Architect: GitHub Repository Audit, Canonical Documents read, Issue/PR state, Architecture Assessment, priority and dependency evaluation, Daily Architecture Dashboard generation, State/ROADMAP update decisions.
- Claude Code: Local Synchronization Audit only — local branch, local HEAD, `origin/main`, working tree, staged/unstaged/untracked state. Read-only, no auto-remediation; the result is passed to the Global Architect as input, not independently re-verified by the Architect.

**Daily Initialization**

Required fields:

- Current Date (derived from the current runtime/conversation context — never inherited)
- ASD State Version
- Last ASD State Update
- Current Project Overview
- Today's Priorities
- Blockers
- Recommended First Action
- Start-of-Day Status: `Ready to Proceed` / `Attention Required` / `Blocked` / `ASD Escalation Required`

After Daily Initialization completes, the normal Morning Brief continues.

Returns

- Current project overview
- Today's priorities
- Blockers

Ref: asd#8, asd#32

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
