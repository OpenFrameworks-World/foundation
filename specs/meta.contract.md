# Meta Contract Specification (v0.1)

## Overview

The Meta Contract is the universal contract that every OpenFrameworks artifact must satisfy.

It defines the shared structure required for any framework, framework card, blueprint, operating model, architecture model, system, value model, evidence record, trust record, certification claim, accreditation record, publishing artifact, or feedback record.

```text
Meta Contract = identity + capability + context + composition + governance + evidence + trust + lifecycle + publishing + value + feedback
```

The Meta Contract prevents every specification from redefining the same foundational fields.

## Purpose

The Meta Contract exists to make every OpenFrameworks artifact:

- identifiable
- composable
- governable
- traceable
- publishable
- trustworthy
- measurable
- evolvable
- interoperable

## Constitutional Basis

The Meta Contract derives from the two OpenFrameworks constitutional principles:

```text
Everything is a framework.
Everything must be composable without losing capability.
```

If everything is a framework, then every artifact needs a common representational contract.

If everything must compose without losing capability, then every artifact must declare capability, boundary, interface, evidence, governance, and lifecycle.

## Applies To

The Meta Contract applies to:

- Framework
- Framework Card
- Framework Blueprint
- Operating Model
- Architecture Model
- System
- Value Model
- Outcome
- Measurement
- Evidence
- Trust Record
- Risk Record
- Certification Claim
- Accreditation Record
- Adoption Record
- Feedback Record
- Foundation Change Proposal
- Published Artifact

## Required Contract Sections

Every OpenFrameworks artifact must declare the following sections.

1. Identity
2. Type
3. Capability
4. Context
5. Relationships
6. Composition
7. Governance
8. Evidence
9. Trust and Risk
10. Lifecycle
11. Publishing
12. Value
13. Feedback
14. Versioning
15. Conformance

---

## 1. Identity

```yaml
identity:
  id:
  name:
  summary:
  description:
  canonical_url:
```

Identity answers:

```text
What is this artifact?
```

---

## 2. Type

```yaml
type:
  artifact_type:
  framework_type:
  category:
  domain:
  tags:
```

Type answers:

```text
What kind of artifact is this?
```

---

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

Capability answers:

```text
What useful ability does this artifact provide or represent?
```

Capability is mandatory because composition must preserve capability.

---

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

Context answers:

```text
Where is this artifact valid?
```

No artifact is universally valid without context.

---

## 5. Relationships

```yaml
relationships:
  parents:
  children:
  dependencies:
  related_artifacts:
  replaces:
  replaced_by:
  conflicts_with:
  supports:
  governs:
  validates:
  measures:
```

Relationships answer:

```text
How is this artifact connected to other artifacts?
```

---

## 6. Composition

```yaml
composition:
  composable:
  interfaces:
  composition_contracts:
  compatible_with:
  conflicts_with:
  substitution_candidates:
  preserved_capabilities:
  added_capabilities:
```

Composition answers:

```text
How can this artifact compose without losing capability?
```

---

## 7. Governance

```yaml
governance:
  owner:
  maintainer:
  reviewer:
  approver:
  risk_owner:
  decision_record:
  separation_of_duties:
  review_cadence:
```

Governance answers:

```text
Who is accountable for this artifact?
```

No artifact is publishable without accountability.

---

## 8. Evidence

```yaml
evidence:
  evidence_refs:
  evidence_level:
  source_quality:
  last_verified_at:
  evidence_gaps:
```

Evidence answers:

```text
What supports the claims made by this artifact?
```

---

## 9. Trust and Risk

```yaml
trust_risk:
  trust_score:
  confidence_score:
  risk_score:
  trust_basis:
  inherited_trust:
  non_inherited_claims:
  risks:
  mitigations:
```

Trust answers:

```text
How much confidence should we have?
```

Risk answers:

```text
What can go wrong?
```

Trust does not automatically transfer through composition.

---

## 10. Lifecycle

```yaml
lifecycle:
  state:
  previous_state:
  next_review_at:
  deprecated_by:
  replacement:
  transition_history:
```

Recommended states:

```text
draft -> reviewed -> validated -> published -> adopted -> measured -> improved -> deprecated -> archived
```

Lifecycle answers:

```text
What state is this artifact in?
```

---

## 11. Publishing

```yaml
publishing:
  publishable:
  publishing_status:
  published_at:
  published_version:
  release_notes:
  blocking_issues:
```

Publishing answers:

```text
Is this artifact authoritative?
```

Publishing is the activation gate.

---

## 12. Value

```yaml
value:
  purpose:
  target_outcomes:
  value_hypothesis:
  expected_value:
  measured_value:
  value_status:
```

Value answers:

```text
Why does this artifact exist, and what value should it create?
```

---

## 13. Feedback

```yaml
feedback:
  feedback_refs:
  adoption_feedback:
  measurement_feedback:
  change_requests:
  foundation_impact:
```

Feedback answers:

```text
What have we learned from use?
```

Feedback keeps the foundation alive.

---

## 14. Versioning

```yaml
versioning:
  version:
  previous_version:
  compatibility:
  migration_guidance:
  changelog:
```

Versioning answers:

```text
How has this artifact changed?
```

---

## 15. Conformance

```yaml
conformance:
  foundation_version:
  schemas:
  conformance_tests:
  conformance_status:
  validation_results:
```

Conformance answers:

```text
Does this artifact satisfy the OpenFrameworks contract?
```

---

## Minimal Meta Contract Example

```yaml
identity:
  id: framework:example
  name: Example Framework
  summary: Demonstrates the OpenFrameworks Meta Contract.

type:
  artifact_type: framework
  framework_type: capability-framework
  domain:
    - example

capability:
  primary_capability: example capability
  capability_statement: Represents an example reusable capability.

context:
  valid_domains:
    - example
  assumptions: []
  constraints: []

relationships:
  dependencies: []

composition:
  composable: true
  interfaces: []
  preserved_capabilities:
    - example capability

governance:
  owner: OpenFrameworks Foundation
  maintainer: OpenFrameworks Foundation

evidence:
  evidence_level: draft

trust_risk:
  trust_score: 0.0
  confidence_score: 0.0
  risk_score: 0.0

lifecycle:
  state: draft

publishing:
  publishable: false
  publishing_status: draft

value:
  purpose: Demonstrate the Meta Contract.
  value_status: hypothesis

feedback:
  feedback_refs: []

versioning:
  version: 0.1.0

conformance:
  foundation_version: 0.1.0
  conformance_status: draft
```

## Meta Contract Validation Rules

An artifact is valid only when:

- identity exists
- artifact type exists
- capability exists
- context exists
- governance owner exists
- lifecycle state exists
- publishing status exists
- version exists
- conformance status exists

An artifact is publishable only when:

- capability is declared
- composition boundaries are declared
- governance accountability exists
- evidence exists for material claims
- trust and risk are assessed
- lifecycle state is eligible
- conformance checks pass
- blocking issues are resolved

## Relationship to Other Specifications

All OpenFrameworks specifications extend the Meta Contract.

```text
Meta Contract
  -> Framework Card
  -> Framework Blueprint
  -> Operating Model
  -> Architecture Model
  -> System
  -> Value Model
  -> Evidence Record
  -> Trust Record
  -> Certification Claim
  -> Accreditation Record
```

The Meta Contract is the common DNA of the OpenFrameworks design system.

## Relationship to Platform

The platform must treat the Meta Contract as the base validation layer for all artifacts.

Before a specialized validator runs, the Meta Contract validator must run.

```text
Meta Contract Validation
  -> Artifact-Specific Validation
  -> Conformance Validation
  -> Publishing Gate
```

## Final Statement

```text
The Meta Contract is the universal contract for every OpenFrameworks artifact.
```

It makes the OpenFrameworks graph coherent, composable, governable, publishable, trustworthy, and evolvable.
