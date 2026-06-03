# OpenFrameworks Foundation

OpenFrameworks Foundation is the open standard, semantic model, governance language, and trust layer for framework intelligence.

It defines the canonical language used to describe, compare, govern, certify, accredit, and operationalize frameworks, standards, protocols, methodologies, operating models, governance models, maturity models, benchmarks, reference architectures, and implementation patterns.

## Purpose

Create a vendor-neutral, evidence-driven, governance-first foundation for framework intelligence.

The foundation exists so every framework-related decision can be:

- explainable
- auditable
- evidence-backed
- vendor-neutral
- reproducible
- comparable
- governable
- traceable to outcomes and value

## What This Repository Defines

- canonical vocabulary
- ontology and JSON-LD context
- JSON Schemas
- framework card model
- capability model
- outcome and value realization model
- stakeholder and accountability model
- vendor-neutrality policy
- trust model
- scoring dimensions
- certification model
- accreditation model
- governance lifecycle
- evidence model
- decision model
- action model

## What This Repository Does Not Implement

This repository is not the hosted product, application backend, UI, workflow engine, dashboard, or enterprise private catalog.

Those belong in the platform implementation.

## Relationship to Platform

```text
OpenFrameworks Foundation
  -> defines the open standard and governance model

OpenFrameworks Platform
  -> operationalizes the foundation as a product
```

## Core vs Foundation

A separate `core` repository is not needed yet.

Use this split:

```text
foundation = open standard, schemas, ontology, governance language
platform   = implementation: registry, API, UI, graph, workflows, publishing
enterprise = private/commercial extensions later if needed
```

Create a separate `core` repository only when there is reusable runtime code that multiple products need to import independently.

## Repository Structure

```text
.
├── ontology/              # JSON-LD context and semantic model
├── schemas/               # JSON Schema definitions
├── glossary/              # Controlled vocabulary
├── taxonomy/              # Domains, capabilities, risks, evidence types
├── governance/            # Policies and lifecycle rules
├── trust/                 # Trust, risk, confidence, evidence models
├── scoring/               # Scoring dimensions and recommendation gates
├── certification/         # Certification levels and badge vocabulary
├── accreditation/         # Enterprise accreditation model
├── models/                # Capability, outcome, stakeholder, decision, action models
├── examples/              # Example framework and capability cards
└── README.md
```

## Open Core Boundary

The foundation remains open.

Commercial value is created by platform capabilities such as hosted registries, private enterprise catalogs, workflow automation, advanced analytics, portfolio rationalization, integrations, managed deployments, and enterprise decision intelligence.

## Status

Early foundation draft.
