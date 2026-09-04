# OAKE Semantic Alignments

## Purpose

OAKE follows a reuse-first approach.

Before introducing OAKE-specific semantic terms, existing ontologies,
semantic resources and controlled vocabularies are evaluated to determine
whether they can satisfy the requirements identified through competency
questions and use cases.

Particular attention is given to semantic resources that can provide a
shared language across professional and amateur astronomy.

OAKE considers professional and amateur astronomy as parts of a single
astronomical ecosystem. They should therefore not be modelled as separate
semantic domains unless a genuine semantic distinction requires it.

Semantic resources are considered at three complementary levels:

1. **Generic semantic models**, providing reusable concepts and relations
   across scientific domains.
2. **Astronomy-specific semantic resources**, providing concepts,
   identifiers and terminology specific to astronomy.
3. **Controlled vocabularies**, providing shared terminology across
   communities and applications.

OAKE acts as a semantic integration framework between these resources
rather than attempting to replace them.


## Decision categories

Semantic alignment decisions use the following categories:

- **REUSE** — an existing semantic resource can be reused directly.
- **ALIGN** — several complementary semantic resources need to be aligned
  or used together.
- **EXTEND** — an existing resource provides an appropriate basis but may
  require additional terminology.
- **CREATE** — no suitable existing resource has been identified and an
  OAKE-specific term may be required.
- **OPEN** — further investigation is required before a decision can be made.


## Current alignment overview

| Concept | Candidate semantic resources | Decision |
|---|---|---|
| Agent | PROV-O | REUSE |
| Activity | PROV-O | REUSE |
| Place | GeoSPARQL | REUSE |
| Time | OWL-Time | REUSE |
| Organisation | W3C ORG | REUSE |
| Result | SOSA/SSN | REUSE |
| Criterion | CCCEV | REUSE |
| Instrument | SOSA/SSN, IVOA OBSI | ALIGN |
| Observing Facility | SOSA/SSN, IVOA OBSF | ALIGN |
| Target | SOSA/SSN, astronomy-specific semantic resources | ALIGN |
| Network | W3C ORG, SOSA/SSN, PPSR Core, CSO, PROV-O | ALIGN |
| Citizen Science / Public Participation | PPSR Core, CSO, SOSA/SSN, PROV-O | ALIGN |
| Recognition | CCCEV, PROV-O, W3C ORG | OPEN |


## Instrument

**Requirement**

Represent astronomical instruments across professional and amateur
astronomy using a shared semantic framework.

**Candidate semantic resources**

- SOSA/SSN
- IVOA Observation Instruments (OBSI)

**Assessment**

SOSA/SSN provides generic concepts for systems participating in
observations and related activities.

OBSI provides astronomy-specific terminology and identifiers for
observation instruments. Its applicability to amateur astronomical
instrumentation requires further evaluation.

The two resources should be considered complementary: SOSA/SSN can
provide the generic observational and system model, while OBSI can
provide astronomy-specific terminology and identifiers.

**OAKE decision**

**ALIGN**

No OAKE-specific `Instrument` class is introduced at this stage.

**Open issues**

- Determine the appropriate alignment between OBSI instruments and
  SOSA/SSN systems.
- Evaluate OBSI coverage beyond professional astronomical facilities.
- Identify controlled vocabularies suitable for instrument types across
  professional and amateur astronomy.


## Observing Facility

**Requirement**

Represent astronomical observing facilities independently of their
professional, institutional or amateur context.

**Candidate semantic resources**

- SOSA/SSN
- IVOA Observation Facilities (OBSF)

**Assessment**

SOSA/SSN provides generic concepts such as `Platform` and relations for
hosting systems.

OBSF provides astronomy-specific identifiers, terminology and
descriptions for observation facilities.

OBSF is a recent resource and currently appears primarily oriented
towards professional astronomical facilities. Its applicability to the
broader astronomical ecosystem therefore requires further evaluation.

The two resources should be considered complementary: SOSA/SSN can
provide the generic structural model, while OBSF can provide
astronomy-specific facility terminology and identifiers.

**OAKE decision**

**ALIGN**

No OAKE-specific `ObservingFacility` class is introduced at this stage.

**Open issues**

- Determine the appropriate relationship between an observation facility
  and `sosa:Platform`.
- Evaluate the relationship between OBSF and OBSI.
- Evaluate how amateur and community-operated observatories can use the
  same semantic model.
- Identify controlled vocabularies suitable for facility types.


## Target

**Requirement**

Represent the astronomical entity or phenomenon targeted by an
observation.

**Candidate semantic resources**

- SOSA/SSN
- IVOA semantic resources
- Astronomy-specific controlled vocabularies

**Assessment**

SOSA/SSN provides `sosa:FeatureOfInterest` for the entity that is the
target of an execution or deployment.

This provides an appropriate generic semantic mechanism for linking an
observation to its target.

Astronomical targets, however, require domain-specific semantics for
describing and classifying astronomical objects and phenomena. These
semantics should preferably be obtained from existing astronomical
resources rather than recreated by OAKE.

**OAKE decision**

**ALIGN**

OAKE should combine the generic observation semantics provided by
SOSA/SSN with astronomy-specific terminology and identifiers.

No OAKE-specific `Target` class is introduced at this stage.

**Open issues**

- Evaluate astronomy-specific resources for astronomical object types.
- Determine appropriate mappings between astronomical target concepts
  and `sosa:FeatureOfInterest`.
- Investigate relevant IVOA and other astronomy community vocabularies.


## Network

**Requirement**

Represent astronomical networks and initiatives that may connect
organisations, people, observing facilities, instruments, activities and
observations across professional and amateur astronomy.

Such networks may combine organisational collaboration, distributed
observational infrastructure, scientific coordination and citizen
participation.

**Candidate semantic resources**

- W3C ORG
- SOSA/SSN
- PPSR Core
- Citizen Science Ontology (CSO)
- PROV-O
- Astronomy-specific semantic resources and controlled vocabularies

**Assessment**

"Network" is a multidimensional concept in the astronomical ecosystem.

An astronomical network may represent:

- an organisational collaboration;
- a distributed infrastructure of instruments or observing facilities;
- a coordinated scientific initiative;
- a citizen-science initiative;
- or a combination of these dimensions.

No single semantic resource is expected to represent every dimension of
an astronomical network.

W3C ORG can contribute to the representation of organisational structures
and collaborations.

SOSA/SSN can represent distributed observational systems, platforms and
deployments. In particular, `sosa:Deployment` provides a generic mechanism
for representing arrangements of systems and platforms deployed for
observational purposes.

PPSR Core and the Citizen Science Ontology can contribute to the
representation of networks and projects involving public participation in
scientific research.

PROV-O can represent agents, activities and provenance relationships
across these structures.

These resources should therefore be considered complementary rather than
alternative models.

**OAKE decision**

**ALIGN**

OAKE should investigate how these semantic resources can be combined to
represent professional, amateur, citizen-science and mixed astronomical
networks without introducing separate domain models.

No OAKE-specific `Network` class is introduced at this stage.

**Open issues**

- Distinguish organisational networks from distributed observational
  infrastructures and scientific initiatives.
- Determine how organisations, people, facilities and instruments
  participate in or belong to networks.
- Investigate the use of `sosa:Deployment` for distributed observing
  infrastructures.
- Determine appropriate mappings between PPSR Core / CSO and the other
  semantic resources used by OAKE.
- Identify controlled vocabularies for astronomical network types.
- Ensure that the same integration approach can represent professional,
  amateur and mixed professional-amateur networks.


## Citizen Science and Public Participation

**Requirement**

Represent public participation in astronomical research and connect
citizen-science projects, participants, datasets and observations with
the broader astronomical ecosystem.

**Candidate semantic resources**

- PPSR Core
- Citizen Science Ontology (CSO)
- SOSA/SSN
- PROV-O
- Astronomy-specific semantic resources and controlled vocabularies

**Assessment**

PPSR Core provides a transdisciplinary framework for Public Participation
in Scientific Research, including project, dataset and observation
metadata.

Its Observation Data Model supports domain profiles, allowing
domain-specific scientific semantics to complement the common
participatory model.

Astronomy is explicitly identified among the scientific domains that may
be represented through domain-specific observational schemas.

The Citizen Science Ontology provides an RDF implementation and extension
of concepts derived from the PPSR conceptual model. Its maturity and
stability should be evaluated before it is adopted as a normative OAKE
dependency.

For astronomy, PPSR Core and CSO can provide the participatory dimension,
while SOSA/SSN and astronomy-specific semantic resources can provide the
semantics of observations, instruments, facilities and astronomical
entities.

PROV-O can complement these resources by representing the provenance of
observations, datasets and derived scientific results.

This creates a potential semantic bridge between Public Participation in
Scientific Research and astronomical semantics without requiring a
separate OAKE model for citizen science.

**OAKE decision**

**ALIGN**

OAKE should investigate mappings between PPSR Core / CSO and the semantic
resources used to represent astronomical observations.

No separate OAKE model for citizen science should be introduced where
these resources provide adequate semantics.

**Open issues**

- Investigate the PPSR Core Astronomical and Space Sciences domain profile.
- Determine mappings between PPSR observation concepts and SOSA/SSN.
- Determine how astronomy-specific IVOA semantics can complement the PPSR
  observation model.
- Evaluate which CSO concepts are sufficiently stable for reuse.
- Evaluate how provenance should connect citizen participation,
  observations, datasets and scientific results.


## Recognition

**Requirement**

Represent recognitions, certifications, labels or similar distinctions
awarded to astronomical places, organisations or other resources.

This includes, for example, dark-sky certifications and other recognition
schemes relevant to the astronomical ecosystem.

**Candidate semantic resources**

- CCCEV
- PROV-O
- W3C ORG
- Domain-specific certification and recognition vocabularies to be
  further investigated

**Assessment**

CCCEV provides a generic semantic framework for requirements, criteria
and evidence used in assessment processes.

However, CCCEV does not by itself provide a generic model for the
recognition, certification or label resulting from such an assessment.

PROV-O and W3C ORG may contribute provenance and organisational
information, but no existing resource has yet been identified as a
sufficient generic representation of Recognition for OAKE.

**OAKE decision**

**OPEN**

No OAKE-specific `Recognition` class is introduced at this stage.

**Open issues**

- Identify existing semantic models for certifications, labels, awards
  and recognition schemes.
- Determine how a recognition is related to the organisation awarding it.
- Determine how the recognised entity is represented.
- Reuse CCCEV for criteria and evidence wherever applicable.
- Represent validity periods using existing temporal vocabularies.
- Identify controlled vocabularies for recognition and certification
  types.


## Cross-domain integration

The semantic resources identified above should not be considered as
isolated modelling alternatives.

OAKE aims to provide an integration framework in which complementary
semantic resources can describe different dimensions of the same
astronomical ecosystem.

For example, a distributed citizen-science observing network may involve:

- organisations described using W3C ORG;
- participants and projects described using PPSR Core / CSO;
- instruments, deployments and observations described using SOSA/SSN;
- astronomical terminology and identifiers provided by IVOA semantic
  resources and controlled vocabularies;
- places described using GeoSPARQL;
- temporal information described using OWL-Time;
- datasets described using DCAT;
- provenance described using PROV-O.

Professional and amateur astronomy should use the same semantic resources
wherever possible. Differences in context, governance, scale or purpose
should be represented through appropriate properties, roles and
controlled vocabularies rather than through parallel semantic models.


## Next investigations

Priority should be given to unresolved alignments that affect several
competency questions and to controlled vocabularies capable of providing
a shared terminology across professional and amateur astronomy.

Current priorities are:

1. Instrument type vocabularies
2. Observing facility type vocabularies
3. PPSR Core / CSO ↔ SOSA/SSN mappings
4. Astronomy-specific target vocabularies
5. Relationships between organisations, facilities, instruments and
   networks
6. Recognition and certification models
