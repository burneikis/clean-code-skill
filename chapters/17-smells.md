# 17. Smells and Heuristics (review checklist)

## How to use this file

This list is an index, not the argument. It tells you *that* something smells,
not *why* or *how to fix it*.

Workflow, per review:
1. Scan the checklist, note the codes that fire.
2. Group the codes by their chapter (column below).
3. **Read each of those chapters before writing the review.** A finding you
   cannot back with the chapter's reasoning is not a finding yet - drop it or
   go read.
4. Cite in the review as `G30 (ch.03)` so the source is checkable.

| Codes | Read before reporting |
| --- | --- |
| C1-C5 | `04-comments.md` |
| E1-E2 | `09-unit-tests.md`, `11-systems.md` |
| F1-F4 | `03-functions.md` |
| G1-G12, G16, G19-G21, G24-G26 | `02-naming.md`, `03-functions.md`, `12-emergence.md` |
| G13-G15, G17-G18, G22-G23, G27-G36 | `06-objects-and-data.md`, `10-classes.md`, `03-functions.md` |
| J1-J3 | `06-objects-and-data.md`, `08-boundaries.md` |
| N1-N7 | `02-naming.md` |
| T1-T9 | `09-unit-tests.md` |

Rule of thumb: 3+ codes from one chapter means the real problem is that
chapter's topic - read it in full and review at that level, not smell by smell.

### Comments (-> `04-comments.md`)
- **C1** Inappropriate info (change histories, metadata belonging in other systems).
- **C2** Obsolete comment - update or delete; they drift from the code.
- **C3** Redundant comment (`i++; // increment i`, javadocs restating signatures).
- **C4** Poorly written comment - if worth writing, write it well and briefly.
- **C5** Commented-out code - delete on sight.

### Environment (-> `11-systems.md`, `09-unit-tests.md`)
- **E1** Build requires more than one step - one command to check out and build.
- **E2** Tests require more than one step - one command or one IDE click.

### Functions (-> `03-functions.md`)
- **F1** Too many arguments (0-3; more needs prejudice against it).
- **F2** Output arguments - change the state of the owning object instead.
- **F3** Flag arguments - the function does more than one thing.
- **F4** Dead function - delete; version control remembers.

### General (-> `03-functions.md`, `06-objects-and-data.md`, `10-classes.md`, `12-emergence.md`)
- **G1** Multiple languages in one source file - minimize number and extent.
- **G2** Obvious behavior unimplemented (principle of least surprise; readers lose trust).
- **G3** Incorrect behavior at boundaries - don't trust intuition; test every corner case.
- **G4** Overridden safeties (silenced warnings, ignored failing tests) - like free credit-card money.
- **G5** Duplication - every instance is a missed abstraction; identical code -> methods; repeated switch/if-else chains -> polymorphism; similar algorithms -> Template Method/Strategy.
- **G6** Code at wrong level of abstraction - lower-level detail in base classes/higher modules (`percentFull` on a general Stack); you can't fake your way out of a misplaced abstraction.
- **G7** Base classes depending on their derivatives - deploy bases independently.
- **G8** Too much information - small tight interfaces; hide data, utilities, constants, temporaries; low coupling.
- **G9** Dead code - unreachable branches, uncalled utilities; give it a decent burial.
- **G10** Vertical separation - define variables/functions near first use.
- **G11** Inconsistency - do similar things the same way (names, conventions).
- **G12** Clutter - empty constructors, unused variables, meaningless artifacts.
- **G13** Artificial coupling - general enums/statics stuck inside specific classes for convenience.
- **G14** Feature envy - a method manipulating another object's data via accessors belongs in that class (occasionally a necessary evil, e.g. report formatting).
- **G15** Selector arguments (boolean/enum/int selecting behavior) - split into functions.
- **G16** Obscured intent - run-on expressions, Hungarian, magic numbers.
- **G17** Misplaced responsibility - put code where a reader would naturally expect it (`PI` with the trig functions); function names should settle it.
- **G18** Inappropriate static - prefer instance methods; only make static when polymorphism will never be wanted (`Math.max` yes, `calculatePay` no).
- **G19** Use explanatory variables - break calculations into named intermediates; hard to overdo.
- **G20** Function names should say what they do (`date.add(5)` - days? mutating?) - if you must read the body, rename.
- **G21** Understand the algorithm - don't stop at "passes the tests"; know *why* it's correct, often by refactoring until it's obvious.
- **G22** Make logical dependencies physical - the depender should explicitly ask (e.g. `getMaxPageSize()`) instead of assuming (a `PAGE_SIZE` constant).
- **G23** Prefer polymorphism to if/else or switch/case - "ONE SWITCH" rule: at most one switch per selection type, creating polymorphic objects.
- **G24** Follow standard conventions, team-agreed; the code itself is the standards document.
- **G25** Replace magic numbers (and tokens like `"John Doe"`) with named constants - except truly self-evident ones in evident context.
- **G26** Be precise: check nulls you invited, first-match assumptions, currency as floats, missing locks, over/under-constrained types. Ambiguity is disagreement or laziness.
- **G27** Structure over convention - abstract methods force compliance; naming conventions don't.
- **G28** Encapsulate conditionals - `if (shouldBeDeleted(timer))` over compound boolean logic.
- **G29** Avoid negative conditionals - `if (buffer.shouldCompact())`.
- **G30** Functions should do one thing - split multi-step functions (loop/check/pay -> three functions).
- **G31** Hidden temporal couplings - make ordering structural (bucket brigade: each function's result feeds the next).
- **G32** Don't be arbitrary - structure by communicated rationale, or others will change it; don't nest public classes in unrelated scopes.
- **G33** Encapsulate boundary conditions - name things like `nextLevel = level + 1` once, don't scatter +1/-1.
- **G34** Functions should descend only one level of abstraction below their name (mixing HTML syntax with rule-size logic); breaking along abstraction lines reveals further lines.
- **G35** Keep configurable data (defaults, constants) at high levels and pass it down; low levels don't own those values.
- **G36** Avoid transitive navigation (`a.getB().getC()`) - Law of Demeter / shy code; immediate collaborators should offer what you need, or architecture goes rigid.

### Java (-> `06-objects-and-data.md`, `08-boundaries.md`) (mostly generalizable)
- **J1** Avoid long import lists - wildcard-import a package you use 2+ classes from; wildcards aren't hard dependencies.
- **J2** Don't inherit constants from interfaces/base classes - it hides their origin; use static import.
- **J3** Constants versus enums - use enums; they're named, checked, and can carry methods and fields.

### Names (-> `02-naming.md`)
- **N1** Choose descriptive names - 90% of readability; reevaluate as meaning drifts; good names overload structure with description.
- **N2** Names at the appropriate level of abstraction (`connect(connectionLocator)`, not `dial(phoneNumber)` on a general Modem).
- **N3** Use standard nomenclature where possible - pattern names (Decorator), conventions (toString), the project's ubiquitous language.
- **N4** Unambiguous names - `renamePageAndOptionallyAllReferences` beats a vague `doRename`; length is justified by explanatory value.
- **N5** Long names for long scopes; `i` is fine for five lines.
- **N6** Avoid encodings - no type/scope prefixes (`m_`, `f`, `vis_`).
- **N7** Names should describe side effects - `createOrReturnOos`, not `getOos`.

### Tests (-> `09-unit-tests.md`)
- **T1** Insufficient tests - test everything that could possibly break.
- **T2** Use a coverage tool - makes gaps obvious.
- **T3** Don't skip trivial tests - documentary value exceeds cost.
- **T4** An ignored test is a question about an ambiguity in requirements.
- **T5** Test boundary conditions - we get the middle right and misjudge the edges.
- **T6** Exhaustively test near bugs - bugs congregate.
- **T7** Patterns of failure are revealing - complete, ordered test cases expose diagnoses.
- **T8** Test coverage patterns are revealing - what executed vs. not explains failures.
- **T9** Tests should be fast - slow tests get dropped.

Heuristics aren't a rulebook: clean code comes from a value system and the
discipline (and care) to apply it continuously.
