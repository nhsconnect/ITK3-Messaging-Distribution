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

- CareConnect-ITK-Header-Practitioner-1
- CareConnect-ITK-Header-PractitionerRole-1
- CareConnect-ITK-Header-Organization-1

The following profiles have changed for this release:

- ITK-MessageHeader-2: the slicing on the event data element has been removed, and now this is bound to the ITK-MessageEvent-2 value set.

The following valuesets have changed in light of changes to their codesystems:

- ITK-MessageEvent-2
- ITK-HandlingKey-2

The following codesystems have changed:

- ITK-MessageEvent-2: new code values for eDischarge, Mental Health eDischarge, Emergency Care eDischarge and Outpatient Letter.
- ITK-HandlingKey-2: new requirements for the coded values.


## 2.0.0-alpha.0 ##
First version published using Jekyll.

