# Persistent Idea Memory

Use this contract for an ongoing research direction. Prefer the user's chosen location or an established idea folder; otherwise use the project root's `ccfa-workfiles/ideas/<topic-id>/`. Do not save private project memory in the skill repository. Keep the folder and its identifiers stable across conversations.

## Files and ownership

- `index.md`: the topic, link to the active idea document, and a short lineage table of retained idea documents with status and the reason each successor was created. It is a locator, not a duplicate idea report.
- `memory.md`: cumulative, concise research memory. Record new paper-derived architectural insights with method-card IDs and source anchors, user decisions, optimizer inferences, rejected or superseded hypotheses with reasons, and open questions. Mark source-supported, inferred, and user-provided statements separately. Update existing entries when a conclusion is refined; preserve consequential earlier decisions and corrections rather than rewriting history as if the current view were always known.
- `idea-001.md`, `idea-002.md`, and so on: coherent idea documents. Start with one broad `idea-001.md` even if the direction is incomplete. Each document states its research problem, central insight, proposed architecture and module roles, relationships to selected paper cards, decisive assumptions, unresolved questions, and next decision. Label unverified claims and planned evidence; do not invent experimental results.

## Continuation and change rule

At the start of a later idea task, read `index.md`, `memory.md`, and the active idea document, then only the relevant method cards or source material. Add a newly supplied paper through `ccf-paper-to-method` first; record what it changes in `memory.md` and in the active idea document or a successor. Do not copy whole paper cards into memory, and do not write idea-derived insights back into paper cards.

Update the active idea document in place when new papers, discussion, or corrections **refine the same core research problem and main mechanism**. Record the material revision and its reason inside that document. Create the next numbered document only when the core problem or main mechanism changes. Preserve the predecessor's substantive content as a historical idea; change only its status and successor link, update `index.md` to point to the successor, and record the reason for the change in `memory.md`. A wording change, extra citation, implementation detail, or small module adjustment does not by itself create a successor. Do not create a new numbered document for every conversation.

If the boundary is genuinely ambiguous, describe the possible successor and the deciding difference; continue updating shared memory and independent parts without silently replacing the active idea. Respect an explicit chat-only or no-new-files request.

## Minimal templates

```markdown
# Idea index: <topic>

Active idea: [Idea 001](idea-001.md)

| Idea | Status | Core change from predecessor |
| --- | --- | --- |
| [Idea 001](idea-001.md) | active | Initial broad idea |
```

```markdown
# Idea memory: <topic>

## Current understanding
- [source-supported / inference / user decision] <insight>; source or idea link; status

## Decisions and lessons
- <decision or rejected route>; reason; date or source change; related idea document

## Open questions
- <question>; what would resolve it; related source or idea
```

```markdown
# Idea 001: <working title>

Status: active | superseded
Predecessor: none | <relative link>
Successor: none | <relative link>

## Research problem and core insight
## Proposed architecture and module roles
## Connections to reference papers
## Assumptions and unresolved questions
## Next decision and planned evidence
## Material revisions
```
