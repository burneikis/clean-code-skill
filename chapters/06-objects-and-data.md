# 6. Objects and Data Structures

- Hiding implementation is about abstraction, not getters/setters - express data in abstract terms (`getPercentFuelRemaining()` vs tank capacity accessors). Blithely adding getters/setters is the worst option.
- Anti-symmetry: objects hide data behind abstractions and expose behavior; data structures expose data and have no significant behavior. Procedural code makes new functions easy and new types hard; OO the reverse. Choose per need - "everything is an object" is a myth.
- Law of Demeter: method `f` of class `C` may call methods of `C`, objects `f` creates, arguments of `f`, and instance variables of `C`. Talk to friends, not strangers. Avoid train wrecks (`a.getB().getC().doX()`) on objects (irrelevant for pure data structures).
- If it's an object, tell it to do something (`ctxt.createScratchFileStream(name)`), don't ask about its internals.
- Avoid hybrids (half object, half data structure) - worst of both worlds.
- DTOs (public data, no functions) are useful at DB/socket boundaries. Active Records are DTOs with `save`/`find`; don't put business rules in them - wrap them in objects that hide the data.
