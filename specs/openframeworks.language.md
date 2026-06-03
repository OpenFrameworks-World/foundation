# OpenFrameworks Language Specification (v0.1)

## Overview

OpenFrameworks Language is the canonical interaction language for operating the OpenFrameworks graph.

The graph defines what exists.

The language defines how humans, agents, validators, registries, workflows, and platforms act on it.

```text
Data Model -> Graph Schema -> Language -> Runtime -> Platform
```

## Purpose

OpenFrameworks Language exists to express framework operations in a consistent, auditable, composable, and machine-actionable way.

It answers:

- How do we define a framework?
- How do we compose frameworks?
- How do we validate an artifact?
- How do we publish authority?
- How do we query the graph?
- How do we explain a decision?
- How do we certify or accredit an artifact?
- How do we trace value and evidence?

## Constitutional Basis

The language derives from two principles:

```text
Everything is a framework.
Everything must be composable without losing capability.
```

Therefore the language must support:

- representation
- composition
- capability preservation
- validation
- publishing
- governance
- trust
- feedback

## Core Statement Form

Every OpenFrameworks Language statement has this general shape:

```text
<verb> <subject> [with <object>] [under <context>] [because <rationale>] [using <evidence>] [as <state>]
```

Examples:

```text
define framework identity-governance
compose framework identity with policy under enterprise-iam-context
validate framework-card identity-governance using meta-contract
publish framework-card identity-governance as v1.0.0
explain decision publish-theory-of-composition-v0.1.0
```

## Core Verbs

### Definition Verbs

```text
define
classify
describe
version
```

### Composition Verbs

```text
compose
extend
connect
replace
supersede
```

### Governance Verbs

```text
review
approve
reject
decide
accept-risk
grant-exception
```

### Validation Verbs

```text
validate
conform
check
block
waive
```

### Publishing Verbs

```text
publish
deprecate
archive
release
```

### Trust Verbs

```text
evidence
measure
score-trust
assess-risk
certify
accredit
```

### Query Verbs

```text
find
show
trace
explain
compare
impact
```

### Runtime Verbs

```text
trigger
execute
transition
record
observe
```

### Feedback Verbs

```text
adopt
feedback
propose-change
improve
```

## Canonical Statements

## 1. Define Framework

```text
define framework <id> capability <capability> context <context>
```

Meaning:

Create or declare a framework entity with capability and context.

## 2. Create Framework Card

```text
define framework-card <id> represents framework <framework-id>
```

Meaning:

Create the canonical publishable representation of a framework.

## 3. Compose Frameworks

```text
compose framework <a> with framework <b> into blueprint <blueprint-id>
```

Meaning:

Declare a governed composition of frameworks.

## 4. Validate Artifact

```text
validate artifact <id> using meta-contract
```

Meaning:

Run Meta Contract validation.

## 5. Evaluate Policy

```text
check policy for artifact <id> at gate <gate-name>
```

Meaning:

Evaluate Meta Policy for a lifecycle or publishing gate.

## 6. Publish Artifact

```text
publish artifact <id> as version <version>
```

Meaning:

Activate authority through the publishing gate.

## 7. Explain Decision

```text
explain decision <id>
```

Meaning:

Return rationale, alternatives, evidence, risk, authority, and state transition.

## 8. Trace Trust

```text
trace trust for artifact <id>
```

Meaning:

Show evidence, risk, confidence, temporal trust records, and inherited/non-inherited claims.

## 9. Impact Analysis

```text
impact artifact <id>
```

Meaning:

Show affected dependents, relationships, compositions, blueprints, systems, accreditations, and adopters.

## 10. Value Trace

```text
trace value for artifact <id>
```

Meaning:

Trace from purpose to outcome to measurement to evidence to feedback.

## Language Objects

OpenFrameworks Language operates on:

- entity
- relationship
- state
- event
- action
- decision
- temporal record
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
- foundation release

## Query Patterns

### Purpose Query

```text
why framework <id>
```

Returns purpose, goal, objective, outcome, and value hypothesis.

### Composition Query

```text
show composition of blueprint <id>
```

Returns participating framework cards, composition contract, preserved capability, added capability, and interfaces.

### Decision Query

```text
why published artifact <id>
```

Returns Decision Record.

### Temporal Query

```text
show artifact <id> at time <timestamp>
```

Returns point-in-time state.

### Trust Query

```text
what evidence supports trust for <id>
```

Returns evidence graph.

### Adoption Query

```text
who adopted artifact <id>
```

Returns adoption records and feedback.

## Language Requirements

The language must be:

- human-readable
- machine-actionable
- graph-aware
- policy-aware
- temporal
- auditable
- composable
- extensible

## Extension Rule

Organizations may extend the language using namespaced verbs and objects.

Example:

```text
acme:approve-security-risk artifact <id>
```

Extensions must not replace canonical verbs where canonical verbs already exist.

## Relationship to Runtime Kernel

Language statements compile into runtime primitives.

```text
Language Statement
  -> Event
  -> Action
  -> Validation
  -> Policy
  -> Decision
  -> State Transition
  -> Graph Update
```

## Relationship to Platform

The platform may expose this language through:

- CLI
- API
- UI commands
- agent instructions
- workflow definitions
- policy rules
- graph queries

## Final Statement

```text
OpenFrameworks Language is the canonical way to define, compose, validate, publish, query, explain, and evolve frameworks.
```
