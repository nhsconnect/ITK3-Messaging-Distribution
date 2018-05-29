---
title: Message Definitions
keywords:  messaging, message definitions
tags: [fhir,messaging,messagedefinitions]
sidebar: foundations_sidebar
permalink: explore_message_definitions.html
summary: "ITK3 Messaging Distribution Message Definitions"
---

{% include custom/search.warnbanner.html %}

## ITK3 Messaging Distribution Message Definitions Overview ##
This section provides ITK3 implementers with the information required to utilise the ITK3 Messaging Distribution MessageDefinition instances. The message definition instances are created to conform to the [ITK-MessageDefinition-1](https://fhir.nhs.uk/STU3/StructureDefinition/ITK-MessageDefinition-1) Profile. These MessageDefinitions specify which Profiles, extensions,value sets, code systems and concept maps are used in the Message Bundle and additional information such as: what responses are allowed to be returned to the sender. The message definition instances main use is for highlighting changes between versions of a message but they may also be used as input into conformance and validation. 

The responses defined in the message definitions do not include MESH responses see notes below:

**Note 1:** When using MESH, additional MESH acknowledgements and responses will be available.  The MESH acknowledgements and responses are not defined in this specification

**Note 2:** Messages are structured in eXtensible Markup Language (XML) only.

The ITK3 Messaging Distribution is based on the [HL7 FHIR STU3 Messaging Implementation](http://hl7.org/fhir/messaging.html) and supports multiple Message Definitions. 

Further guidance on the use of MessageDefinitions will be provided at a late date.
   
----------

## Message Handling Flags ##

Acknowledgement responses can be requested using the message handling flags:

These flags are configured within the [ITK-MessageHeader-2](https://fhir.nhs.uk/STU3/StructureDefinition/ITK-MessageHeader-2) and the actual responses allowed are specified in the Payload message definitions. 

---

## ITK-SendPayload-MessageDefinition-Instance-1 ##

This is the MessageDefinition instance for the ITK3 Message Distribution Send Payload message. This message can be used to send any Payload. The Payload specification should be consulted for the Payload message definition. 

- **Sender:**  Sending System
- **Receiver:** Recipient System
- **MessageDefinition:** ITK-SendPayload-MessageDefinition-Instance-1

<script src="https://gist.github.com/IOPS-DEV/3fb9cde87dc0fc9da48100f9efafef07.js"></script>

---

## ITK-InfAck-MessageDefinition-Instance-1 ##

This is the MessageDefinition instance for the ITK3 Message Distribution Infrastructure Acknowledgement message which can be used to return positive and negative Infrastructure Acknowledgements to a sender of over MESH.

- **Sender:** Sending System
- **Receiver:** Recipient System
- **MessageDefinition:** ITK-InfAck-MessageDefinition-Instance-1

<script src="https://gist.github.com/IOPS-DEV/e4cefe1ba05fc847574d768e93b2cba7.js"></script>

----------

## ITK-BusAck-MessageDefinition-Instance-1 ##

This is the MessageDefinition instance for the ITK3 Message Distribution Business Acknowledgement message which can be used to return positive and negative Business Acknowledgements to a sender of over MESH.

- **Sender:** Sending System
- **Receiver:** Recipient System
- **MessageDefinition:** ITK-BusAck-MessageDefinition-Instance-1

<script src="https://gist.github.com/IOPS-DEV/dabb8d801f2ef88b7bd6311fd26b1eb2.js"></script>

----------









