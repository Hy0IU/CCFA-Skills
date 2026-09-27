# Method library → idea optimizer handoff

## Select and pass

Use the user's base idea and question to search `index.md` by bottleneck, intervention point, input/output, and transfer tags. Read only the relevant full cards. The handoff names the library root, selected card paths and source versions, card completion status, source-supported primitives, inferred transfer hooks, and unresolved requirements. A card is reusable evidence about its original paper; it is not evidence that a new combination will work.

If a selected card is partial or its source version has changed, refresh the affected method/evidence fields with `ccf-paper-to-method` before relying on them. Do not reprocess unchanged PDFs merely because the base idea changes. If external novelty claims matter, `ccf-literature-searcher` checks closest work separately.

## Compatibility before composition

`ccf-idea-optimizer` represents the base idea using the same dimensions as the cards: inputs, outputs, data construction, representation/granularity, supervision, objective, training, inference, compute, and architecture. For each selected primitive, record `compatible`, `conditional`, `conflict`, or `unknown` with a concrete reason and relevant source/card anchor. Check the full method's coupled components rather than treating every primitive as plug-and-play.

For a conditional fit or conflict, specify a proposed **bridge mechanism**: what adapts the input/output or assumption, what new information flow or optimization behavior it creates, and which premise remains to be tested. Keep source-supported operations, the user's base mechanism, and the optimizer's new inference traceable as separate parts. A mere sequence of existing modules is not a bridge.

The optimizer then develops candidate frameworks and a discriminating test under its own skill rules. Its output cites selected card IDs and source anchors, states material compatibility unknowns, and identifies the simplest comparison that could falsify the central interaction claim. `ccf-paper-to-method` updates the library only when paper understanding or source versions change; it does not write the final framework idea into paper cards.
