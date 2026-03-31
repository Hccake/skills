# Chapter Archetypes

Use this reference when selecting a chapter type and opening strategy in Step 3 of the authoring workflow.

## Chapter Types

| Type | Teaching Job | Typical Structure |
|------|-------------|-------------------|
| **Mechanism** | Explain how something works internally | Problem/motivation → core model → detailed walkthrough → boundary conditions → summary |
| **Concept** | Build a mental model for an abstract idea | Anchoring example → definition → properties/rules → counterexamples → implications |
| **Comparison** | Help the reader choose between alternatives | Decision frame → candidates → dimension-by-dimension analysis → decision table → guidance |
| **Source walkthrough** | Guide the reader through implementation code | Entry point → class structure → key data structures → critical code paths → design trade-offs |
| **Troubleshooting** | Diagnose and resolve a category of problems | Symptom → root cause model → diagnostic steps → resolution patterns → prevention |
| **Practice / Case study** | Apply multiple concepts to a concrete problem | Problem setup → constraints → solution design → implementation → evaluation |

A chapter may blend types — a mechanism chapter might include a comparison section, or a concept chapter might end with a troubleshooting sidebar. The primary type determines the spine; secondary types appear as sections within it.

## Source Walkthrough: Expanded Guidance

Source walkthroughs are among the most demanding chapter types. The core challenge is turning a linear code path into a teachable narrative.

### Structure Pattern

1. **Entry point and motivation**: start from the public API or the scenario that triggers the code path. The reader should understand *what problem this code solves* before seeing any implementation.
2. **Class structure overview**: show key fields and their roles before walking through methods. The reader needs to know what state a method operates on before reading the method.
3. **Core code path**: walk through the primary execution flow. Break long methods into fragments, interleaving each fragment with prose that explains the design decision it embodies.
4. **Branch and edge cases**: after the main path is clear, cover secondary paths (error handling, fallback logic, race conditions) that reveal design trade-offs.
5. **Design trade-offs**: close with why the code is designed this way — what alternatives were considered, what constraints drove the design.

### Common Pitfalls

| Pitfall | Fix |
|---------|-----|
| Showing the full method before explaining anything | State the conclusion first: "This method does X by Y. Here is how:" |
| Showing every line of a long method | Trim to the lines that support the current point; mark omissions |
| Narrating syntax instead of decisions | Comments should answer "why this design?" not "what does this line do?" |
| Dumping all code first, then all explanation after | Interleave: code fragment → prose → code fragment → prose |
| Walking through methods before showing fields | Show class structure (fields and their roles) first, then methods |
| No motivation before the code | Start from the problem or API that triggers this code path |

## Opening Strategies

### Conclusion-first

State the core takeaway up front, then unpack the reasoning.

**Use when:**
- The mechanism is complex and the reader needs a mental anchor before diving into details
- The chapter establishes a definition or model that subsequent sections build on
- The reader's primary question is "what is X?" rather than "why does X matter?"

**Do not use when:**
- The conclusion only makes sense after the reader has seen the evidence
- The opening would require so many qualifications that it loses its anchoring power

**Example:** "AQS is a FIFO-queue-based synchronizer skeleton that manages shared state through a single `int` field and a CLH wait queue."

### Question-first

Open with the specific question the chapter answers.

**Use when:**
- The reader arrives with a concrete, well-formed confusion
- The question itself frames the scope naturally
- The chapter has a single dominant question (not a survey of loosely related topics)

**Do not use when:**
- The question is too broad to anchor the reader ("How does concurrency work?")
- The chapter's job is to build a new mental model, not answer an existing question
- Every chapter in the series already uses this strategy — monotony erodes engagement

**Example:** "Why can one thread write a field and another thread read a stale value, even on a single-socket machine?"

### Scenario-first

Open with a concrete situation — a bug, a production incident, a code snippet that behaves unexpectedly.

**Use when:**
- The concept is best understood through its consequences
- A real or realistic scenario immediately demonstrates why the topic matters
- The reader's motivation needs to be established before abstract explanation

**Do not use when:**
- The scenario requires so much setup that it delays the actual teaching
- The chapter's core job is definitional, not experiential
- The scenario is contrived or would not resonate with the target reader

**Example:** "A `SimpleDateFormat` shared across threads intermittently produces corrupted date strings — sometimes `2024-13-32`, sometimes an `ArrayIndexOutOfBoundsException`."

### Misconception-first

Open by stating a common wrong belief, then correct it.

**Use when:**
- The target reader demonstrably holds a specific false mental model
- Correcting the misconception is the chapter's primary teaching job
- The wrong belief is precise enough to state in one sentence

**Do not use when:**
- The "misconception" is really just ignorance (the reader has no prior model, not a wrong one)
- The correction requires extensive background before the reader can understand why it's wrong
- You are manufacturing a strawman to make the opening dramatic

**Example:** "A common claim is that `volatile` guarantees atomicity. It does not — it guarantees visibility and ordering, nothing more."

### Comparison-first

Open with the decision the reader faces.

**Use when:**
- The chapter's primary job is to help the reader choose between alternatives
- The alternatives are already known to the reader (at least by name)
- The decision has practical consequences that the reader cares about

**Do not use when:**
- The reader doesn't yet understand any of the alternatives well enough to compare them
- The chapter needs to teach one mechanism in depth before comparison is meaningful

**Example:** "`synchronized` and `ReentrantLock` both provide mutual exclusion. When should you reach for one over the other?"

## Selection Rules

1. **Match the opening to the chapter's teaching job**, not to a habit or a series-wide default.
2. **Vary openings across a series.** If you can confirm that adjacent chapters in the series use the same opening strategy, choose a different one for the current chapter even if the same strategy technically fits. Monotony signals formula, not craft. If series context is unavailable, choose the strategy that best fits the current chapter's teaching job without worrying about repetition.
3. **State your reasoning.** In the Structure Plan, write one sentence explaining why you chose this strategy and why the most obvious alternative was rejected.
4. **The opening must earn the first 30 seconds.** If the reader could skip the opening and lose nothing, the opening is filler.

## Misuse Patterns

| Pattern | Problem | Fix |
|---------|---------|-----|
| Every chapter opens with a question | Series feels formulaic; questions become performative | Rotate strategies; use question-first only when the reader genuinely arrives with that question |
| Scenario-first with a contrived example | Reader senses the scenario exists to justify the chapter, not to teach | Use a scenario the target reader would actually encounter; if none exists, choose a different strategy |
| Misconception-first without evidence the misconception is real | Feels like a strawman attack | Only use when the misconception is documented (Stack Overflow, common interview answers, textbook errors) |
| Conclusion-first but the conclusion is a tautology | "Thread pools manage a pool of threads" teaches nothing | The conclusion must be non-obvious or synthesize multiple ideas |
| Comparison-first before the reader knows the candidates | Reader cannot evaluate the comparison | Teach the mechanisms first (possibly in earlier chapters), then compare |
| Content-preview list disguised as an opening | "This chapter covers A, B, C, D, and E" is a table of contents, not an opening | Replace with a direct claim, question, or scenario that pulls the reader into the content |
