# clean-code skill

An agent skill that gives a coding assistant the contents of *Clean Code* (Robert C. Martin), distilled chapter by chapter.

## What is in here

- `SKILL.md` - the entry point. Holds the always-on core rules and a routing table that tells the agent which chapter to read for the task at hand.
- `chapters/` - 17 markdown files, one per chapter of the book, condensed to the actionable rules, examples and heuristics.

## How it is used

The agent loads `SKILL.md` when a task involves writing, refactoring or reviewing code. It then reads only the chapters relevant to that task, for example `03-functions.md` when splitting a long function, or `17-smells.md` for a code review checklist.

## Install

Copy or symlink the directory into your agent skills folder:

```sh
git clone <this-repo> ~/.pi/agent/skills/clean-code
```

## Credit

All ideas come from *Clean Code: A Handbook of Agile Software Craftsmanship* by Robert C. Martin. These notes are a summary for reference, not a replacement for the book.
