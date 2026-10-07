# Documentation

This repository contains a curated public view of the Enterprise Modelling & Simulation project. The software implementation and its development history remain private.

## Recommended reading order

1. [Project vision](../vision.md)
2. [Project principles](../principles.md)
3. [Architecture overview](architecture/overview.md)
4. [Accepted architecture decisions](architecture/decisions/)
5. Enterprise creation and domain models
6. Core Methodology, when its public documentation is ready
7. Planned IAM Domain Profile, after enterprise core and generation foundations are complete

## Architecture

The architecture documentation explains the project’s conceptual boundaries and records significant accepted decisions. It distinguishes enterprise definition, generation, state, and simulation and separates stable conceptual models from technology implementations.

- [Architecture overview](architecture/overview.md)
- [Architecture Decision Records](architecture/decisions/)
- [Enterprise Creation Engine](architecture/enterprise-creation-engine.md)
- [Enterprise Generation Model](architecture/generation-model.md) — Proposal
- [Future considerations](architecture/future-considerations.md)

## Enterprise creation

Enterprise Creation defines the foundational context from which enterprises can later be generated.

- [Enterprise](enterprise-creation/enterprise/enterprise.md)
- [Value](enterprise-creation/value/value.md)

## Domains

### Core domain models

- [Core Domain Models](domains/core-domain-models/)
- [Business](domains/core-domain-models/business/model.md)
- [Business Capabilities](domains/core-domain-models/business/capabilities/capabilities.md)
- [Organization](domains/core-domain-models/organization/)
- [Company](domains/core-domain-models/company/)
- [Entity](domains/core-domain-models/entity/)

### Supporting domain models

- [People](domains/supporting-domain-models/people/)
- [Identity](domains/supporting-domain-models/Identity/)
- [Knowledge](domains/supporting-domain-models/knowledge/knowledge.md)
- [Technology](domains/supporting-domain-models/technology/)

See [Domain Classification](domains/domain-classification.md) for the meaning of these categories. Classification describes architectural responsibility, not importance.

Identity is part of the conceptual enterprise core. It is not a completed IAM methodology or Domain Profile. IAM is planned as the first future Domain Profile, but development has not started and depends on completing the enterprise core and generation foundations.

## Methodology

The Core Methodology is the reusable delivery backbone. Its accepted lifecycle retains:

- **Phase 06 — Validation**
- **Phase 07 — Transition to Operations**

Domain Profiles will specialize the Core Methodology without replacing it. Their public documentation will be added only when the underlying work has begun and is ready for publication.

## Document status

- **Accepted** — a governing architectural decision that remains authoritative until explicitly superseded.
- **🟡 Stable** — verified sufficiently to support continued development, but not final or immutable.
- **📝 Draft** — still being developed or verified and not yet a dependable downstream foundation.
- **Proposal** — a candidate direction that does not supersede accepted decisions.
- **Future Consideration** — an idea recorded for later evaluation.
- **Planned** — work that has not started.

No conceptual model is considered final while the Enterprise Creation Engine and enterprise generation process remain under development.

Empty placeholders and private working notes are not published.

## Important notices

Read the root [Disclaimer](../Disclaimer.md) before relying on this material. Copyright and permitted-use information appears in [COPYRIGHT.md](../COPYRIGHT.md).
