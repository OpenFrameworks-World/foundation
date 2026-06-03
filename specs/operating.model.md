# Operating Model Specification (v0.1)

## Overview

An Operating Model is the behavioral layer of OpenFrameworks.

A Framework Blueprint defines what frameworks compose together.

An Operating Model defines how that composition behaves in practice.

```text
Framework Card -> Framework Blueprint -> Operating Model
```

## Purpose

An Operating Model exists to make framework compositions executable, governable, measurable, and repeatable.

It defines:

- actors
- roles
- responsibilities
- workflows
- decision rights
- policies
- controls
- triggers
- actions
- metrics
- escalation paths
- value realization loops

## Relationship to Blueprint

```text
Blueprint = structure
Operating Model = behavior
```

A blueprint says what composes.

An operating model says how the composition operates.

## Required Sections

A valid Operating Model must include:

1. Identity
2. Linked Blueprint
3. Actors and Roles
4. Responsibilities
5. Workflows
6. Decision Rights
7. Policies and Controls
8. Triggers and Actions
9. Metrics
10. Governance
11. Lifecycle
12. Publishing
13. Value Realization

## 1. Identity

```yaml
identity:
  id:
  name:
  version:
  summary:
  description:
  author:
  publisher:
  license:
  created_at:
  updated_at:
```

## 2. Linked Blueprint

```yaml
blueprint:
  blueprint_id:
  blueprint_version:
  composition_context:
  inherited_framework_cards:
```

An Operating Model should link to a Framework Blueprint.

## 3. Actors and Roles

```yaml
actors:
  - actor_id:
    actor_type:
    role:
    authority:
    eligibility:
```

Actor types:

- person
- role
- team
- organization
- system
- agent
- vendor
- regulator

## 4. Responsibilities

```yaml
responsibilities:
  accountable:
  responsible:
  consulted:
  informed:
  escalation_owner:
```

No Operating Model is publishable without accountability.

## 5. Workflows

```yaml
workflows:
  - workflow_id:
    name:
    trigger:
    steps:
    inputs:
    outputs:
    completion_criteria:
```

Workflow steps should declare:

```yaml
step:
  action:
  actor:
  policy_checks:
  decision_required:
  evidence_required:
  output:
```

## 6. Decision Rights

```yaml
decision_rights:
  decision_type:
  recommender:
  reviewer:
  approver:
  risk_acceptor:
  escalation_path:
```

Decision rights define who can decide what.

## 7. Policies and Controls

```yaml
policies_controls:
  policies:
  controls:
  enforcement_method:
  exceptions:
  compensating_controls:
```

## 8. Triggers and Actions

```yaml
triggers:
  - event:
    condition:
    action:
    actor:
    expected_output:
```

Actions are governed operations.

Examples:

- create
- review
- validate
- approve
- reject
- publish
- certify
- accredit
- measure
- escalate
- deprecate
- archive

## 9. Metrics

```yaml
metrics:
  - metric_id:
    name:
    baseline:
    target:
    current:
    unit:
    source:
    cadence:
    confidence:
```

Metrics connect behavior to value.

## 10. Governance

```yaml
governance:
  owner:
  maintainer:
  reviewer:
  approver:
  risk_owner:
  audit_owner:
  review_cadence:
```

## 11. Lifecycle

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

## 12. Publishing

```yaml
publishing:
  publishable:
  publishing_status:
  published_at:
  published_version:
  canonical_url:
  release_notes:
  blocking_issues:
```

Publishing activates authority.

## 13. Value Realization

```yaml
value_realization:
  expected_value:
  value_metrics:
  baseline:
  target:
  actual:
  realization_status:
  evidence:
  review_cadence:
```

Operating Models must be measured after adoption.

## Example

```yaml
identity:
  id: operating-model:identity-governance
  name: Identity Governance Operating Model
  version: 0.1.0
  summary: Operating model for governed identity decisions.

blueprint:
  blueprint_id: blueprint:identity-governance

actors:
  - actor_id: role:identity-owner
    actor_type: role
    role: owner
  - actor_id: role:security-reviewer
    actor_type: role
    role: reviewer
  - actor_id: role:risk-owner
    actor_type: role
    role: risk_acceptor

workflows:
  - workflow_id: workflow:access-request
    name: Access Request Review
    trigger: access-request-created
    steps:
      - action: validate-identity
        actor: role:identity-owner
      - action: evaluate-policy
        actor: role:security-reviewer
      - action: accept-or-reject-risk
        actor: role:risk-owner
      - action: approve-or-deny-access
        actor: role:identity-owner

metrics:
  - metric_id: metric:access-approval-cycle-time
    name: Access Approval Cycle Time
    target: under 24 hours

publishing:
  publishable: true
  publishing_status: draft
```

## Validation Rules

An Operating Model is valid only when:

- linked blueprint is declared
- actors are declared
- workflows are declared
- decision rights are declared
- policies and controls are declared where applicable
- metrics are declared
- governance owner exists
- publishing status is declared

An Operating Model is publishable only when:

- accountability exists
- workflows are complete
- decision rights are clear
- governance review is complete
- risks are declared
- metrics are defined
- blocking issues are resolved

## Relationship to System

An Operating Model becomes a System when it is implemented in people, process, software, data, and infrastructure.

```text
Operating Model -> Implemented System
```

## Final Statement

```text
An Operating Model is a governed behavior model for executing a Framework Blueprint.
```
