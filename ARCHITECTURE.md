# OAKE Architecture

## Purpose

This document provides an overview of the architecture of OAKE — the Ontology of the Astronomical Knowledge Ecosystem.

It describes:

- the main components of the project;
- the role of each component;
- the organisation of the repository;
- the relationships between documentation and semantic artefacts;
- the expected development workflow.

This document focuses on the architecture of the project as a whole.

The detailed semantic architecture is described in [`docs/semantic-architecture.md`](docs/semantic-architecture.md).

---

## Architectural overview

OAKE is designed as a semantic integration framework for the astronomy ecosystem.

It is not limited to a single ontology file.

The project brings together:

- project vision and governance;
- modelling principles;
- conceptual documentation;
- ontology modules;
- controlled vocabularies;
- validation profiles;
- knowledge graphs;
- examples and implementation guidance.

```mermaid
flowchart TB

    OAKE[OAKE Semantic Framework]

    OAKE --> GOV[Vision and Governance]
    OAKE --> DOC[Scientific and Technical Documentation]
    OAKE --> ONT[Ontologies]
    OAKE --> VOC[Controlled Vocabularies]
    OAKE --> SH[Validation Shapes]
    OAKE --> KG[Knowledge Graphs]
    OAKE --> EX[Examples and Applications]
