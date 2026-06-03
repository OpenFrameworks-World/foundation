# Canonical Vocabulary Specification (v0.1)

## Overview

The Canonical Vocabulary defines the allowed terms used by the OpenFrameworks runtime and governance kernels.

The vocabulary makes the framework graph consistent, queryable, enforceable, and interoperable.

```text
Vocabulary = allowed entity types + relationship types + state types + event types + action types + decision types
```

## Purpose

The Canonical Vocabulary prevents every artifact, registry, platform implementation, and organization from inventing incompatible names for the same concepts.

It answers:

- What types of entities exist?
- What relationships are allowed?
- What states are valid?
- What events can happen?
- What actions can be performed?
- What decisions can authorize change?

## 1. Entity Types

Entity types describe what exists in the OpenFrameworks graph.

```text
framework
framework-card
framework-blueprint
operating-model
architecture-model
system
value-model
purpose
goal
objective
outcome
measurement
evidence-record
trust-record
risk-record
decision-record
temporal-record
certification-claim
accreditation-record
adoption-record
feedback-record
foundation-change-proposal
published-artifact
actor
organization
role
policy
control
requirement
metric
interface
composition-contract
```

## 2. Relationship Types

Relationship types describe how entities connect.

```text
composes
composed_of
extends
implements
governs
validates
depends_on
requires
enables
supports
measures
evidences
updates_trust
certifies
accredits
adopts
publishes
triggers
authorizes
replaces
replaced_by
supersedes
superseded_by
conflicts_with
compatible_with
owned_by
maintained_by
reviewed_by
approved_by
risk_owned_by
feedback_for
changes
```

## 3. Lifecycle State Types

Lifecycle states describe the maturity and operational authority of an artifact.

```text
draft
candidate
reviewed
validated
published
adopted
measured
improved
deprecated
archived
blocked
rejected
revoked
superseded
```

## 4. Publishing State Types

Publishing states describe whether an artifact has authority.

```text
draft
candidate
reviewed
published
adopted
deprecated
archived
blocked
```

## 5. Conformance State Types

Conformance states describe validation against the Foundation contract.

```text
draft
not-tested
passed
failed
blocked
waived
```

## 6. Event Types

Events describe what happened.

```text
artifact_created
artifact_updated
review_requested
review_completed
validation_requested
validation_passed
validation_failed
policy_evaluated
policy_passed
policy_failed
publish_requested
artifact_published
artifact_deprecated
artifact_archived
evidence_added
trust_recalculated
certification_requested
certification_issued
certification_expired
accreditation_requested
accreditation_granted
accreditation_expired
adoption_recorded
measurement_recorded
feedback_received
foundation_change_proposed
foundation_release_published
```

## 7. Action Types

Actions describe intentional operations performed by an actor, workflow, system, or agent.

```text
create
update
review
validate
approve
reject
publish
certify
accredit
deprecate
revoke
archive
measure
recalculate_trust
record_evidence
record_adoption
record_feedback
propose_change
release
rollback
supersede
```

## 8. Decision Types

Decision types describe material choices that authorize or explain change.

```text
publish
approve
reject
certify
accredit
deprecate
archive
revoke
supersede
exception
risk-acceptance
composition-approval
foundation-change
release-approval
rollback-approval
```

## 9. Trust Levels

Trust levels describe confidence in claims.

```text
unknown
low
medium
high
verified
```

## 10. Evidence Levels

Evidence levels describe quality of support for a claim.

```text
none
weak
partial
credible
verified
independent
reproducible
```

## 11. Compatibility Values

Compatibility values describe whether entities can compose or interoperate.

```text
unknown
compatible
conditional
incompatible
deprecated
```

## 12. Value Status Types

Value status describes whether expected value has been realized.

```text
hypothesis
planned
measuring
partially-realized
realized
not-realized
abandoned
```

## Vocabulary Governance

New vocabulary terms require a Foundation Change Proposal when they affect:

- schema compatibility
- graph relationships
- validators
- policy gates
- state transitions
- publishing authority
- platform implementation

## Anti-Drift Rule

Implementations must use canonical vocabulary terms unless an approved extension namespace is declared.

## Extension Rule

Organizations may extend vocabulary using namespaced terms.

Example:

```text
acme:internal-risk-review
```

Namespaced terms must not replace canonical terms when a canonical term already exists.

## Final Statement

```text
The Canonical Vocabulary makes the OpenFrameworks graph consistent, enforceable, and interoperable.
```
