# Publishing Gate Model

Publishing is the activation gate for OpenFrameworks Foundation.

A foundation object is not authoritative merely because it exists in the repository. It becomes authoritative only when it is published through the governed publishing process.

## Core Principle

```text
Draft is not authority.
Merge is not authority.
Publishing is authority.
```

## Why Publishing Is the Gate

Without a publishing gate, the foundation becomes a static document store or an uncontrolled collection of drafts.

Publishing makes the foundation living by forcing every authoritative artifact to pass:

- schema validation
- conformance tests
- provenance checks
- governance review
- version assignment
- compatibility review
- release notes
- public publication
- downstream implementation declaration

## Artifact States

```text
draft
  -> candidate
  -> reviewed
  -> approved
  -> published
  -> adopted
  -> deprecated
  -> archived
```

Only `published` artifacts are normative.

## Publishing Levels

### Draft

Work in progress. Not authoritative.

### Candidate

Ready for review and conformance testing.

### Published

Normative foundation artifact. Platform implementations may depend on it.

### Adopted

Published artifact with at least one implementation consuming it.

### Deprecated

Still available, but replaced or scheduled for removal.

### Archived

Retained for historical and audit purposes only.

## Publishable Foundation Artifacts

- ontology
- JSON-LD context
- JSON Schemas
- glossary terms
- taxonomy records
- governance policies
- lifecycle rules
- scoring dimensions
- certification rules
- accreditation rules
- conformance tests
- reference examples
- release bundles

## Publishing Requirements

An artifact may be published only when it has:

- stable identifier
- semantic version
- owner
- reviewer
- approver
- provenance
- license declaration
- compatibility status
- valid example where applicable
- invalid example where applicable
- conformance test where applicable
- changelog entry
- release note entry

## Foundation Release Bundle

A published foundation release is a bundle:

```yaml
release:
  id:
  version:
  status:
  artifacts:
  schemas:
  ontology:
  policies:
  examples:
  conformance_tests:
  compatibility:
  changelog:
  published_at:
  approved_by:
```

## Platform Consumption Rule

The platform must pin a published foundation release.

```yaml
foundation:
  repository: OpenFrameworks-World/foundation
  version: v0.1.0
  status: published
```

The platform must not depend on unpublished drafts except in experimental branches.

## Publishing Workflow

```text
Create or update artifact
  -> Validate structure
  -> Run conformance tests
  -> Review provenance
  -> Review compatibility
  -> Review governance impact
  -> Approve release candidate
  -> Publish versioned release
  -> Generate public documentation
  -> Notify platform consumers
  -> Track adoption
```

## Publishing Gate Checks

Before publication, the gate must verify:

- required fields exist
- schema validation passes
- examples validate correctly
- invalid examples fail correctly
- lifecycle state is eligible
- reviewer and approver are distinct
- vendor-neutrality rules pass when relevant
- breaking changes are declared
- migration guidance exists for breaking changes
- release notes are present

## Normative vs Informative

Foundation artifacts must declare whether they are normative or informative.

### Normative

Required for conformance.

Examples:

- schemas
- ontology context
- lifecycle states
- scoring gates
- certification levels
- publishing rules

### Informative

Helpful guidance, but not required for conformance.

Examples:

- explanatory guides
- examples
- commentary
- tutorials
- rationale documents

## Anti-Static Rule

If an artifact is not published, adopted, deprecated, or archived, it is only draft material.

Draft material must not be treated as foundation authority.

## Core Rule

Foundation becomes real only when published.

Platform becomes compliant only when it consumes a published foundation release and passes conformance.
