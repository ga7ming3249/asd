# Figma OS State

- Version: 20
- Date: 2026-07-25
- Status: Active
- Maintainer: Claude Code (Primary Engineer)
- Verified against: `ga7ming3249/figma-os` main branch (`2838450c91429e9bc9c312103e0741c64e0068d2`), accepted Gate 4 feature head (`dc6361157345ebb8b17264f63aef8fa0e265c5eb`), and ASD Issues, as of 2026-07-25

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
| Current Development Focus | [asd#30](https://github.com/ga7ming3249/asd/issues/30) Gate 5 — Desktop Acceptance ([figma-os#6](https://github.com/ga7ming3249/figma-os/issues/6)); figma-os#2 dependency resolved (Closed 2026-07-24), but Gate 5 remains on Owner Priority Hold pending an explicit Vision Owner decision to resume |
| Recommended First Action | Await explicit Vision Owner decision to resume Gate 5 Desktop Acceptance; once resumed, Gate 5 must inherit `dc636115...` directly (`main` does not contain Gate 4) |
| Gate 5 | [figma-os#6](https://github.com/ga7ming3249/figma-os/issues/6) — Open / Authorized / Owner Priority Hold / not started |
| State Confidence | figma-os#2 Completed / Accepted / Closed 2026-07-24, merged to `main@2838450c9...` via [figma-os#7](https://github.com/ga7ming3249/figma-os/pull/7); Gate 4 head `dc636115...` remains separate and unmerged |

---

# Recommended Next Priorities

Current recommended implementation order. This is a recommendation, not a commitment — it may change whenever Product State is updated.

**Completed — figma-os#2: Type Adjuster Scale UI synchronization**

figma-os#2 is Completed / Accepted / Closed (2026-07-24). Findings A/B/C were corrected; PR [figma-os#7](https://github.com/ga7ming3249/figma-os/pull/7) merged to `main` at `2838450c91429e9bc9c312103e0741c64e0068d2` (implementation commit `874d94dbfa4336ab064822e1ccc07ece12795149`). Verified: Build Success, Typecheck Success, Automated Tests 138/138 passed, Desktop Verification All Pass. Scale State Sync is now an accepted capability of Type Adjuster. Cleanup of the isolated worktree/feature branch (`feature/issue-2-scale-state-sync`) used during implementation is optional maintenance only.

**P1 — figma-os#6: Gate 5 Desktop Acceptance**

Reason: Architect-verified and authorized. figma-os#2's completion resolves the dependency the Owner Priority Hold (2026-07-23) was conditioned on, but per existing policy Gate 5 "resumes only after an explicit Owner priority decision" — no such decision is included in this synchronization. Not a defect, architecture blocker, rejection, or cancellation.

Prerequisite: Resumes only after an explicit Owner priority decision

**P3 — figma-os#3: Type Polish Utility ownership decision**

Reason: Product Architecture Decision remains downstream of figma-os#2 completion.

Prerequisite: figma-os#2 completion

**P4 — Component Package: production trial & polish**

Reason: Recently merged (PR #1, 2026-07-16). Mature it through daily production use and collect small improvements as new Issues before starting the next Foundation work.

Prerequisite: None (the trial itself is the work)

**P5 — Color Inventory: Generate Inventory Page**

Reason: v1 core (Generate / Raw Colors Workbench / Promote) is in production trial; Inventory Page generation is the next increment toward Production promotion.

Prerequisite: None

**P6 — Type Inventory: multiline support ([figma-os#4](https://github.com/ga7ming3249/figma-os/issues/4))**

Reason: Backlog item per ASD priority assessment. Clear workaround exists; lower user impact.

Prerequisite: None (Guide Stamp Canvas Guides, ASD #9, completed 2026-07-17)

**P7 — Composer / Design Style Sheet v2**

Reason: Foundation plugins (Color Inventory, Component Package) need to mature through production use first; see Decisions Pending.

Prerequisite: Component Package and Color Inventory production trials substantially complete

---

# Decisions Pending

Unresolved architectural or product decisions requiring Vision Owner and/or Architect input. Implementation tasks are not listed here.

**Design Style Sheet v2**

Waiting for architecture decision. DSS v1.x is frozen as a spike; v2 is to be redesigned as a Composer after Foundation matures. Includes the recorded ROADMAP homework: redefine the page-generation role split between DSS Colors section and Color Inventory.

**Type Polish Utility ownership** ([figma-os#3](https://github.com/ga7ming3249/figma-os/issues/3))

Waiting for Product Architecture Decision on whether Scale/Baseline/Tracking Utility controls remain in Type Polish or become exclusively owned by Type Adjuster. Depends on completion of [figma-os#2](https://github.com/ga7ming3249/figma-os/issues/2) (Type Adjuster Scale UI synchronization) before any Utility removal is considered. No implementation until this decision is approved.

**Gate 5 resume decision**

Gate 5 (Desktop Acceptance, [figma-os#6](https://github.com/ga7ming3249/figma-os/issues/6)) remains on Owner Priority Hold. The dependency it was conditioned on (figma-os#2) is now resolved (Closed 2026-07-24), but resumption still requires an explicit Vision Owner priority decision, which is not yet given.

---

# Architect Snapshot

Executive summary for ASD Dashboard generation. Intentionally redundant with other sections to optimize Architect initialization (target: understood in under 30 seconds).

Recommended reading order for initialization: **Architect Snapshot → Product Health → Plugin State → Documentation Sync**, descending into other sections only when needed. This Snapshot may serve as the sole input for Dashboard generation.

```text
Architecture
Stable

Current Focus
asd#30 Gate 5 — Desktop Acceptance (figma-os#6); figma-os#2 dependency resolved (Closed 2026-07-24)

Highest Priority
Await explicit Vision Owner decision to resume Gate 5

Next Milestone
Gate 5 Desktop Acceptance (on Owner Priority Hold)

Blockers
Gate 5 resumption awaits an explicit Vision Owner decision; no blocker impedes the overall product architecture

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
| Type Adjuster | `type-adjuster/` | v0.5 | Feature Enhancement | Beta | Gate 4 accepted on unmerged feature branch `dc636115`: explicit pending-request revalidation and Apply, `LF-UPRIGHT-001`, `LF-ROTATE-RUN-001`, validated group-member Nudge, conflict-safe structural Reset. Remains non-judgmental. Scale State Sync ([figma-os#2](https://github.com/ga7ming3249/figma-os/issues/2), Closed) merged to `main` at `2838450c9...` (PR #7, 2026-07-24) as an accepted capability, independent of the unmerged Gate 4/5 lineage |
| Type Polish | `type-polish/` | v0.6 | Research | Experimental | Gate 4 accepted on unmerged feature branch `dc636115`: current-selection-only applied-marker reader, already-applied short-circuit, fail-closed blocked state, and zero document mutation. Owns Analysis, Recommendation, User Decision, and Handoff production. Utility ownership remains under [figma-os#3](https://github.com/ga7ming3249/figma-os/issues/3) |
| Design Style Sheet | `design-style-sheet/` | v0.1.1 | Concept | Experimental (frozen spike) | v1.x preserved in repo as a frozen historical artifact (2026-07-17). No feature development; preservation fixes only. v2 redesign via new ASD Issue |

Out of scope: **Reference Assistant** is not part of `figma-os`. As of 2026-07-23, repository `ga7ming3249/reference-assistant` exists as its independent Product Repository; its Product Issues are owned there. `asd#4` and `asd#6` were closed after Successor Issue transfer to that repository (2026-07-23); `asd#5` remains historical (closed, unchanged).

---

# Recent Changes

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

## Issue #30 — Japanese Vertical — Standard: Architecture-gated scoped exception

- Gate 0 complete
- Gate 1 Closed
- Gate 2 complete
- Gate 3 Formally Closed
- Gate 4 Formally Closed — [figma-os#5](https://github.com/ga7ming3249/figma-os/issues/5), accepted `dc6361157345ebb8b17264f63aef8fa0e265c5eb`
- Gate 5 Architect Kickoff Published
- Gate 5 Primary Implementation Issue [figma-os#6](https://github.com/ga7ming3249/figma-os/issues/6) created and Architect-verified
- Gate 5 Desktop Acceptance authorized, then placed on Owner Priority Hold (2026-07-23) pending figma-os#2; that dependency is now resolved (figma-os#2 Closed 2026-07-24), but Gate 5 still resumes only after an explicit Vision Owner priority decision; product code changes and main merge remain unauthorized until then
- Gate 4 remains unmerged; verified `figma-os/main` is now `2838450c91429e9bc9c312103e0741c64e0068d2` (figma-os#2 merged 2026-07-24) and still does not contain Gate 4

## Vision Owner priority decision — figma-os#2 prioritized (2026-07-23)

- [figma-os#2](https://github.com/ga7ming3249/figma-os/issues/2) became Priority 1; Phase A read-only Architect Kickoff (Current Scale Contract and Integration Review) published. Baseline was canonical `main@c9def9785e86272c8d21d61f14a500cd8b45793c`, not the unmerged Gate 4 head `dc6361157345ebb8b17264f63aef8fa0e265c5eb`. This decision governed figma-os#2's implementation through to its completion (2026-07-24, see below).
- [figma-os#6](https://github.com/ga7ming3249/figma-os/issues/6) (Gate 5 Desktop Acceptance) placed on Owner Priority Hold — remains Open and authorized, not a defect or cancellation. The dependency (figma-os#2) is now resolved; resumption still requires an explicit Owner priority decision.
- [figma-os#3](https://github.com/ga7ming3249/figma-os/issues/3) remains Open / not started, downstream of figma-os#2 completion.
- `figma-os#2`'s `main` lineage and Gate 4/5 (`dc636115...`) still overlap in Type Adjuster and require an explicit future integration/reconciliation scope before combination; no rebase, cherry-pick, or merge between the lineages is authorized.

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
| [asd#30](https://github.com/ga7ming3249/asd/issues/30) | Type Polish / Type Adjuster | - | Japanese Vertical — Standard — Parent Coordination Issue for Gate 5 Desktop Acceptance. figma-os#2 dependency resolved; Gate 5 on Owner Priority Hold pending an explicit Vision Owner decision |
| [figma-os#6](https://github.com/ga7ming3249/figma-os/issues/6) | Type Adjuster / Type Polish | - | Gate 5 — Desktop Acceptance. Architect-verified and authorized; inherited baseline `dc636115...` (unmerged feature branch). Desktop Acceptance not started; figma-os#2 dependency resolved (Closed 2026-07-24), Owner Priority Hold remains pending an explicit Vision Owner decision. Product code changes, PR, and main merge remain unauthorized |
| [figma-os#3](https://github.com/ga7ming3249/figma-os/issues/3) | Type Polish / Type Adjuster | Medium | Product Architecture Decision — canonical Utility (Scale/Baseline/Tracking) ownership. Depends on figma-os#2 |

Closed since last update: asd#9 (Guide Stamp — Canvas Guides), asd#11 (Type Adjuster — Virtual Body punctuation adjustment), asd#3 (Type Inventory multiline — transferred to figma-os#4, 2026-07-22), figma-os#5 (Issue #30 Gate 4 — Safe Local Fix MVP, accepted `dc636115`, not merged to main), figma-os#2 (Type Adjuster Scale UI synchronization, merged via PR #7 to `main@2838450c9...`, 2026-07-24).

(ASD-framework issue asd#8 does not touch figma-os code. Note: distinct from figma-os#4 above, which is a different repository's Issue #4. Reference Assistant Issues are no longer tracked in `asd` — see Out of scope note above.)

---

# Documentation Sync

No known gaps — the reference inconsistencies found during the Repository Issue Ownership Reorganization (bare `asd#30`/`asd#3` references, a misquoted Issue title, three "new ASD Issue" pointers, and Component Package's Canonical Documentation description) were corrected in Phase 3 and verified against `figma-os` main.

(Last sync: 2026-07-25, ASD Nightly Canonical State Synchronization, ASD-side documentation only — no `figma-os` product repository commit was made. This State update records that `figma-os#2` is Completed / Accepted / Closed (2026-07-24): Findings A/B/C were corrected, PR figma-os#7 merged to `main` at `2838450c91429e9bc9c312103e0741c64e0068d2`, verified Build/Typecheck Success, Automated Tests 138/138 passed, Desktop Verification All Pass. Verified `figma-os/main` is now `2838450c91429e9bc9c312103e0741c64e0068d2`, distinct from the accepted Gate 4 feature head `dc6361157345ebb8b17264f63aef8fa0e265c5eb`; `main` is not claimed to contain Gate 4. Prior sync: 2026-07-23, ASD Nightly Canonical State Synchronization — `figma-os#2`'s Phase A Accept remained valid while its scoped implementation, carried out uncommitted in an isolated worktree, received Architect judgment Changes Required pending Findings A/B/C and Desktop Verification. Prior sync: 2026-07-23 (earlier same day), Architect verification of Gate 5 Primary Implementation Issue `figma-os#6` and the resulting Gate 5 Desktop Acceptance authorization. Prior sync: 2026-07-23 (same day), figma-os#5 Gate 4 Formally Closed synchronization. Prior sync: 2026-07-22, figma-os commit `c9def97` — `guide-stamp`, `instance-checker`, `type-inventory`, `component-package` HISTORY.md/ROADMAP.md corrected per the asd#17–#24 Architecture Review. Earlier sync: 2026-07-17, commit `ab69c8b` — README/PLUGINS/ROADMAP/CLAUDE aligned with repository state; DSS v1.x spike committed as a frozen artifact, resolving the previously broken ROADMAP links. New inconsistencies discovered later are recorded here as new items, not as historical notes.)

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
