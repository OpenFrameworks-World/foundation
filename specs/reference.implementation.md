# Reference Implementation Specification (v0.1)

## Overview

The Reference Implementation defines how the OpenFrameworks Foundation should be implemented as a working platform.

The foundation is now complete enough to support implementation.

This specification maps the foundation layers into concrete runtime services, storage models, APIs, validation flows, and publishing workflows.

```text
Foundation
  -> Reference Implementation
  -> Platform
```

## Foundation Layers Implemented

The reference implementation must implement:

- Constitutional Principles
- Theory of Composition
- Meta Contract
- Meta Contract Schema
- Meta Validator
- Meta Policy
- Meta State Machine
- Decision Record
- Temporal Record
- Runtime Kernel
- Canonical Vocabulary
- Graph Schema
- OpenFrameworks Language
- OpenFrameworks Compiler
- OpenFrameworks Execution Engine

## System Components

```text
Registry Service
Graph Store
Validation Service
Policy Service
State Machine Service
Decision Service
Temporal Service
Compiler Service
Execution Service
Publishing Service
Trust Service
Search Service
API Gateway
CLI
Admin UI
Public UI
```

## 1. Registry Service

The Registry Service stores all OpenFrameworks artifacts.

Responsibilities:

- store entities
- store framework cards
- store blueprints
- store operating models
- store architecture models
- store systems
- store value models
- store evidence records
- store trust records
- store decision records
- store published artifacts

Minimum APIs:

```text
POST /artifacts
GET /artifacts/{id}
PUT /artifacts/{id}
GET /artifacts
GET /artifacts/{id}/history
```

## 2. Graph Store

The Graph Store stores nodes, edges, temporal relationships, and graph closure paths.

Responsibilities:

- store canonical nodes
- store typed edges
- enforce edge vocabulary
- support graph traversal
- support impact analysis
- support point-in-time queries

Minimum APIs:

```text
POST /graph/nodes
POST /graph/edges
GET /graph/nodes/{id}
GET /graph/traverse/{id}
GET /graph/impact/{id}
GET /graph/time/{timestamp}
```

## 3. Validation Service

Runs validators in sequence.

```text
Meta Contract Validator
  -> Artifact-Specific Validator
  -> Graph Schema Validator
  -> Composition Validator
  -> Conformance Validator
```

Minimum APIs:

```text
POST /validate/meta
POST /validate/artifact
POST /validate/composition
POST /validate/conformance
```

## 4. Policy Service

Evaluates Meta Policy and artifact-specific policies.

Minimum APIs:

```text
POST /policy/evaluate
POST /policy/exception/request
POST /policy/exception/approve
```

## 5. State Machine Service

Enforces allowed lifecycle transitions.

Minimum APIs:

```text
POST /state/transition
GET /state/{artifact_id}
GET /state/{artifact_id}/history
```

## 6. Decision Service

Creates and stores decision records.

Minimum APIs:

```text
POST /decisions
GET /decisions/{id}
GET /decisions?subject={artifact_id}
```

## 7. Temporal Service

Stores time-bound records and supports point-in-time reconstruction.

Minimum APIs:

```text
POST /temporal
GET /temporal/{artifact_id}
GET /temporal/{artifact_id}/at/{timestamp}
```

## 8. Compiler Service

Translates OpenFrameworks Language statements into operation plans.

Minimum APIs:

```text
POST /compile
```

Input:

```json
{
  "statement": "publish artifact framework-card:identity-governance as version 1.0.0"
}
```

Output:

```json
{
  "operation_plan": {}
}
```

## 9. Execution Service

Executes compiler operation plans.

Minimum APIs:

```text
POST /execute
GET /operations/{id}
```

## 10. Publishing Service

Turns validated, policy-approved artifacts into authoritative published artifacts.

Minimum APIs:

```text
POST /publish
GET /published/{id}
GET /published
```

## 11. Trust Service

Computes and stores trust, risk, and confidence records.

Minimum APIs:

```text
POST /trust/calculate
GET /trust/{artifact_id}
GET /trust/{artifact_id}/history
```

## 12. Search Service

Provides discovery over artifacts and graph.

Minimum APIs:

```text
GET /search?q=
GET /search/frameworks?q=
GET /search/blueprints?q=
GET /search/published?q=
```

## Recommended Storage Model

The reference implementation should use a graph-capable datastore.

Minimum logical tables or collections:

```text
artifacts
nodes
edges
states
events
actions
decisions
temporal_records
evidence_records
trust_records
published_artifacts
operations
validation_results
policy_results
```

## Execution Flow

### Publish Artifact Flow

```text
Language Statement
  -> Compiler Service
  -> Operation Plan
  -> Execution Service
  -> Validation Service
  -> Policy Service
  -> Decision Service
  -> State Machine Service
  -> Temporal Service
  -> Graph Store
  -> Publishing Service
```

### Composition Flow

```text
Compose Statement
  -> Compiler
  -> Operation Plan
  -> Composition Validator
  -> Graph Schema Validator
  -> Policy Evaluation
  -> Decision Record
  -> Blueprint Node
  -> Composition Edges
```

### Trust Flow

```text
Evidence Added
  -> Event
  -> Trust Service
  -> Trust Record
  -> Temporal Record
  -> Graph Update
```

## Implementation Modes

### Local Mode

Single-node developer runtime.

Recommended for:

- local authoring
- validation
- testing
- education

### Server Mode

Hosted registry and graph runtime.

Recommended for:

- public registry
- team usage
- community publishing

### Enterprise Mode

Private, governed, organization-specific runtime.

Recommended for:

- private catalogs
- accreditation workflows
- enterprise governance
- audit trails
- SSO/RBAC integrations

## Platform Boundary

Foundation defines the contract.

Reference Implementation defines expected runtime behavior.

Platform implements product experience.

```text
Foundation = what must be true
Reference Implementation = how it should work
Platform = how users experience it
```

## Minimum Viable Implementation

The first implementation should include:

1. Artifact registry
2. Meta Contract validation
3. Graph node and edge storage
4. Framework Card support
5. Publishing state machine
6. Decision records
7. Temporal history
8. Search
9. Basic public publishing

## Final Statement

```text
The Reference Implementation turns the OpenFrameworks Foundation into a buildable platform architecture.
```
