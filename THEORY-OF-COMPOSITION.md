# The Theory of Composition

OpenFrameworks is built on two constitutional principles:

```text
Everything is a framework.
Everything must be composable without losing capability.
```

The Theory of Composition explains the second principle.

## 1. Composition

Composition is the act of combining frameworks or framework elements to create a larger, more capable framework while preserving the capability, meaning, provenance, governance, and trust of each part.

A composition is valid only when the parts retain their useful capability after being combined.

## 2. Capability Preservation

Composition must preserve capability.

A framework element has capability when it can perform, represent, explain, govern, evaluate, teach, operate, or improve something in a useful way.

If composition destroys that capability, the composition is invalid.

```text
Valid Composition
= combination + preserved capability + increased usefulness
```

## 3. Composition Is Not Aggregation

Aggregation merely places things together.

Composition makes them work together.

```text
Aggregation:
  A + B exist beside each other.

Composition:
  A + B interact without losing their capability.
```

A folder of documents is not a composition.

A governed blueprint where each document has role, relationship, capability, evidence, and lifecycle is a composition.

## 4. Composition Is Not Absorption

Absorption destroys identity.

Composition preserves identity.

When one framework absorbs another so completely that the original capability, provenance, or governance disappears, the result is not valid composition.

```text
Composition preserves identity.
Absorption erases identity.
```

## 5. Composition Is Not Replacement

Replacement substitutes one framework for another.

Composition allows frameworks to cooperate.

A framework may be replaceable, but replacement and composition are different operations.

## 6. Composition Requires Boundaries

A framework can compose only when its boundaries are clear.

Every composable framework must declare:

- purpose
- scope
- capability
- inputs
- outputs
- dependencies
- constraints
- assumptions
- extension points
- incompatibilities
- governance owner
- provenance
- version

Without boundaries, composition becomes confusion.

## 7. Composition Requires Interfaces

Frameworks compose through interfaces.

An interface may be:

- a schema
- a relationship
- an API
- a workflow
- a policy boundary
- a capability contract
- a publishing contract
- a governance rule
- a semantic mapping
- a data exchange format

The interface defines how one framework connects to another.

## 8. Composition Requires Contracts

A contract defines what must remain true when frameworks compose.

A composition contract should declare:

```yaml
composition_contract:
  participants:
  purpose:
  preserved_capabilities:
  added_capabilities:
  interfaces:
  dependencies:
  constraints:
  assumptions:
  risks:
  evidence:
  governance:
  validation:
```

## 9. Composition Has Direction

Composition is not always symmetric.

A policy framework may govern a control framework.

A capability framework may require an implementation framework.

A trust framework may validate a certification framework.

Therefore every composition must declare direction.

Examples:

```text
Policy Framework -> governs -> Control Framework
Capability Framework -> requires -> Implementation Framework
Evidence Framework -> supports -> Trust Framework
Publishing Framework -> activates -> Framework Authority
```

## 10. Composition Has Roles

Each participating framework has a role in the composition.

Common roles:

- source
- target
- parent
- child
- dependency
- extension
- validator
- governor
- evidence provider
- implementation
- measurement source

Composition without roles becomes accidental coupling.

## 11. Composition Has Compatibility

Frameworks may be compatible, conditionally compatible, incompatible, or unknown.

Compatibility must be declared and tested.

```yaml
compatibility:
  status: compatible | conditional | incompatible | unknown
  rationale:
  evidence:
  constraints:
  required_adapters:
```

## 12. Composition Has Loss

Every composition may introduce loss.

Possible losses:

- meaning loss
- capability loss
- context loss
- governance loss
- provenance loss
- trust loss
- operational loss
- performance loss
- compliance loss

OpenFrameworks requires loss to be declared.

A composition is not valid if critical capability loss is hidden.

## 13. Composition Has Gain

Composition should create gain.

Possible gains:

- increased capability
- broader applicability
- better governance
- stronger trust
- improved usability
- better traceability
- reduced duplication
- better decision quality
- faster adoption
- higher value realization

A composition should justify its gain.

## 14. Composition Has Evidence

Composition claims require evidence.

A statement such as:

```text
Framework A composes with Framework B
```

must be supported by evidence, test results, examples, implementation records, or governance review.

## 15. Composition Has Governance

Composition is a governed act.

A material composition must declare:

- who designed it
- who reviewed it
- who approved it
- who owns it
- who maintains it
- who can change it
- who accepts its risks

Composition without accountability is not publishable.

## 16. Composition Has Lifecycle

A composition has its own lifecycle.

```text
draft
  -> reviewed
  -> validated
  -> published
  -> adopted
  -> measured
  -> improved
  -> deprecated
  -> archived
```

A composition can outlive one of its parts only if replacement rules are declared.

## 17. Composition Has Substitution

A composable framework should support substitution.

If a component framework is replaced, the larger composition should preserve intended capability where possible.

Substitution requires:

- equivalent capability
- compatible interface
- acceptable risk
- migration path
- governance approval

## 18. Composition Has Context

A composition valid in one context may fail in another.

Context includes:

- domain
- organization
- jurisdiction
- maturity
- skills
- budget
- risk appetite
- compliance requirements
- operational environment

Composition claims must declare context.

## 19. Composition Has Constraints

Composition is shaped by constraints.

Examples:

- budget
- time
- regulation
- security policy
- vendor neutrality
- data residency
- interoperability
- licensing
- skills
- performance

Constraints must be explicit.

## 20. Composition Has Failure Modes

Composition may fail when:

- boundaries are unclear
- interfaces are missing
- assumptions conflict
- dependencies are hidden
- governance is absent
- capability is lost
- context changes
- evidence is weak
- ownership is unclear
- trust is overstated

A published composition should document known failure modes.

## 21. Composition Is Recursive

A composition can itself become a framework.

```text
Framework + Framework = Composed Framework
Composed Framework + Framework = Larger Framework
```

This is how framework design systems grow.

## 22. Composition Is How Value Emerges

Individual frameworks are useful.

Composed frameworks become systems.

Systems create value.

```text
Framework
  -> Composition
  -> Blueprint
  -> Operating Model
  -> System
  -> Value
```

## 23. Composition Law

The central law of OpenFrameworks composition is:

```text
A composition is valid only if every participating framework preserves its declared capability, and the composed whole creates additional useful capability.
```

## 24. Composition Test

To test a composition, ask:

1. What frameworks are being composed?
2. What capability does each framework bring?
3. What capability must be preserved?
4. What new capability is created?
5. What is lost?
6. What interfaces connect them?
7. What evidence supports the composition?
8. Who governs it?
9. What context is it valid in?
10. How can one part be replaced without breaking the whole?

If these cannot be answered, the composition is not ready to publish.

## 25. OpenFrameworks Composition Principle

```text
Everything must be composable without losing capability.
```

This means every framework must be designed with identity, boundary, interface, contract, evidence, governance, lifecycle, and substitution in mind.

Composition is the mechanism that turns frameworks into systems and systems into value.
