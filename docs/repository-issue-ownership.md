# Repository Issue Ownership Policy

- Status: Adopted
- Version: 1
- Date: 2026-07-22
- Owner: ASD Global Architect
- Source: Repository Issue Ownership Reorganization (Phase 1 Inventory 2026-07-22 / Phase 2 Scope 2026-07-22)

---

# Purpose

This policy defines which repository owns and tracks a given GitHub Issue. It exists so that Issue ownership follows the Primary Deliverable's Canonical Source, not the chat, Agent, or engineer that happened to discover or design the work.

---

# Primary Deliverable / Canonical Source Rule

An Issue is managed in the repository that owns the Canonical Source of the Primary Deliverable the Issue mainly changes, creates, or verifies.

Issue ownership is **not** decided by:

- Which chat discovered the Issue
- Which Agent designed the Issue
- Who implements it
- Where a similar past Issue was placed
- Which tool happens to be available

---

# `asd` Responsibility

`asd` manages:

- Governance
- Global Architecture Principles
- Architecture Process
- State Synchronization
- Product-wide / cross-plugin Coordination
- Shared Frameworks that belong to ASD operation itself

Individual Product implementation Issues are not managed in `asd` as a rule.

---

# `figma-os` Responsibility

`figma-os` manages:

- Type Polish
- Type Adjuster
- Component Package
- Every Figma Plugin inside `figma-os`
- Plugin UI
- Plugin-specific architecture
- Responsibility boundaries between Plugins ("Plugin間の実装上の責務整理")
- Plugin Source, Tests, Build, Product Documentation

If a deliverable's Canonical Source (e.g. Component Package) has actually moved to another repository, that repository takes priority, and the move is reported before any Issue operation.

---

# Other Product Repository Rule

Independent Products (Reference Assistant, CLI, Desktop Application, Web Application, etc.) are managed in their own Product Repository once one exists.

## Repository未作成Productの扱い

For a Product with no repository yet, `asd` may hold the Product Proposal, Initial Scope, and the Repository-creation decision. Implementation Issues move to the Product Repository once it is created. Until then, Issues for that Product correctly remain in `asd` (e.g. Reference Assistant — no repository exists as of 2026-07-22).

---

# Primary Issue Rule

The same work is not actively tracked in more than one repository at a time. Each unit of work has exactly one Primary Issue, which holds Objective, Scope, Acceptance Criteria, Progress, Completion Decision, Close Status, and Handoff Packet.

---

# Cross-Repository Parent / Implementation Issue Rule

When a unit of work requires implementation changes in more than one repository, or mixes ASD-level Architecture/Gate coordination with Product implementation:

- Product-specific implementation work gets its own Implementation Issue in the Product Repository (e.g. `figma-os`)
- Only when ASD-wide judgment or cross-product integration is required does `asd` hold a Parent Coordination Issue
- Parent and Implementation Issues are cross-linked in both directions
- Primary status is not collapsed into the Parent — the Parent references each Implementation Issue's own completion state
- A Parent Coordination Issue is not created merely to reference another repository's Issue

A Gate-based, Architecture-gated Issue (Architecture Gates, Global Architect Review, State Synchronization judgment) may remain the Parent Coordination Issue in `asd` even while its actual code-level Gate work is tracked in a `figma-os` Implementation Issue — see the Conditional Creation Rule below.

## Conditional Creation Rule for Gate-scoped Implementation Issues

A `figma-os` Implementation Issue for a specific Gate is created **only** when the Gate's Objective, In Scope / Out of Scope, Acceptance Criteria, Architecture Constraints, target Plugin/Source, and a confirmed Handoff from the prior Gate are already explicit in the Parent Issue or a formal Architect Kickoff comment. If any of these is missing, no Implementation Issue is created; the gap is reported as `Gate N Issue Specification Required` instead of being filled by assumption.

---

# Closed Issue Historical Preservation

Closed Issues stay in their current repository as historical record. They are not migrated, and are not reopened for the sole purpose of relocating them. A later Successor Issue may reference a Closed Issue, but the Closed Issue itself is untouched.

---

# Active Issue Successor Transfer Rule

An Open, not-yet-started Issue whose Primary Deliverable belongs to another repository's Canonical Source is migrated by the Successor Issue method:

1. Confirm the Issue is genuinely not started (no active branch, PR, or unmerged commit)
2. Create a Successor Issue in the correct repository, preserving Objective, Scope, and Acceptance Criteria
3. Record the Source Issue URL and transfer reason in the new Issue
4. Comment the Successor Issue URL on the original Issue
5. Close the original Issue only after the Successor Issue is confirmed created and cross-linked

An Issue that is already In Progress (active branch/PR/commit) is never migrated automatically — it is reported as `ASD Escalation Required` with the current state and options, and only moved if an explicit decision is already on record.

GitHub's Issue Transfer feature is not used unless history, links, Issue numbers, and Automation impact have been confirmed safe; the Successor Issue method above is the default.

---

# Source Code / Package Movement

Moving Source Code or a Package between repositories is a separate Architecture Decision. It is never bundled into an Issue Ownership reorganization, and is reported as `ASD Escalation Required` if it appears necessary.

---

# Decision Roles

| Role | Responsibility |
|---|---|
| ASD Global Architect | Ownership decisions — which repository an Issue belongs in, Phase-level scope authorization |
| Issue-scoped Architect | In-Issue review, Gate/Completion Decision within a single Issue |
| Claude Code (CC) | Executes GitHub operations, documentation, Commit/Push, under the above decisions |
| Vision Owner | Final decisions on Product Scope, Priority, Merge, and Release |

---

# Out of Scope

Issue Session Protocol and the Proposal / Progress / Completion Packet format are separate Governance work and are not defined by this document.
