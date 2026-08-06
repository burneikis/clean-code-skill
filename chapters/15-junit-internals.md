# 15. JUnit Internals

- Case study: Boy Scout Rule applied to excellent, 100%-covered code (`ComparisonCompactor`).
- Improvements made: remove scope-prefix encodings (`f`); encapsulate conditionals in explaining methods; prefer positive conditionals; rename functions whose names hide side effects (`compact` -> `formatCompactedComparison`); functions do one thing; consistent conventions; expose hidden temporal couplings structurally; fix misleading 1-based "index" names (use "length"); removing them revealed and killed dead if-statements; end with analysis functions and synthesis functions topologically sorted.
- Refactoring is iterative and full of trial and error; some earlier decisions get reversed. No module is immune from improvement.
