# TESS-W stars1523 — OAKE modelling case study

## Purpose

This document is a non-normative OAKE modelling case study based on a
real TESS-W photometer.

The objective is not to define an OAKE-specific model for TESS devices.
Instead, the case study is used to test whether existing semantic
resources can represent, in a coherent way:

- an individual astronomical/environmental observing device;
- its device kind and product/model information;
- its deployment at a physical location;
- its observations and measured properties;
- its participation in a distributed observing network;
- the organisations and people associated with it;
- the data and services through which its observations are made available;
- and the temporal evolution of these relationships.

The example is deliberately centred on one concrete device so that the
semantic choices remain testable and can later be generalised to the
worldwide TESS photometer network.


## Real-world resource

The device used in this case study is:

- **identifier:** `stars1523`
- **device:** TESS-W photometer
- **firmware:** v4.32
- **observation interval:** 60 seconds
- **network:** worldwide TESS photometer network associated with STARS4ALL
- **deployment date used for this case study:** 2025-12-01
- **location:** Kersaint-Plabennec / Kergreach, Brittany, France
- **approximate coordinates used in the current installation context:**
  48.498 N, 4.398 W

The exact technical and administrative metadata used in a future
knowledge graph should be verified against the authoritative TESS
metadata source before publication.


## Modelling questions

The case study should answer the following questions.

1. How should `stars1523` be represented as an individual physical device?
2. How should its TESS/TESS-W/photometer classification be represented?
3. How should product model and manufacturer information be distinguished
   from device type?
4. How should its geographical location be represented?
5. How should its deployment and deployment period be represented?
6. How should the observations made by the photometer be represented?
7. How should the measured properties be represented?
8. How should the device be connected to the wider TESS observing network?
9. How should organisations and people associated with the device be represented?
10. How should data access and datasets be represented?
11. Which semantics are already provided by existing standards?
12. Which semantic gaps, if any, remain for OAKE?


## Semantic decomposition

The real-world case can be decomposed into several complementary
dimensions.

```text
stars1523
│
├── identity
│   └── individual physical device
│
├── classification
│   ├── TESS-W
│   ├── TESS
│   └── Photometer
│
├── product information
│   ├── manufacturer
│   └── model
│
├── capabilities
│   └── measurement of night-sky related properties
│
├── deployment
│   ├── deployment location
│   ├── deployment period
│   └── installation context
│
├── observations
│   ├── observation executions
│   ├── observed properties
│   └── results
│
├── network participation
│   └── worldwide TESS photometer network
│
├── agents
│   ├── operator / maintainer
│   ├── organisations
│   └── network or project organisations
│
└── data access
    ├── observation stream
    ├── dashboard / service
    └── datasets
```


## Candidate semantic resources

| Modelling dimension | Candidate semantic resources | Preliminary role |
|---|---|---|
| Individual device | SAREF, SOSA/SSN | represent the physical device and its observational-system role |
| Device kind | SAREF / SAREF4ENVI | represent TESS and photometer kinds |
| Product model / manufacturer | Schema.org, SAREF | distinguish commercial/product information from equipment type |
| Observation system role | SOSA/SSN | represent the device as a system/sensor when it performs observations |
| Deployment | SOSA/SSN | represent the deployment of the device at a location |
| Place / geometry | GeoSPARQL | represent deployment location and geometry |
| Time | OWL-Time | represent deployment and observation temporal information |
| Observed properties | SOSA/SSN, SAREF4ENVI, domain vocabularies | describe what is measured |
| Observation | SOSA/SSN | represent observation executions |
| Network / project | W3C ORG, SOSA/SSN, PROV-O, PPSR Core where applicable | represent organisational, observational and project dimensions |
| Agents | PROV-O, W3C ORG | represent people and organisations |
| Dataset / data service | DCAT | describe datasets and access services |
| Provenance | PROV-O | describe provenance of observations, data and derived resources |
| Controlled terminology | SKOS | represent reusable classifications where needed |


## Individual device

`stars1523` is a particular physical device and should therefore be
represented independently from the class or kind of device to which it
belongs.

The modelling should preserve the distinction between:

```text
individual device      stars1523
device kind            TESS-W / TESS
broader device kind    Photometer
product model          TESS-W
manufacturer           to be verified
identifier             stars1523
```

The exact relationship between `TESS-W`, the more general TESS device
kind, and the product model must be checked carefully before RDF
publication.

In particular, product model and device kind should not be conflated
simply because the same label may be used in technical documentation.


## SAREF and SAREF4ENVI

SAREF is a strong candidate for representing the distinction between an
individual device and its device kind.

SAREF4ENVI already provides astronomy-relevant terminology for TESS
photometers and should therefore be reused rather than recreated in OAKE.

The intended reuse pattern is conceptually:

```text
stars1523
    └── device kind → TESS
                        └── broader kind → Photometer
```

A future RDF implementation should use the exact current SAREF and
SAREF4ENVI terms and properties after verification against the published
versions selected by OAKE.

OAKE should not create its own `TESS`, `TESSW` or `Photometer` concept
where an existing semantic resource provides the required meaning.


## SOSA/SSN observational role

The physical identity of `stars1523` and its role in an observational
process should be treated as complementary dimensions.

When `stars1523` performs observations, SOSA/SSN provides the generic
semantic framework for describing:

- the observing system or sensor;
- observation executions;
- observed properties;
- features of interest where relevant;
- results;
- deployment;
- and the relationship between the system and the observation.

Conceptually:

```text
stars1523
    │
    ├── deployed through → Deployment
    │
    └── makes → Observation
                    │
                    ├── observed property → ...
                    ├── result → ...
                    └── time → ...
```

The use of a SOSA/SSN class should express the functional observational
role of the resource rather than replace its more general description as
an individual physical device.


## Deployment

The installation of `stars1523` should be represented separately from the
device itself.

This is important because the same device may be:

- moved to another location;
- temporarily removed;
- redeployed;
- operated under different configurations;
- or associated with different networks over time.

A deployment can therefore connect:

```text
Deployment
├── deployed system → stars1523
├── location → Kergreach deployment place
├── start → 2025-12-01
└── end → open / not specified
```

The deployment date used in this case study is **2025-12-01**.

The knowledge graph should not encode the current location as an eternal
intrinsic property of the device when the actual fact being represented
is a temporally bounded deployment.


## Place and geometry

The deployment place should be represented independently from the device.

GeoSPARQL is the preferred generic semantic resource for spatial
representation.

Conceptually:

```text
Kergreach deployment place
    ├── geometry → point
    └── hosts / is location of → deployment
```

The approximate coordinates currently used for this case study are:

```text
latitude  = 48.498
longitude = -4.398
```

These coordinates should be treated as deployment metadata and may later
be replaced by more precise or authoritative coordinates if required.

The modelling should also allow several geographical levels to coexist,
for example:

```text
deployment point
→ locality
→ commune
→ département
→ region
→ country
```

without requiring OAKE-specific geographical classes.


## Temporal dimension

OWL-Time should provide the generic temporal model.

Time is relevant not only to individual observations, but also to:

- the lifetime of the device;
- deployments;
- network participation;
- operational status;
- maintenance periods;
- calibration periods;
- data availability;
- and changes in responsibility or ownership.

For `stars1523`, at minimum the first modelling iteration should
distinguish:

```text
device existence
deployment period
observation time
network participation period
```

These temporal dimensions should not be collapsed into one date.


## Observed properties

TESS photometers are used for night-sky monitoring and SAREF4ENVI already
contains relevant modelling originating from the STARS4ALL use case.

The exact properties to be represented should be verified against the
selected TESS/SAREF4ENVI specification and the actual metadata produced
by `stars1523`.

Candidate measured dimensions include:

- night-sky brightness / light magnitude;
- ambient temperature;
- sky temperature;
- and other device-specific measurements where available.

OAKE should reuse existing semantic descriptions for these properties
whenever possible rather than introduce duplicate OAKE properties.


## Observations and results

Individual observation executions should be represented using SOSA/SSN.

The device currently operates with an observation interval of
approximately **60 seconds**.

A simplified observation pattern is:

```text
Observation
├── made by → stars1523
├── observed property → night-sky brightness
├── result → measured value
├── result time → timestamp
└── deployment / location context → current deployment
```

The exact representation of results should follow the current SOSA/SSN
recommendations rather than rely on deprecated terms.

The case study should therefore verify the current SOSA/SSN result
pattern before RDF examples are committed.


## Network participation

The worldwide TESS photometer network should not automatically be reduced
to a single generic `Network` class.

Several complementary dimensions may be involved:

```text
TESS network
├── distributed observational infrastructure
├── collection of deployed devices
├── scientific initiative
├── project / programme context
├── organisations
├── operators / contributors
└── shared data infrastructure
```

The case study should test whether these dimensions can be represented
using complementary existing resources, in particular:

- SOSA/SSN for systems, platforms and deployments;
- W3C ORG for organisational structures;
- PROV-O for agents and activities;
- PPSR Core where public participation semantics are relevant;
- DCAT for datasets and services.

No OAKE-specific `Network` class should be introduced solely for this
case.


## Agents and organisations

People and organisations associated with `stars1523` should be modelled
through their actual roles and relationships.

Potential relationships include:

- owner;
- operator;
- maintainer;
- installer;
- project participant;
- network coordinator;
- data provider.

These should not automatically become subclasses of `Person` or
`Organization`.

PROV-O provides a generic mechanism for contextual roles and
associations, while W3C ORG provides organisational semantics.

The modelling should distinguish:

```text
who the agent is
from
what role the agent plays
from
during which period the role applies
```


## Data access

The observations produced by `stars1523` are exposed through the TESS
data infrastructure.

A future knowledge graph should distinguish:

- the individual device;
- the observation stream;
- datasets or time-series collections;
- dashboards or data-access services;
- and the project/network through which the data are published.

DCAT is the primary candidate for dataset and data-service description,
with PROV-O used where provenance relationships are required.

The MQTT infrastructure used operationally by TESS may be described when
it is relevant to a competency question, but implementation details
should not be elevated into the core OAKE conceptual model.


## Preliminary mapping summary

| Real-world element | Preliminary semantic approach | Status |
|---|---|---|
| `stars1523` individual device | SAREF device semantics + SOSA/SSN observational role | ALIGN |
| TESS device kind | SAREF4ENVI | REUSE |
| Photometer kind | SAREF4ENVI | REUSE |
| TESS-W product/model distinction | SAREF + Schema.org, to be verified | OPEN |
| Device identifier | existing identifier properties, to be selected | OPEN |
| Deployment | SOSA/SSN | REUSE |
| Deployment place | GeoSPARQL | REUSE |
| Deployment time | OWL-Time | REUSE |
| Observation | SOSA/SSN | REUSE |
| Observed properties | SAREF4ENVI + SOSA/SSN + relevant vocabularies | ALIGN |
| Observation result | current SOSA/SSN pattern, to be verified | OPEN |
| TESS network | SOSA/SSN + ORG + PROV-O + possibly PPSR Core | ALIGN |
| People / organisations | PROV-O + W3C ORG | ALIGN |
| Roles | PROV-O + controlled role vocabularies | ALIGN / OPEN |
| Dataset / data service | DCAT | REUSE |
| Provenance | PROV-O | REUSE |


## Semantic gaps to test

This case study should not assume that OAKE-specific terms are required.

The first implementation should instead test whether existing resources
can answer the relevant competency questions.

Potential gaps to investigate include:

1. the distinction between TESS as a device kind and TESS-W as a product
   model or more specific device kind;
2. a stable representation of participation in the worldwide TESS
   network;
3. operational and lifecycle status terminology;
4. roles such as device operator or station maintainer;
5. relationships between device, deployment, observation stream, dataset
   and public data service;
6. mappings between SAREF/SAREF4ENVI and SOSA/SSN in this concrete use
   case.


## Expected next step

The next step after validating this conceptual mapping is to create a
small RDF/Turtle example for `stars1523`.

That RDF example should:

- reuse only verified external terms;
- avoid introducing OAKE-specific classes unless a demonstrated gap
  remains;
- preserve the distinction between identity, classification, product
  information, observational role, deployment, location and time;
- and remain small enough to be reviewed manually.

The resulting pattern can then be generalised from one device to the
worldwide TESS photometer network.
