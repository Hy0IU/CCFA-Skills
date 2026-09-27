# Method card template

Use these fields to make a card reusable across future base ideas. Preserve existing user sections and omit empty optional detail, but keep unknown requirements visible when they affect transfer. Mark a card `partial` until the relevant method and evidence have been inspected. Use `[S]` for source-supported, `[I]` for analyst inference, and `[U]` for unknown; attach a section/page, figure, equation, table, or stable source location to consequential `[S]` claims. Never invent an anchor.

```markdown
# <Paper title> — method card

Paper ID: <stable ID>
Status: complete | partial
Authors / venue / year: <verified metadata or unknown>
Source: <local source path or stable public link>
Source version: <DOI/arXiv version/date/hash when available>
Last inspected: <YYYY-MM-DD>
Inspected sections/pages: <specific coverage>

## Problem and core insight

- Target task, inputs, and outputs: [S] ... (anchor)
- Root difficulty / prior failure addressed: [S] ... (anchor)
- Why the authors expect their intervention to work: [S] ... (anchor)
- Analyst's causal interpretation, if different: [I] ...

## Method mechanism

Overall flow: <input → intermediate state → intervention → output>

### Primitive: <functional name>

- Input and type/granularity: [S] ... (anchor)
- Operation, including decisive equation or algorithm step: [S] ... (anchor)
- Output and consumer: [S] ... (anchor)
- Purpose in the source method: [S] ... (anchor)
- Dependencies and required assumptions: [S]/[I]/[U] ...
- Coupling to other primitives: [S]/[I]/[U] ...

## Assumptions and compatibility signature

| Dimension | Source method requires | Provenance / anchor | Transfer consequence |
| --- | --- | --- | --- |
| Data and graph construction | | | |
| Representation and granularity | | | |
| Supervision and labels | | | |
| Objective and losses | | | |
| Training and update regime | | | |
| Inference inputs and latency | | | |
| Compute and memory | | | |
| Architecture dependency | | | |

Consumes: <signals, structures, embeddings, gradients, logits, etc.>
Produces: <states, scores, constraints, messages, etc.>
Intervention point: <input / encoder / representation / loss / optimizer / inference / post-processing>

## Evidence and limits

- Main reported result and protocol: [S] ... (table/section anchor; include numbers only if checked)
- Evidence isolating the mechanism: [S] ... (ablation/control anchor, or `not established`)
- Reported failure cases or limitations: [S] ... (anchor)
- Additional plausible limitations: [I] ...

## Transfer and combination hooks

- Transferable primitive and why it can be separated: [I] ...
- Non-transferable or tightly coupled component: [S]/[I] ...
- Required transfer condition: [S]/[I]/[U] ...
- Possible interface with another method or base model: [I] ...
- Compatibility obstacle or conflict to test: [I] ...
- Minimal observation that would test transfer: [I] ...

## Provenance and updates

- Source-supported conclusions: <links to anchored statements above>
- Analyst inferences: <most consequential extrapolations>
- Unknowns requiring source or experiment: <questions>
- Update note: <date, source-version change, sections revised, retained user annotations>
```

`index.md` is a lookup surface, not another summary. Use one row per stable paper ID:

```markdown
| ID | Paper | Source version | Core primitives | Intervention | Transfer tags | Status | Card |
| --- | --- | --- | --- | --- | --- | --- | --- |
| <ID> | <title> | <version> | <functional names> | <point> | <short tags> | complete/partial | [card](papers/<ID>.md) |
```

When a cross-paper `mechanism-primitives.md` is useful, give each primitive a stable functional name, its source-card links, required inputs, produced outputs, and material differences between papers. Do not merge two methods solely because their names sound alike.
