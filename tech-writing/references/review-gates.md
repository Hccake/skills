# Review Gates

Run through these gates before claiming an article is complete. Each gate is a pass/fail check — if any gate fails, revise before finalizing.

## Gate 1: Structural Integrity

- [ ] The opening matches the article's actual teaching job (not a leftover from an earlier draft or a default template).
- [ ] The opening directly engages the reader with a claim, question, scenario, correction, or decision frame — not a content-preview list ("this article covers A, B, C").
- [ ] The material under the H1 is either a short orienting lead (1–3 sentences) or a true first numbered section. No pseudo-numbered prefaces or "Section 0".
- [ ] Section order follows reader learning order: concepts appear before they are used in reasoning.
- [ ] Each section has a distinct teaching purpose that can be stated in one sentence. No section exists solely to "be complete".
- [ ] No section could be deleted without the reader losing something they need for a later section or the conclusion.

## Gate 2: Narrative Coherence

- [ ] Every new concept, term, or data structure is **motivated before named**: the reader understands *why it is needed* before encountering *what it is*.
- [ ] Each non-trivial section has an internal narrative arc (e.g., problem → idea → evidence → implication), not a flat list of knowledge points.
- [ ] Adjacent sections have a logical connection: the conclusion or question raised by one section leads into the next.
- [ ] The reader can answer "why am I reading this paragraph?" at every point in the article. If a passage feels like a detour, it either needs a bridge sentence or should be relocated/removed.
- [ ] No term, structure, or mechanism appears "out of nowhere" — if the reader would say "wait, what is this?", the introduction is missing or misplaced.

## Gate 3: Evidence and Claims

- [ ] Every major conclusion is backed by at least one piece of evidence (spec fact, implementation fact, experiment, or traced behavior).
- [ ] Claims derived from inference are explicitly labeled as such ("based on this, we can infer..." or equivalent).
- [ ] Specification facts and implementation facts are not conflated. If the spec says one thing and the implementation does another, the disagreement is stated.
- [ ] Version-sensitive conclusions are scoped: the version or implementation baseline is stated near the claim, not only in the content contract.
- [ ] No claim overreaches its evidence. Watch for: universal quantifiers ("all", "always", "never") applied to observations from a single version or implementation.

## Gate 4: Depth

- [ ] The depth of every core knowledge point matches the depth level declared in the content contract.
- [ ] At source-code level: key mechanisms are backed by actual annotated source code, not just prose descriptions of what the code does.
- [ ] At principle level: every "how it works" explanation includes the design rationale ("why it works this way").
- [ ] No core knowledge point stops at "what" without reaching the declared depth. If the article says it will explain a mechanism at source-code level, a hand-wavy summary is a gate failure.

## Gate 5: Code and Assets

- [ ] Every code block supports a specific insight or proves a specific point. No code exists for bulk or decoration.
- [ ] Code examples are trimmed to the relevant logic. Imports, boilerplate, and unrelated setup are removed unless they are part of the lesson.
- [ ] Inline comments in code explain non-obvious logic only. No narration of self-evident lines.
- [ ] For source walkthroughs: code is interleaved with prose, not dumped in a wall followed by a wall of explanation.
- [ ] For source walkthroughs: class structure (key fields and their roles) is shown before method walkthroughs.
- [ ] For source walkthroughs: the conclusion or design decision is stated *before* the code block, so the reader knows what to look for.
- [ ] Tables are used for structured comparison, boundary summaries, or trade-off analysis — not for reformatting prose.
- [ ] Diagrams and figures have a clear purpose that text alone cannot achieve as efficiently.
- [ ] Code fences have a language identifier.

## Gate 6: Prose Quality

- [ ] The prose reads like a professional technical book: precise, restrained, explanatory, evidence-led.
- [ ] No AI-flavored patterns. Check for all of the following:
  - Empty transitions: "Let's now look at...", "接下来我们来看..."
  - Padded summaries and motivational filler: "This is a very important concept..."
  - Self-referential framing: "本篇建立了...", "本文将从...角度分析...", "In this article, we explained..."
  - Content-preview sentences that restate the table of contents: "这条路径可以分为三个阶段：发送、存储、消费"
  - Structure plan leakage: sentences that read like section job descriptions rather than direct content
  - Series navigation disguised as content: "详见第 N 篇" blockquotes, "系列对应篇目" table columns, opening paragraphs that preview the next article
  - Series meta-commentary: "贯穿本系列所有篇目", "是理解后续 N 篇的基础"
  - Formulaic symmetry across articles: if this article is part of a series, check whether its section structures, table formats, or paragraph patterns are identical to a sibling article
- [ ] No content-preview openings that restate the table of contents as prose.
- [ ] Terminology is consistent throughout the article. The same concept uses the same term everywhere.
- [ ] Quantifiers ("等", "etc.", "and so on"), negations ("除非", "unless"), and scope words ("所有", "仅") match the actual scope of the claim.
- [ ] Each knowledge point (rule, caveat, definition, mechanism detail) has exactly one authoritative explanation in the article. Other mentions cross-reference it rather than restating it in full.

## Gate 6b: Sentence-Level Clarity (Chinese)

- [ ] Every sentence has an unambiguous subject and object — the reader can answer "who does what to what" without guessing.
- [ ] Parenthetical clarifications do not contradict the main clause they are attached to.
- [ ] Demonstratives and reference words ("期间", "其中", "这", "该") have a clear, unambiguous antecedent in the immediately preceding context.
- [ ] Modifier chains follow natural Chinese order (general → specific, large scope → small scope). Multi-layer attributives read smoothly without backtracking.
- [ ] No double-"被" constructions in the same clause (e.g., "被获取时被撤销" → rephrase to use at most one passive marker).
- [ ] Content (code blocks, examples, remarks) is placed under the section heading that matches its topic. A code block about locking must not appear under an "unlocking" heading, etc.

## Gate 7: Formatting (Chinese)

- [ ] Full-width punctuation in Chinese prose; half-width in code and paths.
- [ ] Space between Chinese text and half-width characters (English, numbers, inline code).
- [ ] No space between Chinese text and full-width punctuation.
- [ ] Inline code backticks only around actual code identifiers, not around Chinese terms or general English concepts.
- [ ] Numbers use half-width Arabic numerals with a space before the unit or measure word.

## Gate 8: Completeness

- [ ] The article ends with a References section (or equivalent local-language heading) listing the authoritative sources actually used.
- [ ] Non-goals stated in the content contract are not accidentally covered in the draft.
- [ ] The article does not introduce concepts that belong in a different article of the series without a clear justification.
- [ ] If a recap/summary section exists, it synthesizes or compares — it does not merely repeat what was already said.

## How to Use

1. Read through all gates sequentially after completing the draft.
2. **Output results explicitly**: list every gate with pass/fail status. For each failure, note the specific location in the article and the fix needed. Do not claim "all gates pass" without showing the per-gate results — silent review is not review.
3. Apply fixes, then re-run only the failing gates and report again.
4. Only mark the article as complete when all gates pass.

An article that passes all gates may still need revision based on user feedback — these gates catch craft and evidence problems, not requirements misalignment.
