# ADR-001 – Business-Driven Enterprise Modelling

Status: Accepted

## Status History

- 2026-07-12 — Proposed
- 2026-07-13 — Accepted
- 2026-07-16 — Reviewed
- 2026-07-17 - Reviewed

---

## Context

The Enterprise Modelling & Simulation aims to model realistic organizations and the environments in which they operate.

A fundamental architectural decision is determining the starting point from which an enterprise is generated.

Possible approaches include:

- Infrastructure-first modelling
- Technology-first modelling
- Security-first modelling
- Identity-first modelling
- Business-driven modelling

Without a clear starting point, generated enterprises risk becoming collections of disconnected systems rather than coherent organizations.

---

## Decision

The simulator shall model enterprises using a business-driven approach.

Enterprise Definition establishes the Value Objectives and Business definitions that describe why the Enterprise exists and how it intends to pursue value.

Enterprise Generation consumes those definitions to create a valid Enterprise state.

---

## Rationale

Real organizations do not exist to operate technology.

Organizations exist to create value.

Business structures emerge to create, deliver, and sustain that value.

Organizations are then established to execute the business.

People, Identities, Knowledge, Technology, Processes, Operational mechanisms, and Security capabilities are introduced to support organizational responsibilities.

This progression more accurately reflects how real enterprises evolve and operate.

The simulator should therefore model enterprises from purpose and value creation rather than from technical infrastructure.

---

## Enterprise Progression

The simulator follows the conceptual progression:

Value
↓
Business
↓
Business Capabilities
↓
Organization

People
Identity
Knowledge
Technology

Each layer provides context for the layers that follow.

Enterprise Operation occurs after Enterprise Generation and is not part of the conceptual progression defined by this ADR.

---

## Consequences

The simulator will:

- Generate Enterprises from Value Objectives and Business definitions.
- Derive organizational structures from business responsibilities.
- Derive roles and people from organizational structures.
- Derive identities from people and organizational responsibilities.
- Derive technology from operational requirements.
- Derive security controls from business and operational risks.

Simulation events should emerge from enterprise activities rather than from isolated technical systems.

This approach promotes realistic relationships between business, operations, technology, identity, and security domains.

---

## Related Documents

- [ADR-003 – Value-Driven Enterprise Generation](ADR-003-value-driven-enterprise-generation.md)
- [Business Domain](../../domains/core-domain-models/business/model.md)
- [Value](../../enterprise-creation/value/value.md)
- [Organization Domain](../../domains/core-domain-models/organization/README.md)
