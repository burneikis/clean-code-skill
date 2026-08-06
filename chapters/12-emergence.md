# 12. Emergence

Kent Beck's four rules of Simple Design (in priority order) let clean design emerge:

1. **Runs all the tests.** Unverifiable systems shouldn't ship. Making a system testable drives small SRP classes, low coupling (DIP, DI), high cohesion. Writing tests leads to better designs.
2. **Contains no duplication** (applied during continuous refactoring). Duplication of code, implementation (`isEmpty` vs `size`), or intent; extract even a few common lines - "reuse in the small" drives reuse in the large; use Template Method for higher-level duplication.
3. **Expresses the programmer's intent**: good names, small functions/classes, standard pattern nomenclature (Command, Visitor), expressive tests as documentation. The most important way is to *try* - take pride; care is a precious resource.
4. **Minimizes classes and methods**: don't be dogmatic (interface-per-class, data/behavior class splits); keep counts low - but this is the lowest priority rule.
