---
title: Message Definitions
keywords:  messaging, message definitions
tags: [fhir,messaging,message definitions]
sidebar: foundations_sidebar
permalink: explore_message_definitions.html
summary: "ITK3 Messaging Distribution Message Definitions"
---

{% include custom/search.warnbanner.html %}

## ITK3 Messaging Distribution Message Definitions Overview ##
This section provides ITK3 implementers with the information required to utilise the ITK3 Messaging Distribution message definitions. The message definitions are profiled using the FHIR MessageDefinition resource. These definitions specify which profiles are used in the bundle and  additional information such as: what responses are allowed to be returned to the sender. The payload specifications also need to be consulted for the payload message definitions.

The ITK3 Messaging Distribution provides a consistent standardised approach to message headers, whilst also providing a message handling specification to control the use of infrastructure and business acknowledgement responses through the use of flags.


**Note 1:** When using MESH, additional MESH acknowledgements and responses will be available.  The MESH acknowledgements and responses are not defined in this specification

**Note 2:** Messages are structured in eXtensible Markup Language (XML) only.

The ITK3 Messaging Distribution is based on the [HL7 FHIR STU3 Messaging Implementation](http://hl7.org/fhir/messaging.html) and and supports multiple Message Definitions. 

----------

## Message Handling Flags ##

Acknowledgement responses can be requested using the message handling flags:

These flags are configured within the [ITK-MessageHeader-2](https://fhir.nhs.uk/STU3/StructureDefinition/ITK-Messageheader-2) and the actual responses allowed are specified in the payload message definitions. 

---

## ITK-SendPayload-MessageDefinition-1 ##

This is the MessageDefinition profile for the ITK3 Message Distribution Send Payload message which can used to send any payload over MESH.

- *Sender:* Sending System
- *Receiver:* Recipient System
- *MessageDefinition:* [ITK-SendPayload-MessageDefinition-1](https://fhir.nhs.uk/STU3/StructureDefinition/ITK-SendPayload-MessageDefinition-1)

---

## ITK-InfAck-MessageDefinition-1 ##

This is the MessageDefinition profile for the ITK3 Message Distribution Infrastructure Acknowledgement message which can used to return positive and negative Infrastructure Acknowledgements to a sender of over MESH.

- *Sender:* Sending System
- *Receiver:* Recipient System
- *MessageDefinition:* [ITK-InfAck-MessageDefinition-1](https://fhir.nhs.uk/STU3/StructureDefinition/ITK-InfAck-MessageDefinition-1)

----------

## ITK-BusAck-MessageDefinition-1 ##

This is the MessageDefinition profile for the ITK3 Message Distribution Business Acknowledgement message which can used to return positive and negative Business Acknowledgements to a sender of over MESH.

- *Sender:* Sending System
- *Receiver:* Recipient System
- *MessageDefinition:* [ITK-BusAck-MessageDefinition-1](https://fhir.nhs.uk/STU3/StructureDefinition/ITK-BusAck-MessageDefinition-1)

----------









