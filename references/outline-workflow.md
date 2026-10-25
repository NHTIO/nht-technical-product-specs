# Outline document workflow

## Connect and discover

Use the existing NHT Specs/Outline connector at https://specs.nht.io. The native remote MCP endpoint is https://specs.nht.io/mcp (Streamable HTTP with client-managed OAuth). Do not create credentials, change workspace settings or configure a client merely to write a spec. If connection is missing, use the client's supported connection flow with the necessary authorization; never request secrets in chat.

Discover the tools and schemas actually exposed by the current client; aliases and capabilities may differ. The NHT connector currently provides logical operations such as collection listing, document search/fetch, collection document tree, template discovery, document creation and targeted update. Do not hard-code a ChatGPT namespace or invent an API action. Paginate supported listings as needed.

Top-level collections represent projects; Welcome is shared guidance, not a destination for project technical specs. Resolve the owning project from the request and existing documents. Reuse the existing hierarchy and canonical document IDs. Search for an existing technical spec before creating another; published collection trees omit drafts and archived documents, so absence from the tree is not proof of nonexistence. An absent project may be inaccessible. Ask rather than create a replacement collection or a general Technical Specifications collection.

A title that includes “template” does not establish a native template. Use template IDs only from actual template discovery. Do not modify a product-spec template to become a technical template.

## Structure and access

Use one canonical technical-spec overview in the owning project, with sections or children as agreed in the outline. Link the product spec, substantive child sections, open questions/dependencies, and decisions so reviewers can navigate without repository sidebars. Prefer explicit returned document URLs over guessed slugs. Keep any existing product-to-technical backlink intact; adding one to the product document requires authorization to edit that document.

Check destination and audience, including returned permission/sharing metadata. Collection membership is not the only access path: document/subtree sharing or public links may broaden it. A readable document does not prove write access. If metadata explicitly denies writes, stop; otherwise attempt only the authorized write, not a disposable permissions test. Do not add members, move collections, or enable public sharing to finish the task. Links do not grant access.

Store review/readiness status in supported metadata or clearly labeled content, not by moving documents between collections. Outline storage publication and human approval are separate. Preserve the existing publication state unless the user authorizes changing it. For an explicitly requested new draft, use publish=false; current create_document defaults publish=true, so set the intended state deliberately. Clarify ambiguous visibility before saving.

## Create or edit

For creation, provide a verified collectionId or parentDocumentId, a separate title, and body text. The body must not begin with H1; start with prose or an H2. Do not import repository frontmatter, VitePress sidebar/config, ::: warning containers, local asset paths or generated llms files. Use ordinary Markdown with a visible “Awaiting …” paragraph for blockers. Verify actual diagram support before promising rendered Mermaid.

For updates, fetch the latest content and metadata first. Prefer update_document with editMode="patch", findText copied exactly from fresh Markdown, and replacement text. The current operation replaces the first match: include enough surrounding context to make it unique. Preserve unrelated user edits, rich formatting, comments, status and hierarchy. Full replacement loses formatting not represented in Markdown; use it only for an authorized full rewrite with those implications accepted.

Re-fetch immediately before writing when intervening changes are plausible. Compare the prepared excerpt and relevant baseline/approval state. Use a revision precondition if the actual API offers one; otherwise describe this as best-effort conflict detection, not atomic locking. On mismatch or patch failure, reconcile with the current document instead of blindly repeating stale content.

Multi-document work is not atomic. Save coherent section-level changes and update the overview/question links using actual returned IDs/URLs. Track which writes succeeded. When only some changes complete, report the partial state and remaining work, without duplicating already-created children or erasing newer edits.

## Verify and resume

After each meaningful save, fetch the affected document(s) and verify the requested content, collection/parent, links and publication state. On an uncertain write outcome, inspect current state before retrying. Stop on an access denial; do not switch identities or routes to bypass it.

At the end of a pass, ensure the overview identifies the product baseline, current sections, decisions, unresolved questions and what to work on next. A short dated change summary is useful for substantive passes, not required noise for every typo. Do not assert a native revision number unless returned by the server, or promise a commit-like snapshot spanning several documents.

Return verified canonical links and a concise saved-state/readiness summary. A local draft is not an Outline save, and a published document is not proof of stakeholder agreement.
