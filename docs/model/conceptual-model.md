# OAKE Conceptual Model

## Status

This document presents the initial conceptual model of OAKE.

The model is deliberately small and generic. It is intended to provide
a stable integration layer for more specialised astronomy ontologies,
vocabularies and knowledge graphs.

## Core concepts

```mermaid
classDiagram

    class Agent {
        +identifier
        +preferredLabel
        +description
    }

    class Activity {
        +identifier
        +preferredLabel
        +description
    }

    class Resource {
        +identifier
        +preferredLabel
        +description
    }

    class Place {
        +identifier
        +preferredLabel
        +description
    }

    class TemporalEntity {
        +identifier
        +preferredLabel
    }

    Agent "0..*" --> "0..*" Activity : participatesIn
    Agent "0..*" --> "0..*" Resource : hasResponsibilityFor
    Activity "0..*" --> "0..*" Resource : involves
    Activity "0..*" --> "0..*" Place : occursAt
    Resource "0..*" --> "0..*" Place : locatedAt
    Activity "0..*" --> "0..1" TemporalEntity : hasTime
    Resource "0..*" --> "0..*" TemporalEntity : hasLifecycle
```

## Modelling principles

- The core must remain intentionally small.
- Existing ontologies should be reused before new OAKE classes or
  properties are introduced.
- Domain-specific concepts should be introduced through modular
  extensions.
- Categorical values should use controlled vocabularies and persistent
  identifiers.
- Temporal information must have an explicit semantic meaning.
- The temporal characteristics of real-world entities must be
  distinguished from the creation and modification dates of their
  descriptions.

## Provisional status

The classes and relation names shown in this document are conceptual.
They do not yet imply that OAKE will define equivalent OWL classes or
properties.

Each concept will be assessed against existing ontologies and tested
through competency questions and representative use cases.
