# 8. Boundaries

- Provider/user tension: providers want broad interfaces, users want focused ones.
- Don't pass boundary interfaces (like `Map`) around the system or return them from public APIs; keep them inside the class (family) that uses them, wrapped in a tailored interface (`Sensors.getById`).
- Learning tests: explore a third-party API with tests instead of experimenting in production code. Better than free: they pin down your understanding and flag behavioral changes on library upgrades.
- Code that doesn't exist yet: define the interface you wish you had, work against it, add an Adapter when the real API arrives; this also creates testing seams.
- Manage boundaries with very few places referring to them - depend on what you control.
