# 7. Error Handling

- Error handling is important, but if it obscures logic it's wrong.
- Use exceptions, not return codes/flags; separate the algorithm from error handling.
- Write the try-catch-finally first: the try block is a transaction; the catch must leave the program consistent. Test-drive with tests that force exceptions.
- Prefer unchecked exceptions: checked exceptions cascade signature changes up the call chain, breaking encapsulation (OCP violation); their costs outweigh benefits outside critical libraries.
- Provide context: message states the failed operation and type of failure.
- Define exception classes by how callers catch them; wrapping third-party APIs and translating to a single exception type is best practice (minimizes dependency, eases mocking, decouples from vendor).
- Define the normal flow: Special Case pattern (e.g. `PerDiemMealExpenses`) so client code needs no exceptional branches.
- Don't return null - return special-case objects or `Collections.emptyList()`; one missing null check spins an app out of control.
- Don't pass null unless the API demands it; forbid it by default.
