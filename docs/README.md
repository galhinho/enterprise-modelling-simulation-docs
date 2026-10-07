# Documentation

Status: 📝 Draft

## Purpose

This directory contains the curated public documentation for Enterprise Modelling & Simulation.

It presents selected architecture, accepted decisions, enterprise-creation concepts, and domain models. Detailed software design, implementation, tests, internal planning, research notes, and complete development history remain in the private development repository.

The public documentation is therefore a maintained representation of the project, not the complete internal source of truth.

## Current structure

### Architecture

The [`architecture/`](architecture/) directory contains:

- the public [architecture overview](architecture/overview.md);
- accepted [Architecture Decision Records](architecture/decisions/);
- the [Enterprise Creation Engine](architecture/enterprise-creation-engine.md) architecture;
- the proposed [Enterprise Generation Model](architecture/generation-model.md);
- selected [future considerations](architecture/future-considerations.md).

### Enterprise creation

The [`enterprise-creation/`](enterprise-creation/) directory defines foundational concepts used to establish enterprise purpose and context:

- [Enterprise](enterprise-creation/enterprise/enterprise.md);
- [Value](enterprise-creation/value/value.md).

### Domains

The [`domains/`](domains/) directory contains conceptual domain models.

Core domain models currently include Business and Organization, with Company and Entity retained as additional concepts within the established taxonomy.

Supporting domain models currently include People, Identity, Knowledge, and Technology.

Value remains an Enterprise Creation concept rather than a Domain.

## Planned public additions

The project architecture provides for a Core Methodology and future Domain Profiles. IAM is intended to become the first Domain Profile, but development of that profile has not started and depends on completion of the enterprise core and generation foundations.

Methodology documents, Domain Profiles, fictional scenarios, roadmaps, and a shared glossary will be added only when the underlying work exists and is ready for publication.

## Document status

Project documents use the following maturity states:

- **📝 Draft** — The document is still being developed or verified. Its concepts should not yet be treated as dependable inputs for downstream design.
- **🟡 Stable** — The document has been verified sufficiently for the current project stage and may be used as a foundation for further work. Stable does not mean final. It may change as enterprise generation, validation, and later simulation reveal new requirements.
- **Proposal** — The document presents a candidate direction under evaluation. A proposal does not supersede an accepted Architecture Decision Record.
- **Accepted** — The document records a governing architectural decision. It remains authoritative until explicitly superseded.
- **Future Consideration** — The subject is recorded for later investigation and is not part of the current implementation focus.
- **Superseded** — The document has been formally replaced and is retained to preserve architectural history.

No conceptual model is considered final while the Enterprise Creation Engine and enterprise generation process remain under development.

`🚧 In Progress` may be used temporarily while a document is actively being edited, but it does not replace maturity status. After active editing, the document should return to either 📝 Draft or 🟡 Stable.

## Recommended reading order

1. [Project vision](../vision.md)
2. [Project principles](../principles.md)
3. [Architecture overview](architecture/overview.md)
4. [Accepted architecture decisions](architecture/decisions/)
5. [Enterprise](enterprise-creation/enterprise/enterprise.md) and [Value](enterprise-creation/value/value.md)
6. [Domain classification](domains/domain-classification.md)
7. [Core domain models](domains/core-domain-models/)
8. Supporting domain models
9. [Enterprise Generation Model](architecture/generation-model.md), read explicitly as a proposal

For detailed navigation, use the [documentation index](index.md).

## Documentation principles

- Documentation First
- Architecture Before Implementation
- Consistency
- Modularity
- Progressive Detail
- Separation of Concerns
- Cross-Document Navigation
- Clear distinction between accepted, stable, draft, proposed, and future material

## Related documents

- [Repository README](../README.md)
- [Vision](../vision.md)
- [Principles](../principles.md)
- [Disclaimer](../Disclaimer.md)
- [Copyright and permitted use](../COPYRIGHT.md)
