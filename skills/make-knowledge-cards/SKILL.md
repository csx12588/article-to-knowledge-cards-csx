---
name: make-knowledge-cards
description: This skill should be used when the user wants to turn a pasted article or a local Markdown/TXT file into 5-8 concise knowledge cards for learning or review. Trigger it on requests such as "把这篇文章做成知识卡片", "把这段内容整理成知识卡片", "帮我把这个 md 文件切成知识点", "make knowledge cards from this article", or whenever a .md/.txt document is provided and the user asks to extract key knowledge, build study cards, or generate self-test questions. It does not support web scraping, PDF input, Anki export, or any graphical interface.
license: MIT
---

# Make Knowledge Cards

## Overview

Convert a pasted article or a local Markdown/TXT file into 5-8 standalone knowledge
cards. Each card teaches exactly one knowledge point and contains a title, the core
knowledge, a concise explanation, and either an example or a self-test question.
The value of this skill is faithful extraction: keep what matters, drop what repeats,
and never invent content that is not in the source.

## Input Handling

Accept exactly two input sources:

1. **Pasted article text** - the user pastes the content directly in the conversation.
2. **Local Markdown/TXT file** - the user provides a path to a `.md`, `.markdown`,
   `.txt`, or `.text` file. Read it with the file-reading tool before working.

Out of scope - state the limitation clearly and ask for a supported input instead of
guessing or substituting content:

- Web pages / URLs (no scraping)
- PDF, Word, PPT, images, or other binary documents
- Anki export or any interactive/graphical output

If the source is a URL, respond that only pasted text or local Markdown/TXT files are
supported, and invite the user to paste the text or save it as `.md`/`.txt`.

If a local file is empty, unreadable, or contains only boilerplate (navigation,
copyright, ads), report this briefly and ask for usable content rather than emitting
empty cards.

## Workflow

### Step 1 - Read and understand the source

Read the whole source once. Identify the topic, the structure, the central claims, and
the supporting material (definitions, mechanisms, steps, data, examples, caveats).

### Step 2 - Extract candidate knowledge points

List every distinct knowledge point as a short phrase. Prefer points that are:

- **Conclusions or principles** the article is built around
- **Mechanisms or causes** that explain "why" / "how it works"
- **Definitions** of terms the reader must know to follow the rest
- **Actionable steps or rules** the reader can apply
- **Common pitfalls, misconceptions, or boundaries** that are easy to get wrong

Ignore filler: greetings, background storytelling with no reusable content, marketing
language, repeated restatements of the same idea.

### Step 3 - Merge duplicates and rank

Merge points that express the same idea, even when worded differently. Then rank by
importance to the article's main message. A point that appears once and carries the
whole argument outranks a detail mentioned twice.

### Step 4 - Select the final set

- Aim for **5-8 cards**.
- Take the top-ranked distinct points. If the source yields more than 8 strong points,
  merge the ones that are two facets of the same idea, then keep the top 8.
- When the source lists several parallel rules, give each rule its own card only if it
  stands on its own; otherwise cover the set in a single card.
- **Never pad to reach a number.** If the source only supports 3 solid knowledge
  points, output 3 and say so in one line. Fewer accurate cards beats 8 padded ones.
- **Never split one idea into several cards** to inflate the count.

### Step 5 - Write each card

For every selected point, produce:

| Field | Requirement |
| --- | --- |
| Title | A specific noun phrase naming the point. Avoid vague titles like "简介", "其他", "补充说明". |
| Core knowledge | One sentence stating the single fact, conclusion, or rule. |
| Explanation | 2-4 sentences: why it holds, how it works, or what it implies. |
| Example or self-test | Exactly one of the two (see below). |

Choose the fourth field by content type, and follow the priority order so nothing is
invented:

- **Self-test question** - first choice for concepts, principles, and definitions. The
  question must be answerable from the card itself.
- **Example** - first choice for methods, procedures, and case-driven content, but only
  when the source already contains a usable example.
- If the source provides no example, use a self-test question rather than inventing
  example data. Fabricated scenarios, numbers, or names violate the no-fabrication rule.

Write in the same language as the source. Output only the cards (plus the optional
short note about a reduced count) - no greeting, no restating the request, no
meta-commentary.

## Knowledge Selection Rules

Apply all of the following, in order of priority:

1. **Extract only what matters** - a reader who studies the cards should get the
   article's essential message.
2. **One card, one knowledge point** - if a card needs "and" to describe its idea,
   split it; if two cards teach the same thing, merge them.
3. **Delete duplication** - no two cards may cover the same point; drop repeated
   content inside the source.
4. **No fabrication** - every statement must be traceable to the source. Do not add
   outside facts, numbers, opinions, "obvious" extensions, or invented examples. If the
   source is vague, stay vague instead of filling gaps.
5. **Quantity follows content** - 5-8 when the material supports it, fewer when it
   does not, and never force the range.

## Output Format

Use this exact structure so results stay predictable:

```markdown
## 知识卡片：<一句话概括文章主题>

### 卡片 1：<标题>
- **核心知识**：<一句话>
- **简明解释**：<2-4 句>
- **例子 / 自测问题**：<二选一>

### 卡片 2：<标题>
...

### 卡片 3：<标题>
...
```

When the source supports fewer than 5 points, add one line right after the heading,
for example: `> 原文信息不足以支撑 5 张卡片，以下为 3 张核心卡片。`

See `references/card-format.md` for field-level detail, good vs. poor examples, and
title-writing guidance. See `references/examples.md` for complete input/output pairs
across several article types.

## Quality Checklist

Before returning the cards, verify every item:

- [ ] Card count is 5-8, or fewer with an explicit note explaining why.
- [ ] Every card has a title, core knowledge, explanation, and one example or self-test.
- [ ] Each card covers exactly one knowledge point; no two cards overlap.
- [ ] Nothing appears that cannot be traced back to the source.
- [ ] Titles are specific and searchable, not generic placeholders.
- [ ] Cards are written in the source's language.

## Resources

### references/

- `references/card-format.md` - Field definitions, title guidance, and good vs. poor
  card examples. Consult when a card feels weak or the format is unclear.
- `references/examples.md` - Full input/output examples for different article types,
  including a short-input case that demonstrates the reduced-count rule.
