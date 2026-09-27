# Method card template

Use this template to capture the paper's architecture for later reuse. Keep it focused on the overall model, module purposes and interactions, and architectural transfer conditions. Do not include experimental results. Include preprocessing, objective, training, inference, or other implementation details only when a specific detail determines whether the architecture can transfer, and state that transfer dependency briefly. Preserve existing user sections and omit empty optional detail, but keep unknown architecture requirements visible. Use `[S]` for source-supported claims, `[I]` for analyst inference, and `[U]` for unknowns; attach a section/page, figure, equation, algorithm, or stable source location to consequential `[S]` claims. Never invent an anchor.

```markdown
# <Paper title> — method card

Paper ID: <stable ID>
Status: complete | partial
Authors / venue / year: <verified metadata or unknown>
Source: <local source path or stable public link>
Source version: <DOI/arXiv version/date/hash when available>
Last inspected: <YYYY-MM-DD>
Inspected sections/pages: <architecture-relevant coverage>

## Task and architectural challenge

- Target task and model inputs/outputs: [S] ... (anchor)
- Architectural bottleneck addressed: [S] ... (anchor)
- Authors' stated design rationale: [S] ... (anchor)
- Analyst's causal interpretation, if different: [I] ...

## Overall architecture

- Architecture flow: <input → main modules/states → output>
- Where the main intervention occurs: [S] ... (anchor)
- How the architecture is intended to address the bottleneck: [S]/[I] ...

### Module: <functional name>

- Architectural role and purpose: [S] ... (anchor)
- Input and output interface: [S] ... (anchor; include only details relevant to module role or transfer)
- Core operation: [S] ... (anchor; include decisive equation/algorithm step only when needed to explain the architecture)
- Dependencies and information flow with other modules: [S]/[I] ... (anchor for source claims)
- Coupling or separability: [S]/[I] ... (anchor for source claims)
- Transfer condition or constraint: [S]/[I]/[U] ...

## Architecture transfer signature

| Transfer-relevant property | Source architecture requires | Provenance / anchor | Consequence for transfer |
| --- | --- | --- | --- |
| Required input, structure, or representation | | | |
| Backbone, topology, or insertion point | | | |
| Module interfaces and dependencies | | | |
| Structural assumptions that must hold | | | |
| Other implementation detail that determines architectural transfer, if any | | | |

## Transferable concepts

- Reusable architectural principle: [I] ... (cite source module/anchor and explain what may transfer)
- Component that is tightly coupled to this paper's architecture: [S]/[I] ...
- Likely interface with another method or base model: [I] ...
- Compatibility question or unresolved requirement: [I]/[U] ...

## Provenance and updates

- Source-supported architecture claims: <links to anchored statements above>
- Analyst interpretations and transfer hypotheses: <most consequential inferences>
- Unknown architecture requirements: <questions that affect transfer>
- Update note: <date, source-version change, sections revised, retained user annotations>
```

`index.md` is a lookup surface, not another summary. Use one row per stable paper ID:

```markdown
| ID | Paper | Source version | Core modules/principles | Intervention | Transfer tags | Status | Card |
| --- | --- | --- | --- | --- | --- | --- | --- |
| <ID> | <title> | <version> | <functional names> | <point> | <short tags> | complete/partial | [card](papers/<ID>.md) |
```

When a cross-paper `mechanism-primitives.md` is useful, give each architectural primitive a stable functional name, its source-card links, required inputs, produced outputs, and material differences between papers. Do not merge two methods solely because their names sound alike.
