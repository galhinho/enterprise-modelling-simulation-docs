# Architecture overview

Status: 📝 Draft

## Purpose

Enterprise Modelling & Simulation provides a conceptual foundation for representing coherent fictional enterprises and, over time, exploring how they operate and change.

The architecture begins with enterprise purpose and business context. It does not begin with a product, vendor, infrastructure estate, or security control set.

This document provides the public high-level view of the project’s architecture. It describes major architectural areas, their responsibilities, how they relate, and their current maturity. Detailed software design and implementation remain in the private development repository.

## Current architectural focus

Current development is focused on:

1. the enterprise conceptual core;
2. enterprise definition and cross-domain relationships;
3. enterprise generation foundations;
4. creation and validation of coherent enterprise state.

Simulation, learning experiences, Domain Profiles, vendor-specific extensions, and AI-assisted capabilities are later architectural areas. Their inclusion below records intended boundaries, not completed functionality.

## High-level components

```text
┌─────────────────────────────────────────────────────────┐
│                    Public consumers                     │
│  Learning experiences · Research · Analysis · Examples │
└───────────────────────────▲─────────────────────────────┘
                            │ consumes models, state,
                            │ scenarios and evidence
┌───────────────────────────┴─────────────────────────────┐
│                 Enterprise simulation                   │
│        Future evolution of valid enterprise state      │
└───────────────────────────▲─────────────────────────────┘
                            │ accepts
┌───────────────────────────┴─────────────────────────────┐
│                  Valid enterprise state                 │
│   Boundary between creation and time-based simulation  │
└───────────────────────────▲─────────────────────────────┘
                            │ produced by
┌───────────────────────────┴─────────────────────────────┐
│                 Enterprise generation                   │
│    Creates coherent instances from definitions and     │
│                  generation inputs                      │
└───────────────────────────▲─────────────────────────────┘
                            │ constrained by
┌───────────────────────────┴─────────────────────────────┐
│                   Enterprise core                       │
│ Value · Business · Organization · Responsibility       │
│ People · Identity · Knowledge · Technology             │
└─────────────────────────────────────────────────────────┘
```

Cross-cutting extensions may later provide Domain Profiles, vendor implementations, learning content, and AI-assisted analysis. They remain outside the stable conceptual core.

## Component responsibilities

### Enterprise core

The enterprise core defines the stable concepts and relationships required to describe an enterprise coherently.

Its role is to answer questions such as:

- why the enterprise exists and what value it pursues;
- which business capabilities are required;
- how the enterprise is organized;
- which responsibilities must be fulfilled;
- how people and other participants relate to the enterprise;
- how identity, knowledge, and technology support participation and operation.

The core is vendor-neutral and is the current centre of development.

### Enterprise generation

Enterprise generation creates valid enterprise instances from enterprise definitions and generation inputs.

It is responsible for coherence across domains. It should not generate isolated lists of departments, people, identities, or technologies without a traceable relationship to enterprise purpose and requirements.

The project is currently establishing this foundation. Detailed generation algorithms and implementation structures are private.

### Enterprise state

Enterprise state is the representation of a valid enterprise at a particular point in time.

It provides a boundary that allows enterprise generation and simulation to evolve independently. A valid state may eventually be generated, imported, or constructed through another compatible mechanism.

### Simulation engine

The simulation engine is a future architectural component. Its responsibility will be to evolve valid enterprise state over simulated time and make resulting changes observable.

Potential concerns include activities, decisions, events, organizational change, technology change, incidents, and other enterprise consequences. These remain planned capabilities.

### Learning experiences

Learning experiences are consumers of the enterprise and simulation layers. They may provide guidance, exercises, assessment, or different professional perspectives.

They are not embedded in the enterprise core or simulation engine. This preserves the simulator’s independence from a particular curriculum.

### Domain Profiles

Domain Profiles are planned methodology extensions rather than enterprise-core components.

They will specialize the Core Methodology for a professional domain while reusing the same enterprise foundation. IAM is intended to be the first Domain Profile, but its development has not started and depends on completion of the enterprise core and generation foundations.

### Vendor and technology implementations

Vendor-specific implementations may later demonstrate how stable concepts are realized through particular technologies.

They belong outside the conceptual core and must identify their limited scope. No product-specific model should redefine an enterprise concept for the rest of the architecture.

### AI-assisted capabilities

AI-assisted capabilities are a possible future extension, not a current architectural dependency.

Where introduced, AI should consume traceable enterprise information and explain evidence rather than invent enterprise facts or replace deterministic rules where repeatability is required.

## How components communicate

The public architecture defines communication in terms of responsibilities and contracts rather than private software interfaces:

- enterprise definitions constrain generation;
- generation produces a valid enterprise state;
- validation confirms that state satisfies applicable invariants;
- simulation consumes valid state and produces state changes and observable outcomes;
- consumers use models, state, scenarios, outcomes, and evidence without owning simulation behaviour;
- extensions add domain- or technology-specific interpretation without changing stable core definitions.

Exact APIs, data structures, persistence mechanisms, and internal event flows are implementation concerns and are not published here.

## Conceptual flow

```text
Value and enterprise purpose
            ↓
Enterprise definition
            ↓
Enterprise generation
            ↓
Valid enterprise state
            ↓
Enterprise simulation
            ↓
Observable outcomes
```

This is a conceptual flow. It describes architectural responsibilities rather than claiming that every capability is already implemented.

## Enterprise definition

Enterprise definition establishes the concepts, relationships, constraints, and invariants that describe a valid enterprise.

Its concerns include:

- value and enterprise purpose;
- business objectives and capabilities;
- organizational structures and responsibilities;
- people and participation;
- identity, knowledge, and technology;
- relationships and constraints across these areas.

Stable enterprise concepts remain separate from changing implementation technologies.

## Enterprise generation

Enterprise generation uses definitions and generation parameters to create a coherent enterprise instance.

Generation is expected to preserve relationships and constraints across domains. For example, organizational responsibilities, participation, identities, knowledge, and technology should arise from enterprise needs rather than being generated as unrelated inventories.

The enterprise core and generation foundations are the current development priority.

## Enterprise state

Enterprise state represents a valid enterprise at a particular point in time. It is the conceptual contract between generation and simulation.

A simulation can consume a valid enterprise state without depending on the mechanism that created it. This boundary allows definition, generation, and simulation to evolve independently.

## Enterprise simulation

Enterprise simulation is the future capability responsible for evolving enterprise state over simulated time. It may eventually represent activities, decisions, organizational change, technology change, events, incidents, and other consequences.

These are architectural intentions, not claims of completed implementation.

## Learning and analysis

Learning experiences, assessments, research tools, and analytical capabilities are consumers of the simulation platform rather than responsibilities embedded in its core.

This separation allows the same enterprise foundation to support multiple perspectives without coupling the simulation to one curriculum or professional discipline.

## Methodology and Domain Profiles

The project’s delivery methodology is separate from the simulation architecture:

- the **Core Methodology** provides a reusable seven-phase delivery lifecycle;
- **Domain Profiles** may later specialize that lifecycle for particular disciplines;
- IAM is the planned first Domain Profile, but its development has not started;
- enterprise core and generation foundations must be completed before IAM profile design begins.

The Core Methodology retains **Phase 06 — Validation** and **Phase 07 — Transition to Operations**.

## Public and private repository boundaries

### Public documentation repository

The current public repository contains:

- selected conceptual architecture;
- accepted architecture decisions;
- curated enterprise and domain models;
- a proposed Enterprise Generation Model;
- selected future architectural considerations.

Planned additions—including public methodology documentation, future Domain Profiles, fictional examples, roadmaps, and a glossary—will be included only when the underlying work exists and is ready for publication.

### Private development repository

The private repository retains:

- source code and project files;
- automated tests and test fixtures;
- internal software architecture and detailed interfaces;
- build outputs and development tooling;
- working backlogs, investigations, reports, and commercial planning;
- complete development history.

The public repository is therefore a curated companion, not a stripped copy or public branch of the private repository.

## Current public documentation structure

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

This structure expresses the current public information architecture. It does not mirror private software folders or create placeholders for work that has not started.

## Maturity summary

| Architectural area | Public status |
| --- | --- |
| Enterprise conceptual core | In active development |
| Enterprise generation foundations | In active development |
| Enterprise state and validation boundaries | Being established |
| Enterprise simulation | Planned |
| Learning experiences | Planned and architecturally separate |
| Core Methodology | Accepted structure; public source material still to be incorporated |
| IAM Domain Profile | Planned first profile; not started |
| Vendor-specific implementations | Future extension |
| AI-assisted capabilities | Future consideration |

## Accepted decisions

The architecture is governed by five accepted decisions:

1. model business-first organizations;
2. keep simulation and learning separate;
3. generate enterprises from value and business definitions;
4. separate conceptual models from technology implementations;
5. separate enterprise definition, generation, and simulation.

See the [Architecture Decision Record catalogue](decisions/).
