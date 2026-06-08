---
name: simplify
description: Review the changed code (the current diff) for reuse, simplification, efficiency, and altitude improvements, then apply the fixes. Use this skill when the user wants to clean up, refine, tidy, or simplify code they just wrote or modified — e.g. "simplify this", "make this cleaner", "reduce the complexity", "refine this implementation". Quality-focused only: it does NOT hunt for correctness bugs (use a code-review skill for that).
---

This skill reviews the code that has changed and applies quality cleanups. It is the
"final polish" pass after code works: it improves structure, clarity, and reuse while
**preserving behavior**. It does not look for correctness bugs, security issues, or
missing tests — pair it with a dedicated code-review skill for those.

## When to use

- After writing or modifying a chunk of code, before committing.
- After a code review has passed and the code works but feels heavier than it should.
- When the user asks to "simplify", "clean up", "tidy", "refine", or "make this clearer".

## What to review

Look only at the changed code (the working-tree diff, or the files the user points at).
Do not rewrite untouched code. Evaluate it along four axes:

1. **Reuse** — Is this reimplementing something the codebase already provides? Prefer an
   existing helper, utility, type, or pattern over a hand-rolled duplicate. Watch for
   copy-pasted blocks that should be factored into one function.
2. **Simplification** — Can the same result be expressed with less? Remove dead code,
   redundant branches, needless intermediate variables, and deep nesting (early returns,
   guard clauses). Collapse over-engineered abstractions that have a single caller.
3. **Efficiency** — Eliminate obviously wasteful work: repeated computation that could be
   hoisted, redundant passes over the same data, unnecessary allocations or network/DB
   round-trips. Do not micro-optimize at the cost of readability or change algorithmic
   behavior speculatively.
4. **Altitude** — Is the code at the right level of abstraction? Flag both over-engineering
   (premature generalization, indirection nobody needs) and under-engineering (a tangle
   that should be one well-named function). Aim for code that reads like the surrounding code.

## Workflow

1. **Identify the diff.** Determine what changed (e.g. `git diff`) or use the files/range
   the user specifies. Scope the review to that.
2. **Read the surrounding context.** Before suggesting reuse or a refactor, confirm the
   helper/pattern you'd reach for actually exists and fits. Match the file's existing
   naming, idiom, and comment density.
3. **Find high-confidence cleanups.** Prefer a few clearly-correct improvements over a
   large speculative rewrite. Each change must keep behavior identical.
4. **Apply the fixes** directly to the working tree (this skill applies changes, it does
   not just suggest them). Keep edits surgical and self-consistent.
5. **Verify nothing broke.** Re-read the result; run the project's tests/linter/build if
   available. Report what you changed and why, grouped by the axis above.

## What this skill does NOT do

- It does not hunt for correctness or security bugs, or write new tests.
- It does not change observable behavior, public APIs, or output (unless the user asks).
- It does not reformat or churn untouched code, and it does not bikeshed style the
  formatter already owns.
- When in doubt about whether a change is purely cosmetic vs. behavior-altering, leave it
  and flag it for the user instead of guessing.
