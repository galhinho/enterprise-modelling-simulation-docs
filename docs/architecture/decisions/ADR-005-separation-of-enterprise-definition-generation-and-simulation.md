# ADR-005 — Separation of Enterprise Definition, Generation, and Simulation

Status: Accepted

## Status History

2026-07-13 - Proposed
2026-07-13 - Accepted

---

## Decision

The Enterprise Modelling & Simulation shall separate enterprise definition, enterprise generation, and enterprise simulation into distinct architectural modules.

The Domain layer defines enterprise concepts, relationships, and invariants.

The Generation module creates valid enterprise instances based on those domain definitions.

The Simulation module accepts valid enterprise states and evolves them over simulated time.

The Simulation module shall not depend directly on the Generation module.

Both modules may depend upon the shared Domain layer and enterprise state contracts.

---

## Rationale

Enterprise creation and enterprise evolution represent different responsibilities.

Separating them allows:

- Enterprises to be created without simulation.
- Simulations to use generated, manually created, imported, or predefined enterprise states.
- Generation and simulation logic to evolve independently.
- Each module to be tested separately.
- Alternative generation and simulation implementations to be introduced later.
- Learning capabilities to use static or dynamic enterprise environments depending on their needs.

---

## Consequences

### Positive

- Clear separation of concerns.
- Improved maintainability.
- Independent testing of generation and simulation.
- Greater architectural flexibility.
- Multiple enterprise creation approaches can share the same simulation engine.

### Negative

- Requires a stable enterprise state contract.
- Additional interfaces and validation layers must be maintained.
- More upfront architectural design is required.

### Neutral

- Generation logic remains outside the Domain layer.
- Simulation behavior remains outside the Generation module.
- Shared concepts continue to have a single source of truth within the Domain layer.

## Future Review

This ADR establishes the initial separation between Enterprise Definition, Enterprise Generation, and Enterprise Simulation.

The ADR should be reviewed during Phase 3 when implementation architecture becomes a primary focus.

Future revisions may expand the definition of:

- Enterprise state contracts
- Module boundaries
- Communication mechanisms
- Simulation integration patterns
- Persistence considerations

The core principle of separation should remain unless a stronger architectural alternative is identified.
