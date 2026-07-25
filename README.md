# ASD

ASD is an **AI Governance Framework**. It coordinates multiple AI systems — each with a clearly defined role — to govern the design, implementation, and review of software products.

ASD is not a project, and this repository is not a code repository. ASD governs projects; this repository holds the governance, architecture, and canonical state that make that coordination possible.

This README is an entry document. It orients first-time readers and points to the canonical sources — it is not itself the Canonical State, and it is not kept in sync with day-to-day project status.

---

## Repository Purpose

`ga7ming3249/asd` is the governance hub for ASD. It holds:

- **Governance** — the AI Collaboration Contract and related policy documents
- **Architecture** — Specifications, ADRs, and Architecture Proposals
- **Canonical State** — the current operational state of ASD and of the `figma-os` product line
- **ASD-wide History and Roadmap** — past decisions and forward-looking priorities at the governance level

Product code, and documentation specific to a product, live in that product's own repository (see [Repository Relationships](#repository-relationships) below) — not here.

## Repository Responsibilities

This repository is responsible for:

- Defining and maintaining the AI roles that govern ASD and their responsibilities
- Recording Architecture decisions (Specifications, ADRs, Proposals) and their status
- Maintaining the canonical, current-state documents that let any AI session initialize without relying on prior chat history
- Coordinating work that spans multiple products or repositories
- Defining which repository owns and tracks a given piece of work

It is explicitly **not** responsible for day-to-day implementation work belonging to a specific product — that is tracked in the product's own repository once one exists.

## AI Roles

ASD coordinates work through a small set of defined roles. This is a high-level introduction only — see `docs/asd-state.md` for full responsibilities and current assignments.

| Role | Purpose |
|---|---|
| **Vision Owner** | Holds product vision, makes final decisions, and grants authorization |
| **Architect** | Defines architecture, writes Issue Specifications, and conducts Architecture Review |
| **Publisher** | Registers, updates, and closes GitHub Issues, faithfully reproducing approved specifications |
| **Primary Engineer** | Performs daily implementation, refactoring, and Git/PR work |
| **Independent Reviewer** | Provides third-party technical review of specifications and implementations, independent of the Architect and implementation roles |

## Repository Relationships

ASD governance spans several repositories, each with a distinct responsibility:

- **[`asd`](.)** (this repository) — Governance, Architecture, and Canonical State for ASD as a whole. Coordinates work across products; does not hold product code.
- **`figma-os`** — The Figma plugin product line (Type Adjuster, Type Polish, Component Package, and others). Holds plugin code, plugin-specific architecture, and each plugin's own documentation.
- **`reference-assistant`** — An independent product with its own repository. Holds its own code, Issues, and documentation; ASD governs it only at the cross-product / governance level, not its day-to-day work.

A product with no repository of its own yet may have its early proposals and scope held in `asd` until a dedicated repository is created for it. See `docs/repository-issue-ownership.md` for the full policy on which repository owns a given piece of work.

## Canonical Documentation

For the current, authoritative state of ASD, start here:

- [`docs/asd-state.md`](docs/asd-state.md) — the current operational state of ASD: active roles, governance, and current project status. The single initialization document for any new ASD session.
- [`docs/ROADMAP.md`](docs/ROADMAP.md) — ASD-wide forward-looking priorities (Now / Next / Future / Icebox).
- [`docs/figma-os-state.md`](docs/figma-os-state.md) — the current product-state source for the `figma-os` repository.

This README does not duplicate the content of those documents. When in doubt, the canonical documents above are authoritative and this README is not.
