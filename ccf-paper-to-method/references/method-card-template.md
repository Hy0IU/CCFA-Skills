# Method card: an explanation that stands on its own

The card is a reusable account of the original paper's architecture, not a set of extraction fields. A later reader should understand the method well enough to compare or compose mechanisms without opening the PDF for basic explanations. Write in the user's language. Use ordinary explanatory prose, a compact flow, and only the equations or details that define an architectural operation. Preserve the paper's terminology where it matters, but explain what each term does.

The outline below is adaptable. Merge or rename sections when that makes the method clearer; retain identity, source version, architectural flow, module interactions, transfer conditions, and provenance. Do not include experimental results. Implementation details belong here only when they change the architecture or its transfer conditions.

```markdown
# <Paper title> — 方法架构解读

Paper ID: <stable ID>
Status: complete | partial
Authors / venue / year: <verified metadata or unknown>
Source: <local source path or stable public link>
Source version: <DOI/arXiv version/date/hash when available>
Last inspected: <YYYY-MM-DD>
Inspected sections/pages: <architecture-relevant coverage>

## 方法要解决什么问题

<Explain the task, the specific architectural bottleneck, and the authors' organizing idea in a short connected account. State the predicted object or output. Attribute the authors' rationale to the paper; label a different causal interpretation [I]. One source anchor can support a coherent paragraph.>

## 模型全貌：信息怎样流动

<A compact, source-faithful flow such as input → representation/graph construction → main branches → fusion → output. Then explain in prose what each branch contributes and where they reconnect. If a training or adaptation loop wraps the prediction path, describe it separately rather than presenting it as another inference-time module. Anchor the overall topology to a figure or method section.>

## 关键模块与连接

### <Functional module name>

<Explain why the module exists; what it receives; the decisive operation in plain language; what representation, score, or decision it emits; and how the next module uses that output. Explain any equation/algorithm step that changes the information flow instead of listing equation numbers. State whether the module can be separated from the rest and what interface it must preserve. Cite the source once after the substantial explanation.>

<Repeat for the modules needed to understand the whole architecture. Group tightly coupled operations when splitting them would obscure their joint purpose.>

## 从一次预测或训练过程看模块如何协同

<Walk a representative input through the important modules and the final output. Use a schematic example only when it clarifies a real operation; label it “示意例子 [I]” and invent no paper result, dataset fact, or unreported behavior. When training changes the architecture's meaning, explain what is adapted or optimized and when.>

## 可以迁移什么，以及需要满足什么

<Explain the reusable architectural principle and the exact insertion point or interface. Identify required inputs, structural assumptions, coupling, and what would need a bridge or redesign in another model. Keep author-stated requirements [S], analyst transfer hypotheses [I], and unresolved requirements [U] distinct. Do not assert that a combination will work merely because components can be connected. A short table is useful only if it adds clarity to the prose.>

## 来源与理解边界

- 论文依据 [S]: <short map from the major explanations above to sections/pages, figures, equations, or algorithms; no repeated list of every citation>
- 分析性解释 [I]: <the consequential interpretations or transfer hypotheses, linked to the source mechanism they interpret>
- 尚未确认 [U]: <architecture details whose absence changes understanding or transfer, or “none material in inspected scope”>
- 更新记录: <date, source-version change, substantive revision, retained user annotations>
```

Use `[S]` for an explanation supported by the paper, `[I]` for the analyst's causal reading or transfer hypothesis, and `[U]` for an unresolved requirement. A paragraph or clearly labeled subsection can carry one tag; do not prefix every sentence. Put its section/page/figure/equation anchor at the end of the substantive paragraph or in the short source map. A bare list such as “input: X; operation: Eq. 4; output: h; purpose: personalization” is incomplete until the card explains how X becomes h, why this affects personalization, and what consumes h.

For example, replace “edge gate + attention → node embedding (Eq. 3)” with a paragraph of this form: “The edge gate uses the visit's attributes to scale the message sent by a neighboring place. Attention then compares that neighbor with the other neighbors of the user. The aggregated result is the user's structural representation, which the later user-fusion module combines with a trajectory representation. The gate therefore changes what each visit contributes, while attention changes its weight relative to other visits.” This is a writing example, not a claim about every paper; verify the actual operations and cite the inspected source before using such prose in a card.

Before saving, read only the card and check whether its account answers these questions without the PDF: What is the central difficulty? What happens to a user, item, or other input from start to finish? Why does each important module exist, and what does it hand to the next one? Which operations happen only during training? What must remain true for a mechanism to transfer? If a key answer is merely a source locator or a module label, add the missing explanation or mark a genuine source gap `[U]`.

`index.md` remains a lookup surface rather than a duplicate card. Use one row per stable paper ID:

```markdown
| ID | Paper | Source version | Core modules/principles | Intervention | Transfer tags | Status | Card |
| --- | --- | --- | --- | --- | --- | --- | --- |
| <ID> | <title> | <version> | <functional names> | <point> | <short tags> | complete/partial | [card](papers/<ID>.md) |
```

When a cross-paper `mechanism-primitives.md` is useful, give each architectural primitive a stable functional name, its source-card links, required inputs, produced outputs, and material differences between papers. Do not merge two methods solely because their names sound alike.
