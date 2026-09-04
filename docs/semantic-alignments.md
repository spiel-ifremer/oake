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
| Network | To be investigated | OPEN |
| Recognition | To be investigated | OPEN |

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

## Next investigations

Priority should be given to concepts currently classified as **OPEN** and
to unresolved alignments that affect several competency questions.

Current priorities are:

1. Network
2. Recognition
3. Instrument type vocabularies
4. Observing facility type vocabularies
5. Relationships between organisations, facilities, instruments and networks
