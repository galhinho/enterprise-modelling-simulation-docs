# Entity Model

**Status:** 🟡 Stable


---

## Definition

An Entity is a representation of something that Exists within the simulated enterprise. It has a unique identity, contains attributes that describe it, maintains relationships with other entities, and evolves throughout its lifecycle.

---

## Core Principles

Every Entity:

- Has a unique identity.
- Contains attributes describing itself.
- Can maintain relationships with other entities.
- Evolves throughout its lifecycle.
- Exists within the simulated enterprise.

---

## Common Properties

| Property | Description |
|----------|-------------|
| ID | Unique identifier for the entity. |
| Name | Human-readable name. |
| Type | The type of entity (Employee, Department, Device, etc.). |
| Created | When the entity was created. |
| Modified | When the entity was last modified. |
| Status | Current lifecycle state (Active, Disabled, Archived, Deleted, etc.). |
| Relationships | Links to other entities. |
| Metadata | Additional attributes that are specific to the entity type and are not part of the common Entity model. |

---

## Identity

Every Entity possesses a unique identifier that distinguishes it from every
other entity within the simulator.

Entity names may change throughout an entity's lifecycle.

The Entity ID never changes.

---

## Adoption

The Entity model provides a reusable abstraction for modeled objects that require identification, attributes, relationships, and lifecycle metadata.

Individual models may adopt the Entity model where those guarantees are required.

Not every simulator concept is required to be an Entity.

The decision to use the Entity model should be based on whether the concept represents a distinct modeled object that requires persistent identity and lifecycle management.

---

## Examples

Entities include:

- Company
- Department
- Employee
- Identity
- Group
- Application
- Device
- Cloud Resource
- Policy
- Incident
- Investigation
- Enterprise

---

## What is NOT an Entity

The following are **not** entities:

- Hiring
- Promotion
- Password Reset
- Provisioning
- Authentication
- Access Review

These represent **processes** or **actions**, not objects that exist within the organization.

---

## Related Documents


- [Enterprise](../../../enterprise-creation/enterprise/enterprise.md)
- [Company](../company/model.md)
- [Identity](../../supporting-domain-models/identity/model.md)
