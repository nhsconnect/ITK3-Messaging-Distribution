---
title: Release Notes
keywords: development, versioning
tags: [development]
sidebar: overview_sidebar
permalink: overview_release_notes.html
summary: Summary release notes of the versions released in ITK3 Messaging Distribution Implementation Guide
---

{% include important.html content="This site is under active development by NHS Digital on behalf of INTEROPen and is intended to provide all the technical resources you need to successfully develop the ITK3 Messaging Distributions. This project is being developed using an agile methodology so iterative updates to content will be added on a regular basis." %}


## 2.1.0-beta ##
This is the third version published using Jekyll.

The following profiles have changed:

- ITK-MessageHeader-2 - This was changed to ensure the ITK3 solution aligns to the ITK2.x solution.
 - Removed the following elements (and sub-elements): author, enterer, destination, responsible and reason.
 - Made the focus element 1..1 (mandatory).
 - The source element is constrained by the removal of all sub elements apart from the endpoint.
- Extension-ITK-MessageHandling-2
 - For the element extension:LocalExtension, changed the cardinality to 0..1 (optional), and made the value[x] sub-element 1..1 (mandatory). 

The diagrams and examples have changed to reflect the changes to the profiles.

The following examples have changed:

- ITK-SendPayload-Invalid-Example-2.xml - Corrected the reference value="https://fhir.nhs.uk/STU3/MessageDefinition/ITK-EDIS-MessageDefinition-1".  The message header is corrected to reference the practitioner and organization.
- ITK-SendPayload-Valid-Example-2.xml - Corrected the reference value="https://fhir.nhs.uk/STU3/MessageDefinition/ITK-EDIS-MessageDefinition-1". The message header is corrected to reference the practitioner and organization.
- ITK-BusinessAck-Success-Example-2.xml - Removed the elements: destination and response, added the element focus.


## 2.1.0-alpha ##
This is the second version published using Jekyll.

The following profiles are tightly constrained ITK replacements of the corresponding Care Connect profiles:

- CareConnect-ITK-Header-Practitioner-1 replaces CareConnect-Practitioner-1
- CareConnect-ITK-Header-PractitionerRole-1 replaces CareConnect-PractitionerRole-1
- CareConnect-ITK-Header-Organization-1 replaces CareConnect-Organization-1

The following profiles have changed for this release:

- ITK-MessageHeader-2: the slicing on the event data element has been removed, and now this is bound to the ITK-MessageEvent-2 value set.
- Extension-ITK-MessageHandling-2: this has been restructured because the handling keys have been reviewed and updated following a decision to move to MESH, where redundant keys have been removed and additional keys added, see the [Handling Specification Section](explore_hand_spec.html) for further details.  In the previous version of this profile this was structured as Key data element containing a valueCodeableConcept and a value.  In this version, each handling key is represented by its own extension URL element, containing the appropriate allowable value.

This valueset has changed:

- ITK-MessageEvent-2 - the value of the system element has changed to "https://fhir.nhs.uk/STU3/CodeSystem/ITK-MessageEvent-2".

This valueset has been removed:

- ITK-HandlingKey-1 - this is no longer needed, as the Handling Key information is modelled as a complex extension which consists of an Extension URL that carries the Handling Key and an associated allowable value in the Extension-ITK-MessageHandling-2 profile.  See the [Handling Specification Section](explore_hand_spec.html) for further details".

This codesystem has changed:

- ITK-MessageEvent-2: there are new code values for eDischarge, Mental Health eDischarge, Emergency Care eDischarge and Outpatient Letter.

This codesystem has been removed:

- ITK-HandlingKey-1: this is no longer needed due to the way that the handling key information is modelled in the Extension-ITK-MessageHandling-2 profile

The XML Examples have been updated to reflect the changes outlined above.

## 2.0.0-alpha.0 ##
First version published using Jekyll.

