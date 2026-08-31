# OAKE Modelling Principles

## Purpose

This document defines the modelling principles that guide the development of the Ontology for the Astronomical Knowledge Ecosystem (OAKE).

These principles provide a common reference for all modelling decisions throughout the project. They aim to ensure consistency, interoperability, modularity and long-term sustainability.

Every new modelling decision should be evaluated against these principles.

---

# Overview

| Identifier | Principle |
|------------|-----------|
| MP1 | Reuse before creating |
| MP2 | Keep the conceptual core intentionally small |
| MP3 | Prefer modularity |
| MP4 | Prefer generic semantic relations |
| MP5 | Prefer controlled vocabularies |
| MP6 | Separate ontologies, vocabularies and knowledge graphs |
| MP7 | Model concepts, not applications |
| MP8 | Prefer semantic stability |
| MP9 | Justify every new concept |
| MP10 | Build an ecosystem, not an ontology |

---

# MP1 — Reuse before creating

## Statement

Reuse existing semantic artefacts whenever possible.

## Rationale

Widely adopted ontologies and standards should be preferred over creating new concepts.

## Examples

- PROV-O
- SOSA / SSN
- W3C ORG
- GeoSPARQL
- OWL-Time
- DCAT
- SKOS
- MOD
- IVOA semantic resources
- Unified Astronomy Thesaurus (UAT)

---

# MP2 — Keep the conceptual core intentionally small

## Statement

The OAKE Core should remain intentionally minimal.

## Rationale

Only concepts that are fundamental across the astronomy ecosystem belong in the conceptual core.

Domain-specific concepts should instead be introduced through specialised modules.

---

# MP3 — Prefer modularity

## Statement

Develop specialised domains as independent semantic modules.

## Rationale

A modular architecture simplifies maintenance, encourages reuse and allows communities to evolve independently while remaining interoperable.

---

# MP4 — Prefer generic semantic relations

## Statement

Prefer a small number of generic semantic relations.

## Rationale

Avoid multiplying specialised ontology properties.

Whenever appropriate, refine semantics through controlled vocabularies rather than creating additional OWL properties.

---

# MP5 — Prefer controlled vocabularies

## Statement

Represent classifications using controlled vocabularies.

## Rationale

Types, roles, statuses and thematic categories should generally be modelled as SKOS concepts rather than ontology subclasses.

---

# MP6 — Separate ontologies, vocabularies and knowledge graphs

## Statement

Maintain a clear separation between conceptual models, terminology and instances.

## Rationale

Each semantic layer has a distinct purpose and lifecycle.

- Ontologies define concepts and relationships.
- Controlled vocabularies define terminology.
- Knowledge graphs contain domain instances.

---

# MP7 — Model concepts, not applications

## Statement

The ontology describes the real world rather than software implementations.

## Rationale

Application-specific constraints should not influence the conceptual model.

---

# MP8 — Prefer semantic stability

## Statement

The conceptual model should evolve slowly.

## Rationale

Long-term stability is more valuable than short-term convenience.

Vocabulary terms and knowledge graphs are expected to evolve more rapidly than the conceptual core.

---

# MP9 — Justify every new concept

## Statement

Every new class or property must have a clear justification.

## Evaluation questions

Before introducing a new concept, ask:

- Does an equivalent already exist?
- Can an existing ontology be reused?
- Could this be represented using a controlled vocabulary?
- Is the concept fundamental?
- Does it answer at least one competency question?

---

# MP10 — Build an ecosystem, not an ontology

## Statement

OAKE aims to support a semantic ecosystem rather than developing an isolated ontology.

## Rationale

The objective is to enable ontologies, controlled vocabularies and knowledge graphs to interoperate through a coherent conceptual framework.

---

# Using these principles

The Modelling Principles are intended to guide every design decision.

Future documentation, discussions and pull requests may therefore refer to individual principles using their identifiers.

Examples:

- "This proposal follows MP1 and MP5."
- "Introducing this class would conflict with MP2."
- "The proposed property should be reconsidered according to MP4."
