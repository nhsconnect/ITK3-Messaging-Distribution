---
title: Message Definitions Overview
keywords:  messaging
tags: [fhir,messaging]
sidebar: foundations_sidebar
permalink: explore_defs_overview.html
summary: "Overview of the Message Definitions section"
---

{% include custom/search.warnbanner.html %}

## Use of Message Definitions ##

For ITK3 message flows, the use of message definitions to replace interactions has been implemented. This section describes the use of message definitions and their proposed usage to help with versioning and managing changes for consumers.

The FHIR resource MessageDefinition defines the characteristics of a message that can be shared between systems, including the type of event that initiates the message, the content to be transmitted and what response(s), if any, are permitted. NHS Digital has for ITK3 messaging over MESH, profiled this resource. The profile contains a complex extension that contains a number of sub-extensions to allow all the version-able components (known as FHIR assets) within the message bundle to be stated along with the version of each asset. The version-able FHIR assets are typed using a value set called ITK-AssetType which allows for more FHIR asset types to be added as required. The current supported asset types are:

- Profiles
- Extensions
- Value sets
- Code systems
- Concept maps

## Message Definition Instances ##

For each message or document type there will be a message definition instance provided. These instances will conform to the [ITK-MessageDefinition-1](https://fhir.nhs.uk/STU3/StructureDefinition/ITK-MessageDefinition-1) profile. For each message or document these MessageDefinitions instances contain information about: 

- The profiles used.
- The extensions used.
- The value sets used.
- The code systems used.
- The concept maps used.
- The version of above assets to highlight changes between versions of a message or document.
- What responses are allowed to be returned to the sender for the message or document.


**Note 1:** When using MESH, additional MESH acknowledgements and responses will be available.  Any responses defined in the message definitions do not include MESH responses.

## Versioning of Message Definitions ##

If any of the assets referred to in the message definition change and are up-versioned then the message definition will be up-versioned accordingly. The message definition will be a Major, Minor or Patch type of up-version dependant on how the change to the asset or assets has been defined (Major, Minor or Patch). 
The long-term goal would ideally be to use message definitions for ascertaining which messages an endpoint or system supports but to do that correctly would require capability statements to be defined by all receiving systems and a system for managing the capability statements to be available. Therefore, for implementations using ITK3, the message definition information should be sent in the ITK MessageHeader handling specification extension. This allows a receiving system to determine whether it can process the received message based on the version of the message definition and the versions of bundled assets without having to parse the actual instance. The receiver then can decide whether to accept or reject the message and if rejecting return an acknowledgement RC004 Message Definition – Processing Error. 

## How the Message Definition is Used ##
            
There are two "patterns" for the use of the message definitions: 

1. For ITK Documents which have two bundles the MessageDefinition carried in the handling specification is the MessageDefinition for the payload (second bundle) which is the FHIR document bundle. 
2. For ITK messages which only have one bundle such as the acknowledgement message the MessageDefinition carried in the handling specification is the MessageDefinition  for that bundle.

This diagram illustrates the two patterns.

<img src="images/explore/message_def.png" style="width:80%;max-width: 80%;">  


