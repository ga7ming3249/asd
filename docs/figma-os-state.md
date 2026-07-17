# Figma OS State

- Version: 3
- Date: 2026-07-17
- Status: Active
- Maintainer: Claude Code (Primary Engineer)
- Verified against: `ga7ming3249/figma-os` main branch and ASD Issues, as of 2026-07-17

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

Connector Read Validation: **Partially Verified (2026-07-17)** — ASD repository readable (metadata, commits, Issues, PR search confirmed); figma-os repository access pending. Validation is not fully complete until the Connector installation grants access to `figma-os` (commit `ab69c8b`, documentation sync, `design-style-sheet/`, and PR #1 remain independently unverified).

---

# Product Health

High-level product condition, readable in a few seconds. Qualitative by design — no commit counts, branch counts, or LOC.

| Field | State |
|---|---|
| Architecture | 🟢 Stable |
| Production Plugins | 6 |
| Beta Plugins | 3 (Type Adjuster; Color Inventory and Component Package in production trial) |
| Experimental Plugins | 2 (Type Polish; Design Style Sheet v1.x frozen spike) |
| Documentation | 🟢 Synced (Documentation Sync completed 2026-07-17) |
| Known Critical Bugs | 0 |
| High Priority Issues | 1 (ASD #9, Guide Stamp) |
| Current Development Focus | Guide Stamp (Canvas Guides) |
| State Confidence | Verified (2026-07-17) — items not verifiable are marked Unknown |

---

# Recommended Next Priorities

Current recommended implementation order. This is a recommendation, not a commitment — it may change whenever Product State is updated.

**P1 — Guide Stamp: Canvas Guides (ASD #9)**

Reason: Component Package v1 Core is complete and frozen. Additive implementation with low architectural risk, already Approved for Implementation, highest immediate user value.

Prerequisite: None

**P2 — Component Package: production trial & polish**

Reason: Recently merged (PR #1, 2026-07-16). Mature it through daily production use and collect small improvements as new Issues before starting the next Foundation work.

Prerequisite: None (the trial itself is the work)

**P3 — Type Inventory: multiline support (ASD #3)**

Reason: Backlog item per ASD priority assessment. Clear workaround exists; lower user impact.

Prerequisite: Guide Stamp Canvas Guides (ASD #9) completed

---

# Decisions Pending

Unresolved architectural or product decisions requiring Vision Owner and/or Architect input. Implementation tasks are not listed here.

**Design Style Sheet v2**

Waiting for architecture decision. DSS v1.x is frozen as a spike; v2 is to be redesigned as a Composer after Foundation matures. Includes the recorded ROADMAP homework: redefine the page-generation role split between DSS Colors section and Color Inventory.

---

# Architect Snapshot

Executive summary for ASD Dashboard generation. Intentionally redundant with other sections to optimize Architect initialization (target: understood in under 30 seconds).

Recommended reading order for initialization: **Architect Snapshot → Product Health → Plugin State → Documentation Sync**, descending into other sections only when needed. This Snapshot may serve as the sole input for Dashboard generation.

```text
Architecture
Stable

Current Focus
Guide Stamp

Highest Priority
Canvas Guides (ASD #9)

Next Milestone
Guide Stamp Canvas Guides complete

Blockers
None

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

This table reflects the actual repository state, which is ahead of `PLUGINS.md` in places (see Documentation Sync).

| Plugin | Dir | Version | Phase | Status | Notes |
|---|---|---|---|---|---|
| Guide Stamp | `guide-stamp/` | v2.x | Maintenance | Production | Open ASD Issue #9 (Canvas Guides, P1) |
| Instance Checker | `instance-checker/` | v1.x | Maintenance | Production | |
| Margin Preflight | `margin-preflight/` | v1.x | Feature Enhancement | Production | Known issue: some Auto Layout frames undetected (collecting cases) |
| Pocket Preview | `pocket-preview/` | v1.0 | Maintenance | Production | Figma / device / Claude Code (MCP) utility panel |
| Type Inventory | `type-inventory/` | v1.4 | Feature Enhancement | Production | Open ASD Issue #3 (multiline support, P3, backlog) |
| Status Stamp | `status-stamp/` | v0.3 | Design Sprint | Production | ASD Issue #1 (stamp-selection update) closed |
| Color Inventory | `color-inventory/` | v1.0 | Design Sprint | Beta | Spec v0.3. v1 core (Generate / Raw Colors Workbench / Promote) in production trial. Promotion criteria in ROADMAP.md |
| Component Package | `component-package/` | v1.0 | Design Sprint | Beta | v1 Core merged (PR #1, 2026-07-16). Spec of record: ASD Issue #2 + supplemental comments. Promotion criteria in ROADMAP.md |
| Type Adjuster | `type-adjuster/` | v0.4 | Utility Polish | Beta | Promotion criteria defined in ROADMAP.md |
| Type Polish | `type-polish/` | v0.6 | Research | Experimental | Knowledge-design phase; feature development paused |
| Design Style Sheet | `design-style-sheet/` | v0.1.1 | Concept | Experimental (frozen spike) | v1.x preserved in repo as a frozen historical artifact (2026-07-17). No feature development; preservation fixes only. v2 redesign via new ASD Issue |

Out of scope: **Reference Assistant** lives in its own repository (not part of `figma-os`). Its operational state is tracked through ASD Issues #4–#6.

---

# Recent Changes

## Component Package v1 Core — completed (ASD Issue #2, closed 2026-07-17)

Implemented in figma-os PR #1 (merged 2026-07-16, +2,804 lines, 11 commits). Verified on Figma by the Vision Owner before merge.

Final architecture, established through 10 supplemental specifications on Issue #2:

- Source Organizer — physically consolidates Component Masters onto a Package page (not a viewer)
- Safe Component Relocation — Component Sets moved whole; standalone masters replaced in place by an Instance
- Page-Scoped — collects only from `figma.currentPage`; one Source Page = one Package (identified by Source Page ID in pluginData)
- Non-Destructive Update — differential updates only; **Regenerable Output does not apply to this plugin** (unlike report-based Foundation plugins)
- Preserve Component Master Geometry — masters isolated in fixed-size Preview Containers, never direct children of Auto Layout
- Figma OS Report Layout — shared header/section/parent-frame structure with Type Inventory / Color Inventory
- Report Appearance — user-configurable background color persisted in pluginData

Core principles now treated as baseline: Never Delete / Never Modify / Never Resize / Never Break Instance Links.

Issue #2 is frozen as the v1 Core baseline. All future enhancements go through new Issues.

---

# Open ASD Issues affecting figma-os

| Issue | Plugin | Priority | Summary |
|---|---|---|---|
| #9 | Guide Stamp | P1 | Add native Figma Canvas Guides (center + mirrored margins) on selected parent frame |
| #3 | Type Inventory | P3 | Preserve multiline text (backlog; after higher-priority work) |

(ASD-framework and Reference Assistant issues — #4, #6, #8 — do not touch figma-os code.)

---

# Documentation Sync

No known gaps.

(Last sync: 2026-07-17, figma-os commit `ab69c8b` — README/PLUGINS/ROADMAP/CLAUDE aligned with repository state; DSS v1.x spike committed as a frozen artifact, resolving the previously broken ROADMAP links. New inconsistencies discovered later are recorded here as new items, not as historical notes.)

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
