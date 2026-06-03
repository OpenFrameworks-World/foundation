# Lifecycle, State, and Transition Model

Every governed asset in OpenFrameworks has a lifecycle.

A lifecycle defines how an asset moves from idea to operation to retirement with evidence, accountability, and auditability.

## Universal Lifecycle States

```text
proposed
  -> draft
  -> in-review
  -> approved
  -> recommended
  -> adopted
  -> operational
  -> deprecated
  -> retired
  -> archived
```

Additional terminal or exception states:

```text
rejected
superseded
suspended
revoked
```

## Lifecycle Object

```yaml
lifecycle:
  current_state:
  previous_state:
  entered_at:
  next_review_at:
  owner:
  transition_history:
```

## Transition Object

```yaml
transition:
  id:
  subject:
  from_state:
  to_state:
  actor:
  rationale:
  evidence:
  policy_checks:
  approval:
  timestamp:
```

## Transition Rules

A transition is valid only when:

- the actor is authorized
- required evidence is present
- required reviewers are declared
- required approvals are complete
- vendor-neutrality checks are satisfied when applicable
- conflicts are disclosed
- policy checks pass or an approved exception exists

## Recommended Gates

### proposed -> draft

Requires:

- asset identity
- owner
- initial scope

### draft -> in-review

Requires:

- complete required fields
- declared provenance
- declared license
- declared relationships

### in-review -> approved

Requires:

- reviewer
- evidence review
- governance review
- neutrality review if applicable

### approved -> recommended

Requires:

- scoring completed
- risk analysis completed
- alternatives documented
- target capability and outcome declared

### recommended -> adopted

Requires:

- accountable owner
- implementation plan
- risk owner
- value hypothesis

### adopted -> operational

Requires:

- operational owner
- metrics
- review cadence
- support model

### operational -> deprecated

Requires:

- replacement or rationale
- migration guidance
- affected stakeholder notification

### deprecated -> retired

Requires:

- confirmed replacement or closure
- residual risk review

### retired -> archived

Requires:

- final record
- retained evidence
- audit trail

## Core Rule

No asset may skip governance states unless an approved exception exists.
