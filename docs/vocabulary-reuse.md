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
| Astronomical object types | IVOA / SIMBAD semantic resources, UAT | OPEN |
| Spectral domains / wavebands | IVOA vocabularies | OPEN |
| Organisation types | To be investigated | OPEN |
| Activity types | To be investigated | OPEN |
| Network types | To be investigated | OPEN |
| Operational status | To be investigated | OPEN |
| Contribution roles | To be investigated | OPEN |
| Recognition types | To be investigated | OPEN |


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
