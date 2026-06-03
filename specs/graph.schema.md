# Graph Schema Specification (v0.1)

## Overview

The Graph Schema completes the OpenFrameworks foundation graph.

It defines the canonical node types, edge types, allowed connections, cardinality rules, constraints, closure requirements, and graph validation rules for OpenFrameworks.

```text
Graph = Nodes + Edges + Constraints + State + Time + Decisions + Evidence + Trust
```

The graph is complete only when every framework artifact can be traced from purpose to value and back into foundation evolution.

---

## Constitutional Basis

OpenFrameworks is governed by two principles:

```text
Everything is a framework.
Everything must be composable without losing capability.
```

The graph schema operationalizes those principles.

---

## Canonical Complete Graph

```text
Purpose
  -> Goal
  -> Objective
  -> Outcome
  -> Value Hypothesis
  -> Framework
  -> Framework Card
  -> Framework Blueprint
  -> Operating Model
  -> Architecture Model
  -> System
  -> Measurement
  -> Evidence
  -> Trust
  -> Certification
  -> Accreditation
  -> Adoption
  -> Feedback
  -> Foundation Change
  -> Foundation Release
```

This graph is recursive: any node may itself be represented as a framework or framework element when useful.

---

## Node Types

### Strategic Nodes

- purpose
- goal
- objective
- outcome
- value-hypothesis
- value-model

### Framework Design Nodes

- framework
- framework-card
- framework-blueprint
- composition-contract
- interface

### Operational Nodes

- operating-model
- architecture-model
- system
- action
- event
- state

### Governance Nodes

- policy
- control
- requirement
- decision-record
- temporal-record
- lifecycle-record
- publishing-record

### Trust Nodes

- evidence-record
- trust-record
- risk-record
- measurement
- metric

### Authority Nodes

- certification-claim
- accreditation-record
- adoption-record
- published-artifact

### Evolution Nodes

- feedback-record
- foundation-change-proposal
- foundation-release

### Actor Nodes

- actor
- person
- role
- team
- organization
- system-actor
- agent

---

## Edge Types

### Purpose and Value Edges

- defines
- drives
- targets
- hypothesizes_value
- realizes_value
- produces_outcome

### Framework Edges

- represents
- has_card
- composed_into
- composed_of
- composes_with
- extends
- implements
- requires
- enables
- supports
- conflicts_with
- compatible_with
- replaces
- supersedes

### Operational Edges

- executes
- triggers
- changes_state
- implemented_by
- operated_by
- measured_by

### Governance Edges

- governed_by
- constrained_by
- satisfies
- violates
- authorized_by
- decided_by
- approved_by
- reviewed_by
- owned_by
- maintained_by
- risk_owned_by

### Trust and Evidence Edges

- evidenced_by
- supports_claim
- updates_trust
- trusted_by
- risk_assessed_by
- measured_by

### Authority Edges

- published_as
- certified_by
- accredited_by
- adopted_by

### Evolution Edges

- feedback_for
- proposes_change
- changes
- released_in
- deprecates
- archived_as

---

## Allowed Core Paths

### Purpose to Framework

```text
purpose -> goal -> objective -> outcome -> value-hypothesis -> framework
```

Required for frameworks that claim organizational or business value.

### Framework to System

```text
framework -> framework-card -> framework-blueprint -> operating-model -> architecture-model -> system
```

Required for frameworks that claim implementation readiness.

### System to Trust

```text
system -> measurement -> evidence-record -> trust-record
```

Required for frameworks that claim measured value or high trust.

### Trust to Authority

```text
trust-record -> certification-claim -> accreditation-record -> adoption-record
```

Required for frameworks that claim certification, accreditation, or adoption authority.

### Feedback to Evolution

```text
adoption-record -> feedback-record -> foundation-change-proposal -> foundation-release
```

Required for living foundation evolution.

---

## Mandatory Node Fields

Every node must satisfy the Meta Contract.

Minimum fields:

```yaml
node:
  id:
  type:
  name:
  capability:
  owner:
  lifecycle_state:
  publishing_state:
  version:
  conformance_status:
```

---

## Mandatory Edge Fields

Every edge must declare:

```yaml
edge:
  id:
  source:
  target:
  relationship_type:
  direction:
  rationale:
  confidence:
  evidence_refs:
  temporal:
```

No untyped edges are allowed.

---

## Cardinality Rules

### Purpose

- A purpose may define many goals.
- A goal must belong to one purpose.

### Goal

- A goal may drive many objectives.
- An objective must belong to one goal.

### Objective

- An objective may target many outcomes.
- An outcome must belong to at least one objective.

### Outcome

- An outcome may have many value hypotheses.
- A value hypothesis must belong to one outcome.

### Framework

- A framework must have at least one framework card.
- A framework may participate in many blueprints.
- A framework may depend on many frameworks.
- A framework may replace or supersede another framework.

### Framework Card

- A framework card must represent one framework.
- A framework card may have many versions.
- A framework card may be published as many artifacts over time.

### Blueprint

- A blueprint must compose at least two framework cards or one framework card plus one composition contract.
- A blueprint may produce many operating models.

### Operating Model

- An operating model should link to one blueprint.
- An operating model may produce many architecture models.

### Architecture Model

- An architecture model should link to one operating model.
- An architecture model may produce many systems.

### System

- A system should implement one architecture model.
- A system must have measurements if it claims realized value.

### Measurement

- A measurement must measure one subject.
- A measurement must produce or link to evidence.

### Evidence

- Evidence may support many claims.
- A material trust claim must have evidence.

### Trust

- A trust record must link to evidence.
- A trust score must be time-bound.

### Certification

- A certification claim must link to a published artifact.
- A certification claim must have expiry or review cadence.

### Accreditation

- An accreditation record must declare context.
- An accreditation record must have valid_from and valid_until or review cadence.

### Adoption

- An adoption record must link to an adopter and artifact.
- Adoption should produce feedback or measurement over time.

### Feedback

- Feedback must link to a source artifact or adoption record.
- Feedback may propose foundation change.

---

## Graph Completeness Classes

### Class 0: Isolated

Node exists but has no required relationships.

Not publishable.

### Class 1: Described

Node satisfies Meta Contract and has owner, capability, lifecycle, and publishing state.

Draft only.

### Class 2: Governed

Node has governance, policy, decision, and lifecycle links.

Candidate or reviewed.

### Class 3: Published

Node passed publishing gate and has published artifact record.

Authoritative in declared context.

### Class 4: Composable

Node has composition metadata, interfaces, compatibility, and capability preservation.

Can participate in blueprints.

### Class 5: Operational

Node links to operating model, architecture model, or system.

Implementation-ready or implemented.

### Class 6: Measured

Node links to measurement and evidence.

Can support trust claims.

### Class 7: Trusted

Node has evidence-backed trust record.

Eligible for certification.

### Class 8: Certified

Node has valid certification claim.

Eligible for accreditation.

### Class 9: Accredited

Node has context-specific accreditation.

Eligible for enterprise adoption.

### Class 10: Living

Node has adoption, feedback, and evolution path.

Participates in foundation learning loop.

---

## Closure Rules

### Value Closure

Any framework claiming value must trace to:

```text
purpose -> outcome -> value-hypothesis -> measurement -> evidence
```

### Trust Closure

Any framework claiming trust must trace to:

```text
evidence -> trust-record -> temporal-record
```

### Publishing Closure

Any authoritative artifact must trace to:

```text
validation -> policy -> decision -> state-transition -> published-artifact
```

### Composition Closure

Any blueprint must trace to:

```text
framework-card -> composition-contract -> capability-preservation -> evidence
```

### Evolution Closure

Any living artifact must trace to:

```text
adoption -> feedback -> foundation-change-proposal -> foundation-release
```

---

## Invalid Graph Conditions

A graph segment is invalid when:

- a node has no type
- an edge has no relationship type
- a framework has no capability
- a published artifact has no decision record
- a trust record has no evidence
- a certification has no expiry or review cadence
- an accreditation has no context
- a blueprint hides capability loss
- a lifecycle transition has no timestamp
- a material state change has no decision or policy rule
- an adoption record has no adopter
- a value claim has no measurement path

---

## Query Requirements

The graph must support these canonical queries:

### Purpose Query

```text
Why does this framework exist?
```

### Capability Query

```text
What capability does this framework provide?
```

### Composition Query

```text
What frameworks compose this blueprint?
```

### Dependency Query

```text
What breaks if this framework changes?
```

### Trust Query

```text
What evidence supports this trust score?
```

### Decision Query

```text
Why was this artifact published?
```

### Temporal Query

```text
What was true at this point in time?
```

### Value Query

```text
What value was realized?
```

### Feedback Query

```text
What did adoption teach us?
```

---

## Platform Requirements

The platform must:

- store all nodes and edges with canonical types
- enforce Meta Contract on nodes
- enforce typed relationships on edges
- validate graph closure before publishing
- support temporal graph queries
- support impact analysis
- support trust traceability
- support decision traceability
- support feedback-to-release traceability

---

## Final Complete Graph Statement

```text
The OpenFrameworks graph is complete when every published framework can be traced from purpose to value, from value to evidence, from evidence to trust, from trust to authority, from authority to adoption, and from adoption back into foundation evolution.
```
