# ADR-003: Value-Driven Enterprise Generation

Status: Accepted

## Status History

2026-07-11 - Proposed
2026-07-11 - Accepted
2026-07-17 - Reviewed

---

## Context

A core objective of the Enterprise Simulation Platform is to generate realistic organizations capable of producing believable operational scenarios.

An early architectural question emerged:

> Should enterprise components be generated independently, or should they be derived from the value the organization exists to create?

Generating departments, employees, technology, and identities independently would produce unrealistic enterprises with little internal consistency.

Real organizations exist to create value. Their structure, processes, and technology are consequences of that purpose.

---

## Decision

The Enterprise Simulation Platform will adopt a **Value-Driven Enterprise Generation** approach.

Enterprise Generation consumes the Value Objectives and Business definitions established during Enterprise Definition.

Generation begins from those definitions and creates a valid Enterprise State.

Each subsequent layer of the simulation will be derived from the previous one.

The generation flow is conceptually defined as:

Need / Opportunity / Value Gap
↓
Value Objective
↓
Enterprise Creation
↓
Business
↓
Business Capabilities
↓
Requirements / Constraints
↓
Organization
People
Identity
Knowledge
Technology

Enterprise Generation concludes with a valid Enterprise State.

That generated Enterprise State may later be consumed by Enterprise Operation and Simulation.

Possible future operational flow:

Enterprise Operation
↓
Activities
↓
Events
↓
Incidents

Each layer provides context and constraints for the next, producing enterprises that remain internally consistent while allowing controlled randomness.

---

## Rationale

Real enterprises are purpose-driven.

Organizations do not create departments, employees, or technology arbitrarily.

Instead, these elements exist to support the creation, delivery, preservation, or support of value.

Building the simulator from the value outward ensures that:

- Enterprise structures remain coherent.
- Generated scenarios reflect realistic business operations.
- Events emerge naturally from operational activities.
- Incidents have meaningful business context.
- Learning experiences remain grounded in realistic enterprise behavior.

---

## Consequences

### Positive

- Enterprises become internally consistent.
- Business context naturally drives operational behavior.
- Supports diverse industries without changing the simulation engine.
- Randomness remains constrained by realistic business rules.
- Simplifies future expansion into additional industries and business types.
- Creates a strong foundation for event and incident generation.

### Trade-offs

- Business models must be defined before enterprise generation.
- Additional modelling effort is required during the early stages of development.
- Dependencies between domains become more explicit.

---

## Architectural Principles

The simulation follows a top-down generation model.

Higher-level domains define constraints for lower-level domains.

Lower-level domains should not introduce behavior that contradicts the business value they support.

Randomness should enhance realism without violating business consistency.

---

## Generation Example

Value Objective:
Provide healthcare services.

↓

Business:
Healthcare Provider

↓

Business Capabilities:
- Emergency Care
- Surgery
- Diagnostics
- Outpatient Care

↓

Requirements:
- Clinical Operations
- Patient Management
- Medical Records
- Appointment Management
- Regulatory Compliance

↓

Organization:
- Emergency Department
- Radiology Department
- Surgery Department
- Administration
- IT

↓

People:
- Doctors
- Nurses
- Receptionists
- Administrators
- IT Staff

↓

Identity:
- Clinical Staff Identities
- Administrative Identities
- IT Administrative Identities

↓

Knowledge:
- Medical Knowledge
- Clinical Procedures
- Regulatory Knowledge
- Operational Knowledge

↓

Technology:
- Electronic Health Records
- Imaging Systems
- Identity Platform
- Network Infrastructure

↓

Valid Enterprise State Generated

## Possible Operational Consumption

The generated Enterprise State may later be consumed by Enterprise Operation and Simulation.

Example:

Enterprise Operation
↓

Activities
↓

Events
↓

Incidents

---

## Future Considerations

Future versions of the simulator may introduce additional layers, such as:

- Value Streams
- Product Lifecycle
- Customer Journey
- Supply Chain
- Regulatory Requirements

These should extend the value-driven model without replacing its core principle.

The Enterprise Simulation Platform should always derive enterprise behavior from the value being delivered rather than generating isolated components independently.

An Enterprise is defined through Value and Business concepts, generated as a valid Enterprise State, and later operated or simulated through activities, events, and state changes.
