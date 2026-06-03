# Composability Principle

Everything in OpenFrameworks is composable.

OpenFrameworks is a design system for representing the world in frameworks. A framework is useful only when it can connect with other frameworks, patterns, policies, controls, capabilities, outcomes, evidence, decisions, and actions.

## Core Principle

```text
Every framework must be designed to compose.
```

## What Composable Means

A composable framework can be:

- reused in different contexts
- connected to other frameworks
- nested inside larger frameworks
- extended without breaking the original
- replaced with alternatives
- versioned independently
- validated independently
- published independently
- governed independently
- traced through relationships

## Composability Layers

```text
Principle
  -> Primitive
  -> Pattern
  -> Framework
  -> Framework Family
  -> Blueprint
  -> Operating System
```

## Required Composability Metadata

Every publishable framework should declare:

```yaml
composability:
  inputs:
  outputs:
  dependencies:
  extension_points:
  compatible_with:
  conflicts_with:
  replaces:
  replaced_by:
  reusable_patterns:
  composition_rules:
```

## Relationship Types

Composable frameworks use typed relationships:

- depends_on
- enables
- requires
- extends
- implements
- governs
- validates
- measures
- replaces
- complements
- conflicts_with
- belongs_to
- composed_of
- composes_with

## Composition Examples

```text
Capability Framework
  + Policy Framework
  + Control Framework
  + Trust Framework
  + Publishing Framework
  = Governance Blueprint
```

```text
Outcome Framework
  + Capability Framework
  + Metric Framework
  + Value Framework
  = Value Realization Blueprint
```

```text
Framework Card
  + Evidence Record
  + Trust Score
  + Certification Claim
  + Publishing Status
  = Trusted Published Framework
```

## Anti-Monolith Rule

A framework should not become a closed monolith.

If a framework cannot be decomposed, extended, replaced, or related, it is not aligned with OpenFrameworks design principles.

## Platform Rule

The platform must support composition by enabling users to:

- link frameworks
- compose blueprints
- compare alternatives
- trace dependencies
- detect conflicts
- validate compatibility
- publish compositions
- measure adoption and value

## Foundation Rule

The foundation must define framework primitives so they can compose consistently across domains.

## North Star

The world is represented in frameworks, and frameworks become powerful when they compose.
