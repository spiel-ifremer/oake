# OAKE Competency Questions

## Purpose

This document defines the competency questions used to guide the conceptual and semantic development of OAKE.

Competency questions describe the kinds of questions that the OAKE semantic framework should be able to answer.

They provide a practical link between community needs, conceptual modelling, semantic alignments and implementation choices.

---

# Principles

Competency questions should express concrete information needs rather than implementation choices.

They should:

- be understandable by domain experts;
- describe realistic questions arising from the astronomy ecosystem;
- remain independent of specific ontologies or technologies;
- help identify the concepts and relationships required by OAKE;
- support the evaluation of existing semantic resources before new terms are introduced.

The terms listed under **Relevant concepts** express conceptual requirements; they do not imply that OAKE must introduce a class with each of these names. Existing semantic resources should be evaluated first.

Domain-specific questions may specialise general questions without requiring separate modelling patterns. For example, CQ22 specialises CQ6 for night-sky measurements.

Question identifiers are stable. Refine existing questions or add new identifiers without renumbering established questions.

---

# Core Competency Questions

## CQ1 — Participation in an activity

**Question:**
Which agents participate in a given activity?

**Relevant concepts:** Agent, Activity

## CQ2 — Location of an activity

**Question:**
Where does a given activity take place?

**Relevant concepts:** Activity, Place

## CQ3 — Time of an activity

**Question:**
When does a given activity take place?

**Relevant concepts:** Activity, Time

## CQ4 — Context of an activity

**Question:**
Which agents participate in a given activity, where does it take place, and when does it occur?

**Relevant concepts:** Agent, Activity, Place, Time

---

# Domain Competency Questions

The following sections will introduce competency questions associated with specific domains of the astronomy ecosystem.

These questions will be developed progressively as OAKE use cases and any necessary extensions are explored. The initial application sequence is TESS / STARS4ALL, Allsky, FRIPON and the astronomy ecosystem in Brittany.

## Observation

### CQ5 — Target of an observation

**Question:**
What astronomical object or phenomenon is the target of a given observation?

**Relevant concepts:** Activity, Target

### CQ6 — Instrument used for an observation

**Question:**
Which instrument was used to perform a given observation?

**Relevant concepts:** Activity, Instrument

### CQ7 — Observing site

**Question:**
From which observing site was a given observation performed?

**Relevant concepts:** Activity, Place

### CQ8 — Agent responsible for an observation

**Question:**
Which agent is responsible for a given observation?

**Relevant concepts:** Agent, Activity

### CQ9 — Time of an observation

**Question:**
When was a given observation performed?

**Relevant concepts:** Activity, Time

### CQ10 — Result of an observation

**Question:**
What result was produced by a given observation?

**Relevant concepts:** Activity, Result

### Observation scope

These initial competency questions provide a first basis for evaluating how existing semantic resources, particularly SOSA/SSN, can support the description of astronomical observations within OAKE.

Additional competency questions may be introduced as concrete use cases reveal further requirements.

## Instrumentation

### CQ11 — Type of instrument

**Question:**
What type of instrument is a given instrument?

**Relevant concepts:** Instrument

### CQ12 — Operator of an instrument

**Question:**
Which agent operates a given instrument?

**Relevant concepts:** Agent, Instrument

### CQ13 — Location of an instrument

**Question:**
Where is a given instrument located?

**Relevant concepts:** Instrument, Place

### CQ14 — Operational status of an instrument

**Question:**
What is the operational status of a given instrument?

**Relevant concepts:** Instrument

### CQ15 — Capabilities of an instrument

**Question:**
What observational or measurement capabilities does a given instrument provide?

**Relevant concepts:** Instrument

### Instrumentation scope

These initial competency questions provide a first basis for evaluating how existing semantic resources can support the description of astronomical instruments within OAKE.

Additional competency questions may be introduced as concrete instrumentation use cases reveal further requirements.

## Organisations

### CQ16 — Type of organisation

**Question:**
What type of organisation is a given organisation?

**Relevant concepts:** Agent, Organisation

### CQ17 — Activities of an organisation

**Question:**
Which activities does a given organisation participate in?

**Relevant concepts:** Agent, Organisation, Activity

### CQ18 — Location of an organisation

**Question:**
Where is a given organisation located?

**Relevant concepts:** Agent, Organisation, Place

### CQ19 — Relationships between organisations

**Question:**
How is a given organisation related to another organisation?

**Relevant concepts:** Agent, Organisation

### CQ20 — Resources operated by an organisation

**Question:**
Which instruments or observing facilities are operated by a given organisation?

**Relevant concepts:** Agent, Organisation, Instrument, Observing Facility

### Organisations scope

These initial competency questions provide a first basis for evaluating how existing semantic resources, particularly W3C ORG and PROV-O, can support the description of organisations and their relationships within OAKE.

Additional competency questions may be introduced as concrete organisational use cases reveal further requirements.

## Dark-sky

### CQ21 — Night-sky measurement

**Question:**
What measurement of the night sky was performed at a given place and time?

**Relevant concepts:** Activity, Place, Time

### CQ22 — Instrument used for a night-sky measurement

**Question:**
Which instrument was used to perform a given night-sky measurement?

**Relevant concepts:** Activity, Instrument

### CQ23 — Result of a night-sky measurement

**Question:**
What result was produced by a given night-sky measurement?

**Relevant concepts:**
Activity, Result

### CQ24 — Dark-sky recognition of a place

**Question:**
What dark-sky label or recognition has been awarded to a given place or territory?

**Relevant concepts:** Place, Recognition

### CQ25 — Awarding organisation

**Question:**
Which organisation awarded a given dark-sky label or recognition?

**Relevant concepts:** Agent, Organisation, Recognition

### CQ26 — Validity period of a recognition

**Question:**
During which period is a given dark-sky label or recognition valid?

**Relevant concepts:** Recognition, Time

### CQ27 — Criteria for a recognition

**Question:**
Which criteria are associated with a given dark-sky label or recognition?

**Relevant concepts:** Recognition, Criterion

### Dark-sky scope

These initial competency questions cover both the observation and measurement of night-sky conditions and the recognition or labelling of places and territories.

They provide a basis for evaluating existing semantic resources for environmental monitoring, astronomical observations, territorial descriptions and recognition schemes.

## Astronomical ecosystem

### CQ28 — Resources associated with an organisation

**Question:**
Which astronomical resources are associated with a given organisation?

### CQ29 — Organisations associated with a place

**Question:**
Which organisations are associated with a given place?

### CQ30 — Resources located at a place

**Question:**
Which instruments, observing facilities or other astronomical resources are located at a given place?

### CQ31 — Participation in a network

**Question:**
Which organisations, instruments or facilities participate in a given astronomical network?

**Scope clarification:** Distinguish participation roles and, where available, their periods of validity. Membership, coordination, operation and instrument contribution should not be treated as interchangeable relationships.

### CQ32 — Ecosystem around an entity

**Question:**
Which organisations, places, instruments, facilities, activities and networks are related to a given entity?

### CQ33 — Astronomical ecosystem within a territory

**Question:** Which organisations, places, facilities, instruments, networks, educational resources and other astronomical entities are associated with a given geographical area?

### CQ34 — Astronomical ecosystem at a given time

**Question:** Which organisations, places, facilities, instruments, networks, activities and other astronomical entities existed or were active at a given time or during a given period?

### CQ35 — Astronomical ecosystem in space and time

**Question:** Which astronomical entities and relationships were associated with a given geographical area at a given time or during a given period?

---

# Cross-cutting Competency Questions

## CQ36 — Instrument deployment history

**Question:**
On which platforms and at which sites was a given instrument deployed, and during which periods?

**Relevant concepts:** Instrument, Platform, Place, Deployment, Time

**Scope clarification:** Preserve the identity of the instrument across successive deployments. Distinguish its physical support from its geographical site. This question complements the location requirement in CQ13 and the broader temporal requirements in CQ34–CQ35.

## CQ37 — Instrument configuration

**Question:**
Which components and device models make up a given observing installation during a specified period?

**Relevant concepts:** Observing Installation, Instrument, Component, Device Model, Configuration, Time

**Scope clarification:** Distinguish the individual device, its functional type and its model. For a camera installation, identify the camera and lens separately when source metadata supports this level of detail. Configuration changes should not erase earlier configurations.

## CQ38 — Associated data and services

**Question:**
Which datasets, images or services are available for a given instrument, observing facility or network, and how can they be accessed?

**Relevant concepts:** Instrument, Observing Facility, Network, Dataset, Image, Service, Access Information

**Scope clarification:** Describe or link to relevant resources, their access locations and any documented access conditions. Answering this question does not require importing all observation data or image archives into the knowledge graph.

## CQ39 — Information provenance

**Question:**
What is the source of a given statement about an astronomical entity or relationship, and when was that statement last updated?

**Relevant concepts:** Statement, Entity, Relationship, Source, Provenance, Time

**Scope clarification:** Distinguish the period when a fact applies from the date when its description was updated. Where available, retain the source's update date separately from the date of ingestion into the graph. Unknown dates must remain unspecified. Provenance must be traceable to the relevant statement, even when it is recorded for a group of statements sharing a source.

---

# Use of Competency Questions

Competency questions are used to evaluate whether existing semantic resources can satisfy OAKE requirements before new semantic terms are introduced.

## Initial use-case coverage

The following examples are proposed validation scenarios, not assertions about existing network data or agreements with their teams. Letters such as P1 and S1 denote fictional identifiers. Candidate sources and their coverage remain to be assessed with the relevant communities.

| Use case | Questions | Example information need | Expected answer | Required relationships | Candidate sources |
| --- | --- | --- | --- | --- | --- |
| TESS / STARS4ALL | CQ13, CQ31, CQ36 | Where was photometer P1 deployed at date D? | P1, its platform, site and a deployment period covering D; network participation if documented | Instrument–deployment–platform; platform/site location; deployment period; network participation | Network metadata and deployment records, if available from the teams |
| Allsky | CQ11, CQ15, CQ37 | Which installations used camera model M and lens model L at date D? | Matching installation identifiers, camera and lens components, their models and configuration periods | Installation–component; device–model; configuration period | Camera map metadata and contributor-supplied configuration records, where available |
| FRIPON | CQ19, CQ20, CQ31 | Which organisations contribute to network N, and which stations do they operate? | Organisations, their participation roles and the stations they operate; validity periods where known | Organisation–network participation; participation role; organisation–station operation | Network and station documentation, to be assessed with the teams |
| Brittany | CQ1–CQ4, CQ17, CQ30, CQ33 | Which associations offer public astronomy activities within territory T during period P, and where? | Associations, activities, locations and dates matching the requested area and period, with evidence of public access | Organisation–activity participation; activity–place; activity–time; place–territory; activity audience/access | Collaborative uMap as a starting point, supplemented by association and event sources |
| Across networks | CQ31, CQ32, CQ35 | Which sites or instruments are associated with more than one network during period P? | Reconciled entity identifiers, their networks and overlapping participation periods | Entity identity links; network participation; participation periods | Reconciled metadata from the participating graphs |
| Data and services | CQ38 | Where can resources associated with instrument P1 be accessed? | Resource identifiers, resource types, access locations and documented access conditions | Instrument–resource association; resource–access information | Documented data catalogues, network services and contributor pages |
| Provenance | CQ39 | Which source supports the statement that organisation A operates station S1? | The relevant source and available statement update information, separately from any operating period | Statement–source; statement update time; relationship validity period | Source records and metadata transformation logs |

Temporal examples can only be answered when the relevant history is available. A current map or configuration record alone does not establish past deployments, configurations or participation.

## Evaluation approach

For each selected question:

1. Define a small example dataset and the expected answer, including the identifiers and relationships to return.
2. Record the required concepts, relationships, temporal conditions and source information.
3. Evaluate whether existing semantic resources can represent these requirements.
4. Check that a query over the example returns the expected answer, including a case that should not match.
5. Record whether the requirement is supported, partially supported or unresolved, and distinguish a modelling gap from missing source data.

The scenarios above are starting points. Public access, participation roles, historical configuration and entity reconciliation may reveal further requirements that should be documented before additional competency questions or OAKE-specific terms are introduced.
