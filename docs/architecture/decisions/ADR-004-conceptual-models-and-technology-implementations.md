# ADR-004 – Separation between Conceptual Models and Implementations

Status: Accepted

## Status History

2026-07-12 - Proposed
2026-07-12 - Accepted

---

## Context

The Enterprise Simulation Platform is intended to provide long-term educational and architectural value.

While enterprise concepts such as Identity, Business, Value, Organization, Authentication, Authorization, Governance, and Incident Management evolve slowly, the technologies, products, vendors, and organizational processes used to implement those concepts change frequently.

Examples include:

- Identity Providers (Microsoft Entra ID, Okta, Keycloak)
- Cloud Providers (Azure, AWS, Google Cloud)
- SIEM Platforms (Microsoft Sentinel, Splunk, QRadar)
- ITSM Platforms (ServiceNow, Jira Service Management)
- HR Platforms (Workday, SAP SuccessFactors)

Similarly, organizations continuously refine internal processes and methodologies while preserving the underlying business objectives.

Embedding specific technologies directly into the conceptual enterprise model would tightly couple the simulator to current implementations, increasing maintenance effort and reducing long-term relevance.

---

## Decision

The simulator shall organize knowledge according to its expected rate of change. Stable concepts shall be isolated from rapidly evolving implementations to minimize architectural impact and simplify long-term maintenance.

Core enterprise concepts define *what* exists and *why* it exists.

Implementation modules define *how* those concepts are realized within a particular technology stack, organizational process, framework, or methodology.

The simulator shall prioritize conceptual understanding while allowing multiple interchangeable implementations.

---

## Rationale

This separation provides several benefits:

- Preserves long-term architectural stability.
- Allows technologies to evolve independently from the enterprise model.
- Enables support for multiple vendors without modifying core domains.
- Simplifies maintenance as products evolve.
- Encourages learning concepts before learning specific tools.
- Improves portability across industries and organizations.

---

## Consequences

Core Domain Models remain stable and vendor-neutral.

Enterprise Domains describe organizational behavior independently of specific products.

Learning modules may introduce vendor-specific implementations without affecting the simulation engine.

New technologies can be introduced as additional implementation modules rather than architectural changes.

---

## Examples

Identity Management

Concept:

- Identity
- Authentication
- Authorization
- Identity Lifecycle

Possible Implementations:

- Microsoft Entra ID
- Okta
- Keycloak
- Ping Identity

---

Security Monitoring

Concept:

- Log Collection
- Correlation
- Alerting
- Investigation

Possible Implementations:

- Microsoft Sentinel
- Splunk
- Elastic Security
- IBM QRadar

---

Cloud Infrastructure

Concept:

- Compute
- Storage
- Networking
- Identity

Possible Implementations:

- Microsoft Azure
- Amazon Web Services
- Google Cloud Platform

---

## Future Considerations

The same separation may be extended beyond technology.

Future implementation modules may represent:

- Organizational methodologies
- Governance frameworks
- Regulatory environments
- Industry-specific operating models
- Regional business practices

without requiring changes to the conceptual architecture.

---

## Related Documents

- ADR-002 – Separation between Simulation and Learning
- ADR-003 – Value-Driven Enterprise Generation.
