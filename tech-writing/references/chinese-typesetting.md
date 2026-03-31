# Chinese Typesetting Rules

Apply these formatting rules when drafting or revising Chinese-language technical chapters. Rules are adapted from [中文文案排版指北](https://github.com/sparanoid/chinese-copywriting-guidelines) with additions for technical writing.

## Punctuation

- Use full-width Chinese punctuation in Chinese prose: `，` `。` `；` `：` `？` `！` `（` `）` `「` `」` `、`
- Use half-width punctuation inside code blocks, inline code, URLs, and file paths.
- Do not mix half-width commas or periods into Chinese sentences.
- Use `「」` or `""` for quotation marks, not `""`(full-width curly quotes) unless the project has an established convention.
- Inside a complete English sentence embedded in Chinese prose, use half-width punctuation: `乔布斯那句话是怎么说的？「Stay hungry, stay foolish.」` ✓
- Do not repeat punctuation marks for emphasis: `！` not `！！！`, `？` not `？？？`.

## Spacing

- **Add a space between Chinese text and half-width characters** (English words, numbers, inline code):
  - `线程池默认使用 ForkJoinPool 作为 scheduler` ✓
  - `线程池默认使用ForkJoinPool作为scheduler` ✗
- **No space between Chinese text and full-width punctuation:**
  - `虚拟线程在阻塞时会 unmount，释放 carrier thread。` ✓
  - `虚拟线程在阻塞时会 unmount ，释放 carrier thread 。` ✗
- **Add a space between Chinese text and markdown links:**
  - `详见 [volatile 的语义与边界](#volatile-的语义与边界) 一节` ✓
  - `详见[volatile 的语义与边界](#volatile-的语义与边界)一节` ✗
- **No space inside inline code backticks:**
  - `` `Thread.sleep()` `` ✓
  - `` ` Thread.sleep() ` `` ✗

## Inline Code

- Use backtick inline code for: class names, method names, field names, annotation names, command-line flags, file names, and literal values.
- Do not use inline code for general English technical terms that are used as natural-language concepts (e.g., "线程池" not `` `线程池` ``, "happens-before" not `` `happens-before` `` unless referring to the specific JMM rule).
- When an English term appears for the first time alongside its Chinese translation, prefer the form: `中文术语（English Term）`.

## Headings

- Headings use Chinese where natural; English terms that have no standard Chinese translation may remain in English.
- Do not add punctuation at the end of headings.
- Keep headings concise — they are navigation aids, not sentences.

## Lists and Tables

- Use consistent list markers within the same level (all `- ` or all `1. `).
- Table cells should be concise. If a cell needs more than one sentence, consider whether the content belongs in a table at all.
- Align table columns for readability in source markdown (optional but preferred).

## Blockquotes

- Use `>` blockquotes for **supplementary remarks, caveats, or tangential context** that is useful but not part of the main narrative flow. Typical uses: implementation caveats, version notes, historical background, "note" / "tip" style asides, or brief comparisons with related concepts.
- Do not use blockquotes for core content that the reader must understand to follow the chapter. If removing the blockquote would leave a gap in the argument, the content belongs in the main text.
- Do not use blockquotes as a substitute for proper sectioning. If a blockquote grows beyond 3–4 sentences, consider whether it should be its own section or a dedicated aside.
- Keep blockquote content concise. A blockquote that is longer than the surrounding paragraph draws disproportionate attention.

## Code Blocks

- Always specify a language identifier after the opening fence: ` ```java `, ` ```text `, etc.
- Annotate code blocks with comments only where the logic is non-obvious; do not narrate every line.
- Keep code examples focused on the point being made. Trim imports, boilerplate, and unrelated setup unless they are part of the lesson.

## Proper Nouns

- Use the official capitalization of product and project names: `GitHub` not `github` / `Github`, `TypeScript` not `Ts` / `typescript`.
- Do not use informal or non-standard abbreviations: `JavaScript` not `JS`（unless the abbreviation is universally understood in context, e.g., `JVM`, `CPU`）.

## Numbers and Units

- Use half-width Arabic numerals: `8 个线程`, not `八个线程` (unless the number is part of an idiomatic expression).
- Add a space between the number and the unit or measure word: `8 个`, `64 KB`, `100 ms`.

## Common Mistakes

| Mistake | Correction |
|---------|------------|
| Missing space between Chinese and English/numbers | Always add one half-width space |
| Half-width comma in Chinese sentence | Use full-width `，` |
| Space before full-width punctuation | No space before `，` `。` `；` etc. |
| Inline code around Chinese terms | Only use backticks for actual code identifiers |
| Language identifier missing on code fences | Always specify: ` ```java `, ` ```bash `, etc. |
| Full-width parentheses around code identifiers | Use half-width: `Thread.sleep()`，not `Thread.sleep（）` |
| Repeated punctuation for emphasis (`！！！`) | Use a single mark: `！` |
| Half-width punctuation inside embedded English sentence | Keep half-width: `Stay hungry, stay foolish.` |
| Wrong capitalization of proper nouns (`github`) | Use official form: `GitHub` |
| No space around markdown links in Chinese text | Add one space on each side |
