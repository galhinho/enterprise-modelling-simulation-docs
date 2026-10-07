# Company Model

**Status:** 📝 Draft

---

## Overview

A Company represents a commercial or legal organizational form through which an Enterprise may pursue one or more Value objectives.

A Company may contain or coordinate organizational structures, people, identities, knowledge, technology, locations, policies, and other enterprise elements.

A Company is not the universal root of the simulator.

The Enterprise provides the broader context being modeled, while Company represents one possible form that an Enterprise may take.

Not every Enterprise is necessarily a Company. Enterprises may also include government agencies, non-profit organizations, educational institutions, healthcare providers, research organizations, and other coordinated entities.

---

## Definition

A Company is an Entity representing a commercial or legal organizational form operating within the simulated enterprise environment.

A Company pursues Value objectives through Business, Business Capabilities, Organization, People, Identity, Knowledge, and Technology.

A Company provides legal, commercial, and organizational context without taking ownership of the responsibilities defined by those Domains.

A Company may represent the primary Enterprise being modeled, participate within a broader Enterprise, or interact with other Enterprises in future simulation scenarios.

---

## Responsibilities

The Company concept is responsible for representing:

- Company name and identifying information
- Commercial or legal form
- Industry and sector
- Headquarters and operating locations
- Operating countries
- Business hours and time zones
- Company size
- Relevant regulatory context
- Relationships with the Enterprise and other Entities
- Legal and commercial identity

Company may maintain relationships with Business, Organization, People, Identity, Knowledge, Technology, and other Domains without replacing their individual responsibilities.

---

## Attributes

- Name
- Industry
- Size
- Headquarters
- Operating Countries
- Business Hours
- Time Zones
- Created Date

---

## Design Principles

- Value objectives provide direction for Company formation.
- Business defines how Value is pursued.
- Business Capabilities influence Company requirements.
- Organization structures responsibilities associated with the Company.
- People and Technology maintain a largely symbiotic relationship.
- Technology enables capabilities rather than defining Company purpose.
- Security protects the Enterprise's ability to pursue and deliver Value.
- Company should remain vendor-neutral and implementation-independent.


---

## Invariants

The following rules currently apply:

- A Company is an Entity.
- A Company represents a commercial or legal organizational form.
- A Company must have a defined relationship to an Enterprise context.
- A Company must have a meaningful purpose connected to one or more Value objectives.
- A Company may relate to multiple enterprise Domains without owning their conceptual responsibilities.
- A Company is not required to be the universal root of every simulation.
- The model should not assume that every Enterprise is a Company.
- The model should preserve the possibility of future multi-Enterprise and ecosystem simulations.

---

## Relationships

- Enterprise
- Business
- Organization
- People
- Identity
- Knowledge
- Technology
- External Entities
- A Company exists to support the pursuit of one or more Value objectives defined within the Enterprise context.


## Relationship to Organizational Characteristics

A Company may be associated with an Organization that possesses characteristics influencing how the Enterprise makes decisions and implements capabilities.

Examples may include:

- Innovation Orientation
- Risk Tolerance
- Compliance Focus
- Cost Sensitivity
- Growth Orientation
- Environmental Orientation

These characteristics belong to the Organization Domain rather than the Company itself.

Company-specific facts such as industry, legal form, size, and geographic presence may influence those characteristics without replacing them.