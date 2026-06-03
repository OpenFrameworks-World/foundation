# Graph Completeness Specification (v0.1)

## Status

The OpenFrameworks graph is coherent but not yet complete.

It has a strong vertical chain, but it still needs explicit value, feedback, adoption, conformance, and publishing-state closure.

## Current Canonical Chain

```text
Framework
  -> Framework Card
  -> Framework Blueprint
  -> Operating Model
  -> Architecture Model
  -> System
  -> Value
```

## Current Supporting Layers

```text
Constitution
  -> Theory of Composition
  -> Conformance Schema
  -> Execution Engine
  -> Registry and Composition Graph
  -> Publishing Gate
```

## Completeness Test

A graph is complete only if it answers these questions:

1. What is being represented?
2. What capability does it provide?
3. How is it represented as a card?
4. How does it compose with other frameworks?
5. What blueprint does the composition produce?
6. How does the blueprint behave operationally?
7. What architecture implements the behavior?
8. What system realizes the architecture?
9. What value does the system create?
10. What evidence proves the value?
11. Who owns and governs every node?
12. What is the publishing state of every node?
13. What trust, risk, and confidence apply?
14. What lifecycle state applies?
15. What feedback changes the graph over time?

## Missing Required Nodes

The graph still needs explicit specifications for:

- Value Model
- Outcome Model
- Evidence Model
- Trust Model
- Risk Model
- Adoption Model
- Feedback Model
- Measurement Model
- Publishing State Model
- Conformance Result Model
- Certification Claim Model
- Accreditation Record Model

## Missing Required Edges

The graph still needs canonical relationship types for:

- realizes_value
- produces_outcome
- measured_by
- evidenced_by
- trusted_by
- certified_by
- accredited_by
- adopted_by
- governed_by
- published_as
- conforms_to
- feeds_back_into
- replaces
- deprecates
- improves

## Complete Graph Shape

```text
Framework
  -> Framework Card
  -> Framework Blueprint
  -> Operating Model
  -> Architecture Model
  -> System
  -> Value Model
  -> Outcome
  -> Measurement
  -> Evidence
  -> Trust
  -> Certification
  -> Accreditation
  -> Adoption
  -> Feedback
  -> Foundation Evolution
```

## Closed Loop Requirement

The graph is incomplete until it loops back from real-world use into foundation improvement.

```text
Published Framework
  -> Adoption
  -> Measurement
  -> Evidence
  -> Feedback
  -> Foundation Change Proposal
  -> New Release
```

## Node Completeness Rule

Every graph node must declare:

```yaml
node:
  id:
  type:
  capability:
  owner:
  lifecycle_state:
  publishing_state:
  evidence_refs:
  trust:
  relationships:
```

## Edge Completeness Rule

Every graph edge must declare:

```yaml
edge:
  source:
  target:
  relationship_type:
  direction:
  rationale:
  evidence_refs:
  confidence:
  lifecycle_state:
```

## Publishability Rule

A graph segment is publishable only when:

- all required nodes exist
- all required edges are typed
- ownership is declared
- capability preservation is verified
- evidence exists
- trust and risk are assessed
- publishing states are valid
- conformance results are recorded

## Current Verdict

```text
Graph status: coherent but incomplete.
```

The next required artifact is:

```text
Value Model Specification v0.1
```

because the current graph reaches System but does not yet formally close the chain to Value, Outcome, Measurement, Evidence, and Feedback.
