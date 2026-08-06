---
name: clean-code
description: "Clean Code (Robert C. Martin) distilled chapter by chapter. Use when writing, refactoring, or reviewing code and you need concrete guidance on naming, function design, comments, formatting, error handling, class design, tests, or code smells."
---

# clean-code

## Core rules (apply always)

- Small functions that do one thing, at one level of abstraction.
- Intention-revealing names; if a name needs a comment, the name failed.
- Prefer 0-2 arguments. No flag arguments. No output arguments.
- Command-Query Separation: do something or answer something, never both.
- Comments compensate for failure to express intent in code.
- No duplication.
- Boy Scout Rule: leave code cleaner than you found it.

## Chapters

Read from `{baseDir}/chapters/`:

| File | Read it when |
| --- | --- |
| `01-clean-code.md` | Arguing about code quality, tech debt, rewrites |
| `02-naming.md` | Naming variables, functions, classes, modules |
| `03-functions.md` | Writing or splitting functions; argument lists; switch statements |
| `04-comments.md` | Adding or reviewing comments and docstrings |
| `05-formatting.md` | File/line length, vertical ordering, whitespace |
| `06-objects-and-data.md` | Object vs data structure, Law of Demeter, DTOs, getters/setters |
| `07-error-handling.md` | Exceptions, error codes, null handling, special cases |
| `08-boundaries.md` | Wrapping third-party APIs, learning tests, undefined interfaces |
| `09-unit-tests.md` | Writing tests, TDD, test readability, F.I.R.S.T. |
| `10-classes.md` | Class size, SRP, cohesion, dependency inversion, OCP |
| `11-systems.md` | Construction vs use, DI, AOP, scaling architecture |
| `12-emergence.md` | The four rules of simple design |
| `13-concurrency.md` | Threads, shared state, concurrency defense principles |
| `14-successive-refinement.md` | Case study: refining a messy working program |
| `15-junit-internals.md` | Case study: critiquing already-good code |
| `16-serialdate.md` | Case study: full refactor of a real class |
| `17-smells.md` | **Code review.** Full smells and heuristics checklist (C/E/F/G/J/N/T codes) |

For any code review, read `17-smells.md` first.
