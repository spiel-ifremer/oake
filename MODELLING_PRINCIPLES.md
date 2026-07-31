# OAKE Modelling Principles

## Purpose

This document describes the modelling principles that guide the development of the Ontology of the Astronomical Knowledge Ecosystem (OAKE).

These principles are intended to ensure consistency, interoperability, modularity and long-term sustainability.

Whenever a modelling decision is made, these principles should take precedence over convenience or short-term implementation choices.

---

# Principle 1 — Reuse before creating

OAKE prioritises the reuse of existing semantic artefacts.

Before introducing a new class, property or vocabulary, contributors should first determine whether an equivalent concept already exists.

Priority should be given to internationally recognised standards and widely adopted community ontologies.

Examples include:

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

# Principle 2 — Keep the conceptual core intentionally small

The OAKE Core should remain minimal.

Only concepts that are fundamental across the entire astronomy ecosystem belong in the core.

Domain-specific concepts should instead be introduced through specialised modules.

The objective is to maximise long-term stability while allowing unlimited future extensions.

---

# Principle 3 — Prefer modularity

OAKE is designed as a modular semantic framework.

Specialised domains should be developed independently while preserving interoperability through the shared conceptual core.

Examples include:

- observations;
- instrumentation;
- organisations;
- citizen science;
- education;
- dark-sky initiatives;
- semantic artefacts.

---

# Principle 4 — Prefer generic semantic relations

Relationships should remain as generic as possible.

Rather than multiplying specialised ontology properties, OAKE favours a limited number of reusable semantic relationships.

Additional semantics should be introduced through controlled vocabularies whenever appropriate.

---

# Principle 5 — Prefer controlled vocabularies

Ontology classes should describe concepts.

Controlled vocabularies should describe classifications.

Whenever possible, categories, roles, statuses, types and thematic domains should be represented using SKOS Concept Schemes rather than ontology subclasses.

This improves flexibility while reducing ontology complexity.

---

# Principle 6 — Separate ontology, vocabularies and knowledge graphs

OAKE distinguishes three complementary semantic layers.

## Ontologies

Describe concepts and relationships.

## Controlled vocabularies

Provide shared terminology and classifications.

## Knowledge graphs

Contain domain-specific instances.

Each layer has a distinct purpose and lifecycle.

---

# Principle 7 — Model concepts, not applications

The ontology should describe concepts that exist independently of any software application or database.

Implementation details should never influence the conceptual model.

---

# Principle 8 — Prefer semantic stability

The conceptual model should evolve slowly.

Vocabulary terms and knowledge graphs are expected to evolve more rapidly.

Long-term stability is considered a primary objective.

---

# Principle 9 — Justify every new concept

Every new ontology class or property should answer the following questions.

- Is this concept really fundamental?
- Does an equivalent already exist?
- Can it be represented using an existing ontology?
- Could a controlled vocabulary be used instead?
- Does it answer at least one competency question?

Only concepts satisfying these criteria should become part of OAKE.

---

# Principle 10 — Build an ecosystem, not an ontology

OAKE is not intended to replace existing semantic resources.

Its objective is to enable them to work together through a coherent conceptual framework.

The long-term ambition of OAKE is therefore to support an open ecosystem of interoperable ontologies, controlled vocabularies and knowledge graphs for astronomy.

---

# Summary

OAKE follows a simple philosophy.

- Reuse before creating.
- Keep the core intentionally small.
- Build modular extensions.
- Prefer generic relations.
- Prefer controlled vocabularies.
- Separate models from data.
- Preserve semantic stability.
- Promote interoperability.
