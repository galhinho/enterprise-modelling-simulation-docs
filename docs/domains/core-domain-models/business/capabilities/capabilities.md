# Business Capabilities

Status: 📝 Draft

---

## Purpose

This document defines the concept of Business Capabilities within the Enterprise Modelling & Simulation.

Business Capabilities represent the abilities required by a Business to pursue its objectives and generate value.

Capabilities describe what an enterprise must be able to do, regardless of how those abilities are implemented.

Business Capabilities act as a bridge between business objectives and enterprise implementation.

They influence how enterprises are structured, staffed, represented, enabled, and operated.

Capabilities help drive decisions across multiple enterprise domains, including Organization, People, Identity, Knowledge, and Technology.

As the simulator evolves, Business Capabilities are expected to become one of the primary mechanisms through which enterprise requirements, constraints, and decisions emerge.

---

## Current State

Business Capabilities have been identified as a foundational enterprise concept.

Current understanding suggests that Capabilities play a central role in translating business objectives into enterprise requirements and implementation decisions.

Capabilities influence multiple domains, including:

- Organization
- People
- Identity
- Knowledge
- Technology

Emerging architectural observations indicate that Capabilities may generate requirements and operate within constraints that influence how enterprises are designed and evolved.

Additional investigation is required to better understand:

- Capability Requirements
- Capability Constraints
- Capability Ownership
- Capability Dependencies
- Capability Maturity
- Capability Evolution

These concepts remain under active exploration and may evolve into dedicated documents as the simulator matures.

---

## Architectural Observation

Business Capabilities do not directly define organizational structures, people, identities, or technologies.

Instead, Business Capabilities generate requirements that influence how these domains are designed and implemented.

Conceptually:

Business
    ↓
Capabilities
    ↓
Requirements
        ↙
Organization
People
Identity
Knowledge
Technology

The exact nature of capability requirements remains under investigation and may evolve into a dedicated concept within the Business Domain.

---

## Architectural Significance

Business Capabilities represent a primary mechanism through which business objectives are translated into enterprise requirements and implementation decisions.

Capabilities influence multiple enterprise domains and frequently act as a central context for enterprise design decisions.

Business objectives often drive the creation, modification, prioritization, or retirement of capabilities.

As a result, capabilities may significantly influence organizational structures, people, identities, technologies, governance approaches, and investment decisions.

Business Capabilities may provide useful context for evaluating how Enterprise activities, events, and outcomes relate to Business Objectives.

---

## Requirements and Constraints

Business Capabilities do not exist in isolation.

Each Capability may introduce requirements and constraints that influence enterprise decisions.

### Requirements

Requirements represent what is necessary for a Capability to operate effectively.

Examples may include:

- Organizational structures
- People
- Knowledge
- Experience
- Identity participation
- Technology resources
- Services
- Platforms

Requirements influence how the enterprise is designed to support a Capability.

### Constraints

Constraints represent factors that limit, shape, or influence how a Capability may be implemented.

Examples may include:

- Budget
- Risk tolerance
- Regulatory obligations
- Geographic considerations
- Available workforce
- Organizational maturity
- Organizational Characteristics

Constraints influence which solutions are practical or acceptable for supporting a Capability.

---

## Relationship to Organizational Characteristics

Capabilities define what an organization must be able to do.

However, capabilities alone do not determine how requirements are fulfilled.

Organizations may possess differing characteristics that influence how capabilities are implemented, prioritized, and evolved.

Examples may include:

- Innovation Orientation
- Risk Tolerance
- Compliance Focus
- Cost Sensitivity
- Growth Orientation
- Environmental Orientation

As a result, organizations with similar capabilities may produce significantly different outcomes due to differing organizational characteristics.

Characteristics do not change the existence of a capability.

Instead, they influence how the organization responds to capability requirements and constraints.

---

## Relationships

Business
    ↓
Business Capabilities
        ↓
Requirements
        ↓
Constraints
                ↘
      Organizational Characteristics
                ↙
Organization
People
Identity
Knowledge
Technology

Business objectives influence the capabilities required by an enterprise.

Organizations provide the structures necessary to deliver those capabilities.

---

## Future Topics

Examples of future topics may include:

- Capability Modelling
- Capability Hierarchies
- Capability Requirements
- Capability Constraints
- Capability Maturity
- Capability Ownership
- Capability Dependencies
- Capability Evolution
- Capability Prioritization
- Capability Implementation
- Relationship to Organizational Characteristics
- Capability Governance

These concepts have been identified but remain intentionally undeveloped until additional architectural understanding is obtained.

## Related Documents

- [Business Model](../model.md)

- [Enterprise](../../../../enterprise-creation/enterprise/enterprise.md)

- [Value](../../../../enterprise-creation/value/value.md)

- [Organization Domain](../../organization/README.md)

- [People Domain](../../../supporting-domain-models/people/model.md)

- [Identity Domain](../../../supporting-domain-models/Identity/model.md)

- [Knowledge Domain](../../../supporting-domain-models/knowledge/knowledge.md)

- [Technology Domain](../../../supporting-domain-models/technology/model.md)

- [ADR-001 — Business-Driven Enterprise Modelling](../../../../architecture/decisions/ADR-001-business-driven-enterprise-modelling.md)

- [ADR-003 — Value-Driven Enterprise Generation](../../../../architecture/decisions/ADR-003-value-driven-enterprise-generation.md)
