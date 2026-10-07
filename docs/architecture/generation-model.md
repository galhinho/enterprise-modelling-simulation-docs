# Enterprise Generation Model

**Status:** Proposal  
**Scope:** Enterprise Generation  
**Last Updated:** 2026-09-29

> **Reader note:** This document records a design proposal under evaluation. Its classifications, characteristics, and generation guidance are not accepted architecture unless supported by an accepted Architecture Decision Record. It does not claim that the described generation capabilities are implemented.

## Purpose

This document describes the proposed conceptual model used to guide enterprise generation.

It defines the characteristics that may constrain or influence generation without specifying the implementation algorithms used to generate an enterprise.

This document is a proposal and does not supersede accepted Architecture Decision Records.

## Relationship to Existing Architecture

This proposal operates within the architectural boundaries established by ADR-004 and ADR-005.

The Domain layer defines enterprise concepts, relationships, and invariants. Generation creates valid enterprise instances based on those domain definitions. Simulation accepts valid enterprise states and evolves them over simulated time.

This document therefore distinguishes between:

- Enterprise concepts and facts that may belong to the Domain model.
- Generation rules that determine how values for those concepts are produced.
- Simulation behaviour that may later change enterprise state over time.

Generation rules must remain outside the Domain layer, and Simulation behaviour must remain outside Generation.

Stable enterprise concepts should remain vendor-neutral. Regulatory, regional, vendor-specific, or other changing implementation concerns should not be embedded directly into stable core concepts.

This proposal does not modify or supersede ADR-004 or ADR-005.

## Generation Principles

Enterprise generation should:

- Begin with simple deterministic behaviour before introducing probabilistic generation.
- Allow generated enterprises to vary while remaining internally coherent.
- Avoid coupling unrelated enterprise characteristics unnecessarily.
- Permit unusual but valid enterprise configurations where appropriate.
- Use deterministic seeded generation when randomness is introduced so generated enterprises can be reproduced.
- Keep regulatory, vendor-specific, and simulation behaviour outside the core generation model unless required by an accepted architectural decision.
- A root seed should remain simple from the user's perspective. Internal deterministic
values required by individual generation streams should be derived from the root
seed rather than requiring separate user-provided seeds.

## Enterprise Scale

Enterprise Scale represents the general workforce scale of an enterprise.

The proposed scale bands are:

| Scale | Employee Range |
| --- | ---: |
| Micro | 1–10 |
| Small | 11–75 |
| Medium | 76–500 |
| Large | 501–2,000 |
| Very Large | 2,001+ |

These ranges are simulation modelling abstractions. They are not intended to represent statutory, regulatory, or external SME classifications.

Scale is currently proposed as a generation input that constrains the generation of employee count.

This direction is intentionally provisional. Future iterations may determine that scale should instead be derived from employee count, or that generation should support both constrained and unconstrained generation modes.

The relationship between Scale and other enterprise characteristics, such as organizational complexity and geographic distribution, remains to be determined.

The generation strategy and practical upper boundary for Very Large enterprises remain unresolved.

## Enterprise Geography

Enterprise geography should distinguish between where an enterprise operates and where its products, services, or customers are located.

These concepts must not be treated as equivalent.

### Headquarters

Headquarters represents the primary organizational location of an enterprise.

Example:

    Headquarters: Portugal

Headquarters is a concrete enterprise fact. It may later be consumed by governance, jurisdictional, regulatory, or other modules.

Headquarters alone must not be assumed to determine every legal or regulatory constraint applicable to the enterprise.

### Operational Presence

Operational Presence represents the concrete geographic locations in which an enterprise maintains operations.

Example:

    Headquarters: Portugal

    Operational Presence:
    - Portugal
    - Spain
    - France

Operational Presence may eventually include countries, regions, sites, legal entities, or other appropriate geographic structures.

The exact representation has not yet been decided.

### Operational Scope

Operational Scope represents the geographic breadth of the enterprise's operations.

Possible classifications may include concepts such as:

- Local
- Regional
- National
- International
- Global

The exact taxonomy is not yet accepted.

Operational Scope may eventually be derived from Operational Presence rather than stored independently.

Scale and Operational Scope may influence one another during generation, but unusual combinations should not automatically be prohibited simply because they are uncommon.

### Market Reach

Market Reach represents the geographic breadth of the markets, customers, or users served by the enterprise.

Market Reach is independent from Operational Presence.

For example, an enterprise may:

    Headquarters: Portugal
    Operational Presence: European Union countries
    Operational Scope: International
    Market Reach: Global

A global Market Reach does not imply that the enterprise maintains global offices, employees, or legal entities.

The exact representation of concrete market presence remains unresolved.

## Geographic and Regulatory Modularity

Geographic facts should be represented independently from the regulatory, jurisdictional, or regional rules that may later interpret them.

For example:

    Enterprise Facts
        |
        +-- Headquarters
        +-- Operational Presence
        +-- Industry
        |
        v
    Future Regulatory / Governance Capability
        |
        +-- Jurisdictional context
        +-- Geographic or political groupings
        +-- Applicable regulatory context
        +-- Resulting constraints

The architectural placement and contract of such future capabilities remain unresolved.

Concepts such as European Union membership should therefore not be hard-coded as enterprise scope classifications.

Instead, concrete locations should provide sufficient information for future modules or capabilities to determine relevant geographic, political, economic, regional, or regulatory context.

The core Generation model does not currently determine which laws or regulations apply to an enterprise.

## Interaction Between Generation Characteristics

Enterprise characteristics should be capable of influencing generation without becoming unnecessarily dependent on one another.

For example:

    Scale
        +
    Operational Presence
        +
    Industry
        +
    Seed
        |
        v
    Generated Enterprise Characteristics

A Very Large enterprise may therefore use its operational distribution as one input when determining an appropriate employee count rather than relying on an arbitrary fixed maximum for the Very Large scale.

The exact constraint and weighting mechanisms are deferred.

## Evolution and Simulation

Generation establishes an initial enterprise state.

Characteristics that can change over time should later be capable of evolving through Simulation.

Examples may include:

- Employee count
- Enterprise scale
- Operational presence
- Market reach
- Organizational structure
- Business maturity

Contextual or derived classifications such as startup stages, scale-up status, or "unicorn" status should not currently be treated as permanent enterprise types.

Their future modelling is deferred until the relevant enterprise state and simulation concepts exist.

## Initial Implementation Strategy

Implementation should proceed incrementally.

### Iteration 1

Introduce the five proposed Enterprise Scale categories and use fixed, deterministic employee counts.

### Iteration 2

Associate Scale with bounded employee-count ranges.

### Iteration 3

Introduce seeded deterministic generation within those ranges.

The same incremental approach should be followed when geographic generation is introduced.

Geographic and regulatory behaviour is not part of the initial Scale implementation.

## Architectural Guardrails

This proposal must remain compatible with accepted architectural decisions.

In particular:

- Enterprise concepts, relationships, and invariants belong to the Domain layer.
- Rules for producing generated enterprise instances belong to Generation.
- Behaviour that evolves enterprise state over time belongs to Simulation.
- Stable core concepts should remain independent from specific vendors and rapidly changing implementation concerns.
- Geographic facts should not directly encode regulatory rules.
- Future regulatory, regional, industry-specific, or vendor-specific capabilities should consume stable enterprise concepts through appropriate contracts.

Any future design requiring Generation logic inside the Domain layer, Simulation behaviour inside Generation, or changing implementation-specific concerns inside stable core concepts requires architectural review.

## Constraint-Driven Generation

Exact employee count is not intended to be a standard user-facing generation constraint. Employee count should normally be generated from Enterprise Scale and other relevant generation characteristics.

Controlled scenarios, predefined enterprise states, testing, or future specialized generation modes may require exact employee counts. Those requirements should be handled separately rather than increasing the complexity of the normal generation request.

### Standard and Controlled Generation

Standard enterprise generation should favor broad, user-friendly constraints. Users may specify characteristics such as Enterprise Scale while concrete values, including employee count, are normally generated.

Exact values should not be required as part of the standard generation experience.

Future controlled generation capabilities may allow selected characteristics to be constrained or overridden with exact values. This may support predefined scenarios, organizational simulations, testing, research, or users requiring specific enterprise characteristics.

Controlled generation should remain separate from the normal generation experience so that additional precision does not increase the complexity required for standard enterprise generation.

The contract and implementation of controlled generation are deferred.

## Deterministic Generation and Reproducibility

Seeded generation should be deterministic. Given the same generation constraints, generation algorithm version, and seed, Generation should produce the same result.

Random generation should avoid unnecessary coupling between unrelated generated
characteristics. Where practical, independent deterministic random streams should be derived for individual generation concerns so that introducing a new random decision does not alter unrelated existing generated values.

For example, Scale, Employee Count, Industry, and Geography may use deterministic random streams derived from the enterprise seed and a stable characteristic identifier.

Reproducibility must not rely on the seed alone. Changes to generation rules may change how deterministic random values are interpreted.

Generation provenance should therefore eventually be capable of identifying:

- The enterprise seed.
- The generation algorithm/version.
- The generation constraints supplied by the user.
- The resulting generated enterprise state.

The generated Enterprise State remains the authoritative representation of the generated enterprise.

Compatibility and long-term support for historical generation algorithm versions remain unresolved.

Deterministic generation should include regression tests using known seeds. Introducing a new independent random decision should be tested to verify that unrelated existing deterministic results remain unchanged.

Known-seed regression tests should form part of the Generation compatibility contract.

When Generation is extended or modified, existing reference seeds should be re-evaluated before the change is considered compatible with the current Generation version.

If existing deterministic results change, the cause should first be investigated to determine whether compatibility can and should be preserved.

A new Generation version should be introduced when a change intentionally or necessarily alters the reproducible interpretation or result of existing Generation References and backward compatibility cannot or should not be preserved.

Historical Generation versions required by supported Generation References should remain reproducible according to the project's compatibility policy.

### Generation References

Generation versions, seeds, and explicit user constraints may eventually be represented through a compact Generation Reference.

A Generation Reference should conceptually identify:

- The generation algorithm version.
- The enterprise seed.
- Explicit generation constraints supplied by the user.

The Generation Reference is distinct from the seed itself. The seed controls deterministic random generation, while the Generation Reference provides the information required to reconstruct the generation request.

A bare seed may be interpreted using the current generation algorithm version.

For example:

    12345

may represent seed `12345` using the current generation version.

A versioned reference may explicitly identify a historical generation version.

For example:

    v1:12345

may identify generation version `1` using seed `12345`.

When displaying, exporting, or sharing a Generation Reference, the generation version should be explicit so that the meaning of a saved reference does not change when the current generation algorithm advances.

Where explicit user constraints are present, a self-contained Generation Reference may encode those constraints together with the version and seed. The exact encoding format remains unresolved.

Generation References should initially be capable of operating without persistent storage.

Future persistent storage may provide shorter identifiers for complex generation profiles, controlled scenarios, or organization-specific configurations. Storage should resolve those identifiers into the same structured generation information used by the Generation engine and should not become a requirement of core generation.

The exact Generation Reference syntax, encoding mechanism, and future storage contract remain unresolved.

### Generation Version and Seed Input

Generation should provide a simple user-facing representation for deterministic generation.

A user may provide a bare seed:

    42

A bare seed is interpreted using the current Generation version.

Conceptually:

    42
        ↓
    Current Generation Version + Seed 42

A user may also provide an explicitly versioned seed:

    v1:42

This identifies Generation version `1` with root seed `42`.

The versioned representation should be used when a generation reference is displayed, saved, exported, or shared so that its meaning remains stable after new Generation versions are introduced.

For example, if Generation version 1 is current:

    User input:
    42

    Resolved reference:
    v1:42

If Generation version 4 later becomes current:

    42
        → v4:42

    v1:42
        → Generation version 1, Seed 42

Generation version and deterministic-random algorithm version are distinct concepts.

The user-facing generation reference identifies the Generation version. The corresponding Generation version determines which deterministic-random algorithm version and generation rules are required.

Users should therefore not need to identify the deterministic-random algorithm version separately.

Seed input parsing should remain separate from deterministic seed derivation. The deterministic-random mechanism should receive structured version and seed information rather than interpreting user-facing generation reference strings.

A Generation Reference should preserve the information required to reproduce the original Generation Request rather than storing every characteristic of the resulting Enterprise.

Characteristics selected through deterministic Generation do not need to be encoded in the Generation Reference because they can be reproduced from the Generation version and root seed.

Explicit user constraints must be preserved because they represent information that cannot be reconstructed from the root seed alone.

As a result, Generation References may vary in length. Generation with fewer explicit constraints can use a shorter reference, while increasingly constrained Generation requires additional encoded information.

The Generation Reference format, encoding mechanism, and any future stored reference mechanism are deferred until the Generation constraint model is sufficiently established.

## Open Questions

The following questions remain unresolved:

- What generation strategy should be used for Very Large enterprises?
- What is the final Operational Scope taxonomy?
- Should Operational Scope be stored or derived from Operational Presence?
- How should countries, regions, sites, and other geographic locations be modelled?
- How should Headquarters relate to enterprises with multiple major organizational centres?
- Should Market Reach remain a broad classification or eventually contain concrete market locations?
- How should Scale and Operational Presence influence generation probabilities?
- How should unusual but valid Scale/geography combinations be weighted?
- What stable contract should future regulatory/governance modules consume?
- How should geographic and regulatory context evolve over simulated time?
- How should future controlled generation constraints and overrides be represented?
- How should conflicts between broad characteristics and exact constraints be validated?
- How should self-contained Generation References encode explicit constraints?
- What syntax should distinguish bare seeds from versioned Generation References?
- At what point should complex Generation References use stored profiles instead of self-contained encoding?
- What compatibility guarantees should historical Generation References provide?

## Deferred Concerns

The following are deliberately outside the current implementation:

- Regulatory rule modelling
- Jurisdiction-specific legal logic
- EU or other geopolitical/regulatory membership logic
- Geographic generation probabilities
- Organizational structure generation from geography
- Employee distribution between locations
- Market/customer generation
- Enterprise evolution
- Business valuation
- Startup, scale-up, unicorn, or similar evolving classifications
- Persistent storage and resolution of stored generation or scenario references
