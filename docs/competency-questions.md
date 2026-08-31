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

---

# Core Competency Questions

## CQ1 — Participation in an activity

**Question:**  
Which agents participate in a given activity?

**Relevant concepts:**
Agent, Activity

## CQ2 — Location of an activity

**Question:**  
Where does a given activity take place?

**Relevant concepts:**
Activity, Place

## CQ3 — Time of an activity

**Question:**  
When does a given activity take place?

**Relevant concepts:**
Activity, Time

## CQ4 — Context of an activity

**Question:**  
Which agents participate in a given activity, where does it take place, and when does it occur?

**Relevant concepts:**
Agent, Activity, Place, Time

---

# Domain Competency Questions

The following sections will introduce competency questions associated with specific domains of the astronomy ecosystem.

These questions will be developed progressively as OAKE modules and use cases are explored.

## Observation

### CQ5 — Target of an observation

**Question:**  
What astronomical object or phenomenon is the target of a given observation?

**Relevant concepts:**
Activity, Target

### CQ6 — Instrument used for an observation

**Question:**  
Which instrument was used to perform a given observation?

**Relevant concepts:**
Activity, Instrument

### CQ7 — Observing site

**Question:**  
From which observing site was a given observation performed?

**Relevant concepts:**
Activity, Place

### CQ8 — Agent responsible for an observation

**Question:**  
Which agent is responsible for a given observation?

**Relevant concepts:**
Agent, Activity

### CQ9 — Time of an observation

**Question:**  
When was a given observation performed?

**Relevant concepts:** 
Activity, Time

### CQ10 — Result of an observation

**Question:**  
What result was produced by a given observation?

**Relevant concepts:**
Activity, Result

### Observation scope

These initial competency questions provide a first basis for evaluating how existing semantic resources, particularly SOSA/SSN, can support the description of astronomical observations within OAKE.

Additional competency questions may be introduced as concrete use cases reveal further requirements.

## Instrumentation

### CQ11 — Type of instrument

**Question:**  
What type of instrument is a given instrument?

**Relevant concepts:**
Instrument

### CQ12 — Operator of an instrument

**Question:**  
Which agent operates a given instrument?

**Relevant concepts:**
Agent, Instrument

### CQ13 — Location of an instrument

**Question:**  
Where is a given instrument located?

**Relevant concepts:**
Instrument, Place

### CQ14 — Operational status of an instrument

**Question:**  
What is the operational status of a given instrument?

**Relevant concepts:**
Instrument

### CQ15 — Capabilities of an instrument

**Question:**  
What observational or measurement capabilities does a given instrument provide?

**Relevant concepts:**
Instrument

### Instrumentation scope

These initial competency questions provide a first basis for evaluating how existing semantic resources can support the description of astronomical instruments within OAKE.

Additional competency questions may be introduced as concrete instrumentation use cases reveal further requirements.

## Organisations

### CQ16 — Type of organisation

**Question:**  
What type of organisation is a given organisation?

**Relevant concepts:**
Agent, Organisation

### CQ17 — Activities of an organisation

**Question:**  
Which activities does a given organisation participate in?

**Relevant concepts:**
Agent, Organisation, Activity

### CQ18 — Location of an organisation

**Question:**  
Where is a given organisation located?

**Relevant concepts:**
Agent, Organisation, Place

### CQ19 — Relationships between organisations

**Question:**  
How is a given organisation related to another organisation?

**Relevant concepts:**
Agent, Organisation

### CQ20 — Resources operated by an organisation

**Question:**  
Which instruments or observing facilities are operated by a given organisation?

**Relevant concepts:**
Agent, Organisation, Instrument, Observing Facility

### Organisations scope

These initial competency questions provide a first basis for evaluating how existing semantic resources, particularly W3C ORG and PROV-O, can support the description of organisations and their relationships within OAKE.

Additional competency questions may be introduced as concrete organisational use cases reveal further requirements.

## Dark-sky

### CQ21 — Night-sky measurement

**Question:**  
What measurement of the night sky was performed at a given place and time?

**Relevant concepts:** 
Activity, Place, Time

### CQ22 — Instrument used for a night-sky measurement

**Question:**  
Which instrument was used to perform a given night-sky measurement?

**Relevant concepts:**
Activity, Instrument

### CQ23 — Result of a night-sky measurement

**Question:**  
What result was produced by a given night-sky measurement?

**Relevant concepts:**  
Activity, Result

### CQ24 — Dark-sky recognition of a place

**Question:**  
What dark-sky label or recognition has been awarded to a given place or territory?

**Relevant concepts:**
Place, Recognition

### CQ25 — Awarding organisation

**Question:**  
Which organisation awarded a given dark-sky label or recognition?

**Relevant concepts:** 
Agent, Organisation, Recognition

### CQ26 — Validity period of a recognition

**Question:**  
During which period is a given dark-sky label or recognition valid?

**Relevant concepts:**
Recognition, Time

### CQ27 — Criteria for a recognition

**Question:**  
Which criteria are associated with a given dark-sky label or recognition?

**Relevant concepts:**
Recognition, Criterion

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

### CQ32 — Ecosystem around an entity

**Question:**  
Which organisations, places, instruments, facilities, activities and networks are related to a given entity?

---

# Use of Competency Questions

Competency questions are used to evaluate whether existing semantic resources can satisfy OAKE requirements before new semantic terms are introduced.
