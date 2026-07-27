# Markdown Cheatsheet

---

## Text Formatting
| Syntax              | Output            |
| ------------------- | ----------------- |
| `**bold**`          | **bold**          |
| `*italic*`          | *italic*          |
| `~~strikethrough~~` | ~~strikethrough~~ |
| highlight           | ==highlight==     |
| `**_bold italic_**` | ***bold italic*** |
| `` `inline code` `` | `inline code`     |

---

## Headings
```
# H1   ## H2   ### H3   #### H4
```

---

## Lists
```
- Unordered item        1. Ordered item
  - Nested item            2. Second item
    - Deep nested              - Mixed nested

- [ ] Unchecked task
- [x] Checked task
```

---

## Links & Images
```
[Link text](https://url.com)
[[Internal note link]]
[[Note|Custom alias]]
![[Embedded note or image]]
![Alt text](image.png)
```

---

## Quotes & Code
```
> Blockquote
>> Nested quote

\`\`\`python
# Fenced code block
print("hello")
\`\`\`
```

---

## Tables
```
| Col 1 | Col 2 |
|-------|-------|
| A     | B     |
```

---

## Obsidian Extras
```
#tag                         → Tag
[[Note]]                     → Internal link
^block-id                    → Block reference
[[Note#Heading]]             → Link to heading
%%comment%%                  → Hidden comment
---                          → Horizontal rule / frontmatter divider
```

---

## Frontmatter (YAML)
```yaml
---
title: My Note
tags: [work, ideas]
date: 2026-05-11
---
```
