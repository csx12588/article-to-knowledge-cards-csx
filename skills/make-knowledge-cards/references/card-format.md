# Card Format Reference

Field-level rules for a single knowledge card, plus the mistakes to avoid.

## Field definitions

| Field | Required | Rule |
| --- | --- | --- |
| Title | Yes | A specific noun phrase naming one knowledge point. Must be searchable on its own. |
| Core knowledge | Yes | Exactly one sentence. One claim, one subject. |
| Explanation | Yes | 2-4 sentences answering why it holds, how it works, or what it implies. |
| Example / self-test | Yes | Choose one. A self-test question, or a concrete example. |

## Title

Write a specific noun phrase that names the point, not the paragraph.

| Good | Poor | Why |
| --- | --- | --- |
| 睡眠通过海马体重放完成记忆巩固 | 记忆 | Too broad, could cover any memory fact. |
| 番茄钟不可分割 | 补充说明 | Names no knowledge point. |
| A branch is only a pointer | 分支 | Too vague to recall anything. |
| 最低系统版本提升至 iOS 15 | 其他变更 | Unsearchable placeholder. |

Banned title words: `简介`, `概述`, `其他`, `补充`, `要点一/二/三`, `About`, `Misc`.

## Core knowledge

One sentence, one claim. It must be a statement, not a topic label.

- Good: `睡眠以约 90 分钟为一个周期。`
- Poor: `关于睡眠周期` (a label, not knowledge)
- Poor: `睡眠以约 90 分钟为一个周期，且分为四到五个阶段，其中深睡最重要。`
  (two claims - split into separate cards)

## Explanation

Explain, do not restate. The core knowledge says *what*; the explanation says *why*,
*how*, or *so what*. Stay inside the source: if the source does not explain a mechanism,
do not supply one from outside knowledge.

## Example or self-test

Choose by content type:

- **Self-test question** - for concepts, principles, and definitions. The answer must be
  derivable from the card's own fields, so the reader can check themselves.
- **Example** - for methods, procedures, and case-driven content.

Priority order for the example field:

1. Use an example that already exists in the source.
2. If the source has no usable example, write a **self-test question** instead.
3. Never invent example data (numbers, scenarios, product names) that the source does
   not contain - that breaks the no-fabrication rule.

## Complete good vs. poor card

Good:

```markdown
### 卡片 3：睡眠由约 90 分钟一个的周期构成
- **核心知识**：睡眠以约 90 分钟为一个周期，每个周期包含 NREM 与 REM 两种睡眠。
- **简明解释**：睡眠不是均匀的整体，而是在非快速眼动睡眠（NREM）和快速眼动睡眠
  （REM）之间循环，单个周期约 90 分钟。理解周期是理解两类睡眠分工的前提。
- **自测问题**：一个睡眠周期大约多长？周期内包含哪两类睡眠？
```

Poor - and why:

```markdown
### 卡片 3：睡眠周期
- **核心知识**：睡眠很重要，包含多个阶段，对记忆有好处，还可以恢复体力。
- **简明解释**：睡眠分为多个阶段，每个阶段都有作用。
- **例子**：小明每天睡 8 小时，考试成绩提升了 20 分。
```

Problems: the title is a topic label; the core knowledge packs four claims into one
sentence; the explanation adds nothing; the example is invented data that the source
never mentioned.

## Special cases

### Enumerations in the source

When the source lists several parallel rules (e.g. "使用时有三个原则"):

- Give each rule its own card **only when** the rule is independently meaningful and
  would be useful on its own.
- Otherwise keep them in one card whose core knowledge states that the rules exist as a
  set, and whose explanation lists them.

Do not create one card per sentence just to reach the target count.

### More than 8 strong points

Merge points that are two facets of the same idea, then keep the top 8 by importance to
the article's central message. Never exceed 8.

### Fewer than 5 strong points

Output the real number and add a one-line note immediately after the article heading:

```markdown
> 原文信息不足以支撑 5 张卡片，以下为 3 张核心卡片。
```

### Source is a list, changelog, or FAQ

Treat each independently useful entry as a candidate point. Skip entries that are pure
bookkeeping (version bumps with no user impact, typo fixes, links).
