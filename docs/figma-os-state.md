# Figma OS State

- Version: 27
- Date: 2026-08-18
- Status: Active
- Maintainer: Claude Code (Primary Engineer)
- Verified against: `ga7ming3249/figma-os` `main` HEAD (`d3ebb1c33ea3d4c4824504309ffe349693556a92`, Repository fact, documentation-only commits `423e605` → `d3ebb1c` on top of `031887c`), and ASD Issues, as of 2026-08-18

---

# Purpose

This document gives the Architect (ChatGPT) visibility into the current state of the `figma-os` repository without requiring direct repository access.

`figma-os` is a private repository and remains private by design. ChatGPT initializes its product context from this document, the same way ASD sessions initialize from `docs/asd-state.md`.

Rules (mirroring `asd-state.md`):

- There is always only one current version. It is updated in place.
- Historical state is preserved through Git history.
- Claude Code updates this document after significant merges or status changes, with Human Authorization.
- This document reports verified facts only. Anything unverified is marked Unknown — Unknown is not a risk.

**Verification channel**: The ChatGPT GitHub Connector is a secondary, read-only verification channel. It is used only to audit that Product State matches the repository when additional confidence is required — never for determining priorities, architecture decisions, or Dashboard generation. Primary sources are always this document and `asd-state.md`.

Connector Read Validation: **Fully Verified (2026-07-17)** — ASD and figma-os repositories are readable. Product State was successfully audited against repository metadata, commit `ab69c8b`, synchronized documentation, the preserved Design Style Sheet v1.x artifact, and Component Package PR #1.

---

# Product Health

High-level product condition, readable in a few seconds. Qualitative by design — no commit counts, branch counts, or LOC.

| Field | State |
|---|---|
| Architecture | 🟢 Stable |
| Production Plugins | 6 |
| Beta Plugins | 3 (Type Adjuster; Color Inventory and Component Package in production trial) |
| Experimental Plugins | 2 (Type Polish; Design Style Sheet v1.x frozen spike) |
| Documentation | 🟢 Synced (Documentation Sync completed 2026-07-17; Canonical User Guide for Type Polish / Type Adjuster delivered 2026-08-18 via [figma-os#10](https://github.com/ga7ming3249/figma-os/issues/10), commit `d3ebb1c33ea3d4c4824504309ffe349693556a92`, under `docs/user-guides/` in `figma-os`) |
| Known Critical Bugs | 0 |
| High Priority Issues | 0 (figma-os#10, `priority:P1`, is now Accepted / Completed / Closed 2026-08-18) |
| Current Development Focus | [figma-os#12](https://github.com/ga7ming3249/figma-os/issues/12) — Type Adjuster: Plain-node Manual Adjustment Strategy (Next Architecture Dependency, decision Issue, no implementation; part of completing the Type Polish / Type Adjuster product architecture — see Product Priority) |
| Recommended First Action | `figma-os#12` — Plain-node Manual Adjustment Strategy |
| Top Product Priority | Type Polish completion (Vision Owner Priority Decision, 2026-08-18) — see Product Priority below |
| Gate 5 | [figma-os#6](https://github.com/ga7ming3249/figma-os/issues/6) — Accepted / Completed / Closed (2026-07-29T11:45:25Z); PR [figma-os#8](https://github.com/ga7ming3249/figma-os/pull/8) Merged to `main` at `d3abd4f46ce89240a22a467bbbf712f4c5e10628` |
| State Confidence | figma-os#6 / Gate 5 Completed / Accepted / Closed 2026-07-29, accepted implementation commit `9253ce8ce46dbd02225f9bfa73019f4662f575de` merged to `main@d3abd4f4...` via [figma-os#8](https://github.com/ga7ming3249/figma-os/pull/8); Gate 4 head `dc636115...` is now merged as part of this lineage |

---

# Product Priority

Vision Owner Priority Decision (2026-08-18). Current priority Figma OS plugins, in order: 1) Type Polish, 2) Type Adjuster, 3) Type Inventory, 4) Color Inventory.

**Type Polish completion is the top-level Product Goal.** Type Adjuster is already mature enough for daily production use on its own, but Figma OS's product strength is realized by the Type Polish (typography judgment: store/reuse, finishing) + Type Adjuster (execution, manual fine-tuning) pairing.

**Type Polish must not be treated as a Japanese-Vertical-only plugin.** Its Canonical Product Identity: store and reuse typography judgment, and semi-automate finishing work (和欧補正・日付・時刻・約物), with future expansion into Japanese Horizontal / Mixed Japanese–Latin / Latin typography. Japanese Vertical being currently the most advanced capability is an implementation-phase state, not a Product Scope limitation.

[figma-os#12](https://github.com/ga7ming3249/figma-os/issues/12) remains the immediate Next Architecture Dependency and Recommended First Action (see Product Health above) — now explicitly framed as part of completing the Type Polish / Type Adjuster product architecture, not an isolated Type Adjuster-only objective.

**This decision does not**: reopen [asd#31](https://github.com/ga7ming3249/asd/issues/31), close [asd#28](https://github.com/ga7ming3249/asd/issues/28), authorize any new implementation, change runtime code, skip figma-os#12, or auto-authorize Horizontal/Latin implementation work.

Unresolved capability-roadmap context requiring reconciliation (asd#28, asd#31, Japanese Horizontal, Mixed Japanese–Latin, Latin typography / standard finishing) — see Decisions Pending below and `docs/ROADMAP.md` → Future → "Type Polish Capability Roadmap Reconciliation".

---

# Recommended Next Priorities

Current recommended implementation order. This is a recommendation, not a commitment — it may change whenever Product State is updated.

**Completed — figma-os#2: Type Adjuster Scale UI synchronization**

figma-os#2 is Completed / Accepted / Closed (2026-07-24). Findings A/B/C were corrected; PR [figma-os#7](https://github.com/ga7ming3249/figma-os/pull/7) merged to `main` at `2838450c91429e9bc9c312103e0741c64e0068d2` (implementation commit `874d94dbfa4336ab064822e1ccc07ece12795149`). Verified: Build Success, Typecheck Success, Automated Tests 138/138 passed, Desktop Verification All Pass. Scale State Sync is now an accepted capability of Type Adjuster. Cleanup of the isolated worktree/feature branch (`feature/issue-2-scale-state-sync`) used during implementation is optional maintenance only.

**Completed — figma-os#6: Gate 5 Desktop Acceptance**

figma-os#6 is Accepted / Completed / Closed (2026-07-29T11:45:25Z). PR [figma-os#8](https://github.com/ga7ming3249/figma-os/pull/8) merged to `main` at `d3abd4f46ce89240a22a467bbbf712f4c5e10628` (accepted implementation commit `9253ce8ce46dbd02225f9bfa73019f4662f575de`). Verified: Type Adjuster full suite 278/278, Scale UI tests 109/109, Gate 4 Local Fix tests 163/163, G5-DEF-002 generated marker tests 6/6, Type Polish full suite 165/165, both builds PASS, Rebased-head Desktop Acceptance 7/7 PASS. Japanese Vertical — Standard / Safe Local Fix MVP Gate 0–Gate 5 are complete; `asd#30` is Closed / Completed.

**Completed — figma-os#3: Type Polish Utility Ownership Canonical Decision**

figma-os#3 is Accepted / Completed / Closed (`state_reason: COMPLETED`, closed `2026-08-18T05:03:24Z`; Issue-scoped Architect final result: Accepted). Architecture Decision comment: [figma-os#3#issuecomment-5323799447](https://github.com/ga7ming3249/figma-os/issues/3#issuecomment-5323799447). **Canonical manual-adjustment owner: Type Adjuster** (Scale / Baseline / Tracking). Type Polish's existing Utility is reclassified as a **Legacy Compatibility Capability Pending Migration/Removal** — immediate removal remains prohibited. This closure is **not** an Implementation Authorization; it does not by itself authorize any Type Polish source change. See "Type Polish Utility Ownership — Migration Chain" below for the follow-up Issues and current status.

**Completed — figma-os#10: Type Polish / Type Adjuster User Guide**

figma-os#10 is Accepted / Completed / Closed (`state_reason: COMPLETED`, closed 2026-08-18; Issue-scoped Architect final result: Accepted, completion comment [figma-os#10#issuecomment-5327103969](https://github.com/ga7ming3249/figma-os/issues/10#issuecomment-5327103969)). Canonical User Guide delivered as Markdown under `docs/user-guides/` in `ga7ming3249/figma-os`: `type-polish.md`, `type-adjuster.md`, `type-polish-type-adjuster-workflow.md`, `glossary.md`, `faq.md`. Navigation added from `README.md`, `PLUGINS.md`, `type-polish/README.md`, `type-adjuster/README.md`. Documentation-only — no runtime source, tests, or `docs/shared/handoff-schema.md` changes. Accepted implementation commit `423e6054b8c20a8c6e4b81cde38c34fb6bca3daf` (initial User Guide), with a follow-up Accepted correction commit `d3ebb1c33ea3d4c4824504309ffe349693556a92` (clarifies that Type Polish's zero-mutation scope covers Document Content only, not the Local Fix Handoff shared-metadata write) — `d3ebb1c...` is the final accepted `main` HEAD. The figma-os#3 canonical ownership model is reflected: Scale/Baseline/Tracking canonical owner is Type Adjuster; Type Polish's own Utility panel is documented as Legacy Compatibility Capability Pending Migration/Removal, never described as a current owner. Verified: Type Polish tests 243/243, Type Adjuster tests 278/278 (via `tsx`), scoped `tsc --noEmit` clean, full link/anchor check clean, UI labels cross-checked verbatim against `ui.html` in both plugins. Follow-up candidates recorded but **not** implemented under figma-os#10: `docs/shared/handoff-schema.md` Gate 4/Gate 5 wording drift, `type-adjuster/HISTORY.md` Gate 3/4/5 history gap, Type Adjuster test-runner ergonomics (no canonical `npm test` script).

Architect-Accepted execution order (2026-08-18, superseding the 2026-07-29 order now that figma-os#10 is Completed), numbered to avoid confusion with GitHub `priority:P0–P3` labels:

**1 — figma-os#12: Type Adjuster — Plain-node Manual Adjustment Strategy**

Reason: Architect-Accepted. Next Architecture Dependency following figma-os#3's Acceptance/Close (2026-08-18). Determines the Maintain/Replace/Discontinue disposition of manual adjustment (Scale/Baseline/Tracking) on plain/ungenerated TextNodes — the largest feature-parity gap identified against Type Adjuster's current `resolveSelection` scope. This Issue is a decision, not an implementation. Per the Vision Owner Priority Decision (2026-08-18, see Product Priority above), this is now explicitly framed as part of completing the Type Polish / Type Adjuster product architecture — not an isolated Type Adjuster-only objective.

Prerequisite: figma-os#3 completion — satisfied 2026-08-18

Downstream of figma-os#12's decision: figma-os#13 (Manual Adjustment Migration, **contingent** — only required if #12 determines Type Adjuster coverage must change), figma-os#14 (Utility Ownership Documentation Migration), figma-os#15 (Utility Deprecation / Removal, **Blocked** — must not be front-run ahead of #12/#13/#14 and regression/Desktop verification). See "Type Polish Utility Ownership — Migration Chain" below.

**2 — asd#31: Japanese Horizontal Typography Analysis Track** (`priority:P2`)

Reason: Architect-Accepted. New capability track beginning at Gate 0; not blocking current production capability. Parent Coordination Issue for a new Gate 0–Gate 5 Japanese Horizontal Typography structure — not incomplete Gate 5 scope (Japanese Vertical — Standard Gate 5 is Accepted / Completed / Closed). Gate 0 Knowledge Collection may begin before figma-os#3 is resolved; Utility removal, transfer, or ownership-changing implementation must not begin before figma-os#3 is resolved. Type Polish remains zero-mutation; Type Adjuster retains execution and document-mutation ownership.

Prerequisite: None for Gate 0 Knowledge Collection; figma-os#3 resolution required before any Utility ownership-changing implementation. Gate 0 may proceed independently when appropriate, but this is not the current first implementation priority.

**Status update (2026-08-05 Nightly Canonical Synchronization)**: asd#31 is Closed (`2026-08-05T10:08:05Z`; single close event, no reopen event exists in GitHub history). KB-0001–KB-0003 are registered in the repository; KB-0004 and KB-0005 are Remote Registration Pending (no repository artifact found for either — see Recent Changes). A repository commit (`5464a78`, 2026-08-01, no PR) implementing read-only Horizontal Analysis exists on `main` but has no identified Architecture Review record — Repository Evidence Identified, Architecture Classification Pending (see Decisions Pending). This priority entry's original text above is preserved as the historical record as of 2026-07-29; it is not rewritten to fit tonight's findings. figma-os#10 (Priority 1) and figma-os#3 (Priority 2) are unaffected and remain the current execution order.

**Status update (2026-08-18)**: figma-os#3 is now Accepted / Completed / Closed. The "Utility removal, transfer, or ownership-changing implementation must not begin before figma-os#3 is resolved" condition above is superseded — the operative gate is now the figma-os#3 follow-up migration chain (figma-os#12 → #13 if applicable → #14 → #15), not figma-os#3 itself. asd#31 remains Closed and this entry remains historical; any future Horizontal Typography work still requires a new Issue and explicit Architecture Authorization, unaffected by the figma-os#3 decision.

**Status update (2026-08-18, second sync)**: figma-os#10 (Type Polish / Type Adjuster User Guide) is now Accepted / Completed / Closed — accepted `main` HEAD `d3ebb1c33ea3d4c4824504309ffe349693556a92`, see "Completed — figma-os#10" above. It no longer occupies Priority 1 in the execution order; the order above is renumbered starting from figma-os#12. A separate Presentation/Distribution-layer Issue was registered in `ga7ming3249/figma-os` for an offline HTML copy of the accepted User Guide; per explicit State Update Decision, that Issue's registration is not itself a target of this State/ROADMAP synchronization and is not tracked in the execution order above.

**3 — Component Package: production trial & polish**

Reason: Recently merged (PR #1, 2026-07-16). Mature it through daily production use and collect small improvements as new Issues before starting the next Foundation work.

Prerequisite: None (the trial itself is the work)

**4 — Color Inventory: Generate Inventory Page**

Reason: v1 core (Generate / Raw Colors Workbench / Promote) is in production trial; Inventory Page generation is the next increment toward Production promotion.

Prerequisite: None

**5 — Type Inventory: multiline support ([figma-os#4](https://github.com/ga7ming3249/figma-os/issues/4))**

Reason: Backlog item per ASD priority assessment. Clear workaround exists; lower user impact.

Prerequisite: None (Guide Stamp Canvas Guides, ASD #9, completed 2026-07-17)

**6 — Composer / Design Style Sheet v2**

Reason: Foundation plugins (Color Inventory, Component Package) need to mature through production use first; see Decisions Pending.

Prerequisite: Component Package and Color Inventory production trials substantially complete

---

# Decisions Pending

Unresolved architectural or product decisions requiring Vision Owner and/or Architect input. Implementation tasks are not listed here.

**Design Style Sheet v2**

Waiting for architecture decision. DSS v1.x is frozen as a spike; v2 is to be redesigned as a Composer after Foundation matures. Includes the recorded ROADMAP homework: redefine the page-generation role split between DSS Colors section and Color Inventory.

**KB-0004 / KB-0005 Remote Registration** (identified 2026-08-05 Nightly Canonical Synchronization)

Neither a `knowledge-base/` entry nor an `architecture-reviews/` file exists in the repository for KB-0004 or KB-0005, despite an Issue comment describing KB-0005's Knowledge Extraction as Complete/Accepted. No source artifact has been located locally or in GitHub to register verbatim. Requires either the original artifact being supplied for verbatim registration, or a Global Architect decision on how to proceed.

**Type Polish Capability Roadmap Reconciliation** (identified 2026-08-18, Vision Owner Priority Decision)

Type Polish's Canonical Product Identity extends beyond Japanese Vertical (see Product Priority above) into Japanese Horizontal / Mixed Japanese–Latin / Latin typography. Reconciliation is required across: [asd#28](https://github.com/ga7ming3249/asd/issues/28) (Japanese Vertical Typography & Latin Kerning Knowledge Review — deliverables completed, Issue itself still Open), [asd#31](https://github.com/ga7ming3249/asd/issues/31) (Japanese Horizontal Typography Analysis Track — Closed, Gate 0 only, KB-0004/KB-0005 Remote Registration Pending, see above), the Horizontal Analysis capability itself (commit `5464a78`, Architecture Classification: Experimental, Accepted Commit: No, Canonical Gate Acceptance Gate 0 only per asd#34), Mixed Japanese–Latin typography (not started), and Latin typography / standard finishing (not started). Reconciliation must determine, per item: Completed / Experimental / Frozen / Unfinished / Successor Issue ownership. New product-specific Issues should normally be registered in `ga7ming3249/figma-os` per the Repository Issue Ownership Policy; an ASD Parent Coordination Issue should exist only where genuine Global Architecture / Gate coordination is required. This is a recorded reconciliation need, not a decision — reconciliation itself requires separate Issue-scoped Architect work. Does not reopen asd#31 or close asd#28.

---

# Type Polish Utility Ownership — Migration Chain

Resolved by [figma-os#3](https://github.com/ga7ming3249/figma-os/issues/3) (Accepted / Completed / Closed, 2026-08-18). No longer a Decisions Pending item; tracked here as an active migration chain instead.

- **Canonical ownership**: Type Adjuster owns manual typography adjustment (Scale / Baseline / Tracking).
- **Type Polish Utility**: Legacy Compatibility Capability Pending Migration/Removal. **Immediate removal is prohibited.**
- **Freeze scope**: The Type Polish no-feature-addition Freeze (`CLAUDE.md`) is not lifted generally. figma-os#3 is superseding authority *only* for the Utility deprecation/removal work below.
- **This is not an Implementation Authorization.** figma-os#3's closure does not itself authorize any Type Polish source change.

| Issue | Title | Status | Dependency |
|---|---|---|---|
| [figma-os#12](https://github.com/ga7ming3249/figma-os/issues/12) | Plain-node Manual Adjustment Strategy | Open — **Next Architecture Dependency** | Depends on figma-os#3 (satisfied) |
| [figma-os#13](https://github.com/ga7ming3249/figma-os/issues/13) | Manual Adjustment Migration | Open — **Contingent**, not an unconditional implementation commitment | Required only if #12 determines Type Adjuster coverage must change |
| [figma-os#14](https://github.com/ga7ming3249/figma-os/issues/14) | Utility Ownership Documentation Migration | Open | figma-os#10 (User Guide) is now Completed 2026-08-18 (commit `d3ebb1c...`) — #14 performs the Canonical ownership-model documentation migration itself (README/ROADMAP language) and should treat the accepted User Guide as sync input, not re-litigate its content |
| [figma-os#15](https://github.com/ga7ming3249/figma-os/issues/15) | Utility Deprecation / Removal | Open — **Blocked** | Blocked on #12, #13 (if applicable), #14, and regression/Desktop verification. Must not be front-run. |

Dependency order: #12 → #13 (if applicable) → #14 → #15.

---

# Architect Snapshot

Executive summary for ASD Dashboard generation. Intentionally redundant with other sections to optimize Architect initialization (target: understood in under 30 seconds).

Recommended reading order for initialization: **Architect Snapshot → Product Health → Plugin State → Documentation Sync**, descending into other sections only when needed. This Snapshot may serve as the sole input for Dashboard generation.

```text
Architecture
Stable

Top Product Priority
Type Polish completion (Vision Owner Priority Decision, 2026-08-18) — see Product Priority. Priority plugin order: 1) Type Polish, 2) Type Adjuster, 3) Type Inventory, 4) Color Inventory.

Current Focus
figma-os#12 — Type Adjuster: Plain-node Manual Adjustment Strategy (Next Architecture Dependency, decision Issue, no implementation; framed as part of completing the Type Polish / Type Adjuster product architecture)

Highest Priority
figma-os#12 — determines Maintain/Replace/Discontinue disposition of manual adjustment (Scale/Baseline/Tracking) on plain/ungenerated TextNodes

Next Milestone
figma-os#12 decision, unblocking the remainder of the Type Polish Utility Ownership — Migration Chain (#13 if applicable → #14 → #15)

Blockers
None affecting Recommended First Action (figma-os#12). Pending, not blocking: KB-0004/KB-0005 Remote Registration for the now-Closed asd#31 track — see Decisions Pending. (Architecture Classification of `main` commit `5464a78` was resolved 2026-08-07 via asd#34 — Experimental, Accepted Commit: No — see Recent Changes.) figma-os#3 resolved 2026-08-18 (Accepted/Closed) — see "Type Polish Utility Ownership — Migration Chain". figma-os#10 (Type Polish / Type Adjuster User Guide) is now Accepted / Completed / Closed 2026-08-18, commit `d3ebb1c33ea3d4c4824504309ffe349693556a92` — see "Completed — figma-os#10" under Recommended Next Priorities. Type Polish capability-roadmap reconciliation (asd#28 / asd#31 / Horizontal / Mixed Japanese–Latin / Latin typography) is outstanding, not blocking — see Decisions Pending.

Overall Health
Healthy
```

---

# Repository Overview

- Repo: `ga7ming3249/figma-os` (private, monorepo)
- Nature: Personal Figma plugin portfolio for production design work
- Development policy: "Grow a personal Figma OS" — stability of existing plugins takes priority over new ideas
- New-feature gate (all 3 required): used weekly / saves 5+ minutes of manual work / not achievable with an existing plugin
- Common conventions: `code.ts` + `ui.html` two-file architecture (some plugins use Vite with `src/` + `dist/`), minimal UI (1–3 buttons, no settings screens), 8pt grid, `pluginData` for identifying generated content

Key documents inside the repo:

- `README.md` — plugin index and build instructions
- `PLUGINS.md` — status/phase management
- `ROADMAP.md` — development policy, Foundation/Composer architecture, implementation order
- `docs/Plugin Handbook.md` — shared design rules and Figma API know-how

---

# Architecture: Foundation / Composer (confirmed 2026-07-12)

```
Foundation Plugins (Workbench — observation + explicit edit commands)
  ├── Color Inventory      (v1 core complete — Generate / Raw Colors Workbench / Promote)
  ├── Type Inventory       (complete, in production use)
  ├── Component Package    (v1 Core complete — see Recent Changes)
  └── Instance Checker     (existing)
        ▼ outputs / shared core
Composer (Mirror — pure observation, no writes)
  └── Design Style Sheet   (v1.x frozen as spike; v2 redesign planned after Foundation matures)
```

**Workbench Principle**: A Foundation Plugin may offer explicitly named edit commands only for facts it has itself observed. Default is observation; edits require the 4-step flow: Preview (impact count) → explicit approval → execute → result report. Only the Composer (DSS) carries the Mirror guarantee (never writes).

---

# Plugin State (reconciled)

This table reflects the verified repository and documentation state as of 2026-07-17.

| Plugin | Dir | Version | Phase | Status | Notes |
|---|---|---|---|---|---|
| Guide Stamp | `guide-stamp/` | v2.x | Maintenance | Production | Canvas Guides added (ASD #9, closed 2026-07-17) |
| Instance Checker | `instance-checker/` | v1.x | Maintenance | Production | |
| Margin Preflight | `margin-preflight/` | v1.x | Feature Enhancement | Production | Known issue: some Auto Layout frames undetected (collecting cases) |
| Pocket Preview | `pocket-preview/` | v1.0 | Maintenance | Production | Figma / device / Claude Code (MCP) utility panel |
| Type Inventory | `type-inventory/` | v1.4 | Feature Enhancement | Production | Open [figma-os#4](https://github.com/ga7ming3249/figma-os/issues/4) (multiline support, P3, backlog — transferred from asd#3, 2026-07-22) |
| Status Stamp | `status-stamp/` | v0.3 | Design Sprint | Production | ASD Issue #1 (stamp-selection update) closed |
| Color Inventory | `color-inventory/` | v1.0 | Design Sprint | Beta | Spec v0.3. v1 core (Generate / Raw Colors Workbench / Promote) in production trial. Promotion criteria in ROADMAP.md |
| Component Package | `component-package/` | v1.0 | Design Sprint | Beta | v1 Core merged (PR #1, 2026-07-16). Canonical Documentation: `component-package/HISTORY.md` + `ROADMAP.md`; `asd#2` body + supplemental comments are the Historical Specification Record from v1 Core implementation. Promotion criteria in ROADMAP.md |
| Type Adjuster | `type-adjuster/` | v0.5 | Feature Enhancement | Beta | Gate 4 + Gate 5 accepted and merged to `main` at `d3abd4f4...` (PR [figma-os#8](https://github.com/ga7ming3249/figma-os/pull/8), 2026-07-29, accepted implementation commit `9253ce8c...`): explicit pending-request revalidation and Apply, `LF-UPRIGHT-001`, `LF-ROTATE-RUN-001`, validated group-member Nudge, conflict-safe structural Reset using the `retained-original-node` architecture, and the shared generated marker contract. Remains non-judgmental. Scale State Sync ([figma-os#2](https://github.com/ga7ming3249/figma-os/issues/2), Closed) is included in the same `main` lineage. **Canonical owner of manual typography adjustment (Scale/Baseline/Tracking)** per [figma-os#3](https://github.com/ga7ming3249/figma-os/issues/3) (Accepted/Closed 2026-08-18) — see "Type Polish Utility Ownership — Migration Chain". User-facing documentation delivered by [figma-os#10](https://github.com/ga7ming3249/figma-os/issues/10) (Accepted/Completed/Closed 2026-08-18, commit `d3ebb1c...`) at `docs/user-guides/type-adjuster.md` |
| Type Polish | `type-polish/` | v0.6 | Research | Experimental | Gate 4 + Gate 5 accepted and merged to `main` at `d3abd4f4...` (PR [figma-os#8](https://github.com/ga7ming3249/figma-os/pull/8), 2026-07-29): current-selection-only applied-marker reader, already-applied short-circuit (priority over generated-skip within a valid Local Fix range), read-only ancestor-chain exclusion of Type Adjuster-generated output, fail-closed blocked state, and zero document mutation. Owns Analysis, Recommendation, User Decision, and Handoff production. **Utility (Scale/Baseline/Tracking) is Legacy Compatibility Capability Pending Migration/Removal** per [figma-os#3](https://github.com/ga7ming3249/figma-os/issues/3) (Accepted/Closed 2026-08-18) — immediate removal prohibited, migration tracked by figma-os#12–#15 (see "Type Polish Utility Ownership — Migration Chain"); a new Japanese Horizontal Typography capability track is tracked by [asd#31](https://github.com/ga7ming3249/asd/issues/31) (Gate 0, not incomplete Gate 5 scope). User-facing documentation delivered by [figma-os#10](https://github.com/ga7ming3249/figma-os/issues/10) (Accepted/Completed/Closed 2026-08-18, commit `d3ebb1c...`) at `docs/user-guides/type-polish.md`. **Canonical Product Identity extends beyond Japanese Vertical** to Japanese Horizontal / Mixed Japanese–Latin / Latin typography per Vision Owner Priority Decision (2026-08-18) — see Product Priority; Type Polish completion is the current top-level Figma OS Product Goal |
| Design Style Sheet | `design-style-sheet/` | v0.1.1 | Concept | Experimental (frozen spike) | v1.x preserved in repo as a frozen historical artifact (2026-07-17). No feature development; preservation fixes only. v2 redesign via new ASD Issue |

Out of scope: **Reference Assistant** is not part of `figma-os`. As of 2026-07-23, repository `ga7ming3249/reference-assistant` exists as its independent Product Repository; its Product Issues are owned there. `asd#4` and `asd#6` were closed after Successor Issue transfer to that repository (2026-07-23); `asd#5` remains historical (closed, unchanged).

---

# Recent Changes

## Vision Owner Priority Decision — Type Polish completion prioritized (2026-08-18)

Vision Owner decision, ASD Canonical State Synchronization. Current priority Figma OS plugins, in order: 1) Type Polish, 2) Type Adjuster, 3) Type Inventory, 4) Color Inventory. **Type Polish completion is the top-level Product Goal** — Type Adjuster is already mature for daily production use on its own, but Figma OS's product strength is realized by the Type Polish (typography judgment store/reuse, finishing) + Type Adjuster (execution, manual fine-tuning) pairing.

- **Type Polish is not a Japanese-Vertical-only plugin.** Canonical Product Identity: store/reuse typography judgment, semi-automate finishing (和欧補正・日付・時刻・約物), with future expansion into Japanese Horizontal / Mixed Japanese–Latin / Latin typography. Japanese Vertical being furthest along is an implementation-phase state, not a Product Scope limit.
- [figma-os#12](https://github.com/ga7ming3249/figma-os/issues/12) remains the immediate Next Architecture Dependency and Recommended First Action, unchanged — now explicitly framed as part of completing the Type Polish / Type Adjuster product architecture rather than an isolated Type Adjuster objective.
- New Decisions Pending item registered: "Type Polish Capability Roadmap Reconciliation" covering [asd#28](https://github.com/ga7ming3249/asd/issues/28), [asd#31](https://github.com/ga7ming3249/asd/issues/31), the Horizontal Analysis capability (commit `5464a78`), Mixed Japanese–Latin typography, and Latin typography / standard finishing.
- **This synchronization does not**: reopen asd#31, close asd#28, authorize any new implementation, change runtime code, skip figma-os#12, or auto-authorize Horizontal/Latin implementation work. No `figma-os` product repository commit was made.
- See `docs/ROADMAP.md` → Future → "Type Polish Capability Roadmap Reconciliation" for the corresponding roadmap entry.

## Issue #10 — Type Polish / Type Adjuster User Guide — Accepted / Completed / Closed (2026-08-18)

[figma-os#10](https://github.com/ga7ming3249/figma-os/issues/10) (Type Polish / Type Adjuster User Guide) is **Accepted / Completed / Closed** (`state_reason: COMPLETED`, closed 2026-08-18; Issue-scoped Architect final result: Accepted). Completion comment: [figma-os#10#issuecomment-5327103969](https://github.com/ga7ming3249/figma-os/issues/10#issuecomment-5327103969).

- Canonical User Guide delivered as Markdown under `docs/user-guides/` in `ga7ming3249/figma-os`: `type-polish.md`, `type-adjuster.md`, `type-polish-type-adjuster-workflow.md`, `glossary.md`, `faq.md`
- Navigation added from `README.md`, `PLUGINS.md`, `type-polish/README.md`, `type-adjuster/README.md`
- Documentation-only diff both rounds — no runtime source, tests, or `docs/shared/handoff-schema.md` changes
- Commit lineage: baseline `031887cbf1b65336682212f13df3d609ce46267a` → `423e6054b8c20a8c6e4b81cde38c34fb6bca3daf` (initial User Guide) → `d3ebb1c33ea3d4c4824504309ffe349693556a92` (Accepted correction: clarifies Type Polish's zero-mutation scope covers Document Content only, not the Local Fix Handoff shared-metadata write). `d3ebb1c...` is the final accepted `figma-os/main` HEAD
- Ownership model reflected: Scale/Baseline/Tracking canonical owner is Type Adjuster; Type Polish's own Utility panel is documented as Legacy Compatibility Capability Pending Migration/Removal per figma-os#3, never described as a current owner
- Verified: Type Polish tests 243/243, Type Adjuster tests 278/278 (via `tsx`, no source changed), scoped `tsc --noEmit` clean, full link/anchor check clean (0 broken links), UI labels cross-checked verbatim against `type-polish/ui.html` / `type-adjuster/ui.html`, Retained Original / generated-structure / Reset wording verified against Gate 5 G5-DEF-001/G5-DEF-002 implementation (original TextNode retained, never removed)
- Follow-up candidates recorded but **not** implemented under figma-os#10: `docs/shared/handoff-schema.md` Gate 4 "consumed-then-removed" wording drift vs. Gate 5 G5-DEF-001 retained-original behavior; `type-adjuster/HISTORY.md` missing Gate 3/4/5 entries; Type Adjuster test execution ergonomics (no canonical `npm test` script/runner)
- A separate Presentation/Distribution-layer Issue (self-contained offline HTML copy of the accepted User Guide for Dropbox viewing) was registered in `ga7ming3249/figma-os`; per explicit State Update Decision, that Issue's registration is not a target of this synchronization and is not tracked in Recommended Next Priorities

## Issue #3 — Type Polish Utility Ownership Canonical Decision Published, Accepted / Completed / Closed (2026-08-18)

[figma-os#3](https://github.com/ga7ming3249/figma-os/issues/3) (Product Decision — Consolidate Type Polish Utility Ownership into Type Adjuster) is **Accepted / Completed / Closed** (`state_reason: COMPLETED`, closed `2026-08-18T05:03:24Z`; Issue-scoped Architect final result: Accepted). Architecture Decision comment: [figma-os#3#issuecomment-5323799447](https://github.com/ga7ming3249/figma-os/issues/3#issuecomment-5323799447); follow-up numbers comment: [figma-os#3#issuecomment-5323827087](https://github.com/ga7ming3249/figma-os/issues/3#issuecomment-5323827087); close comment: [figma-os#3#issuecomment-5323842184](https://github.com/ga7ming3249/figma-os/issues/3#issuecomment-5323842184).

- Canonical manual-adjustment owner: **Type Adjuster** (Scale / Baseline / Tracking)
- Type Polish Utility: reclassified as **Legacy Compatibility Capability Pending Migration/Removal** — immediate removal remains prohibited
- Utility Ownership item removed from Decisions Pending as of this synchronization (was previously recorded there since 2026-07-22)
- Freeze exception: scoped **solely** to the Utility deprecation/removal migration tracked by figma-os#12–#15; the general Type Polish Freeze (`CLAUDE.md`) is otherwise unchanged
- **Not an Implementation Authorization**: figma-os#3's closure does not by itself authorize any Type Polish source change
- Four follow-up Issues created in `ga7ming3249/figma-os`, all Open: [figma-os#12](https://github.com/ga7ming3249/figma-os/issues/12) (Plain-node Manual Adjustment Strategy — **Next Architecture Dependency**), [figma-os#13](https://github.com/ga7ming3249/figma-os/issues/13) (Manual Adjustment Migration, **contingent** on #12), [figma-os#14](https://github.com/ga7ming3249/figma-os/issues/14) (Utility Ownership Documentation Migration), [figma-os#15](https://github.com/ga7ming3249/figma-os/issues/15) (Utility Deprecation / Removal, **Blocked**, must not be front-run)
- Dependency order: #12 → #13 (if applicable) → #14 → #15
- figma-os#10 (User Guide) is unaffected in necessity but its scope must now incorporate the canonical ownership model, coordinated with figma-os#14 to avoid documentation-migration overlap
- See "Type Polish Utility Ownership — Migration Chain" section above for the current dependency table

## Issue #34 — Repository Evidence Classification: Commit `5464a78` Resolved (2026-08-07)

[asd#34](https://github.com/ga7ming3249/asd/issues/34) (Review and Classify Repository Evidence Commit 5464a78) is **Closed / Completed** (`2026-08-07T09:03:45Z`, Issue-scoped Architect final result: Accepted). This resolves the commit-`5464a78` Architecture Classification Pending item recorded in the 2026-08-05 synchronization below; that item has been removed from Decisions Pending accordingly.

- Architecture Classification: **Experimental**
- Accepted Commit: **No**
- Functional Implementation Scope: Gate 2 + partial Gate 3 equivalent (a functional-scope classification only, not Gate Acceptance)
- Canonical Gate Acceptance: **Gate 0 only** — Gate 1 / Gate 2 / Gate 3 Acceptance: **Not established**
- Read-only / zero-mutation: Verified by available static and test evidence
- Recommendation Scope: Present, non-executable
- Rule Promotion: **None**
- Utility Ownership Change: **None**
- Freeze Compliance: **Not established** (the pre-existing Type Polish no-feature-addition Freeze predates the commit; no exception or superseding Architecture Decision was found)
- Immediate Revert: Not required
- Publication Commit: [`031887cbf1b65336682212f13df3d609ce46267a`](https://github.com/ga7ming3249/figma-os/commit/031887cbf1b65336682212f13df3d609ce46267a) — records `references/type-polish/japanese-horizontal-typography/architecture-reviews/ARCHITECTURE-REVIEW-COMMIT-5464A78.md`, `.../review-records/REVIEW-0002.md`, and a `type-polish/HISTORY.md` entry

KB-0004 / KB-0005 Remote Registration Pending is unaffected by this resolution and remains outstanding (see Decisions Pending).

## ASD Nightly Canonical Synchronization — Repository Evidence Review (2026-08-05)

Publisher audit of `ga7ming3249/figma-os` `main` against asd#31's Knowledge Track scope, following an unverified KB-0005 review comment that closed asd#31 (see asd#33). All items below are Repository facts; none constitute Architecture classification.

- **KB-0001–KB-0003**: Registered — `references/type-polish/japanese-horizontal-typography/knowledge-base/` (commits `8b15f28`, `3d22e8a`, `3f1599e`).
- **KB-0004**: Not Found — no file in the repository, no trace in git history on any branch, no GitHub Issue comment content. **Remote Registration Pending.**
- **KB-0005**: Not Found as a repository file. An Architecture Review summary exists as an [asd#31 Issue comment](https://github.com/ga7ming3249/asd/issues/31#issuecomment-5190421555) (`2026-08-05T10:08:00Z`) describing Knowledge Extraction as Complete/Accepted, but no corresponding `knowledge-base/` or `architecture-reviews/` file exists in the repository. **Remote Registration Pending.**
- No Accepted Commit SHA exists for KB-0004 or KB-0005. Publisher has not created, drafted, or reconstructed either artifact — see [Publisher Verification comment on asd#31](https://github.com/ga7ming3249/asd/issues/31#issuecomment-5190980016).
- **Repository Evidence Identified — Architecture Classification Pending**: commit `5464a78bf3500475a8855f10cfb8aaa75b9caa39` (2026-08-01 22:17:35 JST) is on `main`, pushed directly with no associated PR. Per its commit message and diff, it adds a read-only Horizontal Analysis Profile (`japanese-horizontal-standard-v1`) under `type-polish/src/core/horizontal/`: boundary observation (HR-001/HR-002), an unsupported-observation status for HR-003, conflict *detection only* for HR-004 (no auto-resolution), and read-only Recommendation generation with execution capability stated as never enabled; no Vertical pipeline, Type Adjuster, Handoff contract, Generated Marker contract, or Utility code was modified per the commit message. No Architecture Review evidence or formal Acceptance record for this commit has been identified. Not classified here as Accepted, Rejected, Gate 2/3-satisfying, or Canonical Architecture — escalated for Global Architect review (see Decisions Pending).
- asd#31 is **Closed** (`2026-08-05T10:08:05Z`, single close event, no reopen event in GitHub history — see [asd#31 Publisher Verification](https://github.com/ga7ming3249/asd/issues/31#issuecomment-5190980016)).

## figma-os#10 and asd#31 — registered and Architect-Accepted (2026-07-29, second same-day sync)

- [figma-os#10](https://github.com/ga7ming3249/figma-os/issues/10) — Type Polish / Type Adjuster User Guide. Open, Architect-Accepted, Documentation / UX Enablement, `priority:P1`. Labels: `documentation`, `ux`, `type-polish`, `type-adjuster`, `priority:P1`. Canonical source is Markdown inside `ga7ming3249/figma-os`. Scope: Type Polish guide, Type Adjuster guide, combined workflow guide, glossary, FAQ, navigation, maintenance rule. Out of scope: Architecture Guide, Developer Guide, UI redesign, tooltip implementation, onboarding UI.
- [asd#31](https://github.com/ga7ming3249/asd/issues/31) — Type Polish — Japanese Horizontal Typography Analysis Track. Open, Architect-Accepted, Product Capability / Parent Coordination Issue, `priority:P2`. Labels: `enhancement`, `architecture`, `roadmap`, `product:type-polish`, `priority:P2`. New Gate 0–Gate 5 capability track; not incomplete Gate 5 scope (Japanese Vertical — Standard Gate 5 remains Accepted / Completed / Closed). Gate 0 Knowledge Collection may begin before figma-os#3 is resolved; Utility ownership-changing implementation is blocked until figma-os#3 is resolved.
- Architect-Accepted execution order: 1) figma-os#10, 2) figma-os#3, 3) asd#31 (Gate 0 may proceed independently when appropriate, but is not the current first implementation priority).

## figma-os#6 — Gate 5 Desktop Acceptance — Accepted / Completed / Closed (2026-07-29)

- Closed `2026-07-29T11:45:25Z` (2026-07-29 20:45:25 JST), state reason Completed.
- PR [figma-os#8](https://github.com/ga7ming3249/figma-os/pull/8) merged to `figma-os/main` (base `main`, 7 commits, merged `2026-07-29T11:44:32Z`) — accepted implementation commit `9253ce8ce46dbd02225f9bfa73019f4662f575de`, merge commit `d3abd4f46ce89240a22a467bbbf712f4c5e10628`.
- Verified: Type Adjuster full suite `278/278 PASS`, Scale UI tests `109/109 PASS`, Gate 4 Local Fix tests `163/163 PASS`, G5-DEF-002 generated marker tests `6/6 PASS`, Type Polish full suite `165/165 PASS`, Type Adjuster build PASS, Type Polish build PASS.
- Desktop Acceptance: Pre-rebase `9/9 PASS` (macOS `26.5.2 (25F84)`, Figma Desktop App `126.6.14`); Rebased-head `7/7 PASS` (macOS `26.5.2 (25F84)`, Figma Desktop App `126.7.10`).
- Confirmed architecture: Local Fix Reset uses `retained-original-node` — the original TextNode instance is retained and restored, not reconstructed; Reset resolves the unique valid Local Fix group from ancestor/descendant relationships among the Local Fix member, outer Frame, and selection container, failing closed on multiple candidates, corruption, invalidity, or ambiguity. Reset and Nudge availability remain independent conditions.
- Confirmed cross-plugin generated marker contract: Type Adjuster attaches a shared generated marker to the outer Frame on every generation path (horizontal Split, vertical Split, Local Fix Apply); Type Polish reads the ancestor chain read-only and excludes Type Adjuster-generated output from normal analysis, with `already-applied` taking priority over `generated-skip` inside a valid Local Fix range. Type Polish performs zero document mutation.
- Scale UI and Local Fix integration regression Accepted. Gate 4 accepted branch, Gate 4 Integration, Scale UI, and Gate 5 dependency history are closed.
- Generic Vertical Split Reset and Reset button visual state are not Gate 5 defects or unfinished Gate 5 items; they remain Post-Gate-5 Follow-up Candidates only, not created as Issues by this synchronization.
- Current implementation base is now `figma-os/main` merge commit `d3abd4f46ce89240a22a467bbbf712f4c5e10628`.
- `asd#30` (Japanese Vertical — Standard / Safe Local Fix MVP, Gate 0–Gate 5) is Closed / Completed as of this Canonical State Synchronization.

## figma-os#2 — Completed / Accepted / Closed (2026-07-24)

- Findings A, B, and C from the prior Changes-Required review were corrected.
- PR [figma-os#7](https://github.com/ga7ming3249/figma-os/pull/7) merged to `figma-os/main` at `2838450c91429e9bc9c312103e0741c64e0068d2` (implementation commit `874d94dbfa4336ab064822e1ccc07ece12795149`), closing figma-os#2.
- Verified: Build Success, Typecheck Success, Automated Tests 138/138 passed, Desktop Verification All Pass.
- Scale State Sync is recorded as an accepted Type Adjuster capability.
- Verified `figma-os/main` HEAD is now `2838450c91429e9bc9c312103e0741c64e0068d2`.
- A Dedicated Main Worktree is recorded as the canonical verification environment for the latest Type Adjuster builds going forward.
- The Protected Gate 4 checkout (`dc6361157345ebb8b17264f63aef8fa0e265c5eb`) remains a separate, intentionally isolated development environment, unaffected by this merge.
- Cleanup of the isolated worktree/feature branch (`feature/issue-2-scale-state-sync`) used during implementation is optional maintenance only, not required for Issue closure.

## Issue #29 — OpenType Typography Features Capability Review: findings completed

- OpenType write unsupported
- `vert` / `vrt2` / `vkrn` not required
- Latin run preservation
- Node split loses kerning
- Unsafe Unicode rejected
- Remaining Desktop acceptance items outstanding

## Issue #30 — Japanese Vertical — Standard: Architecture-gated scoped exception — Closed / Completed (2026-07-29)

- Gate 0 complete
- Gate 1 Closed
- Gate 2 complete
- Gate 3 Formally Closed
- Gate 4 Formally Closed — [figma-os#5](https://github.com/ga7ming3249/figma-os/issues/5), accepted `dc6361157345ebb8b17264f63aef8fa0e265c5eb`
- Gate 5 Architect Kickoff Published
- Gate 5 Primary Implementation Issue [figma-os#6](https://github.com/ga7ming3249/figma-os/issues/6) created and Architect-verified
- Gate 5 Desktop Acceptance authorized, then placed on Owner Priority Hold (2026-07-23) pending figma-os#2; that dependency was resolved (figma-os#2 Closed 2026-07-24), and Gate 5 subsequently resumed, completed, and was Accepted / Closed 2026-07-29 (see figma-os#6 above)
- Gate 4 lineage (`dc6361157345ebb8b17264f63aef8fa0e265c5eb`) is now merged to `figma-os/main` via the Gate 5 accepted implementation commit `9253ce8ce46dbd02225f9bfa73019f4662f575de` (PR [figma-os#8](https://github.com/ga7ming3249/figma-os/pull/8), 2026-07-29); verified `figma-os/main` is now `d3abd4f46ce89240a22a467bbbf712f4c5e10628`
- Japanese Vertical — Standard / Safe Local Fix MVP Gate 0–Gate 5 are complete; `asd#30` is Closed / Completed as of this Canonical State Synchronization

## Vision Owner priority decision — figma-os#2 prioritized (2026-07-23)

- [figma-os#2](https://github.com/ga7ming3249/figma-os/issues/2) became Priority 1; Phase A read-only Architect Kickoff (Current Scale Contract and Integration Review) published. Baseline was canonical `main@c9def9785e86272c8d21d61f14a500cd8b45793c`, not the unmerged Gate 4 head `dc6361157345ebb8b17264f63aef8fa0e265c5eb`. This decision governed figma-os#2's implementation through to its completion (2026-07-24, see below).
- [figma-os#6](https://github.com/ga7ming3249/figma-os/issues/6) (Gate 5 Desktop Acceptance) was placed on Owner Priority Hold at the time of this decision — not a defect or cancellation. The dependency (figma-os#2) was subsequently resolved, and Gate 5 was later resumed, completed, and Accepted / Closed 2026-07-29 (see figma-os#6 above).
- [figma-os#3](https://github.com/ga7ming3249/figma-os/issues/3) remains Open / not started, downstream of figma-os#2 completion.
- `figma-os#2`'s `main` lineage and Gate 4/5 (`dc636115...`) overlapped in Type Adjuster at the time of this decision; they were subsequently combined via the Gate 5 accepted implementation commit `9253ce8ce46dbd02225f9bfa73019f4662f575de` (PR [figma-os#8](https://github.com/ga7ming3249/figma-os/pull/8), 2026-07-29).

## figma-os#2 — Phase A Accept, Nightly Integration, and Completion (2026-07-23 – 2026-07-24)

- Phase A (Current Scale Contract and Integration Review) received a corrected report and Architect Accept (2026-07-23).
- Scoped implementation was carried out in isolated worktree `/Users/atsushitogami/Developer/figma-os-issue-2-scale-sync` on branch `feature/issue-2-scale-state-sync` (baseline `main@c9def9785e86272c8d21d61f14a500cd8b45793c`).
- Findings A, B, and C (Nightly Integration review, 2026-07-23) were subsequently corrected.
- PR [figma-os#7](https://github.com/ga7ming3249/figma-os/pull/7) merged to `figma-os/main` at `2838450c91429e9bc9c312103e0741c64e0068d2` (implementation commit `874d94dbfa4336ab064822e1ccc07ece12795149`) on 2026-07-24, closing figma-os#2.
- Verified: Build Success, Typecheck Success, Automated Tests 138/138 passed, Desktop Verification All Pass.

## figma-os#2 / figma-os#3 — registered (2026-07-22)

- [figma-os#2](https://github.com/ga7ming3249/figma-os/issues/2) — Type Adjuster Scale UI: synchronize with current selection, improve fine adjustment controls. Independent Product Improvement, no Gate dependency.
- [figma-os#3](https://github.com/ga7ming3249/figma-os/issues/3) — Product Architecture Decision: canonical ownership of Utility (Scale/Baseline/Tracking) between Type Polish and Type Adjuster. Depends on figma-os#2 completion before any Utility removal.

---

# Open Issues Affecting figma-os (asd + figma-os)

| Issue | Plugin | Priority | Summary |
|---|---|---|---|
| [figma-os#4](https://github.com/ga7ming3249/figma-os/issues/4) | Type Inventory | P3 | Preserve multiline text (backlog; after higher-priority work). Transferred from asd#3 (2026-07-22, Repository Issue Ownership Reorganization) |
| [asd#28](https://github.com/ga7ming3249/asd/issues/28) | Type Adjuster / Type Polish | - | Japanese Vertical Typography & Latin Kerning — Knowledge Review deliverables completed |
| [asd#29](https://github.com/ga7ming3249/asd/issues/29) | Type Adjuster / Type Polish | - | OpenType Typography Features — Capability Review findings completed |
| [figma-os#12](https://github.com/ga7ming3249/figma-os/issues/12) | Type Adjuster | - | Plain-node Manual Adjustment Strategy — Next Architecture Dependency following figma-os#3 closure |
| [figma-os#13](https://github.com/ga7ming3249/figma-os/issues/13) | Type Adjuster | - | Manual Adjustment Migration — contingent on figma-os#12 |
| [figma-os#14](https://github.com/ga7ming3249/figma-os/issues/14) | Type Polish / Type Adjuster | - | Utility Ownership Documentation Migration — coordinate with figma-os#10 |
| [figma-os#15](https://github.com/ga7ming3249/figma-os/issues/15) | Type Polish | - | Utility Deprecation / Removal — Blocked on figma-os#12/#13/#14 and regression verification |

Closed since last update: asd#9 (Guide Stamp — Canvas Guides), asd#11 (Type Adjuster — Virtual Body punctuation adjustment), asd#3 (Type Inventory multiline — transferred to figma-os#4, 2026-07-22), figma-os#5 (Issue #30 Gate 4 — Safe Local Fix MVP, accepted `dc636115`, not merged to main), figma-os#2 (Type Adjuster Scale UI synchronization, merged via PR #7 to `main@2838450c9...`, 2026-07-24), figma-os#6 (Issue #30 Gate 5 — Desktop Acceptance, Accepted / Completed, merged via PR #8 to `main@d3abd4f4...`, 2026-07-29), asd#30 (Japanese Vertical — Standard / Safe Local Fix MVP, Gate 0–Gate 5 complete, Closed / Completed, 2026-07-29), asd#31 (Japanese Horizontal Typography Analysis Track, closed `2026-08-05T10:08:05Z`; KB-0004/KB-0005 Remote Registration Pending — see Recent Changes and Decisions Pending, not a completed-and-verified close; commit `5464a78` Architecture Classification resolved via asd#34 — Experimental, Accepted Commit: No; Canonical Gate Acceptance remains Gate 0 only), figma-os#3 (Product Decision — Consolidate Type Polish Utility Ownership into Type Adjuster, Accepted / Completed / Closed `2026-08-18T05:03:24Z`; superseded by follow-up chain figma-os#12–#15, see Recent Changes and "Type Polish Utility Ownership — Migration Chain"), figma-os#10 (Type Polish / Type Adjuster User Guide, Accepted / Completed / Closed 2026-08-18, accepted `main` HEAD `d3ebb1c33ea3d4c4824504309ffe349693556a92`; see Recent Changes).

(ASD-framework issue asd#8 does not touch figma-os code. Note: distinct from figma-os#4 above, which is a different repository's Issue #4. Reference Assistant Issues are no longer tracked in `asd` — see Out of scope note above.)

---

# Documentation Sync

No known gaps in ASD/figma-os internal documentation sync — the reference inconsistencies found during the Repository Issue Ownership Reorganization (bare `asd#30`/`asd#3` references, a misquoted Issue title, three "new ASD Issue" pointers, and Component Package's Canonical Documentation description) were corrected in Phase 3 and verified against `figma-os` main. The previously-noted user-facing documentation gap (no Canonical User Guide for Type Polish / Type Adjuster) is **resolved**: [figma-os#10](https://github.com/ga7ming3249/figma-os/issues/10) is Accepted / Completed / Closed (2026-08-18, commit `d3ebb1c33ea3d4c4824504309ffe349693556a92`) and delivered the Canonical User Guide under `docs/user-guides/` in `figma-os`, incorporating the figma-os#3 canonical ownership decision. Remaining coordination: [figma-os#14](https://github.com/ga7ming3249/figma-os/issues/14) (Utility Ownership Documentation Migration, still Open) should treat the accepted User Guide as sync input for its own README/ROADMAP-language migration, not re-litigate it.

(Last sync: 2026-08-18 (third sync), Vision Owner Priority Synchronization — `asd`-side documentation only (`asd-state.md`, `figma-os-state.md`, `ROADMAP.md`); no `figma-os` product repository commit was made. This State update records: Vision Owner Priority Decision — Type Polish completion is the top-level Figma OS Product Goal; priority plugin order 1) Type Polish, 2) Type Adjuster, 3) Type Inventory, 4) Color Inventory; Type Polish's Canonical Product Identity extends beyond Japanese Vertical to Japanese Horizontal / Mixed Japanese–Latin / Latin typography; figma-os#12 remains the unchanged immediate Next Architecture Dependency, reframed as part of completing the Type Polish / Type Adjuster product architecture; new Decisions Pending item "Type Polish Capability Roadmap Reconciliation" registered covering asd#28/asd#31/Horizontal/Mixed/Latin. Does not reopen asd#31, close asd#28, authorize implementation, change runtime code, skip figma-os#12, or auto-authorize Horizontal/Latin implementation. Prior sync: 2026-08-18 (second sync), ASD Canonical State Synchronization — `asd`-side documentation only (`asd-state.md`, `figma-os-state.md`, `ROADMAP.md`); no `figma-os` product repository commit was made by this sync (figma-os#10's own commits `423e605`/`d3ebb1c` were made and pushed as part of that Issue's own Publisher workflow, prior to this synchronization). This State update records: [figma-os#10](https://github.com/ga7ming3249/figma-os/issues/10) (Type Polish / Type Adjuster User Guide) is Accepted / Completed / Closed 2026-08-18; Canonical User Guide delivered under `docs/user-guides/` in `figma-os`; accepted `figma-os/main` HEAD is now `d3ebb1c33ea3d4c4824504309ffe349693556a92`; Recommended First Action moves to figma-os#12 (Next Architecture Dependency); a separate Presentation/Distribution HTML Issue was registered in `figma-os` but its registration is explicitly not a target of this synchronization per State Update Decision. Prior sync: 2026-08-18 (first sync), ASD Canonical State Synchronization — `asd`-side documentation only (`asd-state.md`, `figma-os-state.md`, `ROADMAP.md`); no `figma-os` product repository commit was made and no source code changed. This State update records: [figma-os#3](https://github.com/ga7ming3249/figma-os/issues/3) (Product Decision — Consolidate Type Polish Utility Ownership into Type Adjuster) is Accepted / Completed / Closed (`2026-08-18T05:03:24Z`); canonical manual-adjustment owner is Type Adjuster; Type Polish Utility is Legacy Compatibility Capability Pending Migration/Removal, immediate removal prohibited; Utility Ownership removed from Decisions Pending; follow-up chain figma-os#12 (Next Architecture Dependency) → #13 (contingent) → #14 → #15 (Blocked) registered; Type Polish Freeze exception scoped solely to #12–#15; `figma-os/main` verified HEAD unchanged at `031887cbf1b65336682212f13df3d609ce46267a`. This synchronization is not an Implementation Authorization. Prior sync: 2026-08-07, ASD Canonical Documentation Synchronization — `figma-os`-side documentation only, no product code changed by this sync. This State update records: [asd#34](https://github.com/ga7ming3249/asd/issues/34) (Review and Classify Repository Evidence Commit 5464a78) is Closed / Completed; commit `5464a78` Architecture Classification is resolved: **Experimental**, **Accepted Commit: No**, Canonical Gate Acceptance **Gate 0 only** (Gate 1 / Gate 2 / Gate 3 Acceptance: Not established); `figma-os/main` verified HEAD is now `031887cbf1b65336682212f13df3d609ce46267a`. KB-0004/KB-0005 Remote Registration Pending remains unresolved. Prior sync: 2026-08-05, ASD Nightly Canonical Synchronization — `figma-os`-side documentation only, no product code changed by this sync. This State update records: `figma-os/main` verified HEAD is now `5464a78bf3500475a8855f10cfb8aaa75b9caa39` (Repository fact); KB-0001–KB-0003 registered, KB-0004/KB-0005 Remote Registration Pending (no artifact found for either); commit `5464a78` (2026-08-01, no PR, read-only Horizontal Analysis per its own commit message) is Repository Evidence Identified — Architecture Classification Pending, escalated to Global Architect, not inferred to satisfy any Gate; asd#31 is Closed with exactly one close event and no reopen event in GitHub history. Prior sync: 2026-07-29, ASD Nightly Canonical State Synchronization (second same-day sync), ASD-side documentation only — no `figma-os` product repository commit was made. This State update records that [figma-os#10](https://github.com/ga7ming3249/figma-os/issues/10) (Type Polish / Type Adjuster User Guide) and [asd#31](https://github.com/ga7ming3249/asd/issues/31) (Japanese Horizontal Typography Analysis Track) are Open and Architect-Accepted, with Architect-Accepted execution order 1) figma-os#10, 2) figma-os#3, 3) asd#31. Prior sync (same day, first sync): This State update recorded that `figma-os#6` (Gate 5 — Desktop Acceptance) is Accepted / Completed / Closed (2026-07-29T11:45:25Z): PR figma-os#8 merged to `main` at `d3abd4f46ce89240a22a467bbbf712f4c5e10628` (accepted implementation commit `9253ce8ce46dbd02225f9bfa73019f4662f575de`), verified Type Adjuster full suite 278/278, Scale UI tests 109/109, Gate 4 Local Fix tests 163/163, G5-DEF-002 generated marker tests 6/6, Type Polish full suite 165/165, both builds PASS, Rebased-head Desktop Acceptance 7/7 PASS. Japanese Vertical — Standard / Safe Local Fix MVP Gate 0–Gate 5 are complete; `asd#30` is Closed / Completed. Prior sync: 2026-07-25, ASD Nightly Canonical State Synchronization, ASD-side documentation only — no `figma-os` product repository commit was made. That State update recorded that `figma-os#2` is Completed / Accepted / Closed (2026-07-24): Findings A/B/C were corrected, PR figma-os#7 merged to `main` at `2838450c91429e9bc9c312103e0741c64e0068d2`, verified Build/Typecheck Success, Automated Tests 138/138 passed, Desktop Verification All Pass. Verified `figma-os/main` is now `2838450c91429e9bc9c312103e0741c64e0068d2`, distinct from the accepted Gate 4 feature head `dc6361157345ebb8b17264f63aef8fa0e265c5eb`; `main` is not claimed to contain Gate 4. Prior sync: 2026-07-23, ASD Nightly Canonical State Synchronization — `figma-os#2`'s Phase A Accept remained valid while its scoped implementation, carried out uncommitted in an isolated worktree, received Architect judgment Changes Required pending Findings A/B/C and Desktop Verification. Prior sync: 2026-07-23 (earlier same day), Architect verification of Gate 5 Primary Implementation Issue `figma-os#6` and the resulting Gate 5 Desktop Acceptance authorization. Prior sync: 2026-07-23 (same day), figma-os#5 Gate 4 Formally Closed synchronization. Prior sync: 2026-07-22, figma-os commit `c9def97` — `guide-stamp`, `instance-checker`, `type-inventory`, `component-package` HISTORY.md/ROADMAP.md corrected per the asd#17–#24 Architecture Review. Earlier sync: 2026-07-17, commit `ab69c8b` — README/PLUGINS/ROADMAP/CLAUDE aligned with repository state; DSS v1.x spike committed as a frozen artifact, resolving the previously broken ROADMAP links. New inconsistencies discovered later are recorded here as new items, not as historical notes.)

---

# Update Procedure

Update whenever one of the following changes:

- Product architecture
- Plugin phase/status
- Recommended implementation order
- Major Issue completion
- Major merge
- Documentation synchronization status
- Outstanding architectural decisions

Process:

- At session end, whether this document needs updating is declared the same way as ASD State:
  - Figma OS State Update: Required
  - Figma OS State Update: Not Required
- Only when "Required" is declared (and authorized) does Claude Code update this file, commit, and push.
- No historical records are kept inside this document. History remains in Git.

---

# Notes

This document is the product-side counterpart to `docs/asd-state.md`:

- `asd-state.md` — how ASD operates (roles, governance, commands)
- `figma-os-state.md` — what is true about the figma-os product right now

Together they allow a new ChatGPT session to direct work across both without repository access.
