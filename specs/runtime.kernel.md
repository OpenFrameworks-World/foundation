# Runtime Kernel Specification (v0.1)

## Overview

The Runtime Kernel defines the minimum executable primitives required to operate OpenFrameworks as a living framework system.

The governance kernel defines authority.

The runtime kernel defines behavior.

```text
Runtime Kernel = Entity + Relationship + State + Event + Action + Decision + Time
```

## Purpose

The Runtime Kernel exists to make OpenFrameworks artifacts executable, observable, auditable, and evolvable.

It answers:

- What exists?
- How is it connected?
- What state is it in?
- What happened?
- What action was taken?
- What decision authorized it?
- When did it happen?

## Runtime Primitives

## 1. Entity

An Entity is any identifiable thing in the OpenFrameworks graph.

Examples:

- framework
- framework card
- framework blueprint
- operating model
- architecture model
- system
- value model
- evidence record
- trust record
- decision record
- certification claim
- accreditation record
- actor
- organization
- published artifact

```yaml
entity:
  id:
  entity_type:
  name:
  version:
  meta_contract_ref:
  lifecycle_state:
  publishing_state:
```

## 2. Relationship

A Relationship is a typed, directional connection between two entities.

```yaml
relationship:
  id:
  source:
  target:
  relationship_type:
  direction:
  rationale:
  evidence_refs:
  confidence:
  temporal:
```

Common relationship types:

- composes
- composed_of
- extends
- governs
- validates
- depends_on
- replaces
- conflicts_with
- supports
- measures
- evidences
- certifies
- accredits
- adopts
- publishes
- triggers
- authorizes

## 3. State

State represents the current lifecycle, publishing, governance, trust, or operational condition of an entity.

```yaml
state:
  entity_id:
  state_type:
  current_state:
  previous_state:
  entered_at:
  valid_until:
  transition_ref:
```

State types:

- lifecycle
- publishing
- governance
- trust
- certification
- accreditation
- adoption
- operational

## 4. Event

An Event is something that happened and may trigger an action or state change.

```yaml
event:
  id:
  event_type:
  subject:
  occurred_at:
  observed_at:
  recorded_at:
  source:
  payload:
```

Event examples:

- artifact_created
- review_requested
- validation_passed
- validation_failed
- policy_passed
- policy_failed
- publish_requested
- artifact_published
- evidence_added
- trust_recalculated
- certification_expired
- feedback_received
- foundation_change_proposed

## 5. Action

An Action is an intentional operation performed by an actor, workflow, system, or agent.

```yaml
action:
  id:
  action_type:
  actor:
  subject:
  input:
  output:
  policy_checks:
  validation_results:
  decision_ref:
  event_refs:
  executed_at:
```

Action examples:

- create
- review
- validate
- approve
- reject
- publish
- certify
- accredit
- deprecate
- revoke
- archive
- measure
- recalculate_trust
- propose_change

## 6. Decision

A Decision authorizes or explains a material action or transition.

```yaml
decision:
  id:
  decision_type:
  subject:
  rationale:
  alternatives:
  evidence_refs:
  risk_assumptions:
  authority:
  state_transition:
```

Decision Records are defined in `specs/decision.record.md`.

## 7. Time

Time makes runtime behavior auditable.

```yaml
time:
  created_at:
  updated_at:
  valid_from:
  valid_until:
  effective_at:
  observed_at:
  recorded_at:
  expires_at:
```

Temporal Records are defined in `specs/temporal.record.md`.

## Runtime Flow

```text
Event
  -> Action
  -> Validation
  -> Policy Evaluation
  -> Decision
  -> State Transition
  -> Temporal Record
  -> Graph Update
```

## Example: Publishing Flow

```text
publish_requested event
  -> publish action
  -> meta validator
  -> meta policy
  -> decision record
  -> state transition: validated -> published
  -> temporal record: published_at
  -> graph update: artifact published
```

## Example: Trust Update Flow

```text
evidence_added event
  -> recalculate_trust action
  -> evidence validation
  -> trust computation
  -> trust state update
  -> temporal trust snapshot
  -> graph update
```

## Runtime Invariants

### 1. No Silent State Change

Every state change must be linked to an event, action, decision, or recorded system rule.

### 2. No Unexplained Authority

Every authoritative transition must be linked to a decision record or policy rule.

### 3. No Untimed Event

Every event must have occurred, observed, or recorded time.

### 4. No Untyped Relationship

Every graph edge must have a relationship type and direction.

### 5. No Unvalidated Publishing

Publishing must pass validation, policy, and state machine guards.

## Relationship to Governance Kernel

The governance kernel defines what is allowed.

The runtime kernel records what happened.

```text
Governance Kernel -> rules
Runtime Kernel -> execution record
```

## Relationship to Platform

The platform must implement the Runtime Kernel to support:

- graph operations
- workflow execution
- publishing
- trust recalculation
- lifecycle transitions
- audit trails
- event history
- state history

## Final Statement

```text
The Runtime Kernel turns OpenFrameworks from a governed design system into an executable framework operating system.
```
