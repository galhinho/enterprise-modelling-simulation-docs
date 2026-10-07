# Enterprise Modelling & Simulation

Enterprise Modelling & Simulation is a documentation-led project exploring how realistic enterprises can be represented and simulated from business, organizational, identity, technology, and operational perspectives.

The project begins with the enterprise rather than a particular product or vendor. Its models connect organizational purpose and value to business capabilities, responsibilities, people, identities, knowledge, and technology. This provides a coherent foundation for exploring how enterprises operate, change, and generate realistic scenarios.

## What this repository contains

This public repository presents selected project material for portfolio, demonstration, and educational viewing, including:

- the project vision and design principles;
- conceptual enterprise and domain models;
- architecture decisions and high-level system architecture;
- the proposed Enterprise Generation Model;
- selected future architectural considerations.

The project architecture also establishes a reusable Core Methodology and future Domain Profiles. Their documentation is not included in the current public repository because that work is not yet ready for publication. Domain Profiles will specialize the methodology without replacing it.

## Planned first Domain Profile

Identity and Access Management is intended to become the first Domain Profile, but development of that profile has not started.

The immediate priority is completing the enterprise core and its generation foundations. Only after that foundation is sufficiently mature will the IAM Domain Profile be designed. This sequencing ensures that IAM requirements are derived from a coherent enterprise model rather than imposed on an incomplete core.

When development begins, the IAM profile is expected to explore questions such as:

- how people and other participants are represented within an enterprise;
- how responsibilities create access requirements;
- how identity lifecycles relate to organizational change;
- how access decisions can be designed, validated, and transitioned into operations;
- how IAM affects and is affected by business, organization, people, knowledge, and technology.

These are areas of intended exploration, not completed methodology or implemented capability.

The project remains vendor-neutral at its conceptual core. Product- or vendor-specific examples may eventually be added at the Domain Profile or implementation layer without redefining the underlying enterprise concepts.

## Planned methodology lifecycle

The accepted methodology structure follows seven phases, but its complete public documentation is not yet included. In particular, the lifecycle retains:

- **Phase 06 — Validation**
- **Phase 07 — Transition to Operations**

These phases are part of the delivery methodology and should not be confused with similarly numbered project or product roadmaps.

## Architecture principles

The project is guided by several accepted architectural decisions:

- model enterprises from business purpose and value rather than starting with technology;
- keep the simulation platform separate from learning experiences;
- generate enterprises from value and business definitions;
- separate stable conceptual models from changing technology implementations;
- separate enterprise definition, enterprise generation, and enterprise simulation.

See [`docs/architecture/decisions/`](docs/architecture/decisions/) for the decision records.

## Repository map

```text
docs/
├── architecture/
│   ├── overview.md
│   ├── decisions/
│   ├── enterprise-creation-engine.md
│   ├── generation-model.md
│   └── future-considerations.md
├── enterprise-creation/
│   ├── enterprise/
│   └── value/
├── domains/
│   ├── core-domain-models/
│   ├── supporting-domain-models/
│   └── domain-classification.md
├── README.md
└── index.md
```

Start with the [documentation index](docs/index.md).

## Project status

This repository is an evolving public documentation set. Documents identify whether they describe accepted decisions, stable concepts, proposals, or future considerations. Documented concepts should not be interpreted as evidence that every related software capability is already implemented.

The software implementation is maintained separately in a private development repository. Source code, automated tests, private development history, internal planning material, and operational integrations are not distributed here. Current development is focused on the enterprise core and enterprise generation foundations; the IAM Domain Profile has not yet entered development.

Planned public additions include the Core Methodology, future Domain Profiles, selected fictional scenarios, and a shared glossary. They will be added only when the underlying work exists and is ready for publication.

## Copyright and use

Copyright © 2026 Guilherme Alhinho. All rights reserved.

This repository is available for portfolio, demonstration, and educational viewing. No open-source licence or general permission to reproduce, modify, redistribute, sublicense, or commercially use its contents is granted.

See [`COPYRIGHT.md`](COPYRIGHT.md) and [`Disclaimer.md`](Disclaimer.md) for further information.
