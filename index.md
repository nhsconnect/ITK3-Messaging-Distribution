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

{% include warning.html content="This site is provided for information only and is intended for those engaged with NHS Digital in the development of FHIR Messaging. It is advised not to develop against these specifications until a formal announcement has been made." %}

# Introduction #

"ITK3 Messaging Distribution" is the term used for a set for generic FHIR messaging components. These messaging components have been developed by NHS Digital to allow a standard approach to FHIR message headers and acknowledgements across NHS message and document flows in England. The payloads are not specified within this site as these components can carry any payload. These components, along with NHS Digital FHIR Message and FHIR Document specifications are part of the ITK3 solution. The NHS Digital payload specifications are available in the [NHS Connect GitHub repository.](https://github.com/nhsconnect)

The ITK3 Messages are created using the formally defined HL7 approach and methodology for the creation and transmission of FHIR Documents using [messages.](https://www.hl7.org/fhir/messaging.html)
   
FHIR Messaging components specified within this site have been developed by NHS Digital and use CareConnect profiles created in collaboration with the INTEROPen community. 

The INTEROPen vision is to create a library of nationally defined HL7® FHIR® resources and interaction patterns that implementers can adopt to simplify integration and interoperability within England's health and social care systems.

Find out more on the [INTEROPen website](http://interopen.org/).

# Using this guide #

This guide has been created to support the adoption of NHS Digital defined FHIR Messages. As such the site is structured around stakeholders involved in building FHIR ITK3 Messaging Solutions including  ITK3 Messaging Solution users, developers and architects.  

{% include custom/messaging_overview.svg %}

The above steps outline a complete journey from imagination and exploring to developing local ITK3 Messaging Solutions using NHS Digital Messages, all the way to deploying a live ITK3 Messaging Solution.

# ITK3 Messaging Distribution Focus #

The current site focuses on a typical FHIR ITK3 Messaging Solution Developer's Journey as highlighted by the green boxes below in the developer journey:

<img src="images/roadmap/guide-focus.png" style="width:100%;max-width: 100%;">


# Resource Roadmap #

The [ITK3 Messaging Distribution journey](overview_the_journey.html) outlines the development roadmap for FHIR Messaging using the ITK3 Messaging Distribution component outlined messaging within this site.

<img src="images/roadmap/messaging_roadmap-online.png" style="width:100%;max-width: 100%;">

The above roadmap illustrates the steps necessary to create, test and verify the messaging components as well as some of the supporting tooling which might be necessary to build to provide viable ITK3 Messaging Solutions. The roadmap is not intended to be complete but to promote discussion, extension and engagement from interested parties.

