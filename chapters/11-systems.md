# 11. Systems

- Separate constructing a system from using it, like construction vs. use of a building. Lazy-init `getService()` idioms scatter setup, hard-code dependencies, and hurt testing.
- Move construction to `main` (dependencies point one way, away from main), use Abstract Factories when the app controls *when* but not *how*, and use Dependency Injection / IoC so classes are passive and a container wires the graph.
- It's a myth you can get systems right the first time: implement today's stories, then refactor and expand. Software architectures *can* grow incrementally if concerns are separated.
- EJB2 counterexample: business logic tightly coupled to the container - untestable, non-reusable, undermines OO.
- Cross-cutting concerns (persistence, transactions, security, caching, logging) cut across object boundaries: handle them with AOP-like mechanisms (Java proxies, Spring/JBoss-style pure-Java frameworks, AspectJ) so domain logic stays as POJOs, decoupled and test-drivable.
- Optimal architecture: modularized domains of concern in POJOs, integrated with minimally invasive aspect-like tools; test-drive it.
- BDUF is harmful; postpone decisions to the last possible moment for the best information. Use standards only when they add demonstrable value.
- Use DSLs/expressive APIs so code reads at the level of domain concepts.
- Whether system or module: never forget to use the simplest thing that can possibly work.
