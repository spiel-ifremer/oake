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
| Instrument | SOSA/SSN, SAREF and extensions, IVOA OBSI | ALIGN |
| Observing Facility | SOSA/SSN, IVOA OBSF | ALIGN |
| Target | SOSA/SSN, astronomy-specific semantic resources | ALIGN |
| Network | W3C ORG, SOSA/SSN, PPSR Core, CSO, PROV-O | ALIGN |
| Citizen Science / Public Participation | PPSR Core, CSO, SOSA/SSN, PROV-O | ALIGN |
| Recognition | Schema.org, CCCEV, PROV-O, W3C ORG, OWL-Time | ALIGN / OPEN |


## Instrument

**Requirement**

Represent astronomical instruments across professional and amateur
astronomy using a shared semantic framework.

**Candidate semantic resources**

- SOSA/SSN
- SAREF and relevant SAREF extensions
- IVOA Observation Instruments (OBSI)
- Astronomy-specific controlled vocabularies

**Modelling considerations**

The representation of an instrument should distinguish several
complementary dimensions:

- the individual physical instrument;
- its instrument type or kind;
- its product model and manufacturer;
- its capabilities or functions;
- its components and relationships with other equipment;
- and its role within a particular observational or operational context.

These dimensions should not be conflated. In particular, an instrument
type should be represented independently from its manufacturer or
commercial product model.

The same instrument type should be usable across professional, amateur
and citizen-science contexts. Differences in ownership, operation,
deployment, scale or use should be represented through relationships
and contextual information rather than through separate instrument
taxonomies.

**Assessment**

SOSA/SSN provides generic concepts for systems participating in
observations and related activities. It provides an appropriate
functional model for representing instruments when they act as systems
or sensors within observational processes.

SAREF and its domain extensions provide complementary semantics for
devices, device kinds, capabilities and related properties. For example,
SAREF4ENVI provides astronomy-relevant device kinds such as TESS
photometers. Such existing terminology should be reused where
applicable rather than recreated within OAKE.

OBSI provides astronomy-specific terminology and identifiers for
observation instruments. Its applicability beyond professional
astronomical facilities and its relationship with SOSA/SSN and SAREF
require further evaluation.

These resources should therefore be considered complementary rather
than alternative models. SOSA/SSN can provide observational and system
semantics, SAREF can contribute device and capability semantics, while
OBSI and other astronomy-specific resources can provide domain
terminology and identifiers.

**OAKE decision**

**ALIGN**

No OAKE-specific `Instrument` class is introduced at this stage.

**Open issues**

- Determine appropriate mappings between SOSA/SSN, SAREF and
  astronomy-specific instrument resources such as OBSI.
- Distinguish consistently between individual instruments, instrument
  types or kinds, product models and manufacturers.
- Determine how instrument capabilities, components and relationships
  with other equipment should be represented.
- Evaluate OBSI coverage beyond professional astronomical facilities.
- Identify controlled vocabularies suitable for instrument types across
  professional, amateur and citizen-science astronomy.
- Identify domain-specific semantic resources providing reusable
  instrument types or device kinds, including relevant SAREF extensions.


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

- Schema.org
- CCCEV
- PROV-O
- W3C ORG
- OWL-Time
- Domain-specific certification and recognition vocabularies where relevant

**Assessment**

Schema.org provides a generic `Certification` model for official
statements about subjects such as persons, organisations and places.
It includes properties for representing the issuing organisation,
validity, expiration, certification status and certification
identification.

This provides a potentially suitable generic model for certification
schemes relevant to OAKE, including certifications awarded to
astronomical places or organisations.

CCCEV provides complementary semantics for representing the
requirements, criteria and evidence involved in assessment processes.
It should therefore be considered alongside certification models rather
than as a representation of the resulting recognition itself.

PROV-O may provide additional provenance information about recognition
and assessment processes, while W3C ORG can represent organisations
involved in issuing or receiving recognitions. Temporal aspects can be
represented using existing temporal vocabularies such as OWL-Time where
more detailed temporal modelling is required.

However, not every form of recognition is necessarily a certification.
Labels, awards, designations, accreditations and other distinctions may
require different semantic representations.

No single semantic resource has yet been identified as sufficient for
representing all forms of recognition relevant to the astronomical
ecosystem.

**OAKE decision**

**ALIGN / OPEN**

OAKE should reuse existing generic semantic models for recognition and
certification where their semantics match the relevant use case.

Schema.org `Certification` should be evaluated as the preferred generic
model for certification schemes, while CCCEV should be reused for
criteria, requirements and evidence where applicable.

PROV-O, W3C ORG and OWL-Time should be reused where provenance,
organisational or temporal information is required.

No OAKE-specific `Recognition` class is introduced at this stage.

**Open issues**

- Evaluate Schema.org `Certification` against representative dark-sky
  recognition schemes.
- Distinguish certification, label, award, designation and accreditation.
- Determine how recognition schemes themselves should be represented.
- Define the relationship between a recognition and the CCCEV criteria
  and evidence used for its assessment.
- Determine how non-certification forms of recognition should be
  represented.
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

Priority should be given to unresolved semantic alignments that affect
several competency questions and to mappings between the complementary
semantic resources identified by OAKE.

Current priorities are:

1. Define mappings between SOSA/SSN, SAREF and astronomy-specific
   resources for instruments and observing facilities.
2. Investigate PPSR Core / CSO ↔ SOSA/SSN mappings for participatory
   astronomical observations.
3. Clarify relationships between organisations, facilities, instruments,
   platforms, deployments and networks.
4. Evaluate representative professional, amateur and citizen-science
   use cases against the proposed alignments.
5. Evaluate Schema.org `Certification` and CCCEV against representative
   recognition schemes.
6. Identify semantic gaps that remain after reuse and alignment of
   existing resources.
