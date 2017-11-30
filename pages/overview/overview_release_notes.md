---
title: Release Notes
keywords: development, versioning
tags: [development]
sidebar: overview_sidebar
permalink: overview_release_notes.html
summary: Summary release notes of the versions released in ITK3 Messaging Distribution Implementation Guide
---

{% include important.html content="This site is under active development by NHS Digital on behalf of INTEROPen and is intended to provide all the technical resources you need to successfully develop the ITK3 Messaging Distributions. This project is being developed using an agile methodology so iterative updates to content will be added on a regular basis." %}

  
## 2.1.0-alpha ##
The second version published using Jekyll.

The following new profiles are constrained versions of the corresponding Care Connect profiles:

- [ITK-Header-Practitioner-1](https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-ITK-Header-Practitioner-1)
- [CareConnect-ITK-Header-PractitionerRole-1](https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-ITK-Header-PractitionerRole-1)
- [ITK-Header-Organization-1](https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-ITK-Header-Organization-1)

The following profiles have changed for this release:

- [ITK-MessageHeader-1](https://fhir.nhs.uk/STU3/StructureDefinition/ITK-MessageHeader-1): the slicing on the event data element has been removed, and now this is bound to the ITK-MessageEvent-1 value set.

## 2.0.0-alpha.0 ##
First version published using Jekyll.

