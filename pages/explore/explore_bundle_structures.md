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
To enable a standardised structure to carry information regarding common end-to-end distribution requirements, two profiles have been defined, the ITK Message Bundle and the ITK Message Header that combine to make up the ITK3 Messaging Distribution Bundle. 

The ITK3 Messaging Distribution Bundle may be used to wrap any payload. This provides a lightweight structure to carry information relating to the end-to-end technical distribution of payloads.
The ITK3 Messaging Distribution Bundle is an autonomous and transport agnostic design, whilst enabling audit, access control and authentication as required by both sender and receivers. Some extensions have been added to the ITK3 Message Header profile to allow a similar functionality to the previous versions of ITK. 

This specification also defines a ITK3 Response message which may be used with the ITK3 Messaging Distribution Bundle.

## The ITK3 Messaging Distribution Bundle ##

The diagram below shows a schematic of the basic ITK3 Messaging Distribution Bundle structure. The ITK3 message bundle is the container for the ITK3 message header and any payload. The message header contains information that pertains to the payload content. The Payload can be anything.

<img src="images/explore/ITKBundle.png" style="width:50%;max-width: 50%;">


## ITK3 Typical Bundle Structures ##


## ITK3 FHIR Document Bundle Structure ##

The diagram below is an example of an ITK3 FHIR document payload that may be used with the ITK3 Messaging Distribution Bundle. When sending FHIR Documents the type of bundle is a document.

<img src="images/explore/ITKDocExample.png" style="width:50%;max-width: 50%;">

## ITK3 Response Bundle Structure ##

The diagram below is an example of a ITK Response message structure.
 
<img src="images/explore/BusExample.png" style="width:50%;max-width: 50%;">


## ITK3 Other Payload Bundle Structure ##

The diagram below is an example of the structure used when a payload has an additional bundle and is one of the types listed below:

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
- **[CareConnect-ITK-Header-Practitioner-1](https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-ITK-Header-Practitioner-1)** - An ITK Header Profile of the FHIR Practitioner resource.
- **[CareConnect-ITK-Header-Organization-1](https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-ITK-Header-Organization-1)** - An ITK Header Profile of the FHIR Organization resource.
- **Payload - one of the following:**
-- **One or more FHIR Resource.** 
-- **The [ITK-Document-Bundle-1](https://fhir.nhs.uk/STU3/StructureDefinition/ITK-Document-Bundle-1) containing a composition and one or more FHIR Resources.**
-- **The [ITK-Payload-Bundle-1](https://fhir.nhs.uk/STU3/StructureDefinition/ITK-Payload-Bundle-1) containing one or more FHIR Resources.**
 
 
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
- **[CareConnect-ITK-Header-Practitioner-1](https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-ITK-Header-Practitioner-1)** - An ITK Header Profile of the FHIR Practitioner resource  
- **[CareConnect-ITK-Header-Organization-1](https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-ITK-Header-Organization-1)** - An ITK Header Profile of the FHIR Organization resource.
- **[ITK-OperationOutcome-1](https://fhir.nhs.uk/STU3/StructureDefinition/ITK-Ack-OperationOutcome-1)** - A NHS Digital Profile of the OperationOutcome resource


## ITK3 Response Bundle Referencing Diagram ##
The diagram shows the referencing between the profiles in the bundle which make up the ITK3 Response message.

<img src="images/explore/ack_message.png" style="width: 75%;max-width: 75%;"> 

## ITK3 Response Bundle Success Example ##

<script src="https://gist.github.com/IOPS-DEV/7fce3d2e89fb18c91f0581819e1bbaa6.js"></script>


## Extensions Used ##

- **[Extension-ITK-CareSettingType-1](https://fhir.nhs.uk/STU3/StructureDefinition/Extension-ITK-CareSettingType-1)** - An NHS Digital extension to header resource to allow the details care setting type that the document was sent from.
- **[Extension-ITK-MessageHandling-2](https://fhir.nhs.uk/STU3/StructureDefinition/Extension-ITK-MessageHandling-2)** - An NHS Digital complex extension to the MessageHeader resource to support the ITK message handling key.
- **[Extension-ITK-SenderReference-1](https://fhir.nhs.uk/STU3/StructureDefinition/Extension-ITK-SenderReference-1)** -An NHS Digital extension to the MessageHeader resource to support a local sender reference.
- **[Extension-CareConnect-NHSCommunication-1](https://fhir.hl7.org.uk/STU3/StructureDefinition/Extension-CareConnect-NHSCommunication-1)** - A CareConnect extension to Patient and Practitioner resources to carry language information suitable for NHS use.
- **[Extension-CareConnect-MainLocation-1](https://fhir.hl7.org.uk/STU3/StructureDefinition/Extension-CareConnect-MainLocation-1)** - A CareConnect extension to the Location resource to allow the main location to be carried/indicated.
- **[organization-period](http://hl7.org/fhir/StructureDefinition/organization-period)** - An HL7 common extension to the Organization resource allows the periods of time to be associated with the organization.















