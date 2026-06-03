# Meta Validator Specification (v0.1)

## Overview

The Meta Validator is the first executable validator in OpenFrameworks.

It validates every OpenFrameworks artifact against the Meta Contract before any artifact-specific validation runs.

```text
Meta Contract Validation
  -> Artifact-Specific Validation
  -> Composition Validation
  -> Conformance Validation
  -> Publishing Gate
```

## Purpose

The Meta Validator ensures every artifact has the universal structure required to be identifiable, composable, governable, traceable, publishable, trustworthy, measurable, and evolvable.

## Inputs

- artifact file
- Meta Contract JSON Schema
- Foundation version
- optional artifact-specific schema

## Required Validation Stages

### 1. Structural Validation

Checks whether required Meta Contract sections exist:

- identity
- type
- capability
- context
- governance
- lifecycle
- publishing
- versioning
- conformance

### 2. Capability Validation

Checks whether the artifact declares:

- primary capability
- capability statement
- capability boundaries where applicable
- capability loss risks where applicable

### 3. Governance Validation

Checks whether the artifact declares:

- owner
- lifecycle state
- publishing status
- review or approval requirements where applicable

### 4. Publishing Validation

Checks whether the artifact can be published.

An artifact is not publishable if:

- blocking issues exist
- required governance is missing
- lifecycle state is incompatible
- conformance status failed or blocked
- material claims lack evidence

### 5. Conformance Validation

Checks whether the artifact declares:

- foundation version
- schema references
- conformance status
- validation results where applicable

## Output

```json
{
  "artifact_id": "string",
  "valid": true,
  "publishable": false,
  "errors": [],
  "warnings": [],
  "required_next_actions": []
}
```

## Validation Result States

- valid
- invalid
- publishable
- not-publishable
- blocked
- warning

## Validator Rule

```text
If an artifact fails Meta Contract validation, no downstream validator should run.
```

## Relationship to Platform

The platform must run the Meta Validator before:

- accepting a framework card
- publishing an artifact
- computing trust
- issuing certification
- issuing accreditation
- adding the artifact to a production graph

## Relationship to Publishing

Publishing is blocked unless Meta Validator passes.

## Final Statement

```text
The Meta Validator is the first gate in the OpenFrameworks publishing pipeline.
```
