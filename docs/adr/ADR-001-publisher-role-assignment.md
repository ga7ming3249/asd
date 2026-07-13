# ADR-001: Publisher Role Assignment

- Status: Accepted
- Date: 2026-07-13
- Owner: ASD

---

## Context

ASD initially proposed using Codex as the Publisher responsible for registering Issue Specifications to GitHub.

A proof-of-concept was conducted using Codex Web and the GitHub Connector.

The evaluation revealed that:

- GitHub Connector does not currently provide reliable GitHub Issue creation.
- Codex falls back to GitHub CLI (`gh`) for Issue creation.
- This requires additional environment setup, authentication, and long-term maintenance (GH_TOKEN, Environment Secrets, Setup Script).

This operational complexity conflicts with ASD's design principle of minimizing operational overhead.

---

## Decision

The Publisher role is retained as a responsibility, but the implementation is changed.

Claude Code is assigned as the Publisher for GitHub Issue registration.

When acting as Publisher, Claude Code must faithfully reproduce the approved Issue Specification.

No rewriting.

No summarization.

No interpretation.

No enrichment.

After Issue registration is complete, Claude Code returns to its normal role as Primary Engineer.

---

## Rationale

This approach provides:

- Minimal operational overhead
- No additional authentication infrastructure
- No persistent PAT management
- Natural integration with the existing implementation workflow
- Preservation of Human Authorization
- Preservation of ChatGPT architectural ownership

The Human remains responsible for Authorization by explicitly requesting Claude Code to publish the Issue Specification.

---

## Consequences

### Positive

- Simpler daily workflow
- Lower maintenance cost
- Better continuity between Issue creation and implementation
- Claude Code understands implementation context before coding

### Negative

- GitHub Issue registration remains a manual approval step.
- Codex is not used for Issue publication.

---

## Future Review

If GitHub Connector gains official Issue creation support without requiring additional authentication infrastructure, this decision may be revisited.

Current role of Codex:

Specialist Engineer

Participation is optional and determined on a per-task basis.

---

## Related Specifications

- Specification 001 — AI Collaboration Contract
