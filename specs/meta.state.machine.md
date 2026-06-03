# Meta State Machine Specification (v0.1)

## Overview

The Meta State Machine defines the universal lifecycle states, transitions, guards, approvals, exceptions, and rollback rules for every OpenFrameworks artifact.

Validation answers:

```text
Is this structurally correct?
```

Policy answers:

```text
Should this be allowed?
```

State machine answers:

```text
Where is this artifact in its lifecycle, and what transition is allowed next?
```

## Position in the Governance Kernel

```text
Constitution
  -> Theory
  -> Meta Contract
  -> Meta Schema
  -> Meta Validator
  -> Meta Policy
  -> Meta State Machine
  -> Conformance Engine
  -> Publishing Gate
```

## Applies To

The Meta State Machine applies to every OpenFrameworks artifact:

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
- adoption record
- feedback record
- foundation change proposal
- published artifact

## Universal States

```text
draft
  -> candidate
  -> reviewed
  -> validated
  -> published
  -> adopted
  -> measured
  -> improved
  -> deprecated
  -> archived
```

Additional exceptional states:

```text
blocked
rejected
revoked
superseded
```

## State Definitions

### draft

Artifact exists but is not authoritative.

### candidate

Artifact is complete enough to enter formal review.

### reviewed

Artifact has completed human or governance review.

### validated

Artifact has passed structural, policy, conformance, or artifact-specific validation.

### published

Artifact is authoritative within its declared scope.

### adopted

Artifact is used by at least one declared adopter.

### measured

Artifact has measurement or value evidence.

### improved

Artifact has been revised based on feedback or measurement.

### deprecated

Artifact is still visible but no longer preferred.

### archived

Artifact is retained for historical, audit, or reference purposes only.

### blocked

Artifact cannot proceed until blocking issues are resolved.

### rejected

Artifact was reviewed and rejected.

### revoked

Artifact previously had authority but lost it.

### superseded

Artifact has been replaced by another artifact.

## Universal Transition Object

```yaml
transition:
  id:
  artifact_id:
  from_state:
  to_state:
  actor:
  requested_at:
  decided_at:
  rationale:
  evidence_refs:
  policy_results:
  validation_results:
  approvals:
  exceptions:
  rollback_target:
```

## Transition Guards

### draft -> candidate

Requires:

- identity exists
- artifact type exists
- owner exists
- capability hypothesis exists

### candidate -> reviewed

Requires:

- Meta Contract validation passed
- required sections present
- reviewer assigned
- context declared

### reviewed -> validated

Requires:

- review completed
- blocking review comments resolved
- artifact-specific validation passed where applicable
- policy evaluation is allow, warn, or approved exception

### validated -> published

Requires:

- publishing gate passed
- approver exists where required
- evidence exists for material claims
- version assigned
- release notes present
- no blocking issues

### published -> adopted

Requires:

- adopter declared
- adoption context declared
- usage scope declared
- risk owner exists where applicable

### adopted -> measured

Requires:

- measurement plan exists
- at least one measurement record exists
- evidence path exists

### measured -> improved

Requires:

- feedback exists
- proposed improvement exists
- affected artifacts identified

### improved -> candidate

Requires:

- new version prepared
- compatibility impact declared
- migration guidance declared when required

### published -> deprecated

Requires:

- rationale exists
- replacement declared or no-replacement rationale exists
- dependent artifacts identified
- deprecation notice prepared

### deprecated -> archived

Requires:

- final lifecycle state recorded
- audit evidence retained
- dependent artifacts migrated or exception recorded

## Exceptional Transitions

### any -> blocked

Allowed when a blocking policy, validation, evidence, governance, or publishing issue exists.

### blocked -> candidate

Requires blocking issues resolved.

### candidate/reviewed/validated -> rejected

Requires review rationale.

### published/adopted/measured -> revoked

Requires revocation reason, affected dependents, risk review, and audit record.

### published/adopted/measured/deprecated -> superseded

Requires replacement artifact and migration guidance.

## Rollback Rules

Rollback is allowed only when:

- target state is declared
- rollback rationale exists
- affected artifacts are identified
- audit trail is preserved
- risk is assessed

Published artifacts may not be silently rolled back.

## Separation of Duties

For material transitions:

```text
creator != reviewer
reviewer != approver
```

Exceptions must be documented.

## Publishing Rule

Only `published` artifacts are authoritative.

```text
Draft is not authority.
Merge is not authority.
Validation is not authority.
Publishing is authority.
```

## Platform Requirements

The platform must:

- enforce allowed transitions
- record every transition
- prevent silent state changes
- block invalid publishing transitions
- expose transition history
- support rollback with audit trail
- link transitions to policy and validation results

## Final Statement

```text
The Meta State Machine turns OpenFrameworks lifecycle into executable governance.
```
