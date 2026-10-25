# Technical content and evidence

## Product-to-technical boundary

Begin with a canonical product-spec link and the version/revision or last-read date available from the source. Identify applicable requirement/acceptance IDs. Do not duplicate the entire product spec into a second drifting source of truth. Record technical constraints required by the product; label newly suggested constraints as proposals.

If no product spec exists, establish the actual authorized requirements from the user and mark the source clearly. Do not fabricate an approved product document or insist on creating one as an unrequested side effect. A missing product decision that affects the design must be returned to the requester. Development-owned choices can be worked through here; they cannot change the promised result silently.

## An adaptable outline

Offer only sections relevant to the work, and obtain outline signoff. A useful starting menu:

- Context, product baseline, scope and technical constraints.
- Current system and proposed architecture, ownership boundaries, data/control flows.
- Public/internal interfaces, data models, schemas and contracts.
- Lifecycle and consistency: transactions, concurrency, retries, idempotency, failure recovery.
- Security, authorization, privacy, retention and operational boundaries.
- Integrations and external dependencies, version compatibility and deployment assumptions.
- Migration, rollout/rollback, observability and operational ownership where applicable.
- Verification mapped to product acceptance criteria and technical risks.
- Implementation plan: bounded work, prerequisites/dependencies and completion checks, when requested.
- Decisions, open questions/dependencies and reference sources.

Do not manufacture performance targets, deadlines, staffing, external service choices or task assignments. A technical work breakdown is prose planning, not permission to create tickets or execute it. Scale document splitting to length and review needs: a small spec can use one document; larger specs can use an overview with section children.

## What a useful design section establishes

Describe the proposed behavior concretely enough to implement. Where relevant, define inputs/outputs and validation, ordering and precedence, state transitions, error semantics, compatibility, authorization boundaries, operational failure handling and verification. Include small contract examples when they remove ambiguity. Mark illustrative code or pseudocode as such; do not present it as tested implementation.

For material choices record: decision or proposal, alternatives considered, reason, consequences, supporting evidence, status, and decision owner/approval source if known. Avoid an ADR bureaucracy for trivial choices. For an external API, distinguish vendor-documented guarantees from observed behavior and assumptions; a plausible example is not proof of a partial-update or isolation guarantee.

## Evidence workflow

Inspect the relevant code and official API/library documentation for the actual supported version. Use available connected tools first; use an authorized browser for documentation that requires JavaScript. Record repository path plus commit/ref for existing behavior when practical, and direct source links beside claims. If a required source is unavailable, say exactly what is unverified and what decision it blocks. Do not substitute confident prose for missing evidence.

Proposed architecture can be reasoned from constraints without pretending it is existing behavior. Explain the reasoning and evidence limits. A passed test reported by another source is a reported result, not a test this author independently ran. Inspection and documentation research do not authorize executing untrusted code or changing a live system.

## Readiness and review checks

Before claiming readiness, check:
- Every relevant product acceptance criterion has a technical path and a verification method.
- Interfaces and data flows agree across sections; naming, defaults, units and versions are consistent.
- Failures, security boundaries and migrations are addressed where material.
- Open questions are visible at the affected sections, with owners/status/date and dependencies; blocked work is not labeled ready.
- Accepted decisions are distinguished from proposals, and no source is cited for a claim it does not support.
- A new reader can identify the baseline, current plan, latest pass, blockers and next step.

A review request alone authorizes review, not edits. Present actionable findings with their evidence and proposed resolution; incorporate changes only within the user's authorized scope.
