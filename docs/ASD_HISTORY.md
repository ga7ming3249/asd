# ASD History

- Version: 1
- Last Reviewed: 2026-07-17
- Status: Active

---

# Purpose

This document records the significant milestones of ASD as a whole — not detailed specification changes (those belong to `docs/asd-state.md` for current state and each plugin's own `HISTORY.md` for plugin-specific design history).

Per Documentation Architecture v1.0 ([#12](https://github.com/ga7ming3249/asd/issues/12)): Past is separated from Present (`asd-state.md`) and Future (`ROADMAP.md`). This file is built from verifiable Git history in `ga7ming3249/asd` and `ga7ming3249/figma-os`. Where a milestone is known only from prior chat context Claude Code cannot access (pre-GitHub ChatGPT conversations), it is marked Unknown rather than invented — Unknown is not a defect, per the Project Dashboard convention in `asd-state.md`.

---

# Timeline

## 2026-06 — Figma OS, pre-ASD

`figma-os` begins as an individual plugin portfolio (first commit `9f1a513`, 2026-06-22), before any ASD governance process exists. Early plugins (Guide Stamp, Instance Checker, Margin Preflight, Pocket Preview, Type Inventory, Type Adjuster, Type Polish, Status Stamp) are built and iterated directly, without Issue-based tracking.

**Unknown**: whether "ASD" existed as a concept in ChatGPT conversations during this period. Not verifiable from Git history alone — pending Architect input if relevant.

## 2026-07 (early) — Continued individual development

Plugin work continues without formal governance: Type Adjuster gains Baseline/Split features, Status Stamp is redesigned, Type Inventory's generation pipeline is hardened, Pocket Preview evolves toward a utility-panel role. `PLUGINS.md` gains a Phase lifecycle definition (2026-07-01).

## 2026-07-12 — Foundation/Composer architecture confirmed; ASD repository created

Same day, two significant events:

- `figma-os`: the Foundation/Composer architecture is confirmed (Foundation Plugins = Workbench, observe + explicit edit commands; Composer = Mirror, pure observation). Design Style Sheet v1.x is frozen as a spike after on-device verification. Color Inventory's Generate + Raw Colors Workbench + Promote Workbench are implemented (commits `483a590`, `756a973`).
- `asd` repository is initialized (`b2c76a4`, "Phase 1A") — the start of ASD's formal GitHub presence.

## 2026-07-13 — ASD governance formalized

- AI Collaboration Contract Draft v0.9 registered (Specification 001).
- ADR-001 (Publisher Role Assignment) accepted: Claude Code becomes Publisher for GitHub Issue registration, replacing an earlier Codex/GitHub Connector approach found unreliable.
- `docs/asd-state.md` created (v1) — the single-version, in-place-updated session-initialization document.
- Status Stamp gains selection-based update support (`85e72fd`) — later formalized as ASD Issue #1.

## 2026-07-16 — Component Package v1 Core merged

figma-os PR #1 merges (`8bed3e0`, 11 commits, +2,804 lines), implementing Component Package as a Source Organizer (not a Viewer) — a major architectural pivot from the original Instance-based preview design.

## 2026-07-17 — High-activity day: Issue-based operation matures, Documentation Architecture adopted

- ASD Issues #1 (Status Stamp), #2 (Component Package v1 Core), #9 (Guide Stamp Canvas Guides), #10 (Local/GitHub/ASD synchronization audit), #11 (Type Adjuster Virtual Body punctuation adjustment), and #12 (Documentation Architecture v1.0) all close.
- Canvas Guides ships for Guide Stamp (`53c515f`, `46e0972`) — Architecture Review catches and corrects an unspecified coordinate-rounding step before approval.
- Virtual Body punctuation adjustment ships for Type Adjuster (`db6d9fb`, `26cc6a5`), v0.4 → v0.5. The Virtual Body approach itself was adopted earlier (validated via spikes around 2026-07-08, in daily use through 2026-07-17) — it supersedes an initially-tried "Gap Spacer" approach, which was rejected after on-device testing.
- ASD Issue #10 audits local/GitHub/documentation synchronization across 5 plugins, corrects `PLUGINS.md` staleness, and establishes the rule that `PLUGINS.md`'s Version field is authoritative over RC labels in commit messages.
- `docs/figma-os-state.md` is created (v1) to give the Architect (ChatGPT) product-state visibility into the private `figma-os` repository without direct access; the ChatGPT GitHub Connector is validated as a secondary, read-only verification channel (Fully Verified).
- Documentation Architecture v1.0 is proposed, reviewed, and approved (ASD Issue #12) — establishing the Past/Present/Future × Whole/Individual documentation structure this file is itself part of.
- Documentation Migration Epic (ASD Issue #13) is created with 13 child Issues (#14–#26) covering `docs/ASD_HISTORY.md`, `docs/ROADMAP.md`, and per-plugin `HISTORY.md`/`ROADMAP.md` for all 11 figma-os plugins.

---

# Open Items

- Pre-2026-07-12 ASD context (if any existed before the GitHub repository) is not recorded here — Unknown, not fabricated. If the Architect has relevant history from earlier ChatGPT conversations, it can be added as a dated entry above.
