# Governance Operating Model Primitives

OpenFrameworks Foundation defines reusable primitives for constraints, assumptions, exceptions, dependencies, and workflows.

These primitives make governance executable instead of merely descriptive.

## Constraint

A constraint is a condition that limits or shapes a decision, recommendation, implementation, or action.

```yaml
constraint:
  id:
  name:
  type:
  description:
  severity:
  owner:
  applies_to:
  evidence:
  expiry:
```

Constraint types:

- budget
- timeline
- compliance
- security
- privacy
- data residency
- licensing
- vendor neutrality
- skill availability
- interoperability
- operational capacity
- architecture standard
- regulatory jurisdiction

## Assumption

An assumption is a belief treated as true for a decision, recommendation, score, or plan.

```yaml
assumption:
  id:
  statement:
  owner:
  confidence:
  evidence:
  impact_if_wrong:
  expiry:
  review_status:
```

Governance rule:

A recommendation with critical assumptions must not be marked final until assumptions are reviewed or explicitly accepted.

## Exception

An exception is a time-bound approved deviation from a policy, control, standard, lifecycle gate, or governance rule.

```yaml
exception:
  id:
  subject:
  policy:
  requested_by:
  approved_by:
  rationale:
  risk:
  compensating_controls:
  start_date:
  expiry_date:
  review_cadence:
  status:
```

Exception statuses:

- requested
- approved
- rejected
- expired
- revoked
- renewed

Governance rule:

No exception may be permanent by default.

## Dependency

A dependency is a required relationship between assets, capabilities, policies, controls, implementations, teams, or systems.

```yaml
dependency:
  id:
  source:
  target:
  dependency_type:
  criticality:
  owner:
  impact:
  evidence:
```

Dependency types:

- requires
- blocks
- enables
- replaces
- is_required_for
- depends_on
- integrates_with
- governed_by
- validated_by

## Workflow

A workflow is an ordered set of governed actions used to produce a decision, approval, certification, accreditation, publication, or lifecycle transition.

```yaml
workflow:
  id:
  name:
  purpose:
  trigger:
  owner:
  steps:
  inputs:
  outputs:
  policies:
  metrics:
  escalation:
```

## Workflow Step

```yaml
workflow_step:
  id:
  name:
  action_type:
  actor:
  required_role:
  inputs:
  outputs:
  policy_checks:
  completion_criteria:
  timeout:
  escalation:
```

## Standard Framework Adoption Workflow

```text
Create Request
  -> Validate Framework Card
  -> Review Evidence
  -> Review Vendor Neutrality
  -> Review Risk
  -> Review Controls
  -> Score Framework
  -> Document Alternatives
  -> Approve or Reject
  -> Publish Decision
  -> Schedule Renewal
```

## Standard Certification Workflow

```text
Validate Asset Card
  -> Verify Provenance
  -> Review Evidence
  -> Review Conflicts
  -> Run Benchmark or Assessment
  -> Assign Certification Level
  -> Issue Badge
  -> Set Expiry
  -> Publish Certification Claim
```

## Standard Accreditation Workflow

```text
Select Capability
  -> Identify Candidate Frameworks
  -> Map Requirements
  -> Map Policies and Controls
  -> Assess Risk
  -> Review Enterprise Fit
  -> Approve Usage Status
  -> Publish Internal Catalog Entry
  -> Monitor Value Realization
```

## Core Rule

Every material governance outcome must be produced by a workflow or explicitly linked to an approved exception.
