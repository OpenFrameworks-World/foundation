# Framework Card Specification (v0.1)

## Overview

A Framework Card is the canonical publishable unit of OpenFrameworks.

Every framework must have a Framework Card before it can be validated, composed, published, trusted, certified, accredited, adopted, or measured.

```text
Framework Card = identity + capability + context + governance + evidence + composition + publishing status
```

## Purpose

The Framework Card exists to make every framework:

- identifiable
- understandable
- composable
- governable
- traceable
- publishable
- reusable
- certifiable
- accreditable
- measurable

## Relationship to Theory

The Theory of Composition states:

```text
Everything is a framework.
Everything must be composable without losing capability.
```

The Framework Card is how a framework declares the capability it brings and the conditions under which it can compose without losing that capability.

## Required Sections

A valid Framework Card must include:

1. Identity
2. Classification
3. Capability
4. Context
5. Composition
6. Governance
7. Evidence
8. Trust
9. Lifecycle
10. Publishing

## 1. Identity

```yaml
identity:
  id:
  name:
  version:
  summary:
  description:
  author:
  publisher:
  license:
  created_at:
  updated_at:
```

## 2. Classification

```yaml
classification:
  framework_type:
  framework_family:
  domain:
  tags:
  maturity_level:
```

Recommended framework types:

- capability-framework
- outcome-framework
- policy-framework
- control-framework
- trust-framework
- risk-framework
- decision-framework
- learning-framework
- publishing-framework
- governance-framework
- architecture-framework
- operating-framework
- implementation-framework
- benchmark-framework
- value-framework

## 3. Capability

```yaml
capability:
  primary_capability:
  secondary_capabilities:
  capability_statement:
  capability_inputs:
  capability_outputs:
  capability_boundaries:
  capability_loss_risks:
```

The capability section is mandatory because composition must preserve capability.

## 4. Context

```yaml
context:
  valid_domains:
  valid_organizations:
  valid_jurisdictions:
  assumptions:
  constraints:
  not_valid_for:
```

A framework is never universally valid without context.

## 5. Composition

```yaml
composition:
  composable: true
  interfaces:
  dependencies:
  compatible_with:
  conflicts_with:
  extends:
  composed_of:
  composes_with:
  substitution_candidates:
  composition_contracts:
```

Composition metadata is mandatory for any published framework.

## 6. Governance

```yaml
governance:
  owner:
  maintainer:
  reviewer:
  approver:
  risk_owner:
  review_status:
  approval_status:
  decision_record:
```

No framework is publishable without accountability.

## 7. Evidence

```yaml
evidence:
  evidence_refs:
  evidence_level:
  source_quality:
  last_verified_at:
  evidence_gaps:
```

Evidence supports claims about capability, trust, compatibility, and value.

## 8. Trust

```yaml
trust:
  trust_score:
  confidence_score:
  risk_score:
  trust_basis:
  inherited_trust:
  non_inherited_claims:
```

Trust does not automatically transfer through composition.

## 9. Lifecycle

```yaml
lifecycle:
  state:
  previous_state:
  next_review_at:
  deprecated_by:
  replacement:
  transition_history:
```

Recommended lifecycle states:

```text
draft -> reviewed -> validated -> published -> adopted -> measured -> improved -> deprecated -> archived
```

## 10. Publishing

```yaml
publishing:
  publishable:
  publishing_status:
  published_at:
  published_version:
  canonical_url:
  release_notes:
  blocking_issues:
```

Publishing is the activation gate.

A framework is not authoritative until published.

## Minimal Card Example

```yaml
identity:
  id: framework:composition-theory
  name: Theory of Composition
  version: 0.1.0
  summary: Theory for composing frameworks without losing capability.
  author: OpenFrameworks World
  publisher: OpenFrameworks Foundation
  license: TBD

classification:
  framework_type: theory-framework
  framework_family: openframeworks-foundation
  domain:
    - framework-design-systems

capability:
  primary_capability: composition reasoning
  capability_statement: Defines how frameworks compose while preserving capability.

composition:
  composable: true
  interfaces:
    - composition-contract
  dependencies:
    - constitutional-principles

governance:
  owner: OpenFrameworks Foundation
  review_status: draft
  approval_status: pending

evidence:
  evidence_level: internal-foundation

trust:
  trust_score: 0.5
  confidence_score: 0.5
  risk_score: 0.3

lifecycle:
  state: published

publishing:
  publishable: true
  publishing_status: published
  published_version: v0.1.0
```

## Validation Rules

A Framework Card is valid only when:

- identity is complete
- capability is declared
- composition metadata exists
- governance owner exists
- evidence level is declared
- lifecycle state is valid
- publishing status is declared

A Framework Card is publishable only when:

- capability is preserved
- governance review is complete
- evidence is sufficient for the claim
- composition risks are declared
- blocking issues are resolved

## Relationship to Registry

The Registry stores Framework Cards.

## Relationship to Graph

The Graph connects Framework Cards through composition relationships.

## Relationship to Publishing

The Publishing System turns approved Framework Cards into authoritative public artifacts.

## Relationship to Platform

The Platform must support authoring, validating, reviewing, publishing, searching, comparing, composing, certifying, accrediting, and measuring Framework Cards.

## Final Statement

```text
The Framework Card is the atomic publishable unit of OpenFrameworks.
```
