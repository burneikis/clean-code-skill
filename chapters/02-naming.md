# 2. Meaningful Names

- Use intention-revealing names: the name answers why it exists, what it does, how it's used. If a name needs a comment, the name failed (`int d; // elapsed days` -> `elapsedTimeInDays`).
- Avoid disinformation: don't say `accountList` unless it's a List; avoid names differing in tiny ways; never lowercase-L or uppercase-O as names.
- Make meaningful distinctions: no number series (`a1, a2`), no noise words (`Info`, `Data`, `theX`, `NameString`, `CustomerObject`).
- Use pronounceable names (`generationTimestamp`, not `genymdhms`) and searchable names. Name length should match scope size; single letters only in tiny scopes.
- Avoid encodings: no Hungarian notation, no `m_` prefixes, no `I` on interfaces (encode the implementation, `ShapeFactoryImp`, if you must).
- Avoid mental mapping; clarity is king.
- Classes: noun phrases (avoid `Manager`, `Processor`, `Data`, `Info`). Methods: verb phrases; accessors/mutators/predicates get `get`/`set`/`is`. Prefer named static factory methods over overloaded constructors.
- Don't be cute or punny. Pick one word per concept (`fetch` vs `get` vs `retrieve` - pick one) and don't use one word for two meanings (`add` vs `insert`/`append`).
- Use solution-domain names (CS/pattern terms) for technical things, problem-domain names otherwise.
- Add context via classes/functions/namespaces (an `Address` class beats `addr` prefixes); don't add gratuitous context (no app-prefix on every class).
