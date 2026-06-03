# Meta Policy Specification (v0.1)

## Overview

The Meta Policy defines the universal permission, publishing, trust, evidence, lifecycle, certification, and accreditation rules for OpenFrameworks artifacts.

Validation answers:

```text
Is this artifact structurally correct?
```

Policy answers:

```text
Should this artifact be allowed to move forward?
```

An artifact may pass Meta Contract validation and still be blocked by Meta Policy.

## Position in the Pipeline

```text
Meta Contract Validation
  -> Artifact-Specific Validation
  -> Meta Policy Evaluation
  -> Conformance Validation
  -> Publishing Gate
```

## Applies To

Meta Policy applies to every OpenFrameworks artifact, including:

- framework
- framework card
- framework blueprint
- operating model
- architecture model
- system
- value model
- evidence record
- trust record
- certification claim
- accreditation record
- published artifact
- feedback record
- foundation change proposal

## Universal Policy Principles

### 1. No Orphan Artifacts

Every artifact must have an owner.

```text
No owner, no publication.
```

### 2. No Capability-Free Artifacts

Every artifact must declare a capability.

```text
No capability, no framework.
```

### 3. No Hidden Context

Every artifact must declare where it is valid and where it is not valid when known.

```text
No context, no reliable reuse.
```

### 4. No Ungoverned Publishing

Publishing requires governance accountability.

```text
Draft is not authority.
Merge is not authority.
Publishing is authority.
```

### 5. No Trust Without Evidence

Trust claims must be backed by evidence.

```text
No evidence, no trust claim.
```

### 6. No Certification Without Review

Certification requires review, evidence, and conformance.

```text
No review, no certification.
```

### 7. No Accreditation Without Context

Accreditation is valid only within a declared context.

```text
No context, no accreditation.
```

### 8. No Composition Without Capability Preservation

Composition must preserve capability.

```text
If capability is lost, composition is invalid.
```

### 9. No Static Authority

Published authority must have lifecycle, review cadence, and feedback path.

```text
No review path, no durable authority.
```

## Policy Gates

## Gate 1: Draft Acceptance

An artifact may enter draft state when:

- identity exists
- artifact type exists
- owner exists
- capability hypothesis exists

## Gate 2: Review Eligibility

An artifact may enter review when:

- Meta Contract validation passes
- required sections are present
- context is declared
- lifecycle state is valid
- publishing status is draft or candidate

## Gate 3: Publish Eligibility

An artifact may be published only when:

- Meta Contract validation passes
- artifact-specific validation passes
- owner exists
- reviewer exists where required
- approver exists where required
- evidence exists for material claims
- trust and risk are assessed where applicable
- blocking issues are empty
- lifecycle state is eligible
- publishing status is candidate or reviewed
- conformance status is passed or explicitly waived by approved exception

## Gate 4: Certification Eligibility

An artifact may be certified only when:

- it is published
- evidence level is sufficient
- reviewer and approver are distinct where required
- conformance status is passed
- trust and risk are evaluated
- certification scope is declared
- expiry or review cadence is declared

## Gate 5: Accreditation Eligibility

An artifact may be accredited only when:

- it is published or certified
- accreditation context is declared
- usage scope is declared
- risk owner exists
- controls are mapped where applicable
- approval authority exists
- review cadence is declared

## Gate 6: Graph Inclusion

An artifact may enter the production graph only when:

- identity is stable
- lifecycle state is not draft
- publishing status is not blocked
- relationship edges are typed
- owner exists
- conformance status is not failed

## Gate 7: Deprecation

An artifact may be deprecated when:

- replacement is declared or rationale is provided
- affected dependents are identified
- migration guidance exists where applicable
- deprecation date is declared

## Gate 8: Archival

An artifact may be archived when:

- it is retired, deprecated, superseded, or invalidated
- final evidence and lifecycle state are preserved
- audit trail is retained

## Policy Decision Output

```json
{
  "artifact_id": "string",
  "policy_result": "allow | deny | warn | requires_exception",
  "gate": "string",
  "reasons": [],
  "required_actions": [],
  "exception_allowed": true
}
```

## Exception Policy

Exceptions are allowed only when:

- exception owner exists
- risk owner accepts risk
- expiry date exists
- rationale exists
- compensating controls exist where applicable

No exception may be permanent by default.

## Policy Severity

Policy findings may be:

- blocking
- warning
- advisory

Blocking findings prevent publication or transition.

## Relationship to Meta Validator

The Meta Validator checks structure.

The Meta Policy checks permission.

Both must pass before publishing.

## Relationship to Platform

The platform must evaluate Meta Policy before:

- publishing artifacts
- certifying artifacts
- accrediting artifacts
- adding artifacts to the production graph
- changing lifecycle state

## Final Statement

```text
The Meta Policy decides whether a valid OpenFrameworks artifact is allowed to become authoritative.
```
