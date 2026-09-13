# AllSky Kersaint-Plabennec — OAKE modelling case study

## Purpose

This document is a non-normative OAKE modelling case study based on a
real operational AllSky installation.

The objective is not to define an OAKE-specific model for AllSky systems.
Instead, the case study is used to test whether existing semantic
resources can represent, in a coherent way:

- a complete observing system assembled from several physical components;
- the camera used as an observational sensor;
- the optical lens and other non-sensor components;
- the computing device and software involved in acquisition and publication;
- the deployment of the system at a physical place;
- the production of images and other data products;
- public access to those products;
- and the spatial and temporal relationships between the installation and
  other observing systems located at the same site.

This case complements the `stars1523` TESS-W case study by focusing on a
more composite observational system.


## Real-world installation

The installation used in this case study is an operational AllSky system
located at Kergreach, Kersaint-Plabennec, Brittany, France.

Current known information:

- **system:** AllSky installation
- **camera:** ZWO ASI678MC
- **lens:** 2.5 mm fisheye lens
- **computer:** Raspberry Pi 5 Model B, 16 GB
- **software:** Allsky
- **operational since:** 2026-09-05
- **public image access:** https://allsky.tail01e8e7.ts.net/allsky/
- **deployment place:** the same site as the TESS-W `stars1523` deployment
- **approximate coordinates:** 48.498 N, 4.398 W
- **field of view:** not yet characterised precisely

The AllSky and TESS-W devices are physically separated by only a few
centimetres. At the spatial precision used by the current examples, they
should therefore reuse the same place resource rather than create two
artificially distinct geographical entities.


## Modelling questions

This case study should answer the following questions.

1. What should be represented as the complete AllSky observing system?
2. What should be represented as the sensor within that system?
3. How should the ZWO ASI678MC camera body be distinguished from the
   complete AllSky installation?
4. How should the 2.5 mm fisheye lens be represented?
5. How should the Raspberry Pi be represented?
6. How should the Allsky software be represented?
7. How should part-whole and subsystem relationships be represented?
8. How should the system deployment be represented?
9. How should the deployment reuse the same place as `stars1523`?
10. How should the operational start date be represented?
11. How should the field of view be represented without assuming a 180°
    coverage that has not been measured?
12. How should generated images be represented?
13. How should the public web endpoint be related to the physical system
    and its data products?
14. Which semantics are already provided by existing standards?
15. Which semantic gaps, if any, remain for OAKE?


## Semantic decomposition

The real-world installation can be decomposed into several complementary
dimensions.

```text
AllSky observing system
│
├── camera
│   └── ZWO ASI678MC
│
├── optics
│   └── 2.5 mm fisheye lens
│
├── computing
│   └── Raspberry Pi 5 Model B, 16 GB
│
├── software
│   └── Allsky
│
├── deployment
│   ├── Kergreach shared observing place
│   ├── operational since 2026-09-05
│   └── field of view not yet characterised
│
├── observations / acquisitions
│   └── sky images
│
└── publication
    └── public AllSky web endpoint
```


## Candidate semantic resources

| Modelling dimension | Candidate semantic resources | Preliminary role |
|---|---|---|
| Complete observing system | SOSA/SSN, SAREF, SAREF4SYST | represent the assembled functional system |
| Camera body | SAREF, SOSA/SSN | represent the individual camera and its sensor role |
| Camera type | SAREF device-kind semantics, astronomy-specific vocabularies | classify the camera independently from brand/model |
| Lens | SAREF / generic physical-resource semantics | represent a physical optical component |
| Computing device | SAREF | represent the Raspberry Pi as a device |
| Software | PROV-O, schema/software vocabularies to investigate | represent acquisition and publication software |
| System composition | SAREF / SAREF4SYST / SOSA/SSN | represent components and functional subsystems |
| Deployment | SOSA/SSN | represent the installation at the observing place |
| Place / geometry | GeoSPARQL | reuse the Kergreach place resource |
| Time | SOSA/SSN, OWL-Time | represent operational and deployment periods |
| Field of view | astronomy-specific / imaging vocabularies to investigate | represent measured angular coverage |
| Image acquisition | SOSA/SSN | represent observation/acquisition activity |
| Image product | PROV-O, DCAT and media/data vocabularies | represent generated images and collections |
| Public access | DCAT and web-service vocabularies | represent access to published products |
| Provenance | PROV-O | connect system, activity, software and generated products |


## Complete AllSky system

The complete AllSky installation should be distinguished from the
individual camera.

Conceptually:

```text
AllSky system
├── camera → ZWO ASI678MC
├── lens → 2.5 mm fisheye lens
├── computer → Raspberry Pi 5
├── software → Allsky
└── deployment → Kergreach
```

The complete system is the functional configuration that performs the
sky-imaging activity.

The ZWO ASI678MC alone should therefore not be treated as synonymous with
the complete AllSky installation.


## Camera

The ZWO ASI678MC is an individual physical camera.

Its representation should distinguish:

```text
individual resource    the actual installed camera
equipment type         astronomical / imaging camera
manufacturer           ZWO
product model          ASI678MC
functional role        sensor within the AllSky system
```

The camera is a strong candidate for representation as a
`saref:Sensor` and `sosa:Sensor` when its observational role is being
described.

Manufacturer and product model information should remain distinct from
the camera-type classification.


## Lens

The 2.5 mm fisheye lens is a physical optical component of the
installation.

It should not automatically be represented as a `sosa:Sensor` or
`sosa:System`.

The lens contributes to the optical characteristics of the complete
system, including its field of view, but its semantic identity should
remain distinct from the camera body and from the complete AllSky system.

The case study should investigate whether a generic part-whole relation
is sufficient or whether a more specific optical-component relation is
available from an existing semantic resource.


## Computing device

The Raspberry Pi 5 Model B, 16 GB, is a physical computing device used
within the installation.

It is not itself the astronomical sensor.

Its role is operational: acquisition control, image processing,
generation of derived products and publication.

SAREF is a candidate for the device-level description, while its exact
functional relationship with the AllSky system should be tested using
SAREF4SYST or another suitable system-composition model.


## Software

The Allsky software should be represented independently from the physical
Raspberry Pi on which it runs.

The model should distinguish:

```text
software
from
computing device
from
physical observing system
```

Potential semantic requirements include:

- software identity;
- software version;
- execution on a computing device;
- role in image acquisition;
- role in image processing;
- role in publication;
- provenance of generated images.

The most appropriate reusable software vocabulary should be investigated
before introducing any OAKE-specific software class or property.


## System composition

This case is intended to test the difference between:

- a physical component;
- a functional subsystem;
- a sensor;
- a generic device;
- and the complete observing system.

Not every component should be forced into `sosa:System`.

For example:

```text
ZWO ASI678MC       → sensor / subsystem candidate
Raspberry Pi       → computing device / subsystem candidate
fisheye lens       → physical optical component
Allsky software    → software resource
AllSky assembly    → complete observational system
```

SAREF and SAREF4SYST should be evaluated for generic composition and
system/subsystem relationships.

SOSA/SSN `hasSubSystem` should only be used where the component being
linked is itself meaningfully a system.


## Shared observing place

The AllSky installation and the TESS-W `stars1523` deployment are located
at the same observing place for the purposes of the current OAKE
examples.

The same place resource should therefore be reused.

Conceptually:

```text
Kergreach observing place
├── TESS-W stars1523 deployment
└── AllSky deployment
```

The approximate geometry currently used is:

```text
POINT (-4.398 48.498)
```

The difference of a few centimetres between the physical devices is below
the spatial resolution relevant to the current examples.

The model should avoid creating a new `Place` merely because a second
device is deployed there.


## Deployment

The AllSky deployment should be represented independently from the
complete system.

Known temporal information:

```text
operational since → 2026-09-05
```

A deployment pattern should allow the system to be moved, replaced or
reconfigured in the future without changing the identity of the place or
necessarily the identity of every component.

Conceptually:

```text
AllSky deployment
├── deployed system → AllSky observing system
├── place → Kergreach observing place
├── start → 2026-09-05
└── end → open / not specified
```

SOSA/SSN is the preferred starting point for this deployment pattern.

A change in the technical configuration of the AllSky system does not
necessarily imply a new deployment.

For example, replacing the fisheye lens while keeping the same camera,
observing system and deployment place should be represented as a change
of system configuration rather than automatically as a new sensor
deployment.

The modelling should therefore distinguish:

- the persistent identity of the observing system;
- its deployment at a place;
- and successive technical configurations valid during particular
  periods.

This is particularly important for optical components because a lens
replacement may change field of view, angular coverage and image
characteristics without changing the identity of the camera or the
deployment place.

Conceptually:

```text
AllSky observing system
│
├── deployment
│   └── Kergreach, since 2026-09-05
│
└── configurations
    ├── configuration A
    │   ├── camera → ZWO ASI678MC
    │   ├── lens → current 2.5 mm fisheye lens
    │   └── validity → from 2026-09-05 until replacement
    │
    └── configuration B
        ├── camera → ZWO ASI678MC
        ├── lens → future replacement lens
        └── validity → from replacement date
```

The exact semantic resource to use for representing temporally valid
technical configurations remains an open alignment question. Existing
configuration, system-composition and provenance models should be
investigated before introducing any OAKE-specific configuration class.


## Field of view

The installation should not currently be described as having a 180°
field of view.

The AllSky label describes the intended observing configuration but does
not by itself prove an exact angular coverage.

The field of view should therefore remain:

```text
OPEN / not yet characterised
```

until it is calculated, measured or obtained from authoritative optical
specifications.

The future representation should distinguish where necessary:

- horizontal field of view;
- vertical field of view;
- diagonal field of view;
- circular image coverage;
- useful sky coverage after masking or obstruction.

This is a vocabulary and data-modelling question rather than a reason to
introduce an OAKE-specific field-of-view property prematurely.


## Image acquisition

The principal observational product of the AllSky installation is a sky
image.

A first semantic pattern should distinguish:

```text
sensor/system
    ↓ performs
observation / acquisition
    ↓ generates
image result / digital resource
```

The observation may include:

- acquisition time;
- exposure duration;
- sensor configuration;
- observed portion of the sky;
- generated image;
- processing provenance.

The exact boundary between a SOSA observation result and a separately
described digital image resource should be tested against real Allsky
output before a Turtle example is finalised.


## Public image access

The public endpoint is:

https://allsky.tail01e8e7.ts.net/allsky/

This URL should not be treated as the identity of the physical camera or
the AllSky system.

The intended distinction is:

```text
physical system
    ↓ produces
images / data products
    ↓ exposed through
public web access
```

A future example should investigate DCAT or another suitable service
description mechanism for representing public access.

The public endpoint may expose current images, archives or derived
products, but these should remain semantically distinct from the service
through which they are accessed.


## Relationship with the TESS-W case study

The AllSky and TESS-W case studies are intentionally complementary.

```text
Kergreach observing place
│
├── TESS-W deployment
│   └── stars1523
│
└── AllSky deployment
    └── composite AllSky observing system
```

The TESS-W case tests a relatively self-contained sensor producing
numerical observations.

The AllSky case adds:

- several physical components;
- system composition;
- software;
- image products;
- public web access;
- optical characteristics;
- and a more explicit distinction between sensor and complete
  observational system.

Together they provide an initial test of whether OAKE can describe
heterogeneous resources deployed at the same real-world observing place.


## Preliminary mapping summary

| Real-world element | Preliminary semantic approach | Status |
|---|---|---|
| Complete AllSky installation | SOSA/SSN + SAREF/SAREF4SYST | ALIGN / OPEN |
| ZWO ASI678MC individual camera | SAREF + SOSA/SSN sensor role | ALIGN |
| Camera type | shared equipment/instrument vocabulary | OPEN |
| Manufacturer ZWO | organisation/product semantics | ALIGN / OPEN |
| Product model ASI678MC | product-model semantics | ALIGN / OPEN |
| 2.5 mm fisheye lens | generic physical-resource/component semantics | OPEN |
| Raspberry Pi 5 | SAREF device semantics | ALIGN |
| Allsky software | software vocabulary to investigate | OPEN |
| Part-whole relationships | SAREF / SAREF4SYST / SOSA/SSN | ALIGN / OPEN |
| AllSky deployment | SOSA/SSN | REUSE |
| Kergreach observing place | shared GeoSPARQL place with stars1523 | REUSE |
| Deployment start date | SOSA/SSN temporal property | REUSE |
| Field of view | existing optical/imaging terminology to investigate | OPEN |
| Image acquisition | SOSA/SSN | ALIGN |
| Image data product | PROV-O / DCAT / media vocabularies | ALIGN / OPEN |
| Public web endpoint | DCAT / service description | ALIGN / OPEN |
| Provenance | PROV-O | REUSE |


## Semantic gaps to test

This case study should not assume that OAKE-specific terms are required.

The first implementation should test whether existing semantic resources
can represent the installation adequately.

Potential gaps to investigate include:

1. a reusable controlled term for an AllSky camera or AllSky imaging
   system;
2. the semantic distinction between camera body, optical component and
   complete observing system;
3. generic part-whole relationships for passive optical components;
4. representation of software within the observing configuration;
5. representation of optical characteristics such as field of view;
6. the relationship between observation, image result and published image
   resource;
7. representation of a continuously updated public AllSky endpoint;
8. operational status and configuration changes over time;
9. representation and temporal validity of successive system
   configurations when components such as lenses, cameras or computing
   equipment are replaced.


## Expected next step

Before creating an RDF/Turtle example, the conceptual mapping should be
reviewed against the actual installed configuration.

The first RDF example should then remain deliberately small and should:

- reuse the same Kergreach place resource as the `stars1523` example;
- distinguish the complete AllSky system from the ASI678MC camera;
- represent the deployment start date as 2026-09-05;
- include only verified physical components;
- leave the field of view unspecified until characterised;
- distinguish the public web endpoint from the physical system;
- preserve the distinction between deployment and technical
  configuration so that future component replacements can be represented
  without rewriting the deployment history;
- and avoid introducing OAKE-specific classes unless a documented
  semantic gap remains.

A later iteration can add one real image acquisition and its resulting
image resource, in the same way that the `stars1523` demonstrator was
progressively extended with real observations.
