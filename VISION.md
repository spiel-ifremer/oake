# OAKE Vision

## Why OAKE?

Astronomy has always been one of the most collaborative scientific disciplines. Professional observatories, space agencies, research infrastructures, universities, amateur astronomers, citizen-science initiatives, educational organisations and dark-sky programmes all contribute valuable knowledge, observations and expertise.

Over the past decades, the astronomy ecosystem has become increasingly rich and diverse. Alongside observations, it now includes datasets, software, publications, services, ontologies, controlled vocabularies, knowledge graphs and many other digital resources.

Although numerous semantic standards already exist, they have generally been developed independently to address specific communities or use cases. As a result, describing and connecting knowledge across the astronomy ecosystem remains difficult.

OAKE (Ontology for the Astronomical Knowledge Ecosystem) aims to address this challenge by providing a semantic framework that promotes the coordinated reuse of existing semantic artefacts.

---

# Vision

OAKE aims to become an open, modular and community-driven semantic framework for the astronomy ecosystem.

Rather than replacing existing ontologies, OAKE promotes their coordinated reuse through common modelling principles, shared semantic practices and modular extensions.

Its ambition is to facilitate semantic interoperability between organisations, projects, infrastructures, instruments, observations, datasets, software, publications and other knowledge resources across professional, amateur, educational and citizen-science communities.

OAKE considers professional and amateur astronomy as parts of a single, interconnected astronomical ecosystem. Rather than modelling them as separate domains, it seeks to provide a common semantic framework through which their organisations, infrastructures, instruments, activities, data and knowledge resources can be described and connected.

OAKE is not limited to astronomical observations, instruments or data. Its scope is the broader astronomical knowledge ecosystem, including people, organisations, communities, activities, places, facilities, equipment, observations, data, knowledge resources and the networks and relationships that connect them.

The primary added value of OAKE lies in making these heterogeneous parts of the astronomical ecosystem semantically interoperable. Rather than replacing existing domain models, OAKE seeks to connect and reuse them within a coherent framework.

Spatial and temporal dimensions are transversal to this ecosystem. OAKE should support not only the description of where astronomical entities and activities are located, but also how they and their relationships evolve over time.

---

# Guiding principles

OAKE is guided by a small number of fundamental principles.

- Reuse before creating.
- Keep the conceptual core intentionally small.
- Prefer generic semantic relations.
- Prefer controlled vocabularies over ontology proliferation.
- Separate ontologies, controlled vocabularies and knowledge graphs.
- Develop domain concepts through modular extensions.
- Promote FAIR principles.
- Encourage community-driven governance.
- Ensure long-term semantic stability.
- Bridge professional and amateur astronomy within a shared semantic ecosystem.
- Design for international, multilingual and cross-community reuse.

---

# Semantic architecture

OAKE distinguishes three complementary semantic layers.

## Ontologies

Ontologies define conceptual models and semantic relationships.

## Controlled vocabularies

Controlled vocabularies define classifications, roles, types and shared terminology.

Whenever appropriate, they should be represented using SKOS.

## Knowledge graphs

Knowledge graphs contain domain-specific instances built upon ontologies and controlled vocabularies.

Together, these three layers support semantic interoperability across the astronomy ecosystem.

---

# Scope

OAKE does not attempt to model astronomy from scratch.

Instead, it provides a stable semantic foundation for integrating existing semantic artefacts and supporting specialised domain modules.

Examples of future modules include:

- observations;
- instrumentation;
- organisations;
- citizen science;
- education and outreach;
- dark-sky initiatives;
- semantic artefacts.

---

# Community

OAKE is developed as an open scientific initiative.

The project aims to foster collaboration between experts in astronomy, ontology engineering, Semantic Web technologies and FAIR data management.

As the project matures, contributors from existing astronomy and semantic communities will be invited to participate in its technical development and governance.

---

# Expected impact

OAKE aims to:

- improve interoperability between astronomy knowledge resources;
- facilitate the discovery and integration of semantic artefacts;
- encourage the reuse of existing standards;
- support FAIR knowledge graphs;
- strengthen links between professional and amateur astronomy;
- foster collaboration across the wider Semantic Web ecosystem.

---

# Current technical direction

OAKE currently explores the development of a lightweight conceptual core supported by existing semantic standards.

Rather than redefining universal concepts, OAKE seeks to build upon widely adopted ontologies and vocabularies such as PROV-O, SOSA/SSN, W3C ORG, GeoSPARQL, OWL-Time, DCAT and SKOS.

The project is also exploring the establishment of a persistent namespace within a broader community-oriented semantic ecosystem.

The current provisional namespace is:

```
https://w3id.org/astrosemantics/oake/
```

This namespace remains provisional and will be discussed with the astronomy semantic community before any permanent adoption.

---

# Long-term ambition

Beyond the development of a single ontology, OAKE aims to foster an open ecosystem of interoperable ontologies, controlled vocabularies and knowledge graphs for astronomy.

Its long-term ambition is to provide a stable, international and multilingual semantic foundation that enables professional and amateur astronomers, researchers, educators, observatories, organisations, citizen-science initiatives, software systems and knowledge infrastructures to describe, discover and connect astronomy knowledge in a consistent, interoperable and sustainable way.
