# OpenFrameworks Compiler Specification (v0.1)

## Overview

The OpenFrameworks Compiler translates OpenFrameworks Language statements into executable graph operations.

```text
Language Statement
  -> Parsed Intent
  -> Runtime Operation
  -> Validation
  -> Policy Evaluation
  -> Decision Record
  -> State Transition
  -> Event Log
  -> Graph Update
```

The compiler is the bridge between human-readable framework language and machine-executable OpenFrameworks runtime behavior.

## Purpose

The compiler exists so humans, agents, CLIs, APIs, UIs, and workflows can express framework operations consistently and produce auditable graph changes.

It answers:

- What does this language statement mean?
- What entity or relationship should be created or changed?
- What validation must run?
- What policy gate applies?
- Is a decision required?
- What event and action should be recorded?
- What state transition should occur?
- What graph update should be committed?

## Input

The compiler accepts OpenFrameworks Language statements.

Examples:

```text
define framework identity-governance capability identity-governance context enterprise-iam
compose framework identity with framework policy into blueprint identity-governance
validate artifact framework-card:identity-governance using meta-contract
publish artifact framework-card:identity-governance as version 1.0.0
explain decision decision:publish-theory-of-composition-v0-1-0
trace trust for artifact framework-card:identity-governance
```

## Output

The compiler outputs an executable operation plan.

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

## Compiler Pipeline

### 1. Parse

Convert language statement into structured intent.

```yaml
parsed_intent:
  verb:
  subject:
  object:
  context:
  rationale:
  evidence:
  target_state:
```

### 2. Resolve Vocabulary

Map verbs, subjects, objects, and states to Canonical Vocabulary.

Unknown terms must either:

- map to canonical vocabulary
- use an approved namespace
- fail compilation

### 3. Resolve Entities

Look up or prepare required graph entities.

Examples:

- framework
- framework-card
- framework-blueprint
- operating-model
- decision-record
- evidence-record

### 4. Build Graph Operation

Determine required node and edge changes.

Examples:

- create entity
- update entity
- create relationship
- update relationship
- change state
- record event
- record action

### 5. Run Validation Plan

Attach required validators:

- Meta Contract Validator
- artifact-specific validator
- composition validator
- graph schema validator
- conformance validator

### 6. Run Policy Plan

Attach required policy gates:

- draft acceptance
- review eligibility
- publish eligibility
- certification eligibility
- accreditation eligibility
- graph inclusion
- deprecation
- archival

### 7. Determine Decision Requirement

Determine whether a Decision Record is required.

Decision Records are required for:

- publish
- approve
- reject
- certify
- accredit
- deprecate
- archive
- revoke
- supersede
- grant exception
- accept risk
- approve composition
- approve foundation change

### 8. Determine State Transition

Map the operation to the Meta State Machine.

Example:

```text
publish artifact X
```

may map to:

```text
validated -> published
```

### 9. Emit Events and Actions

Every compiled operation emits runtime records.

Example:

```yaml
events:
  - publish_requested

actions:
  - publish
```

### 10. Produce Graph Update

The compiler produces a graph update plan.

```yaml
graph_updates:
  create_nodes:
  update_nodes:
  create_edges:
  update_edges:
  state_changes:
```

## Example: Compile Define Framework

Input:

```text
define framework identity-governance capability identity-governance context enterprise-iam
```

Output:

```yaml
operation_plan:
  parsed_intent:
    verb: define
    subject: framework
    object: identity-governance
    context: enterprise-iam
  required_entities:
    - entity_type: framework
      id: framework:identity-governance
  validators:
    - meta-contract
  policy_gates:
    - draft-acceptance
  decision_required: false
  state_transition:
    to_state: draft
  events:
    - artifact_created
  actions:
    - create
```

## Example: Compile Compose Frameworks

Input:

```text
compose framework identity with framework policy into blueprint identity-governance
```

Output:

```yaml
operation_plan:
  parsed_intent:
    verb: compose
    subject: framework:identity
    object: framework:policy
    target: blueprint:identity-governance
  required_entities:
    - framework:identity
    - framework:policy
    - blueprint:identity-governance
  required_relationships:
    - framework:identity composes_with framework:policy
    - blueprint:identity-governance composed_of framework:identity
    - blueprint:identity-governance composed_of framework:policy
  validators:
    - meta-contract
    - composition-conformance
    - graph-schema
  policy_gates:
    - review-eligibility
  decision_required: true
  events:
    - artifact_created
  actions:
    - create
    - validate
```

## Example: Compile Publish Artifact

Input:

```text
publish artifact framework-card:identity-governance as version 1.0.0
```

Output:

```yaml
operation_plan:
  parsed_intent:
    verb: publish
    subject: framework-card:identity-governance
    target_state: published
  validators:
    - meta-contract
    - artifact-specific
    - conformance
  policy_gates:
    - publish-eligibility
  decision_required: true
  state_transition:
    from_state: validated
    to_state: published
  events:
    - publish_requested
    - artifact_published
  actions:
    - publish
  graph_updates:
    state_changes:
      - lifecycle: published
      - publishing_status: published
```

## Compiler Invariants

### 1. No Unknown Canonical Terms

Unrecognized verbs, entity types, relationship types, states, events, actions, or decision types must fail unless namespaced.

### 2. No Graph Mutation Without Operation Plan

Every graph mutation must come from a compiled operation plan or approved internal system rule.

### 3. No Publishing Without Validation and Policy

The compiler must attach validation and policy gates to publishing operations.

### 4. No Material Transition Without Decision

Material lifecycle transitions require Decision Records.

### 5. No Untimed Runtime Records

Events, actions, decisions, and state transitions must have temporal metadata.

## Relationship to Language

OpenFrameworks Language defines expressions.

The compiler translates expressions into runtime plans.

## Relationship to Runtime Kernel

The compiler emits runtime primitives:

- event
- action
- decision
- state transition
- graph update

## Relationship to Platform

The platform may expose the compiler through:

- CLI
- API
- UI command palette
- workflow engine
- agent interface
- CI validation

## Final Statement

```text
The OpenFrameworks Compiler turns framework language into governed graph operations.
```
