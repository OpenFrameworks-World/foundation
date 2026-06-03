# Decision Record Specification (v0.1)

## Overview

A Decision Record is the canonical artifact for recording why an OpenFrameworks artifact changed state, was published, rejected, certified, accredited, deprecated, revoked, or granted an exception.

State changes without decisions are not auditable.

```text
Decision Record = choice + rationale + evidence + alternatives + risk + authority + outcome
```

## Purpose

Decision Records make OpenFrameworks governance explainable, auditable, reversible, and learnable.

They answer:

- What decision was made?
- Why was it made?
- Who made it?
- What alternatives were considered?
- What evidence supported it?
- What risks were accepted?
- What assumptions were made?
- What state transition did it authorize?
- When should it be reviewed?
- What happened after the decision?

## Applies To

Decision Records are required for material actions including:

- publish
- reject
- approve
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
- approve breaking change

## Required Sections

A Decision Record must include:

1. Identity
2. Subject
3. Decision
4. Rationale
5. Alternatives
6. Evidence
7. Risk and Assumptions
8. Authority
9. State Transition
10. Outcome and Review
11. Publishing

## 1. Identity

```yaml
identity:
  id:
  name:
  version:
  created_at:
  updated_at:
```

## 2. Subject

```yaml
subject:
  artifact_id:
  artifact_type:
  artifact_version:
  affected_artifacts:
```

## 3. Decision

```yaml
decision:
  decision_type:
  decision_status:
  decision_summary:
  decision_date:
```

Decision types:

- publish
- approve
- reject
- certify
- accredit
- deprecate
- archive
- revoke
- supersede
- exception
- risk-acceptance
- composition-approval
- foundation-change

Decision statuses:

- proposed
- approved
- rejected
- deferred
- superseded
- revoked

## 4. Rationale

```yaml
rationale:
  problem:
  reason:
  expected_benefit:
  constraints:
```

## 5. Alternatives

```yaml
alternatives:
  considered:
    - option:
      reason_for_rejection:
      tradeoffs:
```

No material recommendation should omit alternatives.

## 6. Evidence

```yaml
evidence:
  evidence_refs:
  evidence_level:
  evidence_gaps:
  reviewer_notes:
```

Evidence supports the decision.

## 7. Risk and Assumptions

```yaml
risk_assumptions:
  risks:
  accepted_risks:
  assumptions:
  confidence:
  mitigations:
```

## 8. Authority

```yaml
authority:
  decision_owner:
  reviewer:
  approver:
  risk_owner:
  separation_of_duties:
```

Material decisions should preserve separation of duties.

```text
creator != reviewer
reviewer != approver
```

## 9. State Transition

```yaml
state_transition:
  from_state:
  to_state:
  transition_id:
  policy_results:
  validation_results:
  exception_refs:
```

A Decision Record may authorize exactly one material transition or explicitly list linked transitions.

## 10. Outcome and Review

```yaml
outcome_review:
  expected_outcome:
  review_date:
  review_cadence:
  success_metrics:
  actual_outcome:
  lessons_learned:
```

Decision quality should be measured over time.

## 11. Publishing

```yaml
publishing:
  publishable:
  publishing_status:
  published_at:
  published_version:
  canonical_url:
```

Some Decision Records may be private, but authority still requires durable recordkeeping.

## Minimal Example

```yaml
identity:
  id: decision:publish-theory-of-composition-v0-1-0
  name: Publish Theory of Composition v0.1.0
  version: 0.1.0

subject:
  artifact_id: theory:composition
  artifact_type: published-artifact
  artifact_version: 0.1.0

decision:
  decision_type: publish
  decision_status: approved
  decision_summary: Publish the canonical initial release of the Theory of Composition.

rationale:
  problem: Foundation requires a canonical theory for composition.
  reason: Composition is the core mechanism that turns frameworks into systems.

alternatives:
  considered:
    - option: Keep as draft only
      reason_for_rejection: Draft has no authority and cannot guide platform implementation.

evidence:
  evidence_level: internal-foundation

risk_assumptions:
  risks:
    - early theory may evolve
  confidence: medium

authority:
  decision_owner: OpenFrameworks Foundation
  separation_of_duties: false

state_transition:
  from_state: validated
  to_state: published

publishing:
  publishable: true
  publishing_status: published
```

## Validation Rules

A Decision Record is valid only when:

- subject exists
- decision type exists
- decision status exists
- rationale exists
- decision owner exists
- state transition is declared where applicable

A Decision Record is publishable only when:

- evidence is declared
- authority is declared
- risks or assumptions are declared where material
- alternatives are declared for recommendations and approvals
- blocking governance issues are resolved

## Relationship to Meta State Machine

State transitions should link to Decision Records.

```text
Transition without decision = weak governance
Decision without transition = advisory record
```

## Relationship to Meta Policy

Meta Policy may require a Decision Record before allowing a gate transition.

## Relationship to Platform

The platform must create or link a Decision Record for material transitions, including publication, certification, accreditation, deprecation, revocation, and exception approval.

## Final Statement

```text
A Decision Record makes OpenFrameworks authority explainable and auditable.
```
