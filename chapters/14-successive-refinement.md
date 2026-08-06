# 14. Successive Refinement (Args case study)

- To write clean code, first write dirty code and then clean it - like drafting prose. Leaving a "working" mess is professional suicide.
- Messes build gradually: in Args, adding just two argument types turned a tidy class into a festering pile. When you see the structure degrading, stop adding features and refactor first.
- Use TDD to keep the system running at all times: many tiny changes, tests passing after each, never broken for long. Sometimes you add scaffolding just to remove it later; refactoring is like a Rubik's cube - many small steps, each enabling the next.
- Much of good design is partitioning - creating appropriate places for different kinds of code (Args vs ArgsException vs one file per marshaler).
- Bad code rots and ferments into a weight that drags the team down; keeping code clean continuously is cheap, cleaning it later is expensive. Never let the rot start.
