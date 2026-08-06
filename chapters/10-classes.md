# 10. Classes

- Organization: constants, static vars, instance vars, then public functions with their private utilities just after (stepdown). Keep things private; loosening encapsulation (e.g. protected for tests) is a last resort.
- Classes should be small - measured in responsibilities, not lines. If you can't give it a concise name (beware `Manager`, `Processor`, `Super`) or describe it in ~25 words without "if/and/or/but", it does too much.
- SRP: one, and only one, reason to change. "Working" and "clean" are different activities - don't stop at working. Many small single-purpose classes are well-labeled drawers, not a junk drawer; system complexity is the same, navigability is far better.
- Cohesion: methods should manipulate the class's instance variables. When some variables are shared by only a few methods, a class is trying to get out - split it. Breaking big functions into small ones naturally spawns small cohesive classes (PrintPrimes example).
- Organize for change: the multi-method `Sql` class violates SRP/OCP; a `Sql` base with one subclass per statement lets you add features by adding classes, not modifying existing ones.
- Isolate from change (DIP): depend on abstractions (a `StockExchange` interface) rather than concrete details (`TokyoStockExchange`); this decoupling enables testing and reuse.
