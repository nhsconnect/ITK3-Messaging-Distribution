---
title: Introduction to ITK3 Messaging Distribution
keywords: homepage
tags: [overview]
sidebar: overview_sidebar
permalink: index.html
toc: false
summary: A brief introduction to getting started with the ITK3 Messaging Distribution.
---

{% include important.html content="This site is under active development by NHS Digital and is intended to provide all the technical resources you need to successfully develop the ITK3 Messaging Distribution components of FHIR messaging. This project is being developed using an agile methodology so iterative updates to content will be added on a regular basis." %}

{% include warning.html content="The examples provided are for illustrative purposes only. They have had no clinical validation. Whilst every effort has been taken to ensure that the examples are consistent with the FHIR profiles and this specification, where there are conflicts the written message specification or FHIR profile shall be considered to take precedence." %}

## Introduction ##

"ITK3 Messaging Distribution" is the term used for a set of generic FHIR messaging components. These messaging components have been developed by NHS Digital to allow a standard approach to FHIR MessageHeaders and responses (acknowledgements) across NHS message and document flows in England. The Payloads are not specified within this specification as these components can carry any Payload. These components, along with NHS Digital FHIR Message and FHIR Document specifications are part of the ITK3 solution. The NHS Digital Payload specifications are available in the [NHS Connect GitHub repository.](https://github.com/nhsconnect)

The ITK3 Messages are created using the formally defined HL7® approach and methodology for the creation and transmission of FHIR® documents and messages. For further information see [FHIR messaging](https://www.hl7.org/fhir/messaging.html) and [FHIR Documents](http://hl7.org/fhir/documents.html).
   
FHIR Messaging components specified within this site have been developed by NHS Digital and use CareConnect profiles created in collaboration with the INTEROPen community. 

The INTEROPen vision is to create a library of nationally defined HL7® FHIR® resources and interaction patterns that implementers can adopt to simplify integration and interoperability within England's health and social care systems.

Find out more on the [INTEROPen website](http://interopen.org/).

## Overview of The ITK3 Messaging Components ##

<img src="images/explore/ITK_header_overview.png" style="width:100%;max-width: 100%;">

## Using this guide ##

This guide has been created to support the adoption of NHS Digital defined FHIR messages and documents. This site has been developed with input from stakeholders such as ITK3 Messaging Solution users, developers and architects.

## Definitions ##
The keywords MUST, MAY, and SHOULD are to be interpreted as described in RFC2119:
* MUST: This word, or the terms "REQUIRED" or "SHALL", means that the definition is an absolute requirement of the specification.
* MUST NOT: This phrase, or the phrase "SHALL NOT", mean that the definition is an absolute prohibition of the specification.
* SHOULD: This word, or the adjective "RECOMMENDED", means that there May exist valid reasons in particular circumstances to ignore a particular item, but the full implications Must be understood and carefully weighed before choosing a different course.
* SHOULD NOT: This phrase, or the phrase "NOT RECOMMENDED" mean that there May exist valid reasons in particular circumstances when the particular behaviour is acceptable or even useful, but the full implications should be understood and the case carefully weighed before implementing any behaviour described with this label.