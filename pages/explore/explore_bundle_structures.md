---
title: Bundles Structure
keywords:  messaging, bundles
tags: [fhir,messaging]
sidebar: foundations_sidebar
permalink: explore_bundle_structures.html
summary: "The structures of the bundles used in the messages"
---

{% include custom/search.warnbanner.html %}

## Background ##
To enable a standardised structure to carry information regarding common end-to-end distribution requirements, two profiles have been defined, the ITK3 Message Bundle and the ITK3 MessageHeader that combine to make up the ITK3 Messaging Distribution Bundle. Two further ITK3 bundle profiles are provided for possible use as the second bundle for a payload: a bundle for use with document payloads and a bundle for all other payload types. These are detailed below.

The ITK3 Messaging Distribution Bundle may be used to wrap any payload. This provides a lightweight structure to carry information relating to the end-to-end technical distribution of payloads.
The ITK3 Messaging Distribution Bundle is an autonomous and transport agnostic design, whilst enabling audit, access control and authentication as required by both sender and receivers. Some extensions have been added to the ITK3 MessageHeader profile to allow a similar functionality to the previous versions of ITK. 

This specification also defines a ITK3 Response message which may be used with the ITK3 Messaging Distribution Bundle.

## The ITK3 Messaging Distribution Bundle ##

The diagram below shows a schematic of the basic ITK3 Messaging Distribution Bundle structure. The ITK3 message bundle is the container for the ITK3 MessageHeader and any payload. The MessageHeader contains information that pertains to the payload content. The Payload can be anything.
The diagrams showing the ITK Message Bundle below are simplified and do not show all the resources which could be contained therein. A fuller version of the [ITK Message Bundle](#itk3-messaging-distribution-bundle-example) can be viewed as an XML example.

<img src="images/explore/ITKBundle.png" style="width:50%;max-width: 50%;">


## ITK3 Typical Bundle Structures ##


## ITK3 FHIR Document Bundle Structure ##

The diagram below is an example of an ITK3 FHIR document payload that may be used with the ITK3 Messaging Distribution Bundle. When sending FHIR Documents the type of bundle is a document.

<img src="images/explore/ITKDocExample.png" style="width:50%;max-width: 50%;">

## ITK3 Response Bundle Structure ##

The diagram below is an example of a ITK3 Response message structure.
 
<img src="images/explore/BUSExample.png" style="width:50%;max-width: 50%;">


## ITK3 Other Payload Bundle Structure ##

The diagram below is an example of the structure used when the payload is an additional bundle, of one of the types listed below:

- message
- transaction
- transaction-response
- batch
- batch-response
- history
- searchset
- collection

<img src="images/explore/ITKPayBundExample.png" style="width:50%;max-width: 50%;">


## The ITK3 Messaging Distribution Bundle Resources ##

This Bundle is a generic bundle for sending any payload.

The Bundle consists of the following FHIR Resource Profiles.

- **[ITK-Message-Bundle-1](https://fhir.nhs.uk/STU3/StructureDefinition/ITK-Message-Bundle-1)** - A NHS Digital Profile of the FHIR Bundle resource.
- **[ITK-MessageHeader-2](https://fhir.nhs.uk/STU3/StructureDefinition/ITK-MessageHeader-2)** - A NHS Digital Profile of the FHIR MessageHeader resource.	
- **[CareConnect-ITK-Header-Practitioner-1](https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-ITK-Header-Practitioner-1)** - An ITK3 Header Profile of the FHIR Practitioner resource.
- **[CareConnect-ITK-Header-Organization-1](https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-ITK-Header-Organization-1)** - An ITK3 Header Profile of the FHIR Organization resource.
- Payload - one of the following:

-- One or more FHIR Resource. 

-- The **[ITK-Response-OperationOutcome-1](https://fhir.nhs.uk/STU3/StructureDefinition/ITK-Response-OperationOutcome-1)**

-- The **[ITK-Document-Bundle-1](https://fhir.nhs.uk/STU3/StructureDefinition/ITK-Document-Bundle-1)** containing a composition and one or more FHIR Resources.

-- The **[ITK-Payload-Bundle-1](https://fhir.nhs.uk/STU3/StructureDefinition/ITK-Payload-Bundle-1)** containing one or more FHIR Resources.
 
 
## ITK3 Messaging Distribution Bundle Diagram ##

The diagram shows the referencing between the profiles in the bundle which make up the a typical ITK3 Messaging Distribution Bundle.

<img src="images/explore/send_payload_message.png" style="width: 75%;max-width: 75%;"> 

## ITK3 Messaging Distribution Bundle Example ##

<script src="https://gist.github.com/IOPS-DEV/6d9972c89354a0cdd07714464fdb5698.js"></script>

## ITK3 Response Bundle ##

ITK3 Responses are used to convey information from the receiving system back to the sending system, the messages are clinically agnostic and relay information regarding errors in the received ITK3 Messaging Distribution Bundle, such as a failure in validation due to incorrect structure. This Response message also allows systems to report that a message was received without error. When a message is received without error at the infrastructure or technical layer it may subsequently error later at the business layer.

The Bundle consists of the following FHIR Resource Profiles.

- **[ITK-Message-Bundle-1](https://fhir.nhs.uk/STU3/StructureDefinition/ITK-Message-Bundle-1)** - A NHS Digital Profile of the FHIR Bundle resource.
- **[ITK-MessageHeader-2](https://fhir.nhs.uk/STU3/StructureDefinition/ITK-MessageHeader-2)** - A NHS Digital Profile of the FHIR MessageHeader resource.	
- **[CareConnect-ITK-Header-Practitioner-1](https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-ITK-Header-Practitioner-1)** - An ITK3 Header Profile of the FHIR Practitioner resource  
- **[CareConnect-ITK-Header-Organization-1](https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-ITK-Header-Organization-1)** - An ITK3 Header Profile of the FHIR Organization resource.
- **[ITK-Response-OperationOutcome-1](https://fhir.nhs.uk/STU3/StructureDefinition/ITK-Ack-OperationOutcome-1)** - A NHS Digital Profile of the OperationOutcome resource


## ITK3 Response Bundle Referencing Diagram ##
The diagram shows the referencing between the profiles in the bundle which make up the ITK3 Response message.

<img src="images/explore/ack_message.png" style="width: 75%;max-width: 75%;"> 

## ITK3 Response Bundle Success Example ##

<script src="https://gist.github.com/IOPS-DEV/7fce3d2e89fb18c91f0581819e1bbaa6.js"></script>


## Extensions Used ##

- **[Extension-ITK-MessageHandling-2](https://fhir.nhs.uk/STU3/StructureDefinition/Extension-ITK-MessageHandling-2)** - An NHS Digital complex extension to the MessageHeader resource to support the ITK3 message handling key.
















