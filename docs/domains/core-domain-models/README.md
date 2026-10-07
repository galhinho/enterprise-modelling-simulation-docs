# Core Domain Models

Status: 🟡 Stable

---

# Purpose

This directory contains the core conceptual models that define an enterprise within the Enterprise Modelling & Simulation.

These models establish the common language, relationships, and responsibilities used throughout the simulator.

The Core Domain Models serve as the conceptual foundation upon which enterprise generation, simulation, learning modules, and future implementations are built.

---

# Objectives

The Core Domain Models aim to:

- Define the fundamental concepts of an enterprise.
- Establish clear boundaries between domains.
- Promote a common terminology across the project.
- Encourage modular and extensible design.
- Provide stable conceptual foundations for future development.

---

# Domain Structure

Each domain represents a specific aspect of an enterprise.

Although domains are developed independently, they collaborate to describe a complete organization.

Examples include:

- Business
- Value
- Organization
- Identity
- Technology
- Products
- People

Additional domains may be introduced as the simulator evolves.

---

## Domain Perspectives

Domains may contribute differently to the simulator.

Some domains primarily define enterprise structure.

Others primarily influence enterprise behavior.

A domain's role as Core or Supporting does not necessarily determine whether it is Structural or Behavioral.

These perspectives should be viewed as complementary classifications rather than replacements.

---

# Design Principles

The Core Domain Models follow these principles:

- Separation of Concerns
- Modularity
- Vendor Neutrality
- Documentation First
- Capability-Driven Evolution
- Extensibility

Each domain should focus on a single conceptual responsibility while remaining capable of interacting with other domains through well-defined relationships.

---

# How to Use

When introducing a new enterprise concept:

1. Determine whether it belongs within an existing domain.
2. Create a new domain only when the concept represents a distinct responsibility.
3. Document relationships between domains rather than duplicating concepts.
4. Follow the public documentation status definitions and architecture boundaries described in the [documentation overview](../../README.md).

---

# Related Documents

- [Documentation overview](../../README.md)
- [Architecture overview](../../architecture/overview.md)
- [Architecture decisions](../../architecture/decisions/)
- [Domain classification](../domain-classification.md)
