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

The following profiles are tightly constrained ITK replacements of the corresponding Care Connect profiles:

- CareConnect-ITK-Header-Practitioner-1 replaces CareConnect-Practitioner-1
- CareConnect-ITK-Header-PractitionerRole-1 replaces CareConnect-PractitionerRole-1
- CareConnect-ITK-Header-Organization-1 replaces CareConnect-Organization-1

The following profiles have changed for this release:

- ITK-MessageHeader-2: the slicing on the event data element has been removed, and now this is bound to the ITK-MessageEvent-2 value set.
- Extension-ITK-MessageHandling-2: this has been restructured because the handling keys have been reviewed and updated following a decision to move to MESH, where redundant keys have been removed and additional keys added, see the [Handling Specification Section](explore_hand_spec.html) for further details.  In the previous version of this profile this was structured as Key data element containing a valueCodeableConcept and a value.  In this version, each handling key is represented by it's own extension element, containing the appropriate allowable value.

The following valuesets have changed:

- ITK-MessageEvent-2 - the value of the system element has changed to "https://fhir.nhs.uk/STU3/CodeSystem/ITK-MessageEvent-2".
- ITK-HandlingKey-2 - the value of the system element has changed to "https://fhir.nhs.uk/STU3/CodeSystem/ITK-HandlingKey-2".

The following codesystems have changed:

- ITK-MessageEvent-2: there are new code values for eDischarge, Mental Health eDischarge, Emergency Care eDischarge and Outpatient Letter.
- ITK-HandlingKey-2: the transport used for ITK 3 is only MESH, so a number of the handling specification keys are redundant.  Secondly, the interaction identifier has been replaced with a URL of a MessageDefinition profile, which will detail the required information. Therefore, the following changes have been made:
  + *Removed the concept element for "INTID" (Interaction ID)*
  + *Removed the concept element for "PID" (Profile ID)*
  + *Removed the concept element for "SNDO" (Send Only)*
  + *Removed the concept element for "SNDREC" (Send And Receive)*
  + *Removed the concept element for "SNDSRVC" (Sending Service)*
  + *Removed the concept element for "FHIRVER" (FHIR Version)*
  + *Added the concept element for "RecipientType " (Indicates the type of recipient)*
  + *Added the concept element for "Priority" (Indicates the type of recipient)*
  + *Added the concept element for "MessageDefinition Reference" (A reference to a URL for the MessageDefinition for the payload)*
  + *Added the concept element for "SenderReference " (A reference that the sender includes and wants returned in any response.)*


## 2.0.0-alpha.0 ##
First version published using Jekyll.

