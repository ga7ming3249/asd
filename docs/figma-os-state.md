# Figma OS State

- Version: 12
- Date: 2026-07-23
- Status: Active
- Maintainer: Claude Code (Primary Engineer)
- Verified against: `ga7ming3249/figma-os` main branch (`c9def9785e86272c8d21d61f14a500cd8b45793c`) and ASD Issues, as of 2026-07-22

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
| Documentation | 🟢 Synced (Documentation Sync completed 2026-07-17) |
| Known Critical Bugs | 0 |
| High Priority Issues | 0 |
| Current Development Focus | Issue #30 — Japanese Vertical — Standard — Gate 4: Safe Local Fix MVP (Gate 3 complete; Manual Handoff Transport adopted; execution not yet implemented) |
| Recommended First Action | Gate 4 Architect Kickoff (asd#30) |
| State Confidence | Verified (2026-07-22) — items not verifiable are marked Unknown |

---

# Recommended Next Priorities

Current recommended implementation order. This is a recommendation, not a commitment — it may change whenever Product State is updated.

**P1 — Component Package: production trial & polish**

Reason: Recently merged (PR #1, 2026-07-16). Mature it through daily production use and collect small improvements as new Issues before starting the next Foundation work.

Prerequisite: None (the trial itself is the work)

**P2 — Color Inventory: Generate Inventory Page**

Reason: v1 core (Generate / Raw Colors Workbench / Promote) is in production trial; Inventory Page generation is the next increment toward Production promotion.

Prerequisite: None

**P3 — Type Inventory: multiline support ([figma-os#4](https://github.com/ga7ming3249/figma-os/issues/4))**

Reason: Backlog item per ASD priority assessment. Clear workaround exists; lower user impact.

Prerequisite: None (Guide Stamp Canvas Guides, ASD #9, completed 2026-07-17)

**P4 — Composer / Design Style Sheet v2**

Reason: Foundation plugins (Color Inventory, Component Package) need to mature through production use first; see Decisions Pending.

Prerequisite: Component Package and Color Inventory production trials substantially complete

---

# Decisions Pending

Unresolved architectural or product decisions requiring Vision Owner and/or Architect input. Implementation tasks are not listed here.

**Design Style Sheet v2**

Waiting for architecture decision. DSS v1.x is frozen as a spike; v2 is to be redesigned as a Composer after Foundation matures. Includes the recorded ROADMAP homework: redefine the page-generation role split between DSS Colors section and Color Inventory.

**Type Polish Utility ownership** ([figma-os#3](https://github.com/ga7ming3249/figma-os/issues/3))

Waiting for Product Architecture Decision on whether Scale/Baseline/Tracking Utility controls remain in Type Polish or become exclusively owned by Type Adjuster. Depends on completion of [figma-os#2](https://github.com/ga7ming3249/figma-os/issues/2) (Type Adjuster Scale UI synchronization) before any Utility removal is considered. No implementation until this decision is approved.

---

# Architect Snapshot

Executive summary for ASD Dashboard generation. Intentionally redundant with other sections to optimize Architect initialization (target: understood in under 30 seconds).

Recommended reading order for initialization: **Architect Snapshot → Product Health → Plugin State → Documentation Sync**, descending into other sections only when needed. This Snapshot may serve as the sole input for Dashboard generation.

```text
Architecture
Stable

Current Focus
Issue #30 — Japanese Vertical — Standard — Gate 4: Safe Local Fix MVP

Highest Priority
Gate 4 Architect Kickoff (asd#30)

Next Milestone
Gate 4 — Safe Local Fix MVP

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
| Type Adjuster | `type-adjuster/` | v0.5 | Feature Enhancement | Beta | Manual final-adjustment tool — owns explicit Local Fix execution and final manual adjustment; not an automatic composition engine (asd#30 responsibility boundary). Open [figma-os#2](https://github.com/ga7ming3249/figma-os/issues/2) (Scale UI current-selection sync, Medium). Promotion criteria defined in ROADMAP.md |
| Type Polish | `type-polish/` | v0.6 | Research | Experimental | Issue #30 scoped exception — Gate 3 complete. Owns Analysis, Recommendation, User Decision, and Manual Handoff production. Utility (Scale/Baseline/Tracking) ownership under review — [figma-os#3](https://github.com/ga7ming3249/figma-os/issues/3) |
| Design Style Sheet | `design-style-sheet/` | v0.1.1 | Concept | Experimental (frozen spike) | v1.x preserved in repo as a frozen historical artifact (2026-07-17). No feature development; preservation fixes only. v2 redesign via new ASD Issue |

Out of scope: **Reference Assistant** is not part of `figma-os`. As of 2026-07-23, repository `ga7ming3249/reference-assistant` exists as its independent Product Repository; its Product Issues are owned there. `asd#4` and `asd#6` were closed after Successor Issue transfer to that repository (2026-07-23); `asd#5` remains historical (closed, unchanged).

---

# Recent Changes

## Issue #29 — OpenType Typography Features Capability Review: findings completed

- OpenType write unsupported
- `vert` / `vrt2` / `vkrn` not required
- Latin run preservation
- Node split loses kerning
- Unsafe Unicode rejected
- Remaining Desktop acceptance items outstanding

## Issue #30 — Japanese Vertical — Standard: Architecture-gated scoped exception

- Gate 0 complete
- Gate 1 Closed
- Gate 2 complete
- Gate 3 Formally Closed
- Gate 4 Architect Kickoff Required

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
| [asd#30](https://github.com/ga7ming3249/asd/issues/30) | Type Polish / Type Adjuster | - | Japanese Vertical — Standard — Architecture-gated scoped exception. Gate 3 Formally Closed / Gate 4 Architect Kickoff Required |
| [figma-os#2](https://github.com/ga7ming3249/figma-os/issues/2) | Type Adjuster | Medium | Synchronize Scale UI with current selection; improve fine adjustment controls. No Gate dependency |
| [figma-os#3](https://github.com/ga7ming3249/figma-os/issues/3) | Type Polish / Type Adjuster | Medium | Product Architecture Decision — canonical Utility (Scale/Baseline/Tracking) ownership. Depends on figma-os#2 |

Closed since last update: asd#9 (Guide Stamp — Canvas Guides), asd#11 (Type Adjuster — Virtual Body punctuation adjustment), asd#3 (Type Inventory multiline — transferred to figma-os#4, 2026-07-22).

(ASD-framework issue asd#8 does not touch figma-os code. Note: distinct from figma-os#4 above, which is a different repository's Issue #4. Reference Assistant Issues are no longer tracked in `asd` — see Out of scope note above.)

---

# Documentation Sync

No known gaps — the reference inconsistencies found during the Repository Issue Ownership Reorganization (bare `asd#30`/`asd#3` references, a misquoted Issue title, three "new ASD Issue" pointers, and Component Package's Canonical Documentation description) were corrected in Phase 3 and verified against `figma-os` main.

(Last sync: 2026-07-22, figma-os commit `c9def97` — `guide-stamp`, `instance-checker`, `type-inventory`, `component-package` HISTORY.md/ROADMAP.md corrected per the asd#17–#24 Architecture Review. Prior sync: 2026-07-17, commit `ab69c8b` — README/PLUGINS/ROADMAP/CLAUDE aligned with repository state; DSS v1.x spike committed as a frozen artifact, resolving the previously broken ROADMAP links. New inconsistencies discovered later are recorded here as new items, not as historical notes.)

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
