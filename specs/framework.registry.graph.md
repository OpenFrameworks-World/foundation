# Framework Registry & Composition Graph (v0.1)

## Overview

The Framework Registry is the system of record for all frameworks and compositions in OpenFrameworks.

It operationalizes the Theory of Composition by maintaining a queryable, governed, versioned graph of all frameworks and their relationships.

---

## Core Concept

```text
Frameworks are nodes.
Compositions are edges.
The system is a graph.
```

---

## Primary Responsibilities

The Registry must:

- store all frameworks
- store all composition claims
- validate structure using conformance schema
- track versions and lifecycle states
- compute trust and capability metadata
- expose queryable graph interfaces

---

## Data Model

### Framework Node

```json
{
  "id": "string",
  "version": "string",
  "capability": "string",
  "interfaces": [],
  "dependencies": [],
  "governance_owner": "string",
  "trust_level": 0.0,
  "lifecycle": "draft | validated | published | deprecated",
  "provenance": "string"
}
```

---

### Composition Edge

```json
{
  "composition_id": "string",
  "from_framework": "string",
  "to_framework": "string",
  "relationship": "composes | extends | governs | validates | depends_on",
  "contract": "object",
  "capability_preservation": true,
  "trust_impact": 0.0
}
```

---

## Graph Semantics

### Relationship Types

- composes
- extends
- governs
- validates
- depends_on
- replaces
- conflicts_with
- supports

---

## Validation Rules

A node or edge is valid only if:

- it conforms to schema
- capability preservation is satisfied
- governance metadata exists
- trust constraints are met

---

## Query Capabilities

The registry must support:

### 1. Framework lookup

```text
GET framework by id
```

### 2. Composition traversal

```text
trace all frameworks composing a system
```

### 3. Capability search

```text
find frameworks that provide capability X
```

### 4. Impact analysis

```text
what breaks if framework X changes
```

---

## Trust Computation

Each framework has:

- base trust score
- inherited trust score
- composition-adjusted trust score

```text
Trust(Fc) = f(trust(F1..Fn), evidence, governance, validation)
```

---

## Lifecycle Rules

```text
Draft → Validated → Published → Deprecated → Archived
```

Only "Published" frameworks can participate in production compositions.

---

## Registry Guarantees

The registry guarantees:

- traceability
- reproducibility
- governance enforcement
- compositional correctness
- version integrity

---

## Relationship to Execution Engine

- Registry stores state
- Execution Engine validates state transitions
- Conformance Schema defines rules

---

## Relationship to Theory

- Theory defines meaning of frameworks
- Registry stores instances of frameworks
- Graph represents composition reality

---

## Final Statement

```text
The Framework Registry is the living graph of all composable knowledge systems.
```
