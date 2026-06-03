# Canonical Traceability Model

OpenFrameworks Foundation defines a complete traceability chain from institutional purpose to realized value.

## Traceability Chain

```text
Mission
  -> Goal
  -> Objective
  -> Outcome
  -> Capability
  -> Requirement
  -> Policy
  -> Control
  -> Framework
  -> Standard
  -> Protocol
  -> Implementation
  -> Product or Service
  -> Action
  -> Metric
  -> Measurement
  -> Value Realization
```

## Mission

A mission is the durable reason an institution, program, platform, or initiative exists.

Minimum fields:

```yaml
mission:
  id:
  name:
  description:
  owner:
  stakeholders:
  scope:
  created_at:
  updated_at:
```

## Goal

A goal is a broad desired future state aligned to the mission.

```yaml
goal:
  id:
  name:
  mission:
  description:
  owner:
  time_horizon:
  success_indicators:
```

## Objective

An objective is a specific, bounded target that supports a goal.

```yaml
objective:
  id:
  name:
  goal:
  description:
  owner:
  target_date:
  success_metrics:
  constraints:
```

## Outcome

An outcome is a measurable change in state that matters to a stakeholder.

```yaml
outcome:
  id:
  name:
  objective:
  stakeholder:
  baseline_state:
  target_state:
  measurement_method:
  value_status:
```

## Capability

A capability is a measurable ability required to achieve an outcome.

```yaml
capability:
  id:
  name:
  domain:
  outcomes:
  enabling_frameworks:
  controls:
  metrics:
```

## Requirement

A requirement is a necessary condition that a capability, framework, implementation, or system must satisfy.

```yaml
requirement:
  id:
  name:
  capability:
  type:
  statement:
  priority:
  verification_method:
  acceptance_criteria:
```

Requirement types:

- functional
- non-functional
- security
- compliance
- operational
- financial
- interoperability
- data
- governance

## Policy

A policy is a rule or directive that constrains or guides decisions and actions.

```yaml
policy:
  id:
  name:
  owner:
  scope:
  statement:
  controls:
  exceptions:
  enforcement:
  review_frequency:
```

## Control

A control is a mechanism used to enforce, verify, reduce risk, or ensure compliance with a policy or requirement.

```yaml
control:
  id:
  name:
  policy:
  requirement:
  type:
  implementation_guidance:
  evidence_required:
  test_method:
  frequency:
```

Control types:

- preventive
- detective
- corrective
- compensating
- directive
- automated
- manual

## Action

An action is an intentional operation performed by an actor, system, workflow, or agent.

```yaml
action:
  id:
  name:
  actor:
  subject:
  action_type:
  input:
  output:
  policy_checks:
  decision:
  timestamp:
```

Action types:

- create
- review
- approve
- reject
- recommend
- certify
- accredit
- publish
- deprecate
- retire
- escalate
- measure
- renew

## Metric

A metric is a defined measurement used to evaluate progress, performance, risk, quality, trust, or value.

```yaml
metric:
  id:
  name:
  subject:
  unit:
  formula:
  baseline:
  target:
  current:
  source:
  cadence:
  confidence:
```

## Value Realization

Value realization is the verified evidence that an adopted framework, capability, policy, control, or implementation delivered the intended outcome.

```yaml
value_realization:
  id:
  outcome:
  baseline:
  target:
  actual:
  benefit:
  cost:
  confidence:
  evidence:
  status:
```

## Core Governance Rule

No framework recommendation is complete unless it traces to:

```text
Outcome -> Capability -> Requirement -> Policy or Control -> Evidence -> Metric -> Value Hypothesis
```
