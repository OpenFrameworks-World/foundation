# Living Foundation Operating Model

OpenFrameworks Foundation must not become a static specification repository.

It is a living standard that evolves through evidence, implementation feedback, conformance testing, governance review, and versioned releases.

## Problem

A foundation becomes static when it only contains documents, diagrams, schemas, and principles without feedback from real platform usage.

Static foundations drift away from reality.

OpenFrameworks Foundation must remain connected to implementation, adoption, validation, and measurable outcomes.

## Operating Principle

```text
Foundation defines the contract.
Platform exercises the contract.
Conformance tests verify the contract.
Feedback improves the contract.
Versioning stabilizes the contract.
```

## Living Foundation Loop

```text
Foundation Model
  -> Platform Implementation
  -> Registry Data
  -> Validation Results
  -> Benchmark Results
  -> Governance Decisions
  -> Adoption Feedback
  -> Foundation Change Proposal
  -> Review
  -> Versioned Release
```

## Required Living Mechanisms

### 1. Versioned Releases

Foundation must publish versioned releases.

Examples:

- `v0.1.0-draft`
- `v0.2.0-alpha`
- `v1.0.0`

Every platform implementation must declare which foundation version it supports.

### 2. Conformance Tests

Foundation must include conformance tests for:

- schema validity
- required fields
- lifecycle transitions
- vendor-neutrality requirements
- trust and scoring gates
- certification claims
- accreditation claims
- traceability completeness

### 3. Change Proposals

Material changes must go through Foundation Change Proposals.

A proposal should include:

- problem
- affected model
- proposed change
- rationale
- examples
- compatibility impact
- migration guidance
- review decision

### 4. Reference Examples

Foundation must include executable reference examples.

Examples:

- valid framework card
- invalid framework card
- valid capability card
- valid recommendation record
- valid certification claim
- valid accreditation record
- valid lifecycle transition

### 5. Implementation Feedback

Platform repositories should report:

- validation failures
- unclear definitions
- missing fields
- impossible constraints
- scoring ambiguity
- workflow gaps
- adoption blockers

### 6. Compatibility Policy

Foundation changes must declare compatibility level:

- patch: clarification or non-breaking update
- minor: additive model change
- major: breaking schema, ontology, or governance change

### 7. Deprecation Policy

Foundation may deprecate fields, terms, states, or rules.

Deprecations must include:

- reason
- replacement
- migration path
- sunset date

## Source of Truth Rules

- Foundation owns meaning.
- Platform owns execution.
- Tests connect meaning to execution.
- Releases prevent uncontrolled drift.
- Feedback prevents static decay.

## Required Repository Additions

```text
rfcs/                  # Foundation Change Proposals
conformance/           # Tests and validation cases
releases/              # Versioned release notes
examples/valid/        # Valid reference examples
examples/invalid/      # Invalid reference examples
compatibility/         # Compatibility and deprecation policy
adoption/              # Implementation feedback and adoption reports
```

## Core Rule

A foundation object is not stable until it has:

- definition
- schema or formal representation
- valid example
- invalid example
- conformance test
- lifecycle policy
- versioned release status

## Relationship to Platform

The platform must not blindly implement the latest foundation draft.

The platform must pin a foundation version and report incompatibilities through change proposals.

## Anti-Static Rule

No foundation release may be declared stable unless at least one platform implementation validates against it.
