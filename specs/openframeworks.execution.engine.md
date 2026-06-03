# OpenFrameworks Execution Engine Specification (v0.1)

## Overview

The OpenFrameworks Execution Engine executes operation plans produced by the OpenFrameworks Compiler.

The Language expresses intent.

The Compiler turns intent into an operation plan.

The Execution Engine runs the operation plan against validators, policies, state machines, decision records, temporal records, and the graph.

```text
Language
  -> Compiler
  -> Operation Plan
  -> Execution Engine
  -> Validators
  -> Policies
  -> Decisions
  -> State Transitions
  -> Events
  -> Actions
  -> Graph Updates
```

## Purpose

The Execution Engine exists to make OpenFrameworks operational.

It ensures that no artifact is created, changed, published, certified, accredited, deprecated, revoked, archived, or added to the graph without passing the required governance and runtime checks.

## Inputs

The Execution Engine accepts an Operation Plan from the Compiler.

```yaml
operation_plan:
  statement:
  parsed_intent:
  required_entities:
  required_relationships:
  validators:
  policy_gates:
  decision_required:
  state_transition:
  events:
  actions:
  graph_updates:
  errors:
  warnings:
```

## Outputs

The Execution Engine returns an Execution Result.

```yaml
execution_result:
  operation_id:
  status:
  artifact_refs:
  event_refs:
  action_refs:
  decision_refs:
  transition_refs:
  temporal_refs:
  graph_update_refs:
  validation_results:
  policy_results:
  errors:
  warnings:
```

Execution statuses:

```text
planned
running
succeeded
failed
blocked
rolled_back
partially_applied
```

## Execution Pipeline

### 1. Receive Operation Plan

The engine receives a compiled operation plan.

If the plan has compiler errors, execution must not start.

### 2. Create Execution Context

```yaml
execution_context:
  operation_id:
  actor:
  source:
  requested_at:
  foundation_version:
  idempotency_key:
```

### 3. Resolve Entities and Relationships

The engine resolves all required entities and relationships against the registry and graph.

Missing required entities block execution unless the operation explicitly creates them.

### 4. Run Validators

Validators must run in order:

```text
Meta Contract Validator
  -> Artifact-Specific Validator
  -> Graph Schema Validator
  -> Composition Validator
  -> Conformance Validator
```

If Meta Contract validation fails, downstream validators must not run.

### 5. Evaluate Policies

The engine evaluates Meta Policy and any artifact-specific policies.

Policy outcomes:

```text
allow
deny
warn
requires_exception
```

Blocking policy failures stop execution.

### 6. Resolve Decision Requirement

If a material transition requires a Decision Record, the engine must either:

- create a draft Decision Record
- link an approved Decision Record
- block execution until a decision exists

### 7. Execute State Transition

The engine applies the Meta State Machine.

A state transition is allowed only when:

- source state matches
- target state is allowed
- transition guards pass
- required decision exists
- policy allows transition

### 8. Record Events

The engine records events before and after material operations.

Examples:

- publish_requested
- artifact_published
- validation_failed
- trust_recalculated

### 9. Record Actions

The engine records actions performed by actors, systems, workflows, or agents.

Every action must link to:

- actor
- subject
- input
- output
- policy checks
- validation results
- decision where applicable
- timestamp

### 10. Apply Graph Updates

The engine commits node and edge changes to the graph only after validators, policies, and state transition checks pass.

Graph updates may include:

- create node
- update node
- create edge
- update edge
- change state
- attach evidence
- attach decision
- attach temporal record

### 11. Create Temporal Records

Every material mutation must create or update temporal metadata.

Published artifacts must receive `published_at`.

State transitions must record `decided_at`, `effective_at`, and `recorded_at` where applicable.

### 12. Return Execution Result

The engine returns the full result with references to all created or updated records.

## Execution Invariants

### 1. No Execution Without Operation Plan

Every mutation must originate from a compiler operation plan or approved internal system rule.

### 2. No Graph Mutation Before Validation

Validation must pass before graph mutation.

### 3. No Publishing Without Policy Approval

Publishing requires policy allow or approved exception.

### 4. No Material Transition Without Decision

Material lifecycle transitions must link to a Decision Record.

### 5. No Silent Mutation

Published artifacts must not be silently overwritten.

### 6. No Untimed Mutation

Every material mutation must record time.

### 7. No Untyped Graph Edge

Every created edge must use canonical vocabulary or approved namespace.

### 8. No Hidden Partial Failure

Partial execution must be marked `partially_applied` and require review or rollback.

## Idempotency

The engine should support idempotency keys to prevent duplicate graph mutations.

```yaml
idempotency:
  key:
  operation_hash:
  previous_result:
```

## Rollback

Rollback is allowed only when:

- rollback target is declared
- affected entities are identified
- decision record or system rule authorizes rollback
- temporal history is preserved
- audit trail is retained

Published artifacts may not be silently rolled back.

## Example: Publish Execution

Input operation:

```text
publish artifact framework-card:identity-governance as version 1.0.0
```

Execution flow:

```text
Receive Operation Plan
  -> Run Meta Contract Validator
  -> Run Framework Card Validator
  -> Run Conformance Validator
  -> Evaluate Publish Eligibility Policy
  -> Require Decision Record
  -> Transition validated -> published
  -> Record publish_requested event
  -> Record publish action
  -> Record artifact_published event
  -> Set published_at
  -> Update graph
  -> Return execution result
```

## Example Execution Result

```yaml
execution_result:
  operation_id: operation:publish-framework-card-identity-governance-v1
  status: succeeded
  artifact_refs:
    - framework-card:identity-governance
  event_refs:
    - event:publish-requested
    - event:artifact-published
  action_refs:
    - action:publish
  decision_refs:
    - decision:publish-identity-governance-v1
  transition_refs:
    - transition:validated-to-published
  validation_results:
    - meta-contract:passed
    - framework-card:passed
    - conformance:passed
  policy_results:
    - publish-eligibility:allow
```

## Relationship to Compiler

The Compiler plans.

The Execution Engine executes.

```text
Compiler = intent to plan
Execution Engine = plan to governed graph mutation
```

## Relationship to Registry and Graph

The Execution Engine is the only component allowed to perform governed production graph mutations.

## Relationship to Platform

The platform must use the Execution Engine for:

- artifact creation
- validation
- publishing
- certification
- accreditation
- lifecycle transitions
- graph updates
- trust recalculation
- feedback processing
- foundation release operations

## Final Statement

```text
The OpenFrameworks Execution Engine turns compiled framework intent into governed, auditable, temporal graph execution.
```
