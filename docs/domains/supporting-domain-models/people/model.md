# People Model

Status: 🟡 Stable

---

## Overview

The People Domain represents the human participants who contribute to, interact with, and are affected by the enterprise.

People perform work, exercise judgment, hold responsibilities, use technology, make decisions, and participate in organizational relationships.

Within the simulator, People should be modeled as active enterprise participants rather than passive organizational resources.

---

## Definition

A Person is a human participant represented within the enterprise simulation.

A Person may contribute to the enterprise as an employee, contractor, executive, customer, partner, advisor, volunteer, or other participant type.

People may hold responsibilities, occupy positions, perform roles, possess capabilities, use identities, access technology, and participate in business and organizational activities.

---

## Purpose

The purpose of the People Domain is to represent the individuals through whom enterprise responsibilities, activities, decisions, and interactions are carried out.

The People Domain answers questions such as:

- Who participates in the enterprise?
- What can they do?
- What responsibilities do they hold?
- Where do they belong within the organization?
- What identities and access do they require?
- How do they interact with other people and enterprise systems?
- How do they change throughout their relationship with the enterprise?

---

## Responsibilities

The People Domain is responsible for:

- Representing human participants.
- Defining participant types.
- Representing individual capabilities and limitations.
- Connecting people to organizational responsibilities.
- Connecting people to positions, roles, teams, and departments.
- Supporting identity creation and lifecycle processes.
- Supporting interpersonal and reporting relationships.
- Representing participation in enterprise activities.
- Supporting changes in employment or participation state.
- Providing human context for decisions, events, and incidents.

---

## Characteristics

People:

- Are distinct from identities, roles, and positions.
- May hold multiple roles or responsibilities.
- May participate in multiple organizational structures.
- Possess capabilities, knowledge, and experience.
- Require authority, access, resources, and information to fulfil responsibilities.
- May join, move within, or leave the enterprise.
- May act differently depending on context, culture, incentives, and constraints.
- May make decisions that influence enterprise outcomes.
- May be internal or external to the company.
- May exist before, during, or after an active organizational assignment.

---

## Core Concepts

The People Domain is built upon several foundational concepts:

- Person
- Participant Type
- Position
- Role
- Assignment
- Capability
- Skill
- Experience
- Responsibility
- Authority
- Availability
- Employment or Participation Status

These concepts should remain distinct.

A Person is the human being.

A Position is an organizational place that may be occupied.

A Role groups expected behavior or responsibilities.

An Assignment connects a Person to a Position, Role, Team, Department, or Responsibility.

An Identity represents the digital or system-recognized representation of the Person.

## Related Supporting Domains

- Identity
- Knowledge
- Technology

---

### Human Influence

People do not merely occupy organizational positions.

Their knowledge, skills, experience, decisions, relationships, and behavior influence how the organization operates and evolves.

Organizations with similar structures may behave differently because of differences in the people who participate within them.

The influence of an individual within an enterprise is not determined solely by organizational position or authority.

Knowledge, experience, relationships, responsibilities, critical skills, and organizational dependencies may significantly affect the impact an individual has on enterprise outcomes.

As a result, individuals occupying similar positions may have substantially different levels of organizational influence and organizational impact.

The loss, absence, or replacement of certain individuals may affect organizations differently depending on the responsibilities, knowledge, relationships, and dependencies associated with those individuals.

Detailed influence and dependency modelling remains outside the current scope but should remain possible.

---

## Attributes

Examples of Person attributes include:

- Person Identifier
- Name
- Participant Type
- Employment or Participation Status
- Organizational Assignments
- Positions
- Roles
- Responsibilities
- Capabilities
- Skills
- Knowledge
- Experience
- Manager or Reporting Relationship
- Location
- Working Arrangement
- Availability
- Start Date
- End Date
- Lifecycle State

Sensitive personal information should only be modeled when required by the simulation and should remain separate from general organizational attributes.

---

## Invariants

The following conditions should remain true:

- A Person is not the same as an Identity.
- A Person is not the same as a Role.
- A Person is not the same as a Position.
- A Person may exist without an active organizational assignment.
- Organizational responsibilities should be assigned through identifiable relationships.
- A Person should receive sufficient authority, access, and resources to fulfil assigned responsibilities.
- Changes to organizational assignments may require corresponding identity, access, and technology changes.
- A Person may hold multiple simultaneous assignments where the organizational model allows it.

---

## Design Principles

### Human-Centered Modelling

People should be modeled as active participants with capabilities, judgment, limitations, and relationships.

---

### Separation of Person, Position, Role, and Identity

These concepts should remain distinct to avoid coupling the human participant directly to organizational structure or technical access.

---

### Assignment-Based Participation

People participate in organizations through explicit assignments rather than being permanently embedded within one structural unit.

---

### Responsibility Alignment

Responsibilities assigned to people should align with their roles, authority, capabilities, and organizational context.

---

### Lifecycle Awareness

People and their organizational participation should evolve independently but remain coordinated.

---

### Contextual Behavior

People may respond differently to the same event depending on context, organizational culture, knowledge, incentives, and previous experience.

Detailed behavioral simulation remains outside the current scope but should remain possible.

---

## Examples

Examples of People include:

- Employee
- Contractor
- Executive
- Manager
- Intern
- Consultant
- Volunteer
- Advisor
- Customer
- Supplier Representative
- External Auditor

---

## Relationships

### Organization

People participate in organizational structures through assignments, positions, roles, teams, departments, and reporting relationships.

### Responsibility

People may be assigned responsibilities directly or inherit them through roles and positions.

### Identity

A Person may have one or more digital identities used to interact with enterprise systems.

### Technology

People use devices, applications, infrastructure, and services to perform work.

### Business

People perform activities that contribute to business capabilities and value delivery.

### Company

The Company may establish the legal, contractual, or administrative relationship through which a Person participates.

### Enterprise

People participate within the Enterprise through organizational assignments, responsibilities, identities, and activities.

---

## Related Documents

- Organization Model
- Responsibility Model
- Identity Model
- Company Model
- Business Model
- Entity Model
- Knowledge
- Experience
- Influence

## Major Concepts

The People Domain contains several concepts that may be expanded as the simulator evolves.

### Participation

Represents how people engage with and contribute to the enterprise through assignments, roles, responsibilities, and activities.

### Experience

Represents accumulated practical exposure, lessons learned, and familiarity gained through participation in activities and responsibilities.

### Influence

Represents the ability of individuals to affect decisions, outcomes, behaviors, and enterprise operations.

Influence is not determined solely by organizational position or authority.

### Relationships

Represents formal and informal connections between people, teams, departments, customers, partners, and other enterprise participants.

Relationships may significantly affect communication, collaboration, knowledge transfer, and enterprise outcomes.

---

## Future Evolution 

People become increasingly significant as the simulator evolves from enterprise definition and generation toward enterprise operation, change, and long-term evolution.

Many enterprise events, decisions, risks, and organizational changes originate from human participation, relationships, knowledge, experience, and influence.
