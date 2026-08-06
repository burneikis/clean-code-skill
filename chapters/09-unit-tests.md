# 9. Unit Tests

- Three Laws of TDD: no production code without a failing test; no more test than suffices to fail (compile failure counts); no more production code than suffices to pass. A ~30-second cycle.
- Dirty tests are equivalent to (or worse than) no tests: they rot, get expensive, get discarded, and then the production code rots. Test code is as important as production code.
- Tests enable the -ilities: with tests, fear of change disappears and you can improve architecture; without them every change is a possible bug.
- Clean tests = readability: clarity, simplicity, density of expression. Build-Operate-Check structure; hide irrelevant detail behind a domain-specific testing API that evolves via refactoring.
- Dual standard: test code can sacrifice efficiency (memory/CPU) - never cleanliness.
- Minimize asserts per test and test one concept per test function (given-when-then naming helps).
- F.I.R.S.T.: Fast, Independent, Repeatable (any environment), Self-validating (boolean pass/fail), Timely (written just before the production code).
