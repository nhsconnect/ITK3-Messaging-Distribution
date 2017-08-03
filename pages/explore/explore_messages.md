---
title: Messages 
keywords:  messaging
tags: [fhir,messaging]
sidebar: foundations_sidebar
permalink: explore_messages.html
summary: "ITK3 Distribution Messages"
---

{% include custom/search.warnbanner.html %}

{% include custom/messaging_overview.svg %}

## ITK Send Payload ##

This message is a generic message for sending any payload.

The Bundle consists of the following FHIR Resource Profiles.

- **ITK-Message-Bundle-1** - A NHS Digital Profile of the FHIR Bundle resource.
- **ITK-MessageHeader-1** - A NHS Digital Profile of the FHIR MessageHeader resource.	
- **CareConnect-Practitioner-1** - A CareConnect Profile of the FHIR Practitioner resource 
- **CareConnect-Location-1** - A CareConnect Profile of the FHIR Location resource.
- **CareConnect-Organization-1** - A CareConnect Profile of the FHIR Organization resource.
- **Payload** - Any Resource or Profile. 
- 
## ITK Send Payload Bundle Diagram ##

The diagram shows the referencing between the profiles in the bundle which make up the Send Payload Message.

<img src="images/explore/send_payload_message.png" style="width: 75%;max-width: 75%;"> 

## ITK Send Payload Example ##

<script src="https://gist.github.com/unicorn150161/4cc76d52e3a93ce529efdffcaa487396.js"></script>

## ITK Infrastructure Acknowledgement Response ##

ITK Infrastructure Acknowledgements are used to convey information from the receiving Clinical Systems back to the sending system, the messages are clinically agnostic and relay information regarding errors in the payload wrapper, such as a failure in schema validation. This response message also allows systems to acknowledge that a message was received without error. When a message is received without error at the infrastructure layer it may subsequently error later at the business layer.

The Bundle consists of the following FHIR Resource Profiles.

- **ITK-Message-Bundle-1** - A NHS Digital Profile of the FHIR Bundle resource.
- **ITK-MessageHeader-1** - A NHS Digital Profile of the FHIR MessageHeader resource.	
- **CareConnect-Practitioner-1** - A CareConnect Profile of the FHIR Practitioner resource 
- **CareConnect-Location-1** - A CareConnect Profile of the FHIR Location resource.
- **CareConnect-Organization-1** - A CareConnect Profile of the FHIR Organization resource.
- **ITK-OperationOutcome-1** - A NHS Digital Profile of the OperationOutcome resource


## ITK Infrastructure Acknowledgement Bundle Diagram ##
The diagram shows the referencing between the profiles in the bundle which make up the Infrastructure Acknowledgement Response message.

<img src="images/explore/ack_message.png" style="width: 75%;max-width: 75%;"> 

## ITK Infrastructure Acknowledgement Bundle Success Example ##

<script src="https://gist.github.com/unicorn150161/8894acb45610bdebae8b7f18bffea35c.js"></script>

## ITK Business Acknowledgement Response ##
ITK Business Acknowledgements are used to convey information from the receiving Clinical Systems back to the sending system, this can include Patient Known or Patient Unknown information alongside information regarding accuracy or inaccuracy of the clinical payload.This response message also allows systems or individuals to acknowledge that a message was received without error

The Bundle consists of the following FHIR Resource Profiles.

- **ITK-Message-Bundle-1** - A NHS Digital Profile of the FHIR Bundle resource.
- **ITK-MessageHeader-1** - A NHS Digital Profile of the FHIR MessageHeader resource.	
- **CareConnect-Practitioner-1** - A CareConnect Profile of the FHIR Practitioner resource 
- **CareConnect-Location-1** - A CareConnect Profile of the FHIR Location resource.
- **CareConnect-Organization-1** - A CareConnect Profile of the FHIR Organization resource.
- **ITK-OperationOutcome-1** - A NHS Digital Profile of the OperationOutcome resource


## ITK Business Acknowledgement Bundle Diagram ##
The diagram shows the referencing between the profiles in the bundle which make up the Business Acknowledgement Response message.

<img src="images/explore/ack_message.png" style="width: 75%;max-width: 75%;"> 


## ITK Business Acknowledgement Bundle Success Example ##

<script src="https://gist.github.com/unicorn150161/6d74aac6b6e7305814f56188ea9b9baa.js"></script>



[ITK Send Payload]: ../Profile.ITKSendPayload/Profile.ITKSendPayload.html
[ITK Infrastructure Acknowledgement Response]: ../Profile.ITKInfAckResponse/Profile.ITKInfAckResponse.html
[ITK Business Acknowledgement Response]: ../Profile.ITKBusinessAckResponse/Profile.ITKBusinessAckResponse.html
