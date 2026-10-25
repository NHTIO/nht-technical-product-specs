# NHT Technical Specs

A reusable agent skill for collaboratively creating and maintaining technical specifications in **NHT Specs (Outline)**. It turns product requirements into evidence-backed architecture, contracts, decisions, verification plans and implementation guidance without treating specification writing as permission to implement.

The skill keeps the useful parts of a documentation-site workflow: agree the outline, research claims, draft section by section, track owned open questions, and leave a reviewable record after each pass. Outline documents and links replace site scaffolding, navigation configuration and publication commits.

## Use

The repository is `NHTIO/nht-technical-product-specs`; the skill/package name is **`nht-technical-specs`**. Load the repository root as a skill using your agent client's supported skill mechanism, preserving `SKILL.md`, `agents/`, and `references/` together. When copying into a client skill directory, use the folder name `nht-technical-specs`.

Example request:

> Use $nht-technical-specs to develop the technical specification in NHT Specs from our agreed product requirements. Start with an outline for review.

For a later pass:

> Use $nht-technical-specs to incorporate the supplied review feedback into this existing specification, preserving unrelated edits and unresolved questions.

A working authorized NHT Specs/Outline connection is needed to read or save documents. The endpoint is https://specs.nht.io/mcp; use your client's supported secure OAuth flow. Installing this skill does not configure access, create credentials or change permissions.

## Contents

- [SKILL.md](SKILL.md): scope, collaborative passes, research, decisions and readiness.
- [Technical content](references/technical-content.md): adaptable outline, evidence and verification guidance.
- [Outline workflow](references/outline-workflow.md): destination discovery, safe creation/patching and readback.
- [Agent metadata](agents/openai.yaml): display name and example invocation.

The complementary [NHT Product Specs skill](https://github.com/NHTIO/nht-product-specs) addresses the requester's what, why, deliverables and acceptance criteria. This skill handles the engineering how while keeping the product baseline authoritative.

Publication of this package does not install it in any client. The skill does not authorize code changes, deployments, ticket updates, broader document sharing, or changes to the product requirements. No project-specific specifications, credentials or secret values belong in this repository.
