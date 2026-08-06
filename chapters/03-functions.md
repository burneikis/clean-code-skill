# 3. Functions

- Small - a few lines. Rarely 20 lines. Blocks in `if`/`else`/`while` should be one line, usually a call. Indent level at most one or two.
- Do one thing: all statements one level of abstraction below the function's name. If you can extract a function whose name is not merely a restatement, it does more than one thing. Sections within a function are a symptom.
- Stepdown Rule: code reads top-down like nested "TO" paragraphs, each function followed by those at the next level.
- Switch statements: tolerate one per selection type, buried in a low-level (abstract factory) class creating polymorphic objects, never repeated.
- Descriptive names: long descriptive beats short enigmatic; be consistent in phrasing across a module.
- Arguments: 0 best, then 1, then 2; 3 needs very special justification; more should not be used. Monadic forms: asking about the arg, transforming it, or an event. Flag arguments are terrible - split the function. Group related args into objects (`makeCircle(Point center, double r)`). Varargs count as one list arg.
- No side effects and no hidden temporal couplings (`checkPassword` must not `Session.initialize()`). Avoid output arguments - change the owning object's state instead.
- Command-Query Separation: do something or answer something, never both (`if (set("username",...))` is the anti-example).
- Prefer exceptions to error codes (error-code enums are dependency magnets). Extract try/catch bodies into functions; if `try` exists it should be the first word, error handling is the function's one thing.
- DRY: duplication may be the root of all evil in software.
- Small functions make structured programming's single entry/exit rules mostly moot; multiple returns are fine, avoid goto.
- Nobody writes functions like this first pass: write it long and messy with tests, then massage and refine.
