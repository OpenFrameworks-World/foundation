# OpenFrameworks Foundation

## Purpose

OpenFrameworks Foundation defines the constitutional, semantic, governance, runtime, graph, language, and execution contracts for OpenFrameworks.

It is the open design system contract for representing, composing, publishing, governing, trusting, and operationalizing frameworks.

The Foundation exists so frameworks can become governed, publishable, composable, trusted, measurable, reusable, and evolvable assets.

---

## Constitutional Principles

OpenFrameworks is governed by two principles:

```text
Everything is a framework.
Everything must be composable without losing capability.
```

These principles drive every specification, schema, validator, policy, state machine, graph rule, and platform behavior.

---

## Core Interpretation

A framework is a reusable structure that represents capability.

A framework may represent a method, policy, control, operating model, architecture, standard, protocol, decision model, learning model, governance model, capability model, outcome model, trust model, value model, or publishing model.

Composition is the governed combination of frameworks into larger frameworks while preserving the declared capability of each part.

---

## Foundation Stack

```text
Constitution
  -> Ontology
  -> Theory
  -> Meta Contract
  -> Meta Schema
  -> Meta Validator
  -> Meta Policy
  -> Meta State Machine
  -> Decision Record
  -> Temporal Record
  -> Runtime Kernel
  -> Canonical Vocabulary
  -> Graph Schema
  -> Language
  -> Compiler
  -> Execution Engine
  -> Reference Implementation
  -> Platform
```

---

## Constitutional Layer

Defines meaning and worldview.

Canonical artifacts:

- `PRINCIPLES.md`
- `DESIGN-SYSTEM.md`
- `THEORY-OF-COMPOSITION-CANONICAL.md`
- `ontology/foundation.ontology.md`

---

## Governance Kernel

Defines authority.

Canonical artifacts:

- `specs/meta.contract.md`
- `schemas/meta.contract.schema.json`
- `specs/meta.validator.md`
- `specs/meta.policy.md`
- `specs/meta.state.machine.md`
- `specs/decision.record.md`
- `specs/temporal.record.md`

The governance kernel ensures artifacts are not only structurally valid, but also governed, reviewed, publishable, explainable, auditable, and historically traceable.

---

## Runtime Kernel

Defines behavior.

Canonical artifact:

- `specs/runtime.kernel.md`

The runtime kernel reduces OpenFrameworks execution to:

```text
Entity
Relationship
State
Event
Action
Decision
Time
```

---

## Graph Layer

Defines structure.

Canonical artifacts:

- `specs/canonical.vocabulary.md`
- `specs/graph.schema.md`
- `specs/graph.completeness.md`
- `specs/framework.registry.graph.md`

The graph is complete when every published framework can be traced from purpose to value, from value to evidence, from evidence to trust, from trust to authority, from authority to adoption, and from adoption back into foundation evolution.

---

## Artifact Layer

Defines primary framework artifacts.

Canonical artifacts:

- `specs/framework.card.md`
- `specs/framework.blueprint.md`
- `specs/operating.model.md`
- `specs/architecture.model.md`
- `specs/purpose.value.loop.md`

Primary chain:

```text
Framework
  -> Framework Card
  -> Framework Blueprint
  -> Operating Model
  -> Architecture Model
  -> System
  -> Value
```

---

## Language Layer

Defines expression.

Canonical artifact:

- `specs/openframeworks.language.md`

The language allows humans, agents, APIs, UIs, CLIs, and workflows to express operations such as:

```text
define framework
compose framework
validate artifact
publish artifact
trace trust
explain decision
measure value
propose change
```

---

## Execution Layer

Defines operation.

Canonical artifacts:

- `specs/openframeworks.compiler.md`
- `specs/openframeworks.execution.engine.md`
- `specs/reference.implementation.md`

The compiler turns language into operation plans.

The execution engine turns operation plans into governed, auditable, temporal graph mutations.

---

## Publishing Rule

Publishing is the activation gate.

```text
Draft is not authority.
Merge is not authority.
Validation is not authority.
Publishing is authority.
```

A published artifact must be valid, governed, policy-approved, versioned, time-bound, and traceable to a decision.

---

## Complete Graph

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

---

## Minimal Platform Handoff

The platform should implement:

- Registry Service
- Graph Store
- Validation Service
- Policy Service
- State Machine Service
- Decision Service
- Temporal Service
- Compiler Service
- Execution Service
- Publishing Service
- Trust Service
- Search Service
- API Gateway
- CLI
- Admin UI
- Public UI

---

## Foundation Status

Version: `v0.1.0-rc`

Status: Release Candidate

The conceptual foundation is complete enough to start runtime and platform implementation.

---

## Core Statement

```text
Everything is a framework.
Everything must be composable without losing capability.
Composition turns frameworks into systems.
Systems create value.
Publishing activates authority.
Evidence earns trust.
Feedback keeps the foundation alive.
```
