# OAKE Vocabulary Reuse

## Purpose

OAKE follows a reuse-first approach not only for ontologies and semantic
models, but also for controlled vocabularies.

Controlled vocabularies provide shared terminology for describing and
classifying resources across the astronomical ecosystem.

Particular attention is given to vocabularies that can provide a common
language across professional, amateur and citizen-science astronomy.

Before introducing new terminology, OAKE should:

1. identify existing controlled vocabularies;
2. evaluate their coverage against OAKE competency questions and use cases;
3. reuse existing concepts whenever possible;
4. align complementary vocabularies where necessary;
5. extend shared astronomy vocabularies when appropriate;
6. introduce OAKE-specific terminology only when a documented gap remains.

OAKE should avoid creating separate vocabularies for professional and
amateur astronomy when the same concepts can be represented through a
shared astronomical vocabulary.


## Decision categories

Vocabulary reuse decisions use the following categories:

- **REUSE** — an existing vocabulary provides suitable terminology.
- **ALIGN** — terminology from several complementary vocabularies needs
  to be used or mapped together.
- **EXTEND** — an existing vocabulary provides an appropriate basis but
  additional terminology may be required.
- **CREATE** — no suitable vocabulary has been identified and an
  OAKE-specific vocabulary may be required.
- **OPEN** — further investigation is required before a decision can be made.


## Current vocabulary overview

| Domain | Candidate resources | Decision |
|---|---|---|
| Instrument types | UAT, IVOA semantic resources, OBSI, emerging OntoPortal-Astro resources | EXTEND / OPEN |
| Observing facility and station types | OBSF, IVOA semantic resources, SOSA/SSN, Wikidata | ALIGN / OPEN |
| Astronomical object types | IVOA Object Types, SIMBAD, UAT | REUSE / MONITOR |
| Spectral domains / wavebands | IVOA Messenger vocabulary, UCD1+, PhotDM | REUSE |
| Organisation types | W3C ORG, SKOS, external organisation classifications | ALIGN / OPEN |
| Activity types, techniques and purposes | SOSA/SSN, IVOA semantic resources, UAT, PPSR Core, CSO | ALIGN / OPEN |
| Network types | W3C ORG, SOSA/SSN, PPSR Core, CSO | ALIGN / OPEN |
| Operational status | Existing lifecycle and status vocabularies to be investigated | EXTEND / OPEN |
| Contribution roles | PROV-O, CRediT, PPSR Core, CSO, IVOA semantic resources | ALIGN / OPEN |
| Recognition types | Schema.org, CCCEV, PROV-O, external recognition and certification vocabularies | ALIGN / OPEN |


## Instrument Types

**Requirement**

Provide a shared controlled terminology for classifying astronomical
instruments across professional, amateur and citizen-science astronomy.

**Candidate resources**

- Unified Astronomy Thesaurus (UAT)
- IVOA semantic resources
- Observation Instruments (OBSI)
- Emerging OntoPortal-Astro instrument-type resources

**Assessment**

Existing astronomical semantic resources already provide terminology
for several instrument types, including telescopes, photometers and
spectrometric instruments.

OBSI primarily provides identifiers and descriptions for named
astronomical instruments rather than a comprehensive taxonomy of
instrument types.

No single current resource has yet been identified as providing a
comprehensive and coherent controlled vocabulary covering instrument
types across professional, amateur and citizen-science astronomy.

The development of an instrument-type ontology has also been identified
as a possible future activity within the OntoPortal-Astro ecosystem.

**OAKE decision**

**EXTEND / OPEN**

OAKE should reuse existing astronomical terminology wherever possible
and investigate how emerging astronomy instrument-type vocabularies can
cover the requirements identified by OAKE.

OAKE should not introduce a separate amateur-astronomy instrument
vocabulary.

Where terminology required by amateur or citizen-science astronomy is
missing, preference should be given to contributing or aligning these
terms with shared astronomy vocabularies.

**Open issues**

- Establish a crosswalk between UAT, OBSI and relevant IVOA resources.
- Evaluate coverage of telescope types and optical configurations.
- Evaluate cameras and all-sky imaging systems.
- Evaluate photometers and night-sky brightness instruments.
- Evaluate meteor and fireball detection instruments.
- Evaluate amateur and professional spectroscopic instrumentation.
- Monitor emerging OntoPortal-Astro work on instrument-type semantics.

## Observing Facility Types

**Requirement**

Provide shared terminology for classifying astronomical observing
facilities across professional, amateur and citizen-science astronomy.

**Candidate resources**

- IVOA Observation Facilities (OBSF)
- IVOA semantic resources
- Wikidata
- Relevant domain-specific facility classifications

**Assessment**

The IVOA Observation Facilities work provides a shared nomenclature for
identifying astronomical observation facilities and resolving their
names and aliases.

Its semantic scope includes observatories, telescopes, spacecraft,
space probes, space missions and other facilities supporting
observational activities.

Existing IVOA work also provides candidate facility categories such as
Observatory, Spacecraft, Space Mission and Telescope.

These categories are largely independent of whether a facility is
operated by a professional institution, an amateur organisation or an
individual observer.

However, distributed observing infrastructures introduce additional
requirements. Citizen-science and amateur observing networks frequently
use stations or observing sites hosting instruments such as all-sky
cameras, meteor cameras or photometers. The representation and
classification of these resources requires further investigation.

SOSA/SSN provides a suitable generic semantic model for representing
observing stations as platforms hosting instruments or other systems.

However, no dedicated IVOA controlled vocabulary has currently been
identified for classifying astronomical station or platform types.
Terms such as observing station, monitoring station, meteor station or
all-sky station may therefore require alignment with other existing
vocabularies or future extension of shared astronomical terminology.

**OAKE decision**

**ALIGN / OPEN**

OAKE should reuse the IVOA Observation Facilities nomenclature for
identifying facilities wherever applicable and align facility
classification with existing astronomical and generic semantic
resources.

OAKE should not introduce separate facility types for professional and
amateur astronomy.

Distributed observing stations should, where appropriate, be modelled
using `sosa:Platform` rather than through an OAKE-specific `Station`
class. The classification of such platforms should remain vocabulary-
driven and is currently an open vocabulary-reuse issue.

**Open issues**

- Determine the distinction between an observing facility, observatory
  and observing site.
- Treat distributed observing stations as candidate specialisations or
  classifications of `sosa:Platform` rather than introducing an
  OAKE-specific `Station` class.
- Evaluate existing controlled terminology for station and platform
  types, including observing stations, monitoring stations and
  instrument stations.
- Evaluate TESS, AllSky and FRIPON stations as representative use cases.
- Evaluate the facility-type classifications available through OBSF,
  IVOA resources and Wikidata.
- Determine whether additional shared terminology is required for
  community-operated and citizen-operated observing facilities.
## Astronomical Object Types

**Requirement**

Provide shared controlled terminology for classifying the astronomical
nature of targets involved in observations and other astronomical
activities.

**Candidate resources**

- IVOA Object Types
- SIMBAD object-type classification
- Unified Astronomy Thesaurus (UAT)

**Assessment**

The IVOA Object Types vocabulary is specifically designed to represent
types of astronomical objects, ranging from stars to galaxies.

It is based closely on the object-type classification used by SIMBAD
and is intended for use in astronomical data models, including the
classification of observation targets.

This vocabulary should be distinguished from the identification of a
specific astronomical target. For example, M31 is an astronomical
object that may be represented as a feature of interest in an
observation, while Galaxy represents its astronomical object type.

UAT provides complementary scientific terminology and may support
cross-references or mappings, but the IVOA Object Types vocabulary is
more directly aligned with the requirement for target classification.

The IVOA Object Types vocabulary is currently published as a draft and
has not yet reached approved IVOA vocabulary status.

**OAKE decision**

**REUSE / MONITOR**

OAKE should reuse IVOA Object Types as the preferred controlled
vocabulary for classifying the astronomical nature of observation
targets wherever applicable.

OAKE should not introduce a separate vocabulary of astronomical object
types.

The evolution and normative status of the IVOA vocabulary should be
monitored.

**Open issues**

- Monitor the evolution and approval status of IVOA Object Types.
- Evaluate mappings between IVOA Object Types and UAT where useful.
- Distinguish consistently between target identity and target
  classification in OAKE examples and mappings.
- Evaluate requirements for targets that are not conventional
  astronomical objects.

## Spectral Domains and Wavebands

**Requirement**

Provide shared terminology for describing the spectral domains or
messengers associated with astronomical instruments, observations,
datasets and other resources.

**Candidate resources**

- IVOA Messenger vocabulary
- IVOA UCD1+
- IVOA Photometry Data Model (PhotDM)

**Assessment**

The IVOA provides established semantic resources for representing
spectral domains and related concepts.

The IVOA Messenger vocabulary provides controlled terminology for the
general classification of the messenger or spectral domain relevant to
an astronomical resource. It extends the traditional concept of
waveband beyond electromagnetic radiation and therefore supports a
broader multi-messenger astronomy context.

UCD1+ provides complementary terminology for describing quantities
related to the electromagnetic spectrum and should be used where more
specific semantic descriptions of measured quantities are required.

PhotDM provides additional semantics for photometric filters and
bandpasses where detailed photometric information is required.

These resources address different levels of description and should be
used complementarily rather than replaced by an OAKE-specific
vocabulary.

**OAKE decision**

**REUSE**

OAKE should reuse the IVOA Messenger vocabulary for general spectral
domain or messenger classification.

UCD1+ and relevant IVOA data models should be reused when more detailed
spectral or photometric descriptions are required.

OAKE should not introduce a separate vocabulary for spectral domains or
wavebands.

**Open issues**

- Define usage patterns distinguishing general messenger classification
  from quantitative spectral coverage.
- Determine when UCD1+ terminology is required in OAKE datasets and
  mappings.
- Evaluate PhotDM when photometric filters and bandpasses become part
  of OAKE use cases.

## Organisation Types

**Requirement**

Provide shared terminology for classifying organisations participating
in the astronomical ecosystem, including astronomical associations,
clubs, scientific societies, universities, research institutes and
other organisations.

**Candidate resources**

- W3C Organization Ontology (ORG)
- SKOS
- Existing general-purpose organisation classifications
- Domain-specific classifications where relevant

**Assessment**

W3C ORG provides a suitable generic semantic model for organisations
and supports their classification through `org:classification`, whose
values can be represented using SKOS concepts.

However, no comprehensive astronomy-specific controlled vocabulary has
been identified for classifying the different kinds of organisations
participating in the astronomical ecosystem.

Organisation type should also be distinguished from other dimensions
such as organisational role, activity, scientific domain and legal
status. For example, an observatory operator is primarily a role played
by an organisation rather than necessarily a distinct type of
organisation.

Professional and amateur astronomy should not be represented through
separate fundamental organisation classes. Shared organisation types
should be used wherever the organisational nature is equivalent.

**OAKE decision**

**ALIGN / OPEN**

OAKE should reuse `org:Organization` and the classification mechanisms
provided by W3C ORG.

Organisation classifications should use controlled terminology wherever
suitable vocabularies exist.

OAKE should not introduce an ontology hierarchy of astronomy-specific
organisation classes at this stage.

No OAKE-specific organisation-type vocabulary should be introduced
until the requirements and existing classifications have been evaluated
more systematically.

**Open issues**

- Identify existing controlled vocabularies for general organisation
  types.
- Evaluate terminology for astronomical clubs, associations and
  scientific societies.
- Evaluate terminology for universities, research institutes and
  observatory organisations.
- Distinguish organisation type from role, activity and legal status.
- Determine whether astronomy-specific organisation terminology is
  actually required.

## Activity Types, Techniques and Purposes

**Requirement**

Provide shared terminology for describing activities across the
astronomical ecosystem, including scientific observations, technical
operations, data-related activities, education, outreach and
participatory activities.

**Candidate resources**

- SOSA/SSN
- IVOA semantic resources
- Unified Astronomy Thesaurus (UAT)
- PPSR Core
- Citizen Science Ontology (CSO)
- Other general-purpose activity vocabularies where relevant

**Assessment**

Activities in the astronomical ecosystem cannot be represented
adequately through a single flat classification.

Several distinct dimensions should be considered.

SOSA/SSN already provides semantic classes for observational and
instrument-related executions, including observations, sampling and
deployments.

Astronomical techniques such as imaging, photometry and spectroscopy
represent a different classification dimension and should not
automatically be modelled as fundamental subclasses of Activity.

Similarly, purposes such as research, education and outreach should be
distinguished from the nature of the activity itself.

Data processing, calibration, maintenance and other technical
activities introduce additional requirements that may be covered by
existing scientific or general-purpose semantic resources.

Citizen-science and participatory activities should reuse PPSR Core and
related semantic resources where applicable.

**OAKE decision**

**ALIGN / OPEN**

OAKE should distinguish the semantic nature of an activity from its
technique, purpose, scientific domain and participation model.

Existing semantic classes such as those provided by SOSA/SSN should be
reused where applicable.

OAKE should not introduce a single monolithic taxonomy of astronomical
activities.

Controlled vocabularies for techniques, purposes and other activity
dimensions should be identified and reused or aligned before
OAKE-specific terminology is considered.

**Open issues**

- Identify controlled terminology for astronomical observing
  techniques such as imaging, photometry and spectroscopy.
- Identify terminology for education, outreach and training activities.
- Evaluate terminology for calibration, maintenance and data-processing
  activities.
- Clarify the distinction between activity type, technique, purpose and
  scientific domain.
- Evaluate PPSR Core and CSO terminology for participatory activities.
- Determine which activity dimensions should be represented through
  controlled vocabularies.

## Network Types

**Requirement**

Provide shared terminology for describing and classifying networks,
collaborations and coordinated initiatives across the astronomical
ecosystem.

**Candidate resources**

- W3C Organization Ontology (ORG)
- SOSA/SSN
- PPSR Core
- Citizen Science Ontology (CSO)
- Astronomy-specific semantic resources where relevant

**Assessment**

The concept of a network in the astronomical ecosystem covers several
distinct but potentially overlapping dimensions.

Organisational networks and collaborations may be represented using
W3C ORG, particularly where multiple organisations participate in a
coordinated structure.

Observational and instrumental networks can be represented using
SOSA/SSN concepts such as `sosa:System`, `sosa:Platform` and
`sosa:Deployment`. SOSA/SSN explicitly supports deployments involving
networks of sensors or other observational systems.

Participatory scientific initiatives may additionally be described
using PPSR Core and related citizen-science semantic resources. PPSR
Core distinguishes projects from higher-level programmes or campaigns,
providing a complementary representation for coordinated scientific
initiatives.

These dimensions may overlap. A single astronomical initiative may
simultaneously constitute an organisational collaboration, a
distributed observational infrastructure and a participatory research
programme.

No comprehensive astronomy-specific controlled vocabulary has been
identified for classifying network types.

**OAKE decision**

**ALIGN / OPEN**

OAKE should represent networks through existing semantic resources
according to the nature of the network rather than introducing a single
generic OAKE network model.

OAKE should not introduce an `oake:Network` class at this stage.

A dedicated taxonomy of astronomical network types should not be
introduced unless competency questions and use cases demonstrate that
network classification cannot be derived adequately from existing
semantic structures, participation models and purposes.

**Open issues**

- Clarify the distinction between organisational networks,
  observational networks and scientific programmes or initiatives.
- Evaluate representative networks such as TESS and FRIPON.
- Determine when explicit network-type classification is required.
- Evaluate terminology for distributed observational infrastructures.
- Evaluate PPSR Core and CSO for participatory network structures.
- Investigate astronomy-specific terminology only where existing
  generic resources prove insufficient.

## Operational Status

**Requirement**

Provide shared controlled terminology for describing the operational
and lifecycle status of instruments, observing facilities, stations,
platforms and other astronomical resources.

**Candidate resources**

- Existing lifecycle and status vocabularies
- IVOA semantic resources
- SOSA/SSN
- Domain-specific status vocabularies where relevant

**Assessment**

Operational status is relevant to several kinds of resources across the
astronomical ecosystem, including instruments, observing facilities and
distributed observing stations.

No comprehensive astronomy-specific controlled vocabulary has currently
been identified for representing the operational or lifecycle status of
these resources.

The requirement should be distinguished from the semantic modelling of
the resource itself. SOSA/SSN provides generic models for systems and
platforms, but does not by itself provide the controlled lifecycle
terminology required by OAKE.

Several dimensions may also need to be distinguished. Lifecycle status,
operational status, availability and temporary conditions such as
maintenance should not automatically be represented through a single
flat status vocabulary.

**OAKE decision**

**EXTEND / OPEN**

OAKE should investigate existing generic and domain-specific lifecycle
and operational-status vocabularies before introducing new terminology.

Where an existing vocabulary provides a suitable conceptual basis,
preference should be given to extending or aligning that vocabulary
rather than creating an OAKE-specific status vocabulary.

OAKE should not introduce ontology classes corresponding to individual
operational states.

**Open issues**

- Identify existing generic lifecycle and operational-status
  vocabularies.
- Determine whether lifecycle status, operational status and
  availability require separate classification dimensions.
- Evaluate terminology such as planned, commissioning, operational,
  inactive, under maintenance and decommissioned.
- Test the terminology against instruments, observing facilities and
  distributed observing stations.
- Investigate relevant terminology used by professional observatories,
  citizen-science networks and amateur astronomical infrastructures.
- Determine whether an extension of an existing shared vocabulary is
  sufficient before considering OAKE-specific terminology.

## Contribution Roles

**Requirement**

Provide shared controlled terminology for describing the roles played
by people and organisations in astronomical activities, projects,
observations and other contributions to the astronomical ecosystem.

**Candidate resources**

- PROV-O
- CRediT (Contributor Roles Taxonomy)
- PPSR Core
- Citizen Science Ontology (CSO)
- IVOA semantic resources
- Other domain-specific role vocabularies where relevant

**Assessment**

Contribution roles should be distinguished from agent types.

A person or organisation may play different roles depending on the
activity or context in which it participates. PROV-O provides a generic
semantic mechanism for representing such contextual roles through
`prov:Role`, `prov:hadRole` and qualified associations.

CRediT provides established controlled terminology for research
contributions such as investigation, methodology, data curation,
software, validation and project administration. It is therefore
relevant to part of the OAKE contribution landscape but does not cover
all astronomical participation roles.

PPSR Core and related citizen-science semantic resources provide
complementary terminology and structures for participation in
citizen-science projects.

IVOA resources provide some roles associated with astronomical
resources and data curation, including creator, contributor, publisher
and contact, but do not constitute a comprehensive vocabulary of
astronomical participation roles.

Astronomy-specific roles such as observer, instrument operator,
station maintainer or observatory operator require further
investigation.

**OAKE decision**

**ALIGN / OPEN**

OAKE should use PROV-O as the generic semantic mechanism for
representing contextual roles.

Existing controlled role vocabularies should be reused according to
their scope. CRediT should be reused for research-contribution roles
where applicable, while PPSR Core and related resources should be
considered for participatory-science roles.

OAKE should not introduce ontology classes for individual contributor
roles.

Astronomy-specific role terminology should only be introduced or
extended where existing shared vocabularies do not adequately cover
identified requirements.

**Open issues**

- Evaluate terminology for observer and observation-related roles.
- Evaluate terminology for instrument and station operators.
- Evaluate roles associated with observatory and facility operation.
- Evaluate volunteer and citizen-science participation roles.
- Establish mappings between overlapping CRediT, PPSR Core and
  astronomy-specific roles where appropriate.
- Distinguish contribution roles from organisational roles and
  responsibilities.
- Determine whether astronomy-specific extensions to existing role
  vocabularies are required.

## Recognition Types

**Requirement**

Provide shared terminology for describing different forms of
recognition relevant to the astronomical ecosystem, including
certifications, labels, awards, designations and similar distinctions.

**Candidate resources**

- Schema.org
- Core Criterion and Core Evidence Vocabulary (CCCEV)
- PROV-O
- Existing certification, award and recognition vocabularies
- Domain-specific recognition schemes where relevant

**Assessment**

Recognition should be distinguished from the criteria and evidence used
to obtain it.

Schema.org provides a generic `Certification` model for official
statements about subjects including persons, organisations and places.
It also provides properties for the issuing organisation, validity,
expiration, status and certification identifier.

This model is potentially applicable to recognition schemes in the
astronomical ecosystem, particularly certifications awarded to places
or organisations.

CCCEV provides complementary semantics for the criteria, requirements
and evidence involved in assessment processes but does not by itself
represent the resulting recognition.

Not every form of recognition should automatically be considered a
certification. Labels, awards, designations, accreditations and other
forms of recognition may have different semantics.

No comprehensive controlled vocabulary has yet been identified for
classifying these different recognition types.

**OAKE decision**

**ALIGN / OPEN**

OAKE should reuse existing generic recognition and certification models
where their semantics match the relevant recognition scheme.

Schema.org `Certification` should be evaluated as the preferred generic
model for certification schemes, while CCCEV should be reused for
criteria, requirements and evidence where applicable.

OAKE should not introduce a taxonomy of recognition types at this stage.

Additional controlled terminology should only be introduced or extended
where existing shared vocabularies do not adequately represent the
recognition types required by OAKE use cases.

**Open issues**

- Evaluate Schema.org `Certification` against representative dark-sky
  recognition schemes.
- Distinguish certification, label, award, designation and
  accreditation.
- Identify existing controlled vocabularies for recognition types.
- Determine how recognition schemes themselves should be represented.
- Define the relationship between a recognition and the CCCEV criteria
  used for its assessment.
- Represent issuing organisations and validity periods using existing
  semantic resources.
