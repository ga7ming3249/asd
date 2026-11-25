# ASD State

- Version: 51
- Date: 2026-11-25
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

### Type Polish Freeze Governance Synchronization — 2026-08-21

Accepted [asd#35](https://github.com/ga7ming3249/asd/issues/35) is the superseding Architecture authority over the existing Type Polish no-feature-addition Freeze **solely for the Accepted Preset Platform Product Development track**:

`figma-os#17 → figma-os#18 → figma-os#19`

This is a scoped exception, not a general lifting of the Type Polish Freeze. The general Type Polish Freeze remains in force outside this track.

- [figma-os#17](https://github.com/ga7ming3249/figma-os/issues/17) remains **Accepted / Completed / Closed** under this authority and requires no re-review, revert, or reclassification. The previously missing explicit Freeze-supersession record is classified as an **Architecture governance / documentation gap**, not an implementation defect.
- [figma-os#18](https://github.com/ga7ming3249/figma-os/issues/18) and [figma-os#19](https://github.com/ga7ming3249/figma-os/issues/19) may rely on this exception only within their respective Accepted Issue scopes and only for Type Polish source, persistence, validation, UI, and directly supporting changes necessary to implement the Accepted asd#35 Preset Platform Architecture.
- This authority does **not** automatically extend to [figma-os#20](https://github.com/ga7ming3249/figma-os/issues/20), Japanese Horizontal productionization, general Mixed Japanese–Latin implementation, Latin typography, OpenType expansion, future Type Polish capability tracks, Type Adjuster ownership changes, reintroduction of Scale / Baseline / Tracking Utility into Type Polish, or unrelated Type Polish features. Separate Architecture Authorization is required where applicable.
- The independent `time` preset discrepancy remains unresolved: documentation `80%`, shipped runtime `65%`, Canonical production value `Unknown`. This Freeze Governance Decision does not authorize production `time` `PresetRevision` creation, activation, or legacy binding.

**Publication execution note:** this Canonical synchronization was explicitly authorized by the Vision Owner and executed through the ASD Proxy Execution path because Claude Code's execution boundary prevented it from writing a governance change affecting its own future operating constraints. Claude Code remains the assigned Publisher / Primary Engineer and resumes responsibility after read-only verification of the published Canonical state.

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
- ASD Operations Architecture Improvement — Daily Initialization Workflow v2 ([asd#32](https://github.com/ga7ming3249/asd/issues/32), 2026-08-01): Global Architect initialization is standardized as a five-stage Session Lifecycle (Session Creation → Workspace Validation → Architecture Initialization → Execution → Finalization). GitHub Repository — `docs/asd-state.md`, `docs/figma-os-state.md`, `docs/ROADMAP.md` on the target branch — is now the Canonical Primary Source for Daily Initialization; daily re-upload of Canonical Documents by the Vision Owner is discontinued. Responsibility is split: GitHub Audit (Canonical Documents, Issue/PR state, dependencies, priority) remains a Global Architect responsibility, while Local Synchronization Audit (local branch, local HEAD vs `origin/main`, working tree, staged/unstaged/untracked state) is a Claude Code responsibility — read-only, no auto-remediation, its result passed to the Global Architect as input rather than independently re-verified. Daily Sessions are created inside the ASD Project as new chats named `ASD-YYMMDD`; moving an ordinary chat into the ASD Project afterward is not the standard flow. Start-of-Day status is one of `Ready to Proceed` / `Attention Required` / `Blocked` / `ASD Escalation Required`. The ASD Operations Prompt Library (`asd-prompt-library.html`, managed under a separate Canonical Repository — see the Canonical Source registration below, 2026-08-07) has been updated accordingly and Accepted in Issue-scoped Architect review; the former separate next-morning-verification prompt is now merged into the ASD Daily Initialization Workflow v2 prompt. `asd#32` remains Open pending Close after this Canonical Documentation Synchronization.
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
- ASD Canonical State Synchronization (2026-08-07): [asd#34](https://github.com/ga7ming3249/asd/issues/34) (Review and Classify Repository Evidence Commit 5464a78) is **Closed / Completed** (`2026-08-07T09:03:45Z`, state reason Completed; Issue-scoped Architect final result: Accepted). This resolves the commit-`5464a78` portion of the 2026-08-05 Nightly Synchronization Blocked status recorded above: Repository Evidence Classification for that commit is now **Complete**. Canonical Architecture Classification: **Experimental**; **Accepted Commit: No**. Repository Status: Verified Repository Evidence. Functional Implementation Scope: Gate 2 + partial Gate 3 equivalent (a functional-scope classification only, not Gate Acceptance). Canonical Gate Acceptance remains **Gate 0 only** — Gate 1, Gate 2, and Gate 3 Acceptance are each explicitly recorded as **Not established**, not retroactively marked complete. Read-only / zero-mutation: Verified by available static and test evidence (no live Figma Desktop / Gate 5 acceptance was performed by this Issue). Recommendation Scope: present, non-executable. Rule Promotion: **None** — HR-001–HR-006 remain unchanged Rule Candidates in Rule Catalog v0.2. Utility Ownership Change: **None identified**. Freeze Compliance: **Not established** — the pre-existing Type Polish no-feature-addition Freeze (`CLAUDE.md`, in effect since 2026-06-27) predates the commit, and no exception or superseding Architecture Decision was found; this synchronization does not reinterpret or remove the Freeze. Immediate Revert: **Not required** by Issue #34; any future modification or removal requires a separate authorized Architecture/implementation decision. Canonical publication commit: [`031887cbf1b65336682212f13df3d609ce46267a`](https://github.com/ga7ming3249/figma-os/commit/031887cbf1b65336682212f13df3d609ce46267a), recording `references/type-polish/japanese-horizontal-typography/architecture-reviews/ARCHITECTURE-REVIEW-COMMIT-5464A78.md`, `references/type-polish/japanese-horizontal-typography/review-records/REVIEW-0002.md`, and a corresponding `type-polish/HISTORY.md` entry. Process findings from Issue #34 were provided to [asd#33](https://github.com/ga7ming3249/asd/issues/33#issuecomment-5215025080) (Standardize Issue Completion Authority and Operation Directives) as process evidence only — Issue #33 itself remains Open and its own process-standardization conclusions are not decided or adopted as Global Rule by this synchronization. This synchronization does **not** resolve the KB-0004 / KB-0005 Remote Registration Pending status recorded 2026-08-05 above, which remains outstanding and was out of Issue #34's scope. Any further ASD State consequence of this classification (beyond this Repository-fact record) remains a decision for the ASD Global Architect.
- ASD Operations Prompt Library — Canonical Source registered (2026-08-07): The ASD Operations Prompt Library (`asd-prompt-library.html`, referenced in the [asd#32](https://github.com/ga7ming3249/asd/issues/32) record above) is Canonically managed in its own repository, `ga7ming3249/asd-operations` (`main` branch, file `asd-prompt-library.html`) — not as a local file outside any repository's management. Verified Commit: `f3837c992bb7dea82c859c67454e1372683a3279`. Status: P0 / P1 / P2 **Completed / Accepted**. Verified `.user-input` count: **18** (matches expectation). Local copies of this HTML file are Pull-synced viewing copies of GitHub `main`, not a Canonical Source in their own right. GitHub Pages is not published for `ga7ming3249/asd-operations` (`has_pages: false`, verified 2026-08-07).
- ASD Canonical State Synchronization (2026-08-18): [figma-os#3](https://github.com/ga7ming3249/figma-os/issues/3) (Product Decision — Consolidate Type Polish Utility Ownership into Type Adjuster) is **Accepted / Completed / Closed** (`state_reason: COMPLETED`, closed `2026-08-18T05:03:24Z`; Issue-scoped Architect final result: Accepted). Architecture Decision comment: [figma-os#3#issuecomment-5323799447](https://github.com/ga7ming3249/figma-os/issues/3#issuecomment-5323799447). **Canonical ownership of manual typography adjustment (Scale / Baseline / Tracking) is Type Adjuster.** Type Polish's existing Utility (Scale/Baseline/Tracking preset controls in `code.ts`/`ui.html`) is reclassified as a **Legacy Compatibility Capability Pending Migration/Removal** — **immediate removal remains prohibited**. Utility Ownership is removed from Decisions Pending in `figma-os-state.md` as of this synchronization. Four follow-up Issues were created in `ga7ming3249/figma-os` and remain Open: [figma-os#12](https://github.com/ga7ming3249/figma-os/issues/12) (Plain-node Manual Adjustment Strategy), [figma-os#13](https://github.com/ga7ming3249/figma-os/issues/13) (Manual Adjustment Migration — **contingent** on #12's determination, not an unconditional implementation commitment), [figma-os#14](https://github.com/ga7ming3249/figma-os/issues/14) (Utility Ownership Documentation Migration), and [figma-os#15](https://github.com/ga7ming3249/figma-os/issues/15) (Utility Deprecation / Removal — **Blocked** on #12, #13 if applicable, #14, and regression/Desktop verification; not to be front-run). Dependency order: #12 → #13 (if applicable) → #14 → #15. The pre-existing Type Polish no-feature-addition Freeze (`CLAUDE.md`) is **not** lifted generally; figma-os#3 is recorded as superseding authority **only** for the Utility deprecation/removal migration tracked by #12–#15, and for no other Type Polish change. **This synchronization is not an Implementation Authorization** — figma-os#3's closure does not by itself authorize removing Type Polish Utility. The next Architecture Dependency is [figma-os#12](https://github.com/ga7ming3249/figma-os/issues/12). Separately, figma-os#3's resolution does not remove the need for [figma-os#10](https://github.com/ga7ming3249/figma-os/issues/10) (Type Polish / Type Adjuster User Guide, still Open) — #10 now additionally needs to reflect the new ownership model, and its scope must be coordinated with #14 to avoid documentation-migration overlap (#14 owns the Utility-ownership-model documentation change itself; #10 owns the overall User Guide incorporating it).
- Vision Owner Priority Synchronization (2026-08-18, third sync): Current priority Figma OS plugins, in order: 1) Type Polish, 2) Type Adjuster, 3) Type Inventory, 4) Color Inventory. **Type Polish completion is the top-level Product Goal.** Type Adjuster is already mature enough for daily production use on its own, but Figma OS's product strength is realized by the Type Polish (typography judgment: store/reuse, finishing) + Type Adjuster (execution, manual fine-tuning) pairing. **Type Polish must not be treated as a Japanese-Vertical-only plugin** — its Canonical Product Identity is to store and reuse typography judgment and semi-automate finishing work (和欧補正・日付・時刻・約物), with future expansion into Japanese Horizontal / Mixed Japanese–Latin / Latin typography; Japanese Vertical being currently the most advanced capability is an implementation-phase state, not a Product Scope limitation. [figma-os#12](https://github.com/ga7ming3249/figma-os/issues/12) remains the unchanged immediate Next Architecture Dependency, now explicitly framed as part of completing the Type Polish / Type Adjuster product architecture rather than an isolated Type Adjuster-only objective. **This synchronization does not**: reopen [asd#31](https://github.com/ga7ming3249/asd/issues/31), close [asd#28](https://github.com/ga7ming3249/asd/issues/28), authorize any new implementation, change runtime code, skip figma-os#12, or auto-authorize Horizontal/Latin implementation work. asd#28 / asd#31 and the unresolved Japanese Horizontal / Mixed Japanese–Latin / Latin typography capability work require roadmap reconciliation — recorded as a new Decisions Pending item in `figma-os-state.md` ("Type Polish Capability Roadmap Reconciliation") and in `docs/ROADMAP.md` → Future → "Type Polish Capability Roadmap Reconciliation". No `figma-os` product repository commit was made by this synchronization.
- ASD Canonical State Synchronization (2026-08-18, second sync): [figma-os#10](https://github.com/ga7ming3249/figma-os/issues/10) (Type Polish / Type Adjuster User Guide) is **Accepted / Completed / Closed** (`state_reason: COMPLETED`, closed 2026-08-18; Issue-scoped Architect final result: Accepted; completion comment [figma-os#10#issuecomment-5327103969](https://github.com/ga7ming3249/figma-os/issues/10#issuecomment-5327103969)). Canonical User Guide delivered as Markdown under `docs/user-guides/` in `ga7ming3249/figma-os` (`type-polish.md`, `type-adjuster.md`, `type-polish-type-adjuster-workflow.md`, `glossary.md`, `faq.md`), with navigation added from `README.md`, `PLUGINS.md`, and both plugin `README.md` files. Documentation-only — no runtime source, tests, or `docs/shared/handoff-schema.md` changes. Accepted `figma-os/main` HEAD is now `d3ebb1c33ea3d4c4824504309ffe349693556a92` (baseline `031887c` → `423e605` initial User Guide → `d3ebb1c` Accepted correction clarifying that Type Polish's zero-mutation scope is Document Content only, not the Local Fix Handoff shared-metadata write). Incorporates the figma-os#3 canonical ownership model: Scale/Baseline/Tracking canonical owner is Type Adjuster; Type Polish's own Utility panel is documented as Legacy Compatibility Capability Pending Migration/Removal, never described as a current owner. Verified: Type Polish tests 243/243, Type Adjuster tests 278/278 (via `tsx`), scoped typechecks clean, full link/anchor check clean, UI labels cross-checked verbatim, Retained Original / generated-structure wording verified against Gate 5 G5-DEF-001/G5-DEF-002 (original TextNode retained, never removed). Follow-up candidates recorded but **not** implemented under figma-os#10: `docs/shared/handoff-schema.md` Gate 4/Gate 5 wording drift, `type-adjuster/HISTORY.md` Gate 3/4/5 history gap, Type Adjuster test-runner ergonomics. figma-os#10 no longer occupies Priority 1 in the execution order recorded 2026-07-29 above; Recommended First Action moves to [figma-os#12](https://github.com/ga7ming3249/figma-os/issues/12) (Next Architecture Dependency). A separate Presentation/Distribution-layer Issue (self-contained offline HTML copy of the accepted User Guide, for Dropbox viewing) was registered in `ga7ming3249/figma-os`; by explicit State Update Decision, that Issue's registration is not itself a target of this State/ROADMAP synchronization.
- ASD Canonical State Synchronization (2026-08-19): [figma-os#12](https://github.com/ga7ming3249/figma-os/issues/12) (Type Adjuster — Plain-node Manual Adjustment Strategy) is **Accepted / Completed / Closed** (Issue-scoped Architect final result: Accepted). Architecture Decision comment: [figma-os#12#issuecomment-5336743790](https://github.com/ga7ming3249/figma-os/issues/12#issuecomment-5336743790). **Disposition: Discontinue** for all three capabilities — Scale, Baseline, Tracking — on plain/ungenerated TextNode: Type Adjuster's selection resolver will **not** be extended to accept plain TextNodes for these. **Not** a decision to discontinue the Type Polish plugin/product. Evidence: repository Evidence Collection established the Split-anchored vs. plain-TextNode semantic differences between Type Adjuster and Type Polish's legacy Utility; usage frequency of the legacy Utility could not be determined from repository evidence alone (`Unknown`). Vision Owner then supplied direct current-workflow evidence: fine adjustment already goes through Split → Type Adjuster once needed; plain TextNode is used for a separate, unaffected capability — per-range font assignment (mixed JP/EN, Mincho/Gothic mixing). **New Canonical Product Boundary**: Type Polish = preset-based typography preparation/composition; Type Adjuster = individual fine typography adjustment on generated (post-Split) structure; canonical workflow `Text Layer → Type Polish → Type Adjuster (Split → fine adjustment)` — a role-division description, not a mandate that every Text Layer passes through Type Polish. Reaffirms, does not reopen, figma-os#3's Canonical Ownership decision. Immediate Utility removal remains prohibited (figma-os#3); Type Polish Capability Roadmap Reconciliation is not decided by this Decision. [figma-os#13](https://github.com/ga7ming3249/figma-os/issues/13) (Manual Adjustment Migration) is **Closed / Not Planned** — comment [figma-os#13#issuecomment-5336745232](https://github.com/ga7ming3249/figma-os/issues/13#issuecomment-5336745232) — carrying no independent scope once figma-os#12 decided Discontinue for all three capabilities; no implementation was started. The Type Polish Utility Ownership Migration Chain dependency order is now **`#14 → #15`** (was `#12 → #13 if applicable → #14 → #15`); [figma-os#14](https://github.com/ga7ming3249/figma-os/issues/14) is the current next step, not yet started. A follow-up candidate (Type Adjuster Split-target selection UX friction) was recorded in the figma-os#12 closing comment for future Architect/Vision Owner scoping — no new GitHub Issue was created, and it is not added to `figma-os-state.md` or `ROADMAP.md` by this synchronization. This synchronization does not implement figma-os#14/#15, remove Type Polish Utility code, decide Type Polish Capability Roadmap Reconciliation, or make any `ga7ming3249/figma-os` product repository commit — both Issue actions were GitHub comment/close operations via `gh`; `figma-os/main` HEAD is unchanged at `d3ebb1c33ea3d4c4824504309ffe349693556a92`.
- ASD Canonical State Synchronization (2026-08-19, second sync): [figma-os#14](https://github.com/ga7ming3249/figma-os/issues/14) (Type Polish / Type Adjuster — Utility Ownership Documentation Migration) is **Accepted / Completed / Closed** (`state_reason: COMPLETED`, closed `2026-08-19T06:11:42Z`; Issue-scoped Architect final result: Accepted). Completion comment: [figma-os#14#issuecomment-5338253440](https://github.com/ga7ming3249/figma-os/issues/14#issuecomment-5338253440). Accepted implementation commit `f2555451c3423960478792b7e1562e5bff86f01e` on `figma-os/main` (fast-forward from `d3ebb1c33ea3d4c4824504309ffe349693556a92`) — documentation-only, exactly `type-polish/README.md` (+4 lines) and `type-adjuster/README.md` (+2 lines) changed. `type-polish/README.md` gained a "Utilityパネルの位置づけ（Ownership）" subsection (Utility = Legacy Compatibility Capability; Canonical Owner = Type Adjuster per figma-os#3; not yet removed, tracked by figma-os#15; explicitly not a Type Polish deprecation). `type-adjuster/README.md` gained a "Scale / Baseline / TrackingのCanonical Owner" line (Type Adjuster = Canonical Owner; Type Polish's panel = Legacy Compatibility only). Audit: the figma-os#10 User Guide was checked against the figma-os#12 Product Boundary and required no changes — already correct, and its workflow diagram already documents cases that end at Type Polish (not a mandatory pipeline). `ROADMAP.md` had no stale language. Verified no runtime/source files changed, no Utility code/UI removed, no plain TextNode behavior changed, no ASD State changed by the Issue itself; local HEAD == `origin/main` == `f2555451...`, working tree clean. **This closure is not an Implementation Authorization for figma-os#15.** The Type Polish Utility Ownership Migration Chain dependency order is now **`#15`** only (was `#14 → #15`); figma-os#15 is unblocked on documentation but requires its own new Issue-scoped Architect session (fresh Specification, baseline, prerequisites, regression/Desktop-verification check) before any implementation. This synchronization does not implement figma-os#15, remove Type Polish Utility code, or decide Type Polish Capability Roadmap Reconciliation. figma-os#14's own commit/push and completion-comment/close operations were made as part of that Issue's own Publisher workflow, prior to this synchronization; `figma-os/main` HEAD is unchanged by this synchronization at `f2555451c3423960478792b7e1562e5bff86f01e`.
- ASD Canonical State Synchronization (2026-08-20): [figma-os#15](https://github.com/ga7ming3249/figma-os/issues/15) (Type Polish / Type Adjuster — Utility Deprecation / Removal) is **Accepted / Completed / Closed** (`state_reason: COMPLETED`, closed `2026-08-20T06:14:08Z`). Accepted implementation commit `d08b39b03403c3e55bf9948f871e350b245878da` on `figma-os/main` (previous HEAD `f2555451c3423960478792b7e1562e5bff86f01e`) — removes the legacy Scale/Baseline/Tracking Utility (`applyScale`/`applyBaseline`/`applyTracking` and its UI block) from `type-polish/code.ts`/`ui.html`, and updates `type-polish/HISTORY.md`; no `type-adjuster/**` changes. Prerequisites verified satisfied: figma-os#12, #13, #14 (all Accepted/Closed as recorded above), and Prerequisite 4 (Regression/Desktop verification) — `npm run build`/`typecheck`/`test` all PASS (243/243), post-removal Figma Desktop regression 5/5 Pass (Utility removal, Preset + Update, Japanese Vertical Analyze, Japanese Horizontal Analyze, Local Fix Handoff). **The Type Polish Utility Ownership Migration Chain (figma-os#12 → #13 → #14 → #15) is now complete** — no remaining chain steps. **Type Adjuster remains Canonical Owner of Scale/Baseline/Tracking (figma-os#3) — unchanged, not newly decided by this closure. Type Polish itself remains active and is not deprecated** — preset preparation/apply/update, Japanese Vertical/Horizontal analysis, and Local Fix Handoff remain active. figma-os#15's own ASD Canonical State update was explicitly recorded as out of scope for its closure and is performed by this synchronization. Two new ASD Parent Architecture Issues were verified as real (opened 2026-08-20 by the Vision Owner's account, `ga7ming3249`, via `gh issue view`) and are registered here, having been created by the Architect acting as an authorized proxy and explicitly authorized by the Vision Owner in the ASD Daily Session: [asd#35](https://github.com/ga7ming3249/asd/issues/35) (Type Polish — Preset Platform & Product Development — Product Development Parent Architecture Track, primary) and [asd#36](https://github.com/ga7ming3249/asd/issues/36) (Type Polish — Typography Knowledge & Preset Lifecycle — Knowledge Growth Parent Architecture Track, parallel supporting track). Intended relationship: Knowledge Track (asd#36) → Accepted Rule/Preset Proposal → Product Track (asd#35) → Issue-scoped Implementation → Verification → Feedback to Knowledge. asd#35/asd#36 replace figma-os#15 as Recommended Next Action / Development Focus in `figma-os-state.md`. **This synchronization does not authorize**: new Type Polish runtime implementation, Japanese Horizontal implementation, Latin implementation, or any Type Adjuster ownership change — asd#35/#36 registration is architecture-track setup only. No further `figma-os` product repository commit was made by this synchronization itself; `figma-os/main` HEAD is unchanged at `d08b39b03403c3e55bf9948f871e350b245878da`.
- ASD Canonical Synchronization (2026-08-21): [figma-os#17](https://github.com/ga7ming3249/figma-os/issues/17) (Preset Platform Foundation) is **Accepted / Completed / Closed** (Issue-scoped Architect final result: Accepted). Final relevant commit: `a96ad202337ba72d9732b75e169cc2ba807e71ec` on `figma-os/main` (three commits on top of `d08b39b03403c3e55bf9948f871e350b245878da`: `0c211feab00fe0d957d600adb3a5342289ee9c7d` Foundation implementation, `115fee7a7397ec76dc5886c231aa34d78c391db5` test-only `debugCorrupt` op, `a96ad202337ba72d9732b75e169cc2ba807e71ec` fix exposing it in the debug harness UI). **Preset Platform Foundation is now Implemented**: `PresetIdentity`/`PresetRevision`, `PresetOrigin`/`PresetProvenance`, independent identity lifecycle (Active/Deprecated/Retired) and revision status (Draft/Active/Superseded/Deprecated), Registry persistence (`figma.clientStorage`), `PresetApplicationSnapshot` and `TypePolishInstanceMetadata` (separate document pluginData keys), fail-closed typed validation, independently-versioned registry/document schema migration infrastructure, immutable released-revision semantics, explicit Publish / Detect Update / Apply Update separation (Detect and Apply create no revision and mutate no Registry/document state beyond the explicitly targeted document), Deprecated/Retired lifecycle resolution (existing bound documents remain usable from their persisted snapshot; Deprecated blocks brand-new Apply only; Retired additionally excludes from browse), and a same-lineage, non-destructive Merge foundation (human-reviewed, no automatic cross-identity/three-way merge). Verified: Type Polish full suite 306/306 PASS (243 pre-existing + 63 new Foundation tests), Gate 3 Handoff 54/54 PASS, Gate 4 applied-marker 18/18 PASS, typecheck/build clean, and **Figma Desktop Acceptance Cases 1–9 all PASS** (Figma Desktop App `126.7.10`, macOS `14.8.5 (23J423)`), executed live by the Vision Owner with concrete evidence (presetId/revisionId lineage, revision counts before/after, document snapshot bindings) recorded on the Issue. **Boundaries preserved**: Type Adjuster remains Canonical Owner of Scale/Baseline/Tracking; Type Polish's legacy Utility remains absent (not reintroduced); zero-mutation analysis and the existing Local Fix Handoff boundary are unchanged; existing wao/date/time/yakumono production behavior was not migrated onto the Platform or intentionally changed. **Known Discrepancies remain unresolved, not resolved by this synchronization**: (1) stale Type Polish README Utility-removal wording; (2) time preset documentation `80%` vs. runtime `65%` — Canonical behavior remains **Unknown**, blocker remains owned by [figma-os#18](https://github.com/ga7ming3249/figma-os/issues/18); (3) legacy `updatePolish()` unguarded `JSON.parse` remains untouched. **Product sequencing**: figma-os#17 is complete; [figma-os#18](https://github.com/ga7ming3249/figma-os/issues/18) (Existing Capability Migration / Reference) is now the next Product implementation dependency; [figma-os#19](https://github.com/ga7ming3249/figma-os/issues/19) (Preset Management UI) remains downstream; each still requires its own Issue-scoped Architect authorization before implementation. [asd#36](https://github.com/ga7ming3249/asd/issues/36) remains the parallel Knowledge track, unaffected. **New Product Architecture / Rule Standardization Issue registered**: [figma-os#20](https://github.com/ga7ming3249/figma-os/issues/20) (Type Polish — Typography Rule & Spacing Standardization, verified via `gh issue view`, opened 2026-08-21 by the Vision Owner's account) — created from figma-os#17 Desktop Acceptance observations (wao Japanese/Latin boundary spacing, time `:` spacing, yakumono's narrower-than-general-usage hard-coded bracket set, and reliance on undocumented fixed spacing values), addressing **pre-existing** typography-rule ambiguity, **not** a figma-os#17 regression; it does not automatically block all of figma-os#18; it must not resolve the time `80%`/`65%` discrepancy by assumption; it coordinates with [asd#36](https://github.com/ga7ming3249/asd/issues/36) for source/evidence work; and its registration authorizes no runtime implementation by itself. **This synchronization does not authorize**: figma-os#18 implementation, figma-os#19 implementation, figma-os#20 runtime changes, Japanese Horizontal productionization, Latin/OpenType implementation, or any Type Adjuster ownership change.
- ASD Canonical State Synchronization (2026-08-20, second sync — asd#35 Architecture Completion): [asd#35](https://github.com/ga7ming3249/asd/issues/35) (Type Polish — Preset Platform & Product Development) is **Accepted / Completed / Closed** (`state_reason: COMPLETED`, Issue-scoped Architect final result: Accepted — Close Authorized). Closing comment: [asd#35#issuecomment-5354946773](https://github.com/ga7ming3249/asd/issues/35#issuecomment-5354946773). Product Architecture work is complete; **the Preset Platform Architecture is now established as the Canonical Type Polish product architecture** — asd#35 no longer presents as pending Architecture work anywhere in this document, `figma-os-state.md`, or `ROADMAP.md`. **Canonical Type Polish Product Architecture**: Type Polish is a Preset-based Typography Product Platform, with stable Preset identity, versioned content revisions, independently versioned schemas, provenance, and lifecycle state modeled as distinct responsibilities; document application state (`PresetApplicationSnapshot`) is distinct from runtime instance metadata (`TypePolishInstanceMetadata`); existing documents never silently update when a Preset changes — Update Available detection is read-only, and Apply Update is explicit and binds/re-resolves against an already-published revision without creating a new revision; Built-in / Recommended / User-created origins remain distinct; editing an Active User-created Preset creates the next revision under the same identity, while editing Built-in / Recommended creates a new User-created identity/fork; Supersede / Deprecate are non-destructive; Merge policy is human-reviewed and non-destructive, and Merge UI remains Deferred; Knowledge changes never automatically promote to runtime Presets — only an explicit Preset Change Proposal / Product Issue flow does so; Product evidence may feed back into Knowledge only through explicit records. **Type Adjuster remains Canonical Owner of Scale/Baseline/Tracking; Type Polish's analysis zero-mutation and the existing Local Fix Handoff boundary remain preserved** — all unchanged by this Architecture. **Follow-up Product Issues registered** in `ga7ming3249/figma-os`, with Architecture sequencing 1) [figma-os#17](https://github.com/ga7ming3249/figma-os/issues/17) (Preset Platform Foundation) 2) [figma-os#18](https://github.com/ga7ming3249/figma-os/issues/18) (Existing Capability Migration / Reference) 3) [figma-os#19](https://github.com/ga7ming3249/figma-os/issues/19) (Preset Management UI) — **registration is not simultaneous implementation authorization**; each requires its own Issue-scoped execution/review process. **Capability Classification** (none promoted beyond the status listed): Japanese Vertical — Accepted Production Capability, primary migration/reference capability; existing wao mixed-font correction — narrow Accepted Production behavior; Japanese Horizontal — Experimental Repository Evidence / Gate 0 only; complete Mixed Japanese–Latin — Planned but Unimplemented; Latin typography — Planned but Unimplemented; OpenType — Knowledge/Rule Evidence; [asd#28](https://github.com/ga7ming3249/asd/issues/28) — Knowledge/Rule Evidence; [asd#31](https://github.com/ga7ming3249/asd/issues/31) — Experimental Repository Evidence + Gate 0 supporting infrastructure. **Known Discrepancies preserved as unresolved** (not resolved by this synchronization): (1) stale Type Polish README Utility-removal wording; (2) time preset documentation `80%` vs. runtime `65%` — **Canonical behavior: Unknown**, blocker owned by [figma-os#18](https://github.com/ga7ming3249/figma-os/issues/18); (3) legacy `updatePolish()` unguarded `JSON.parse` — the new Platform architecture requires fail-closed validation, legacy remediation remains conditional unless required by implementation/migration scope. **Recommended Next Product Action** replaces asd#35 as the active Product Architecture action: the Recommended Product implementation sequence begins with [figma-os#17](https://github.com/ga7ming3249/figma-os/issues/17) (Foundation); [figma-os#18](https://github.com/ga7ming3249/figma-os/issues/18) remains downstream of #17; [figma-os#19](https://github.com/ga7ming3249/figma-os/issues/19) consumes the Foundation and coordinates with migration state. [asd#36](https://github.com/ga7ming3249/asd/issues/36) remains the parallel Typography Knowledge & Preset Lifecycle Architecture Track, unaffected. **Deferred / Future, explicitly unauthorized**: Japanese Horizontal productionization, general Mixed Japanese–Latin, Latin typography, OpenType capability, Merge UI, import/export. **This Canonical synchronization does not itself authorize implementation of figma-os#17/#18/#19** — it records the Accepted Architecture and roadmap only. No `figma-os` product repository commit was made by this synchronization; `figma-os/main` HEAD is unchanged at `d08b39b03403c3e55bf9948f871e350b245878da`.
- ASD Nightly State Synchronization (2026-08-22): [figma-os#18](https://github.com/ga7ming3249/figma-os/issues/18) (Existing Capability Migration / Reference, Japanese Vertical Primary) is **Accepted / Completed / Closed** (Issue-scoped Architect final result: Accepted). Accepted implementation/instrumentation commit `22044e05ba26c43474ca5a01669b38483f293bdb` on `figma-os/main`. **Legacy `wao`/`date`/`yakumono` migration onto the #17 Preset Platform Foundation is implemented**, and "Japanese Vertical — Standard" is registered on the Platform as a reference/Built-in entry with its existing read-only analysis/regression behavior confirmed unchanged. Verified: Type Polish full suite `354/354` PASS, typecheck/build clean, and **Vision Owner Figma Desktop Acceptance `7/7` PASS** (legacy wao / legacy date / legacy yakumono / corrupt legacy metadata fail-closed / repeated recognition idempotency / production `time` Hard Block / Japanese Vertical read-only regression). Fail-closed and idempotent migration behavior is verified, including partial-write rollback and partial-state detection/recovery; legacy `META_KEY` metadata retention is preserved on every migrated document. **Production `time` remains explicitly excluded**: no production `time` `PresetRevision` was created, activated, or bound to any legacy instance; the independent blocker (documentation `80%` vs. shipped runtime `65%`, Canonical production value `Unknown`) remains unresolved — not resolved by this synchronization. **Next Product implementation step: [figma-os#19](https://github.com/ga7ming3249/figma-os/issues/19)** (Preset Management UI). **[figma-os#21](https://github.com/ga7ming3249/figma-os/issues/21)** (Type Adjuster — Node 24 test-runner compatibility, opened 2026-08-22 by the Vision Owner's account, verified via `gh issue view`) is registered as an **independent Type Adjuster test-infrastructure maintenance follow-up — it does not block figma-os#19**. The existing Type Polish Freeze exception remains scoped solely to `figma-os#17 → #18 → #19`, unchanged and not broadened by this synchronization. This synchronization does not resolve the `time` `80%`/`65%` discrepancy, reopen or re-review figma-os#18, or alter figma-os#19 scope.
- ASD Nightly Canonical State Synchronization — Operations Follow-up (2026-08-22): [asd-operations#1](https://github.com/ga7ming3249/asd-operations/issues/1) (ASD Prompt Library — Nightly Integration → Canonical Sync flow refinement) registered **Open** (created `2026-08-22T03:50:34Z` by the Vision Owner's account, verified via `gh issue view`), in `ga7ming3249/asd-operations`. An ASD Operations / Prompt Library workflow-improvement Issue, created from a 2026-08-22 operational finding that the Nightly handoff between the Prompt Library's Section 14 (Nightly Issue Handoff Packet integration in ASD), Section 15 (Canonical synchronization instruction for CC), and Section 16 (Canonical synchronization verification in ASD) is ambiguous: Section 14 already asks the ASD Global Architect to generate an executable `Instructions for CC` block, while Section 15 is labeled as directly copyable into CC despite containing unresolved placeholders (`[Issue番号]`, `[commit SHA]`, `[確定事実として追記または変更する内容]`, `[コミットメッセージ]`, etc.). When the unfilled Section 15 template was sent directly to CC on 2026-08-22, **CC correctly stopped rather than inferring Issue numbers, commit SHAs, Canonical facts, or a commit message — no repository mutation resulted.** Intended correction (Issue scope, not yet implemented): `Issue Handoff Packets → ASD Nightly Integration → ASD generates a fully-resolved / placeholder-free CC instruction → CC executes Canonical synchronization → ASD verifies result`; Section 15 must not be treated as an unfilled template sent directly to CC; a no-Canonical-update-required path and CC's stop-on-unresolved-placeholder behavior are both part of the Issue's defined scope. **This is a registration record only — the Prompt Library fix itself is Open/Not Implemented, not Accepted or Completed.** This Issue does not block the current Figma OS Product sequence (`#17 Completed → #18 Completed → #19 Next`) and does not itself change any Figma OS Product state, the Type Polish Freeze exception, or the production `time` blocker.
- ASD Canonical State Synchronization (2026-11-19, **progress synchronization — not an Acceptance decision**): Global Architect decision "State Update Required / Approved for Publication" (Decision Date 2026-11-19). [figma-os#20](https://github.com/ga7ming3249/figma-os/issues/20) (Type Polish — Typography Rule & Spacing Standardization) **Step 15–17 are Completed**, including **Step 17 — Desktop P3 Evidence Integration**. **S1-A Overall: Pending. W-1 / Y-1 Overall: Inconclusive. Y-1 Visual Quality: Unacceptable** (Vision Owner assessment — see `figma-os-state.md` for the separation of evidence-derived findings, Vision Owner assessments, and unverified local-only facts). **Issue #20 remains Open / Not Accepted.** **Production `time` migration remains a Hard Block** (the `80%` doc vs `65%` runtime discrepancy stays unresolved; nothing here authorizes it). **Resume point: Step 18 — S1-A Gate Decision & Evidence Finalization Planning**, in the Issue #20 dedicated chat. This synchronization does **not** accept S1-A, W-1, Y-1, or Issue #20, does **not** authorize `time` migration, and grants no implicit authorization; subsequent Gate/Acceptance decisions are evaluated separately by the Global Architect. Scope: `asd`-side documentation only (`asd-state.md`, `figma-os-state.md`); `docs/ROADMAP.md` (v26) and the `figma-os` repository (HEAD unchanged at `22044e05ba26c43474ca5a01669b38483f293bdb`) were not modified, and GitHub Issue #20 was not updated or closed.
- ASD Canonical State Synchronization (2026-11-23, **partial synchronization — Step 19 S1-A Closure; not a Gate Pass, not an Acceptance**): Global Architect decision "Partial State Synchronization — Option 1 Approved". Records the Vision Owner's Step 19 decision of 2026-11-20 for [figma-os#20](https://github.com/ga7ming3249/figma-os/issues/20): **S1-A Activity Status: Closed — Inconclusive; Validation Result: Inconclusive; W-1 / Y-1: Inconclusive; Gate Pass: Not established; Y-1 Visual Quality: Unacceptable** (Vision Owner assessment); **W-1 Structural Verification Acceptance: Not established; S1-B: Not Authorized.** **Issue #20 remains Open / Not Accepted. figma-os#18 remains Accepted / Completed / Closed. Production `time` migration remains a Hard Block.** This supersedes the "S1-A Overall: Pending / resume at Step 18" wording of the 2026-11-19 entry above, which is kept as the record of that date. **Evidence Reference / Storage Status**: the closure record is `Figma-Plugin-Validation/Evidence/S1-A/` (README §12; `images/INDEX.md`, 16 images identified by SHA-256) under `~/Library/CloudStorage/Dropbox/Development/Claude/`; it is **not under Git management** and **not published to GitHub**, and Dropbox retention/recoverability is **not guaranteed** (file hashes read on 2026-11-23 are recorded in `figma-os-state.md`). **Deferred / Evidence Pending**: registration of additional date/time/yakumono discrepancy candidates from the Step 20 read-only audit (audit evidence not located; nothing registered), and new Canonical responsibility-boundary wording for #20 / #18 / asd#36 (not authored). Scope: `asd`-side documentation only (`asd-state.md`, `figma-os-state.md`); `docs/ROADMAP.md`, the `figma-os` repository (HEAD unchanged at `22044e05ba26c43474ca5a01669b38483f293bdb`, re-verified 2026-11-23) and GitHub Issue #20 were not modified. No Plugin implementation, Issue state, Migration prohibition or Freeze Exception scope is changed.
- ASD Canonical State Synchronization (2026-11-25, **documentation-only; additional discrepancy registration — no value, root cause or classification decided**): Global Architect decision "Option A — Approved with Evidence Verification Gate". Registers, as **unresolved observed discrepancies** for [figma-os#20](https://github.com/ga7ming3249/figma-os/issues/20): D-1 date scale (docs 85% / implementation 70%), D-2 date spacing (−2px / −1px), D-4 time spacing (−2px / −3px), D-5 time alignment (BASELINE / CENTER), D-6 yakumono scope (README 「句読点・括弧類」 vs implemented 18 bracket characters; fact vs README-scope interpretation kept distinct). D-3 (time colon scale 80% / 65%) was already registered and is preserved without duplication. For every entry: Intended Behavior Unknown, Correct Value Unknown, Root Cause Unknown, Defect Classification Undetermined, Migration Impact Undetermined. **Evidence**: `Figma-Plugin-Validation/Evidence/Issue-20/Step-22_Discrepancy-Evidence.md` (8,414 bytes, SHA-256 `8c87aed0ec17ff095f222d0844ba142c082b27e23445d1c8bf6a1de0cbc591b0`) — a new Step 21–22 verification record, not a reconstruction of the Step 20 original; **not under Git management**, Dropbox retention not guaranteed; the checksum identifies the file version only and does not prove the observations correct. Publisher verified file/checksum/size and the cited `figma-os` `22044e05…` source lines directly. Full table and source references: `figma-os-state.md` v37. **Existing responsibilities (documentation, not new allocation)**: figma-os#20 = Typography Rule Standardization, Current Behavior Classification, Product Policy, Disposition proposals; figma-os#18 = Accepted Migration History, behavior-preserving constraints, production `time` migration Hard Block; asd#36 = Source Registration, Evidence, Provenance, Knowledge / Rule Candidate Lifecycle. **Deferred, not promoted to Known Discrepancies**: O-1 (`WAO_EN_OFFSET = 0.05` undocumented), O-2 (different Japanese character classifiers in Polish vs Horizontal Analysis) — kept in Issue #20's observation record. **Unchanged**: S1-A Closed — Inconclusive; Issue #20 Open / Not Accepted; Issue #18 Accepted / Completed / Closed; S1-B Not Authorized; production `time` migration Hard Block; Type Polish Freeze Exception; no runtime implementation, typography value decision, or Issue creation/reopening/closure. Scope: `asd`-side documentation only (`asd-state.md`, `figma-os-state.md`); `docs/ROADMAP.md`, the `figma-os` repository (HEAD unchanged at `22044e05ba26c43474ca5a01669b38483f293bdb`) and GitHub Issue #20 were not modified.

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
| [asd#36](https://github.com/ga7ming3249/asd/issues/36) | Type Polish | - | Open | Typography Knowledge & Preset Lifecycle — Parent Architecture Track (parallel supporting), registered 2026-08-20; continuous knowledge/evidence intake feeding Rule Catalog / Preset Candidates |
| [figma-os#19](https://github.com/ga7ming3249/figma-os/issues/19) | Type Polish | - | Open | Preset Management UI — Product Implementation Issue, registered 2026-08-20; **next Product implementation dependency** now that figma-os#17 and figma-os#18 are both Accepted/Completed/Closed (2026-08-21, 2026-08-22); consumes figma-os#17's Foundation and figma-os#18's migrated legacy capability state; not blocked by figma-os#21 |
| [figma-os#20](https://github.com/ga7ming3249/figma-os/issues/20) | Type Polish | - | Open | Typography Rule & Spacing Standardization — Product Architecture / Rule Standardization Issue, registered 2026-08-21 from figma-os#17 Desktop Acceptance observations (pre-existing typography-rule ambiguity, not a #17 regression); does not automatically block all of #18/#19; coordinates with asd#36; authorizes no runtime implementation by itself; **2026-11-19 progress synchronization (not Acceptance)**: Step 15–17 Completed (Step 17 Desktop P3 Evidence Integration), W-1/Y-1 Overall Inconclusive, Y-1 Visual Quality Unacceptable (Vision Owner assessment), production `time` migration Hard Block; **2026-11-23 Step 19 S1-A Closure synchronization (not Gate Pass, not Acceptance)**: S1-A Activity Status Closed — Inconclusive, Validation Result Inconclusive, Gate Pass Not established, S1-B Not Authorized, **Open / Not Accepted**, production `time` migration Hard Block unchanged; Evidence is local and not under Git (see `figma-os-state.md`); **2026-11-25**: additional observed discrepancies D-1, D-2, D-4, D-5, D-6 registered as unresolved (D-3 pre-existing; all Correct Value / Root Cause Unknown, Classification / Migration Impact Undetermined), **Open / Not Accepted** unchanged |
| [figma-os#21](https://github.com/ga7ming3249/figma-os/issues/21) | Type Adjuster | - | Open / Maintenance | Node 24 test-runner compatibility — independent test-infrastructure follow-up, registered 2026-08-22 from a discrepancy discovered during figma-os#18 regression running (`ERR_UNSUPPORTED_TYPESCRIPT_SYNTAX` in two `type-adjuster` test files under Node 24's native TS-stripping); does not block figma-os#19 |
| [reference-assistant#1](https://github.com/ga7ming3249/reference-assistant/issues/1) | Reference Assistant | P1 | Open | Daily Preview Operation — Primary Issue, Successor to asd#4. reference-assistant#5's Safety Blocker is resolved (Closed 2026-07-25); Daily Preview resumption is not automatically decided by this synchronization and remains subject to separate Owner-controlled operating conditions |
| [reference-assistant#7](https://github.com/ga7ming3249/reference-assistant/issues/7) | Reference Assistant | - | Open / Maintenance | Post-migration Cleanup After Dropbox Development Directory Migration. Independent low-priority maintenance issue; not remaining reference-assistant#5 work |
| [reference-assistant#3](https://github.com/ga7ming3249/reference-assistant/issues/3) | Reference Assistant | P2 | Open | Design Library Location Selection and Safe Relocation Model — Architecture Issue |
| [asd#33](https://github.com/ga7ming3249/asd/issues/33) | ASD Process | - | Open | Standardize Issue Completion Authority and Operation Directives — Architecture Improvement addressing insufficient separation between Review Decision, Completion, and GitHub Operation, following an unverified KB-0005 review comment that closed asd#31 |
| [asd-operations#1](https://github.com/ga7ming3249/asd-operations/issues/1) | ASD Operations | - | Open | ASD Prompt Library — Nightly Integration → Canonical Sync flow refinement — Operations workflow-improvement Issue, registered 2026-08-22, addressing the ambiguous Section 14 → 15 → 16 Nightly handoff (Section 15 mislabeled as directly usable while containing unresolved placeholders); does not block the Figma OS Product sequence |

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
- **Type Polish / Type Adjuster manual-adjustment ownership** ([figma-os#3](https://github.com/ga7ming3249/figma-os/issues/3), Accepted / Completed / Closed 2026-08-18): canonical ownership of manual typography adjustment (Scale/Baseline/Tracking) is Type Adjuster — **unchanged, carried forward through the full Migration Chain below.** Type Polish's Utility was a Legacy Compatibility Capability Pending Migration/Removal; the Migration Chain tracked by figma-os#12 → #13 → #14 → #15 is **now complete** (figma-os#15 Accepted / Completed / Closed 2026-08-20, commit `d08b39b03403c3e55bf9948f871e350b245878da`) and the legacy Utility has been removed from Type Polish. This decision (and its migration) is architecture/removal-scoped only; it does not authorize any other Type Polish change, and Type Polish itself remains active, not deprecated.
- **Plain-node manual adjustment: Discontinue** ([figma-os#12](https://github.com/ga7ming3249/figma-os/issues/12), Accepted / Completed / Closed 2026-08-19): Scale, Baseline, and Tracking on plain/ungenerated TextNode are all decided **Discontinue** — Type Adjuster's selection resolver is not extended to accept plain TextNodes for these. Not a decision to discontinue the Type Polish plugin/product. [figma-os#13](https://github.com/ga7ming3249/figma-os/issues/13) (Manual Adjustment Migration) is Closed / Not Planned as a result, with no independent scope. **Product Boundary** (new Canonical fact): Type Polish = preset-based typography preparation/composition; Type Adjuster = individual fine typography adjustment on generated (post-Split) structure; canonical workflow `Text Layer → Type Polish → Type Adjuster (Split → fine adjustment)` — a role-division description, not a mandate that every Text Layer passes through Type Polish. Type Polish's per-range font assignment on plain TextNode (e.g. mixed JP/EN, Mincho/Gothic mixing) is unaffected. See `figma-os-state.md` → "Completed — figma-os#12" and "Type Polish Utility Ownership — Migration Chain" for full detail.
- **Utility Ownership documentation migration: Completed** ([figma-os#14](https://github.com/ga7ming3249/figma-os/issues/14), Accepted / Completed / Closed 2026-08-19, commit `f2555451c3423960478792b7e1562e5bff86f01e`): `type-polish/README.md` and `type-adjuster/README.md` now state the figma-os#3 Canonical Owner model explicitly. The figma-os#10 User Guide required no changes after audit against the figma-os#12 Product Boundary. See `figma-os-state.md` → "Completed — figma-os#14" for full detail.
- **Utility Deprecation / Removal: Completed** ([figma-os#15](https://github.com/ga7ming3249/figma-os/issues/15), Accepted / Completed / Closed 2026-08-20, commit `d08b39b03403c3e55bf9948f871e350b245878da`): the legacy Scale/Baseline/Tracking Utility is removed from `type-polish/code.ts`/`ui.html`. Prerequisites (figma-os#12/#13/#14, regression/Desktop verification) all verified satisfied. **Type Adjuster remains Canonical Owner of Scale/Baseline/Tracking (unchanged). Type Polish itself remains active and is not deprecated.** The Type Polish Utility Ownership Migration Chain (figma-os#12 → #13 → #14 → #15) is now complete. See `figma-os-state.md` → "Completed — figma-os#15" and "Type Polish Utility Ownership — Migration Chain" for full detail.
- **Type Polish Parent Architecture Tracks registered** ([asd#35](https://github.com/ga7ming3249/asd/issues/35) — Preset Platform & Product Development, primary; [asd#36](https://github.com/ga7ming3249/asd/issues/36) — Typography Knowledge & Preset Lifecycle, parallel supporting; both 2026-08-20): replace figma-os#15 as Recommended Next Action / Development Focus now that the Migration Chain is complete. Intended relationship: Knowledge Track (asd#36) → Accepted Rule/Preset Proposal → Product Track (asd#35) → Issue-scoped Implementation → Verification → Feedback to Knowledge. Registration is architecture-track setup only — does not authorize new Type Polish runtime implementation, Japanese Horizontal implementation, Latin implementation, or any Type Adjuster ownership change.
- **asd#35 — Architecture Completion** (Accepted / Completed / Closed, 2026-08-20): Product Architecture work for asd#35 is complete. **Type Polish's Canonical Product Architecture is now a Preset-based Typography Product Platform** — stable Preset identity, versioned content revisions, independently versioned schemas, provenance, and lifecycle state are distinct responsibilities; document application state is distinct from runtime instance metadata; existing documents never silently update on Preset change; Built-in/Recommended/User-created origins remain distinct; Supersede/Deprecate are non-destructive; Merge is human-reviewed and non-destructive with Merge UI Deferred; Knowledge changes never auto-promote to runtime Presets. Type Adjuster remains Canonical Owner of Scale/Baseline/Tracking; Type Polish zero-mutation analysis and the Local Fix Handoff boundary are unchanged. Follow-up Product Issues [figma-os#17](https://github.com/ga7ming3249/figma-os/issues/17) (Foundation) → [figma-os#18](https://github.com/ga7ming3249/figma-os/issues/18) (Existing Capability Migration/Reference) → [figma-os#19](https://github.com/ga7ming3249/figma-os/issues/19) (Preset Management UI) are the Recommended Product implementation sequence, replacing asd#35 as the active Product Architecture action; none is implementation-authorized by asd#35's closure. [asd#36](https://github.com/ga7ming3249/asd/issues/36) remains the parallel Knowledge track. See "Recent Changes" entry above and `figma-os-state.md` → "Recent Changes" for full detail.
- **Preset Platform Foundation: Implemented** ([figma-os#17](https://github.com/ga7ming3249/figma-os/issues/17), Accepted / Completed / Closed 2026-08-21, final commit `a96ad202337ba72d9732b75e169cc2ba807e71ec`): domain model (`PresetIdentity`/`PresetRevision`/`PresetOrigin`/`PresetProvenance`), independent identity lifecycle/revision status, Registry persistence, `PresetApplicationSnapshot`/`TypePolishInstanceMetadata`, fail-closed validation, independently-versioned registry/document schema migration, immutable released-revision semantics, explicit Publish/Detect Update/Apply Update separation, Deprecated/Retired lifecycle resolution, and same-lineage non-destructive Merge foundation are now live in `type-polish/src/preset-platform/**`. Figma Desktop Acceptance Cases 1–9 all Pass. **Type Adjuster remains Canonical Owner of Scale/Baseline/Tracking; Type Polish's zero-mutation analysis and Local Fix Handoff boundary are unchanged; existing wao/date/time/yakumono production behavior was not migrated onto the Platform.** Known Discrepancies (README wording; time `80%`/`65%` — Canonical: Unknown, owned by figma-os#18; legacy `updatePolish()` JSON.parse) remain unresolved. Next Product implementation dependency: [figma-os#18](https://github.com/ga7ming3249/figma-os/issues/18). A new Rule Standardization Issue, [figma-os#20](https://github.com/ga7ming3249/figma-os/issues/20), was registered from Desktop Acceptance typography-quality observations — not a #17 regression, does not block all of #18, must not resolve `80%`/`65%` by assumption. See `figma-os-state.md` → "Completed — figma-os#17" for full detail.
- **Existing Capability Migration / Reference: Implemented** ([figma-os#18](https://github.com/ga7ming3249/figma-os/issues/18), Accepted / Completed / Closed 2026-08-22, accepted implementation/instrumentation commit `22044e05ba26c43474ca5a01669b38483f293bdb`): legacy `wao`/`date`/`yakumono` production capability is migrated onto the #17 Preset Platform Foundation — fail-closed legacy-metadata parse/validate/candidate-construct/persist transaction, idempotent Built-in preset seeding, snapshot-then-instance-metadata persistence with rollback on partial-write failure and explicit partial-state detection/recovery on the next open, and automatic (not Update-gated) recognition via plugin-launch page scan / `currentpagechange` / `selectionchange`. "Japanese Vertical — Standard" is registered as a Platform reference/Built-in entry; its existing read-only analysis/regression behavior is unchanged. Legacy `META_KEY` metadata is retained (not archived or removed) on every migrated document. Verified: Type Polish full suite `354/354` PASS, typecheck/build clean, **Figma Desktop Acceptance `7/7` PASS** executed live by the Vision Owner (legacy wao / legacy date / legacy yakumono / corrupt legacy metadata fail-closed / repeated recognition idempotency / production `time` Hard Block / Japanese Vertical read-only regression). **Production `time` remains explicitly excluded** — no production `time` `PresetRevision` created, activated, or bound; the `80%`/`65%` documentation-vs-runtime discrepancy remains unresolved, Canonical value `Unknown`, not resolved by this Issue or this synchronization. Next Product implementation dependency: [figma-os#19](https://github.com/ga7ming3249/figma-os/issues/19). [figma-os#21](https://github.com/ga7ming3249/figma-os/issues/21) (Type Adjuster — Node 24 test-runner compatibility) is registered as an independent maintenance follow-up discovered during this Issue's regression running — does not block figma-os#19. See `figma-os-state.md` → "Completed — figma-os#18" for full detail.
- **Type Polish Canonical Product Identity** (Vision Owner Priority Decision, 2026-08-18): Type Polish is **not** a Japanese-Vertical-only plugin. Its Canonical Product Identity is to store and reuse typography judgment, and semi-automate finishing work (和欧補正・日付・時刻・約物), with future expansion into Japanese Horizontal / Mixed Japanese–Latin / Latin typography. Japanese Vertical currently being the most advanced capability is an implementation-phase state, not a Product Scope limitation. Type Polish completion is the current top-level Figma OS Product Goal; priority plugin order is 1) Type Polish, 2) Type Adjuster, 3) Type Inventory, 4) Color Inventory. Unresolved capability-roadmap reconciliation (asd#28 / asd#31 / Japanese Horizontal / Mixed Japanese–Latin / Latin typography) is tracked in `figma-os-state.md` Decisions Pending and `docs/ROADMAP.md` Future — not decided by this note itself, and no Horizontal/Latin implementation is authorized by it.

## Current main

Verified ASD base main before this State update: `02c5d9ec351ee68fe362e7438bf0e59c9d7569f1`

Verified figma-os main: `22044e05ba26c43474ca5a01669b38483f293bdb` — current `figma-os/main` HEAD as verified 2026-08-22 (Repository fact; figma-os#18's accepted implementation/instrumentation commit, on top of `a96ad202337ba72d9732b75e169cc2ba807e71ec`, delivering legacy `wao`/`date`/`yakumono` migration onto the Preset Platform Foundation, "Japanese Vertical — Standard" Built-in registration, and Desktop Acceptance debug-harness instrumentation — see Architecture Notes above and `figma-os-state.md` → "Completed — figma-os#18" for the commit's internal history across the Issue's review rounds).

Supersession chain: `22044e05ba26c43474ca5a01669b38483f293bdb` (figma-os#18, verified 2026-08-22) supersedes `a96ad202337ba72d9732b75e169cc2ba807e71ec` (figma-os#17, 2026-08-21; three commits delivering the Preset Platform Foundation — `0c211feab00fe0d957d600adb3a5342289ee9c7d` domain/registry/validation/migration/persistence, `115fee7a7397ec76dc5886c231aa34d78c391db5` test-only `debugCorrupt` op, `a96ad202337ba72d9732b75e169cc2ba807e71ec` fix exposing it in the harness UI), which supersedes `d08b39b03403c3e55bf9948f871e350b245878da` (figma-os#15, verified 2026-08-20; removes the legacy Scale/Baseline/Tracking Utility from `type-polish/code.ts`/`ui.html` on top of `f2555451...`), which supersedes `f2555451c3423960478792b7e1562e5bff86f01e` (figma-os#14, verified 2026-08-19; documentation-only, `type-polish/README.md` + `type-adjuster/README.md` on top of `d3ebb1c33ea3d4c4824504309ffe349693556a92`), which supersedes `d3ebb1c33ea3d4c4824504309ffe349693556a92` (verified 2026-08-18; documentation-only commits `423e6054b8c20a8c6e4b81cde38c34fb6bca3daf` and `d3ebb1c33ea3d4c4824504309ffe349693556a92` on top of `031887c`, delivering figma-os#10's Canonical User Guide under `docs/user-guides/`), which superseded `031887cbf1b65336682212f13df3d609ce46267a` (verified 2026-08-07; includes commits `8b15f28`/`3d22e8a`/`3f1599e` — KB-0001–KB-0003 registration —, `5464a78` — Horizontal Analysis Profile implementation, Architecture Classification: **Experimental**, **Accepted Commit: No** ([asd#34](https://github.com/ga7ming3249/asd/issues/34), see Current Project Overview) —, and `031887c` — Canonical Architecture Review / Review Record / HISTORY publication recording that classification), which superseded `5464a78bf3500475a8855f10cfb8aaa75b9caa39` (verified 2026-08-05), which superseded `d3abd4f46ce89240a22a467bbbf712f4c5e10628` (figma-os#6 / PR #8, 2026-07-29), which itself superseded `2838450c91429e9bc9c312103e0741c64e0068d2` (figma-os#2 / PR #7, 2026-07-24).

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

**figma-os#3 — Accepted / Completed / Closed**

Product Decision — Consolidate Type Polish Utility Ownership into Type Adjuster. Closed `2026-08-18T05:03:24Z`, state reason Completed, Issue-scoped Architect final result: Accepted. Architecture Decision comment: [figma-os#3#issuecomment-5323799447](https://github.com/ga7ming3249/figma-os/issues/3#issuecomment-5323799447). Canonical manual-adjustment owner: Type Adjuster (Scale/Baseline/Tracking). Type Polish Utility reclassified: Legacy Compatibility Capability Pending Migration/Removal — immediate removal prohibited. Four follow-up Issues created and remain Open: [figma-os#12](https://github.com/ga7ming3249/figma-os/issues/12) (Plain-node Manual Adjustment Strategy), [figma-os#13](https://github.com/ga7ming3249/figma-os/issues/13) (Manual Adjustment Migration, contingent on #12), [figma-os#14](https://github.com/ga7ming3249/figma-os/issues/14) (Utility Ownership Documentation Migration), [figma-os#15](https://github.com/ga7ming3249/figma-os/issues/15) (Utility Deprecation / Removal, Blocked). Dependency order: #12 → #13 (if applicable) → #14 → #15. The Type Polish Freeze exception is scoped solely to the #12–#15 Utility deprecation/removal migration, not a general Freeze lift. No source code was changed to produce this Decision; no implementation is authorized by this closure. Next Architecture Dependency: figma-os#12. This did not remove the need for [figma-os#10](https://github.com/ga7ming3249/figma-os/issues/10) (User Guide) — #10's scope incorporated the new ownership model; #10 is now itself Completed (see next entry).

**figma-os#10 — Type Polish / Type Adjuster User Guide — Accepted / Completed / Closed**

Closed 2026-08-18, state reason Completed, Issue-scoped Architect final result: Accepted. Completion comment: [figma-os#10#issuecomment-5327103969](https://github.com/ga7ming3249/figma-os/issues/10#issuecomment-5327103969). Canonical User Guide delivered as Markdown under `docs/user-guides/` in `ga7ming3249/figma-os`: `type-polish.md`, `type-adjuster.md`, `type-polish-type-adjuster-workflow.md`, `glossary.md`, `faq.md`. Navigation added from `README.md`, `PLUGINS.md`, `type-polish/README.md`, `type-adjuster/README.md`. Documentation-only diff both rounds. Accepted implementation commit `423e6054b8c20a8c6e4b81cde38c34fb6bca3daf` (initial User Guide), corrected by Accepted commit `d3ebb1c33ea3d4c4824504309ffe349693556a92` (clarifies Type Polish's zero-mutation scope is Document Content only, excluding the Local Fix Handoff shared-metadata write) — `d3ebb1c...` is the accepted `figma-os/main` HEAD. figma-os#3's canonical ownership model is reflected: Scale/Baseline/Tracking canonical owner is Type Adjuster; Type Polish's own Utility panel is Legacy Compatibility Capability Pending Migration/Removal, never described as a current owner. Verified: Type Polish tests 243/243, Type Adjuster tests 278/278 (via `tsx`), scoped typechecks clean, full link/anchor check clean, UI labels cross-checked verbatim, Retained Original wording verified against Gate 5 G5-DEF-001 (original TextNode retained, never removed). Follow-up candidates recorded but not implemented: `docs/shared/handoff-schema.md` Gate 4/Gate 5 wording drift, `type-adjuster/HISTORY.md` Gate 3/4/5 history gap, Type Adjuster test-runner ergonomics. A separate Presentation/Distribution HTML Issue was registered in `ga7ming3249/figma-os` for an offline copy of this Guide; per explicit State Update Decision its registration is not tracked as part of this synchronization.

**figma-os#12 — Plain-node Manual Adjustment Strategy — Accepted / Completed / Closed**

Closed 2026-08-19, Issue-scoped Architect final result: Accepted. Architecture Decision comment: [figma-os#12#issuecomment-5336743790](https://github.com/ga7ming3249/figma-os/issues/12#issuecomment-5336743790). Disposition: **Discontinue** for all three capabilities (Scale, Baseline, Tracking) on plain/ungenerated TextNode — Type Adjuster's selection resolver is not extended to accept plain TextNodes for these; not a decision to discontinue Type Polish itself. Evidence Collection found the Split-anchored vs. plain-TextNode semantic differences between Type Adjuster and Type Polish's legacy Utility, and that legacy Utility usage frequency was `Unknown` from repository evidence alone; the Vision Owner then supplied direct current-workflow evidence (fine adjustment already goes through Split → Type Adjuster; plain TextNode is used for a separate, unaffected per-range font-assignment capability). New Canonical Product Boundary recorded: Type Polish = preset-based typography preparation/composition; Type Adjuster = individual fine typography adjustment on post-Split structure; canonical workflow `Text Layer → Type Polish → Type Adjuster (Split → fine adjustment)`. Reaffirms, does not reopen, figma-os#3. Immediate Utility removal remains prohibited; Type Polish Capability Roadmap Reconciliation is not decided by this Decision. A follow-up candidate (Type Adjuster Split-target selection UX friction) was recorded in the closing comment, not created as a new Issue.

**figma-os#13 — Manual Adjustment Migration — Closed / Not Planned**

Closed 2026-08-19. Comment: [figma-os#13#issuecomment-5336745232](https://github.com/ga7ming3249/figma-os/issues/13#issuecomment-5336745232). Carried no independent scope — entirely contingent on figma-os#12, which decided Discontinue for all three capabilities, so no Type Adjuster manual-adjustment implementation is required or was started. The Type Polish Utility Ownership Migration Chain dependency order is now `#14 → #15`.

**figma-os#14 — Utility Ownership Documentation Migration — Accepted / Completed / Closed**

Closed `2026-08-19T06:11:42Z`, state reason Completed, Issue-scoped Architect final result: Accepted. Completion comment: [figma-os#14#issuecomment-5338253440](https://github.com/ga7ming3249/figma-os/issues/14#issuecomment-5338253440). Accepted implementation commit `f2555451c3423960478792b7e1562e5bff86f01e` on `figma-os/main` (fast-forward from `d3ebb1c33ea3d4c4824504309ffe349693556a92`) — documentation-only, exactly `type-polish/README.md` and `type-adjuster/README.md` changed. Canonical Owner statement (Type Adjuster owns Scale/Baseline/Tracking; Type Polish's Utility is Legacy Compatibility Capability Pending Migration/Removal, not a Type Polish deprecation) now lives in both plugin READMEs, not only the figma-os#10 User Guide. Audit against the figma-os#12 Product Boundary found the User Guide and `ROADMAP.md` already correct — no changes made to either. No runtime/source, Utility code/UI, plain TextNode behavior, Type Adjuster Split UX, or ASD State changes. Not an Implementation Authorization for figma-os#15. The Type Polish Utility Ownership Migration Chain dependency order is now `#15` only.

**figma-os#15 — Utility Deprecation / Removal — Accepted / Completed / Closed**

Closed `2026-08-20T06:14:08Z`, state reason Completed. Accepted implementation commit `d08b39b03403c3e55bf9948f871e350b245878da` on `figma-os/main`, previous HEAD `f2555451c3423960478792b7e1562e5bff86f01e`. Prerequisites satisfied: figma-os#12 (Discontinue disposition), figma-os#13 (Closed as not needed), figma-os#14 (documentation migration), Prerequisite 4 Regression/Desktop verification (`npm run build`/`typecheck`/`test` PASS, 243/243; post-removal Figma Desktop regression 5/5 Pass). Removed `applyScale`/`applyBaseline`/`applyTracking` and the Utility UI block from `type-polish/code.ts`/`ui.html`; updated `type-polish/HISTORY.md`. No `type-adjuster/**` changes; no plain-TextNode Scale/Baseline/Tracking support added; preset/apply/update, analysis, Local Fix Handoff, and persistence semantics unchanged. **Type Adjuster remains Canonical Owner of Scale/Baseline/Tracking (figma-os#3) — unchanged. Type Polish itself is not deprecated** — preset preparation/apply/update, Japanese Vertical/Horizontal analysis, and Local Fix Handoff remain active. **The Type Polish Utility Ownership Migration Chain (figma-os#12 → #13 → #14 → #15) is now complete** — no remaining steps. This Issue's own ASD Canonical State update was explicitly out of scope for its closure and is performed by this synchronization.

**asd#35 / asd#36 — Type Polish Parent Architecture Tracks registered**

Two new ASD Parent Architecture Issues, opened 2026-08-20 by the Vision Owner's account and verified via `gh issue view` before registration here: [asd#35](https://github.com/ga7ming3249/asd/issues/35) (Type Polish — Preset Platform & Product Development, primary — Product Architecture / capability roadmap reconciliation now that the Migration Chain is complete) and [asd#36](https://github.com/ga7ming3249/asd/issues/36) (Type Polish — Typography Knowledge & Preset Lifecycle, parallel supporting — continuous knowledge/evidence intake feeding Rule Catalog / Preset Candidates). Created by the Architect acting as an authorized proxy, explicitly authorized by the Vision Owner in the ASD Daily Session. Intended relationship: Knowledge Track (asd#36) → Accepted Rule/Preset Proposal → Product Track (asd#35) → Issue-scoped Implementation → Verification → Feedback to Knowledge. Replace figma-os#15 as Recommended Next Action / Development Focus. Registration is architecture-track setup only — does not authorize new Type Polish runtime implementation, Japanese Horizontal implementation, Latin implementation, or any Type Adjuster ownership change.

**asd#35 — Architecture Completion, Accepted / Completed / Closed (2026-08-20, second sync)**

Closed `state_reason: COMPLETED`, Issue-scoped Architect final result: Accepted — Close Authorized. Closing comment: [asd#35#issuecomment-5354946773](https://github.com/ga7ming3249/asd/issues/35#issuecomment-5354946773). Records the Accepted Architecture: Type Polish is a Preset-based Typography Product Platform (stable Preset identity, versioned content revisions, independently versioned schemas, provenance, lifecycle state as distinct responsibilities; document application state distinct from runtime instance metadata; no silent existing-document update — read-only Update Available detection, explicit Apply Update binding/re-resolving against an already-published revision; distinct Built-in/Recommended/User-created origins; Active User-created edit → next revision same identity; Built-in/Recommended edit → new User-created identity/fork; non-destructive Supersede/Deprecate; human-reviewed non-destructive Merge with Merge UI Deferred; Knowledge changes never auto-promote to runtime Presets; Product→Knowledge feedback only via explicit records). Type Adjuster remains Canonical Owner of Scale/Baseline/Tracking; Type Polish zero-mutation analysis and the Local Fix Handoff boundary remain preserved. Registers follow-up Product Issues [figma-os#17](https://github.com/ga7ming3249/figma-os/issues/17) (Preset Platform Foundation), [figma-os#18](https://github.com/ga7ming3249/figma-os/issues/18) (Existing Capability Migration / Reference), [figma-os#19](https://github.com/ga7ming3249/figma-os/issues/19) (Preset Management UI), Architecture-sequenced 1→2→3 — registration is not simultaneous implementation authorization; each requires its own Issue-scoped execution/review process. Capability Classification recorded without promoting any item beyond its listed status: Japanese Vertical = Accepted Production Capability (primary migration/reference capability); existing wao mixed-font correction = narrow Accepted Production behavior; Japanese Horizontal = Experimental Repository Evidence / Gate 0 only; complete Mixed Japanese–Latin = Planned but Unimplemented; Latin typography = Planned but Unimplemented; OpenType = Knowledge/Rule Evidence; asd#28 = Knowledge/Rule Evidence; asd#31 = Experimental Repository Evidence + Gate 0 supporting infrastructure. Known Discrepancies preserved unresolved: stale Type Polish README Utility-removal wording; time preset `80%` doc vs. `65%` runtime — Canonical behavior: Unknown, blocker owned by figma-os#18; legacy `updatePolish()` unguarded `JSON.parse`, remediation conditional. Recommended Next Product Action replaces asd#35: begins with figma-os#17 (Foundation), figma-os#18 downstream, figma-os#19 consumes Foundation and coordinates with migration state; asd#36 remains the parallel Knowledge track, unaffected. Deferred/unauthorized: Japanese Horizontal productionization, general Mixed Japanese–Latin, Latin typography, OpenType capability, Merge UI, import/export. This synchronization does not authorize implementation of figma-os#17/#18/#19 — Architecture and roadmap only. No `figma-os` product repository commit was made; `figma-os/main` HEAD unchanged at `d08b39b03403c3e55bf9948f871e350b245878da`.

**figma-os#17 — Preset Platform Foundation — Accepted / Completed / Closed (2026-08-21)**

Issue-scoped Architect final result: Accepted. Final relevant commit `a96ad202337ba72d9732b75e169cc2ba807e71ec` on `figma-os/main` (three commits on top of `d08b39b03403c3e55bf9948f871e350b245878da`: `0c211feab00fe0d957d600adb3a5342289ee9c7d` — Foundation implementation, domain/registry/validation/migration/persistence in `type-polish/src/preset-platform/**` plus a debug harness scaffold in `code.ts`/`ui.html`; `115fee7a7397ec76dc5886c231aa34d78c391db5` — test-only `debugCorrupt` op added to the harness dispatcher for Desktop Acceptance Case 8; `a96ad202337ba72d9732b75e169cc2ba807e71ec` — fix exposing `debugCorrupt` in the harness `<select>`, which had been unreachable from the UI). Implements the domain model, Registry persistence, document persistence (`PresetApplicationSnapshot`/`TypePolishInstanceMetadata`), fail-closed validation, and independently-versioned schema migration infrastructure defined by the Accepted asd#35 Architecture — does **not** migrate existing production Type Polish presets (wao/date/time/yakumono) onto the Platform.

Verified: Type Polish full suite 306/306 PASS (243 pre-existing + 63 new), Foundation tests 63/63 PASS, Gate 3 Handoff 54/54 PASS, Gate 4 applied-marker 18/18 PASS, typecheck/build clean. **Figma Desktop Acceptance Cases 1–9 all PASS** (Figma Desktop App `126.7.10`, macOS `14.8.5 (23J423)`), executed live by the Vision Owner with concrete evidence recorded on the Issue: registry identity/revision persistence across plugin restart (`presetId preset_n0lw58pn42zijl20vwh6qc19`); an existing document staying bound to its original revision after newer revisions were published; Detect Available Update reported as read-only with Registry state deep-equal before/after; Apply Available Update rebinding only the explicitly targeted document (a second document sharing the same prior revision was left untouched); a declined update leaving a document's persisted snapshot unchanged; Deprecated identity blocking brand-new Apply while remaining browsable and its existing bound document staying operational; Retired identity additionally excluded from browse while its existing bound document stayed operational; corrupt Snapshot/InstanceMetadata/Registry payloads all failing closed with original bytes preserved and no plugin crash; and existing wao/date/time/yakumono Apply/Update, the Utility panel's continued absence, Gate 2 Analyze, and Gate 3 Handoff UI all confirmed unchanged.

**Boundaries preserved**: Type Adjuster remains Canonical Owner of Scale/Baseline/Tracking; Type Polish's legacy Utility remains absent; zero-mutation analysis and Local Fix Handoff are unchanged. **Known Discrepancies remain unresolved**: stale README wording; time `80%`/`65%` — Canonical behavior: Unknown, owned by figma-os#18; legacy `updatePolish()` unguarded `JSON.parse`. A follow-up Product Architecture / Rule Standardization Issue, [figma-os#20](https://github.com/ga7ming3249/figma-os/issues/20) (Type Polish — Typography Rule & Spacing Standardization, verified via `gh issue view`, opened 2026-08-21 by the Vision Owner's account), was registered from Desktop Acceptance visual observations (wao/time spacing, yakumono's narrow bracket set, undocumented fixed spacing values) — explicitly recorded as pre-existing behavior, **not** a figma-os#17 regression, does not automatically block all of figma-os#18, must not resolve the `80%`/`65%` discrepancy by assumption, coordinates with [asd#36](https://github.com/ga7ming3249/asd/issues/36), and its registration does not itself authorize any runtime change. Next Product implementation dependency: [figma-os#18](https://github.com/ga7ming3249/figma-os/issues/18) (Existing Capability Migration / Reference); [figma-os#19](https://github.com/ga7ming3249/figma-os/issues/19) remains downstream. **This synchronization does not authorize** figma-os#18/#19 implementation, figma-os#20 runtime changes, Japanese Horizontal productionization, Latin/OpenType implementation, or any Type Adjuster ownership change.

**figma-os#18 — Existing Capability Migration / Reference — Accepted / Completed / Closed (2026-08-22)**

Issue-scoped Architect final result: Accepted. Accepted implementation/instrumentation commit `22044e05ba26c43474ca5a01669b38483f293bdb` on `figma-os/main` (on top of `a96ad202337ba72d9732b75e169cc2ba807e71ec`), reached across four Issue-scoped Architect review rounds (initial implementation → automatic-migration-trigger and partial-state-handling fixes → Desktop Acceptance instrumentation → Desktop Acceptance execution). Migrates the existing Type Polish production capability (Japanese Vertical — Standard, `wao`, `date`, `yakumono`) onto the #17 Preset Platform Foundation with no observable typography behavior change: a fail-closed legacy-`PluginMeta`-to-Platform migration transaction (read → validate → construct candidate → validate candidate → persist → recognized-complete), idempotent Built-in preset seeding for the four migratable capability shapes (never `time`), snapshot-then-instance-metadata persistence with rollback on a partial-write failure and explicit detection/recovery of an unrecoverable partial state on the next open, and automatic recognition — not gated behind Update or any migration-specific user action — via a plugin-launch page scan, `figma.on('currentpagechange', …)`, and `figma.on('selectionchange', …)`. "Japanese Vertical — Standard" has no document-level legacy metadata (it is a pre-existing zero-mutation analyzer) and is registered Platform-side as a Built-in reference entry only; its existing analysis/regression behavior is confirmed unchanged. Legacy `META_KEY` metadata is retained (not archived or removed) on every migrated document, since the existing legacy Update code path still reads it directly.

Verified: Type Polish full suite `354/354` PASS, `npx tsc --noEmit` clean, `npm run build` clean. **Figma Desktop Acceptance: 7/7 PASS**, executed live by the Vision Owner against this exact commit: (1) legacy wao — automatic recognition without Update, `snapshot.kind`/`metadata.kind` = `current`, bound to the fixed `builtin_wao_preset_v1`/`builtin_wao_revision_v1`, state stable across reselect, no visual change after a subsequent normal Update; (2) legacy date — same points, month/day-suffix `scale: 0.7` resolved behavior preserved; (3) legacy yakumono — same points; (4) corrupt legacy metadata — a controlled `seedLegacyFixture` malformed-JSON payload produced an explicit `invalid`/`"malformed JSON"` migration outcome, no Platform state written, corrupt legacy bytes preserved; (5) repeated recognition — before/after Platform state stable across reselect/page-change/relaunch, no duplicate migration, no new instance identity, no timestamp change, no revision rebinding; (6) production `time` Hard Block — legacy `time` metadata present but `snapshot.kind`/`metadata.kind` remained `empty` throughout, `migrateLegacy` returned an explicit `blocked` outcome citing the Hard Block, no Canonical value adopted; (7) Japanese Vertical — Standard — Analyze completed read-only with no document mutation, output behaviorally unchanged. Persistence-failure and partial-state-recovery cases were not manufactured live (no supported way to inject a transient `setPluginData` failure, and unsafe quota exhaustion was explicitly ruled out) — satisfied instead by deterministic automated failure-injection tests in `type-polish/test/preset-platform-legacy-migration.test.ts`, part of the passing `354/354`.

**Provenance discipline**: migration binds every legacy document to a fixed, single-revision Built-in identity per capability shape — not a claim that the document historically "had" that Preset revision (legacy Type Polish had no Preset concept at all; historical provenance is simply not recorded/not provable), but a migration-time deterministic classification, since each shape's segmenter is currently a pure function of text/stored-metadata with exactly one possible parameter value (`{}`). Per-document resolved state (wao's detected fonts/sizes, date/yakumono's segment text) is preserved verbatim in `resolvedState`, never inferred from a shared "latest" value.

**Boundaries preserved**: Type Adjuster remains Canonical Owner of Scale/Baseline/Tracking; Type Polish's zero-mutation analysis and Local Fix Handoff boundary are unchanged; `applyPolish()` (brand-new documents) was not modified — this Issue migrates existing legacy documents only. **Production `time` remains explicitly excluded**: no production `time` `PresetRevision` was created, activated, or bound to any legacy instance; the `80%`/`65%` documentation-vs-runtime discrepancy remains unresolved, Canonical production value `Unknown` — **not resolved by this Issue or by this synchronization**. **Discovered discrepancy**: `type-adjuster`'s `node --test` suite has 2 pre-existing failures under Node 24 (`ERR_UNSUPPORTED_TYPESCRIPT_SYNTAX` in `type-adjuster/test/gate4-figma-mock.ts`, a TS parameter-property construct), unrelated to and untouched by this Issue — registered as [figma-os#21](https://github.com/ga7ming3249/figma-os/issues/21) (Type Adjuster — Node 24 test-runner compatibility, independent maintenance follow-up, does not block figma-os#19). Next Product implementation dependency: [figma-os#19](https://github.com/ga7ming3249/figma-os/issues/19) (Preset Management UI). **This synchronization does not authorize** figma-os#19 implementation, does not resolve the `time` `80%`/`65%` discrepancy, does not broaden the Type Polish Freeze exception beyond `figma-os#17 → #18 → #19`, and does not reopen or re-review figma-os#18.

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
