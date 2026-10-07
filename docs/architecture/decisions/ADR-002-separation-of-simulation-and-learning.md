# ADR-002: Separation between Simulation and Learning

Status: Accepted

# Status History

2026-07-11 - Proposed
2026-07-11 - Accept
2026-07-17 - Reviewed

---

# Context

The long-term vision of the project is to provide a realistic enterprise environment capable of supporting multiple learning experiences, including Identity & Access Management (IAM), Cloud, Cybersecurity, Networking, Infrastructure, DevOps, IT Operations, and other enterprise disciplines.

An early architectural question emerged:

> Should the learning experience be tightly integrated into the simulator itself, or should the simulator exist independently from the educational components?

Coupling both concerns would increase complexity, make future expansion more difficult, and tightly bind educational content to the enterprise simulation.

---

# Decision

The project will be developed in two distinct architectural layers:

## 1. Enterprise Simulation Platform

The Enterprise Simulation Platform is responsible for creating and maintaining a living enterprise.

Its responsibilities include:

- Enterprise generation
- Business generation
- Organizational structure
- People generation
- Identity generation
- Technology generation
- Business processes
- Enterprise operations
- Event generation
- Incident generation
- Investigation support
- Evaluation mechanisms

The simulation operates independently of any specific learning objective.

Its purpose is to model how an enterprise behaves.

---

## 2. Learning Platform

The Learning Platform consumes the Enterprise Simulation Platform.

It provides learning experiences from different professional perspectives, including but not limited to:

- Identity & Access Management
- Cloud Engineering
- Cybersecurity
- Security Operations
- Network Operations
- Infrastructure Engineering
- DevOps
- IT Support
- Human Resources
- Compliance
- Governance

Learning modules do not generate the enterprise.

Instead, they interact with the existing simulated environment.

The Enterprise Simulation Platform is the product. The Learning Platform is one of its consumers

---

# Rationale

Separating the simulation from the learning experience provides several advantages:

- Clear separation of concerns.
- Independent evolution of both systems.
- Improved maintainability.
- Greater extensibility.
- Support for multiple learning paths without modifying the simulation engine.
- Potential use of the simulation engine outside of educational scenarios.

This architecture allows the simulator to become a reusable enterprise simulation platform rather than a collection of isolated training scenarios.

---

# Consequences

## Positive

- Modular architecture.
- Easier addition of future learning modules.
- Enterprise simulation remains technology-agnostic.
- Educational content remains independent of simulation logic.
- Supports enterprise, research, and educational use cases.
- Simplifies future commercial editions.

## Trade-offs

- Requires well-defined interfaces between the simulation engine and learning modules.
- Learning functionality cannot be fully developed until the simulation platform reaches sufficient maturity.
- Initial development focuses on the simulation engine before educational features.

---

# Future Considerations

Potential consumers of the Enterprise Simulation Platform include:

- Individual learners
- Educational institutions
- Enterprise training
- Internal company simulations
- Research environments
- AI-assisted experimentation

The simulation engine should remain sufficiently generic to support future use cases that may not yet be defined.
