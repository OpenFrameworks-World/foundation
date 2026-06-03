# Temporal Record Specification (v0.1)

## Overview

A Temporal Record is the canonical OpenFrameworks artifact for representing time, validity, history, expiry, observation, review, and change.

Without time, the OpenFrameworks graph is only a snapshot.

With time, the OpenFrameworks graph becomes a living system.

```text
Temporal Record = valid time + observed time + recorded time + effective time + review time + expiry time
```

## Purpose

Temporal Records make OpenFrameworks artifacts historically traceable, auditable, reviewable, and evolvable.

They answer:

- When was this artifact created?
- When did it become valid?
- When did it become authoritative?
- When was it observed?
- When was it recorded?
- When does it expire?
- When must it be reviewed?
- When was it superseded?
- What was true at a given time?

## Applies To

Temporal Records apply to every OpenFrameworks artifact, including:

- framework
- framework card
- framework blueprint
- operating model
- architecture model
- system
- value model
- evidence record
- trust record
- risk record
- decision record
- certification claim
- accreditation record
- adoption record
- feedback record
- published artifact
- foundation release

## Required Temporal Fields

```yaml
temporal:
  created_at:
  updated_at:
  valid_from:
  valid_until:
  effective_at:
  observed_at:
  recorded_at:
  published_at:
  review_at:
  expires_at:
  superseded_at:
  archived_at:
```

## Temporal Meaning

### created_at

When the artifact was first created.

### updated_at

When the artifact was last modified.

### valid_from

When the artifact starts being valid in its declared context.

### valid_until

When the artifact stops being valid in its declared context.

### effective_at

When the artifact takes effect operationally.

### observed_at

When the represented fact, event, measurement, or evidence was observed.

### recorded_at

When the observation was recorded in OpenFrameworks.

### published_at

When the artifact became authoritative through the publishing gate.

### review_at

When the artifact must be reviewed.

### expires_at

When the artifact expires unless renewed.

### superseded_at

When the artifact was replaced by another artifact.

### archived_at

When the artifact moved to historical or audit-only status.

## Temporal Relationships

```yaml
temporal_relationships:
  previous_version:
  next_version:
  supersedes:
  superseded_by:
  replaces:
  replaced_by:
  derived_from:
  valid_during:
```

## Temporal Queries

The platform should support temporal questions:

```text
What was true on this date?
What version was active then?
What decision caused this change?
What trust score existed at that time?
What certification was valid then?
What accreditation had expired?
What evidence was available when the decision was made?
```

## Temporal Integrity Rules

### 1. No Silent Mutation

Published artifacts must not be silently overwritten.

A material change requires a new version or transition record.

### 2. No Authority Without Publication Time

An artifact cannot be authoritative without `published_at`.

### 3. No Certification Without Expiry

Certification must declare expiry or review cadence.

### 4. No Accreditation Without Validity Window

Accreditation must declare valid context and valid period.

### 5. No Evidence Without Observation Time

Evidence should declare when it was observed and when it was recorded.

### 6. No Trust Without Time

Trust scores should be time-bound.

A trust score without a timestamp is incomplete.

## Temporal State Example

```yaml
identity:
  id: framework:composition-theory
  name: Theory of Composition

temporal:
  created_at: 2026-06-03T00:00:00Z
  updated_at: 2026-06-03T00:00:00Z
  valid_from: 2026-06-03T00:00:00Z
  published_at: 2026-06-03T00:00:00Z
  review_at: 2026-09-03T00:00:00Z
  expires_at: null

temporal_relationships:
  previous_version: null
  next_version: null
```

## Version-Time Separation

Version and time are related but not identical.

```text
Version = identity of change
Time = when change occurs or applies
```

Example:

```text
v1.0 may be published on January 1.
v1.0 may become effective on February 1.
v1.0 may expire on December 31.
```

## Relationship to Decision Records

Every material temporal change should link to a Decision Record.

```text
Decision -> Transition -> Temporal Record
```

## Relationship to State Machine

State transitions must record time.

```yaml
transition:
  from_state:
  to_state:
  decided_at:
  effective_at:
  recorded_at:
```

## Relationship to Trust

Trust is temporal.

```yaml
trust_snapshot:
  trust_score:
  confidence_score:
  risk_score:
  calculated_at:
  valid_until:
  evidence_refs:
```

## Relationship to Publishing

Publishing creates authority at a point in time.

```text
Draft + Publishing Gate + published_at = Authoritative Artifact
```

## Platform Requirements

The platform must:

- preserve temporal history
- support point-in-time queries
- prevent silent overwrites of published artifacts
- link temporal changes to decisions
- track validity windows
- track expiry and review dates
- show supersession and replacement chains

## Final Statement

```text
Time turns the OpenFrameworks graph from a snapshot into a living, auditable system.
```
