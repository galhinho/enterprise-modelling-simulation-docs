# Enterprise Creation Engine

## Purpose

The purpose of this document is to define the architecture and guiding principles of the Enterprise Creation Engine, the foundational component of the Enterprise Modelling & Simulation platform.

This document describes the overall concept of the engine, its responsibilities, generation process, required inputs, outputs, design principles, validation strategy, and deterministic generation model. It establishes the architectural foundation required for the engine to generate coherent, internally consistent, and believable enterprise models that serve as the basis for all future platform capabilities.

Additionally, this document defines the minimum functional and architectural requirements necessary for the Enterprise Creation Engine to be considered complete for the **v0.1.0** milestone.

---

## Objectives

The Enterprise Creation Engine aims to establish the foundational capability of the Enterprise Modelling & Simulation platform by generating coherent, internally consistent, and believable enterprise models that resemble real-world organizations.

Its primary objectives are to:

- Generate enterprise models with realistic organizational structures and relationships.
- Produce enterprise models that are internally consistent and suitable for future platform capabilities.
- Serve as the foundational engine upon which future engines and platform extensions are built.
- Minimize the amount of information required from the user while maximizing the quality and realism of the generated enterprise.
- Ensure deterministic generation by producing identical enterprise models when provided with the same inputs, generation parameters, and engine configuration.

---

## Scope

### Responsibilities

The Enterprise Creation Engine is responsible for:

- Generating a complete and structured enterprise model.
- Generating realistic organizational structures, departments, and reporting hierarchies.
- Generating believable employees, roles, and enterprise identities.
- Generating enterprise infrastructure and supporting metadata.
- Establishing relationships between generated entities while maintaining organizational, identity, and infrastructure consistency.
- Validating the generated enterprise model to ensure it satisfies the platform's integrity and consistency requirements.

### Out of Scope

The Enterprise Creation Engine is **not** responsible for:

- Executing enterprise simulations.
- Generating operational events or security incidents.
- Delivering learning or training experiences.
- Providing AI-assisted guidance or automation.
- Implementing capabilities belonging to other platform engines or optional modules.

These capabilities are designed as separate architectural responsibilities and may later be implemented as independent engines or platform modules. This separation promotes modularity, maintainability, scalability, extensibility, and clear boundaries across the Enterprise Modelling & Simulation platform without implying that every component is already implemented.

## Design Principles

The Enterprise Creation Engine is built upon the following principles:

- Believability over randomness.
- Deterministic generation.
- Minimal user input.
- Maximum internal consistency.
- Modular generation.
- Validation before persistence.
- Extensibility through independent generation modules.
- Automatically generated enterprises shall be fictional by default. While generated enterprises may share common organizational characteristics with real-world organizations, the generation process shall not intentionally reproduce identifiable companies, their branding, or proprietary organizational structures.

---

## Functional Requirements

The Enterprise Creation Engine must:

- Accept the minimum required generation inputs:
  - Enterprise name
  - Industry
  - Enterprise size
  - Region
  - Generation seed

- Validate all required inputs before beginning generation.

- Generate a structured enterprise model based on the provided inputs.

- Generate an organizational structure appropriate to the selected industry and enterprise size.

- Generate departments, roles, employees, and reporting relationships.

- Generate enterprise identities associated with the corresponding employees.

- Generate a basic infrastructure model appropriate to the generated enterprise.

- Establish valid relationships between all generated entities.

- Prevent invalid relationships, including:
  - Employees without departments
  - Departments without responsible leadership
  - Identities without associated employees
  - Infrastructure objects without valid ownership or location
  - Circular reporting relationships

- Produce deterministic results when provided with identical inputs, generation parameters, engine version, and configuration version.

- Record generation metadata, including:
  - Generation seed
  - Engine version
  - Schema or configuration version
  - Generation timestamp

- Validate the complete enterprise model before persistence.

- Reject or report enterprise models that fail validation.

- Produce the generated enterprise in a structured format that can be consumed by future engines and platform modules.

---

## Non-Functional Requirements

The Enterprise Creation Engine shall satisfy the following non-functional requirements:

- Prioritize the generation of believable enterprise models over purely random generation.
- Ensure deterministic generation when provided with identical inputs, generation parameters, and engine configuration.
- Minimize the amount of information required from the user while allowing meaningful personalization of the generated enterprise.
- Maintain a high level of internal consistency across all generated entities and their relationships.
- Validate the generated enterprise model before it is persisted or made available to other platform components.
- Maintain a modular architecture that isolates enterprise creation from simulation, learning, AI, and other platform capabilities.
- Support future extensibility without requiring modifications to the engine's core responsibilities.

---

## Generation Pipeline

1. Inputs
2. Input Validation
3. Context Initialization
4. Enterprise Generation
5. Relationship Resolution
6. Enterprise Validation
7. Persistence

---

## Generation Inputs

The Enterprise Creation Engine requires a minimal set of user-provided inputs to generate a believable enterprise.

### Required

- Enterprise Name
- Industry
- Enterprise Size
- Region

### Optional

- Generation Seed
- Domain Name
- Country
- Language
- Additional configuration options

---

## Generation Context

During initialization, the Enterprise Creation Engine creates a shared generation context.

The generation context contains information required throughout the generation process, including:

- Generation configuration
- Master seed
- Derived subsystem seeds
- Enterprise metadata
- Runtime generation state

The generation context is shared across all generation modules and remains valid for the lifetime of the generation process.

---

## Deterministic Generation

The Enterprise Creation Engine is deterministic.

Given identical:

- Enterprise Name
- Industry
- Enterprise Size
- Region
- Generation Seed
- Engine Version
- Schema Version

the engine MUST generate the same enterprise model.

This guarantees:

- Reproducibility
- Debugging
- Validation
- Regression testing
- Training consistency
- Scenario sharing

---

### Hierarchical Seed Architecture

A single master seed is provided by the user.

The Enterprise Creation Engine derives subsystem seeds from the master seed.

Example:

Master Seed
├── Organization
├── Identity
├── Infrastructure
├── Applications
├── Network
└── Security

This allows each subsystem to evolve independently while maintaining deterministic generation.

---

## Validation Pipeline

Before an enterprise is considered valid, the generated model is validated.

Example validation rules:

- Every department has a manager.
- Every employee belongs to a department.
- Every workstation belongs to a site.
- Every identity belongs to an employee.
- Reporting structures contain no cycles.
- Every server belongs to a network.
- Applications have assigned owners.

Invalid models are rejected and regenerated or reported depending on the generation mode.
