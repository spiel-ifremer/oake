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

**Conceptual anchors:**  
Agent, Activity

## CQ2 — Location of an activity

**Question:**  
Where does a given activity take place?

**Conceptual anchors:**  
Activity, Place

## CQ3 — Time of an activity

**Question:**  
When does a given activity take place?

**Conceptual anchors:**  
Activity, Time

## CQ4 — Context of an activity

**Question:**  
Which agents participate in a given activity, where does it take place, and when does it occur?

**Conceptual anchors:**  
Agent, Activity, Place, Time

---

# Domain Competency Questions

The following sections will introduce competency questions associated with specific domains of the astronomy ecosystem.

These questions will be developed progressively as OAKE modules and use cases are explored.

## Observation

### CQ5 — Target of an observation

**Question:**  
What astronomical object or phenomenon is the target of a given observation?

**Conceptual anchors:**  
Activity

### CQ6 — Instrument used for an observation

**Question:**  
Which instrument was used to perform a given observation?

**Conceptual anchors:**  
Activity

### CQ7 — Observing site

**Question:**  
From which observing site was a given observation performed?

**Conceptual anchors:**  
Activity, Place

### CQ8 — Agent responsible for an observation

**Question:**  
Which agent is responsible for a given observation?

**Conceptual anchors:**  
Agent, Activity

### CQ9 — Time of an observation

**Question:**  
When was a given observation performed?

**Conceptual anchors:**  
Activity, Time

### CQ10 — Result of an observation

**Question:**  
What result was produced by a given observation?

**Conceptual anchors:**  
Activity

### Observation scope

These initial competency questions provide a first basis for evaluating how existing semantic resources, particularly SOSA/SSN, can support the description of astronomical observations within OAKE.

Additional competency questions may be introduced as concrete use cases reveal further requirements.

## Instrumentation

### CQ11 — Type of instrument

**Question:**  
What type of instrument is a given instrument?

**Conceptual anchors:**  
Instrument

### CQ12 — Operator of an instrument

**Question:**  
Which agent operates a given instrument?

**Conceptual anchors:**  
Agent, Instrument

### CQ13 — Location of an instrument

**Question:**  
Where is a given instrument located?

**Conceptual anchors:**  
Instrument, Place

### CQ14 — Operational status of an instrument

**Question:**  
What is the operational status of a given instrument?

**Conceptual anchors:**  
Instrument

### CQ15 — Capabilities of an instrument

**Question:**  
What observational or measurement capabilities does a given instrument provide?

**Conceptual anchors:**  
Instrument

### Instrumentation scope

These initial competency questions provide a first basis for evaluating how existing semantic resources can support the description of astronomical instruments within OAKE.

Additional competency questions may be introduced as concrete instrumentation use cases reveal further requirements.

## Organisations

### CQ16 — Type of organisation

**Question:**  
What type of organisation is a given organisation?

**Conceptual anchors:**  
Agent

### CQ17 — Activities of an organisation

**Question:**  
Which activities does a given organisation participate in?

**Conceptual anchors:**  
Agent, Activity

### CQ18 — Location of an organisation

**Question:**  
Where is a given organisation located?

**Conceptual anchors:**  
Agent, Place

### CQ19 — Relationships between organisations

**Question:**  
How is a given organisation related to another organisation?

**Conceptual anchors:**  
Agent

### CQ20 — Resources operated by an organisation

**Question:**  
Which instruments or observing facilities are operated by a given organisation?

**Conceptual anchors:**  
Agent, Instrument, Place

### Organisations scope

These initial competency questions provide a first basis for evaluating how existing semantic resources, particularly W3C ORG and PROV-O, can support the description of organisations and their relationships within OAKE.

Additional competency questions may be introduced as concrete organisational use cases reveal further requirements.

---

# Use of Competency Questions

Competency questions are used to evaluate whether existing semantic resources can satisfy OAKE requirements before new semantic terms are introduced.
