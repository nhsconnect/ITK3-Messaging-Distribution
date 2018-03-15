---
title: Handling Specification
keywords: workflow
tags: [development,fhir,profiles]
sidebar: foundation_sidebar
permalink: explore_hand_spec.html
summary: "The ITK3 Handling Specification Usage."
---

{% include custom/search.warnbanner.html %}

## Overview ##

There are a number of extensions added to the ITK messageHeader profile which are referred to as the handling specifications. These extensions are used to control messaging behaviour such as when to send an acknowledgement. 

**Important Note 1: There is no default behaviour for any handling keys unless specified by the payload specification.  For example; the payload specification may mandate that a particular handling key always be populated or define some default behaviour for a particular key.  The payload specification must always be consulted when implementing handling key behaviour on a sending or receiving system.**

## ITKMessageHandling Extension ##

This is a complex extension which consists of an Extension URL that carries the Handling Key and an associated allowable value which is described in the table below. 

**Important Note 2: As this value set is extensible other keys and values may be used by local agreement.**


<table style="width:100%;max-width: 100%;">
<tr>
<th>Extension URL</th>
<th>Usage</th>
<th>Allowable Values</th>
<th>Definition</th>
</tr>

<tr>
<td rowspan="2">BusAckRequested</td>
<td rowspan="2">Populated when sender requires a business level response to be returned</td>
<td>true</td>
<td>The business level response has been requested</td>
</tr>
<tr>
<td>false</td>
<td>The business level response has not been requested</td>
</tr>

<tr>
<td rowspan="2">InfAckRequested</td>
<td rowspan="2">Populated when sender requires an infrastructure level response to be returned</td>
<td>true</td>
<td>The infrastructure response has been requested</td>
</tr>
<tr>
<td>false</td>
<td>The infrastructure level response has not been requested</td>
</tr>


<tr>
<td rowspan="2">RecipientType</td>
<td rowspan="2">Indicates the type of recipient</td>
<td>FA</td>
<td>For Action - the recipient has been sent the payload for action. The action required by the recipient will be either explicit in the payload or there will be a business rule defined.</td>  
</tr>
<tr>
<td>FI</td>
<td>For information - No Action is required by the recipient and they may process the payload as they see fit.</td>
</tr>

<tr>
<td rowspan="4">Priority</td>
<td rowspan="4">Indicates the priority that processing of the payload should be given by the recipient.<br>These codes are taken from the value set: <a href="https://fhir.nhs.uk/STU3/ValueSet/ITK-Priority-1">ITK-Priority-1</a><br>This value set is derived from the FHIR value set:<a href="http://hl7.org/fhir/ValueSet/request-priority">request-priority</a></td>
<td>routine</td>
<td>The request has normal priority</td>
</tr>
<tr>
<td>urgent</td>
<td>The request should be actioned promptly – a higher priority than routine</td>
</tr>
<tr>
<td>asap</td>
<td>The request should be actioned as soon as possible - higher priority than urgent</td>
</tr>
<tr>
<td>stat</td>
<td>The request should be actioned immediately - highest possible priority. E.g. an emergency</td>
</tr>

<tr>
<td>MessageDefinition</td>
<td>A reference to the MessageDefinition for the payload</td>
<td></td>
<td>This MessageDefinition will detail the information to allow correct processing of the payload. Such as profiles used, message event type, profiles used, responses allowed/ required etc...</td>
</tr>

<tr>
<td>SenderReference </td>
<td>A reference that the sender includes and wants returning in any response.</td>
<td>Any String up to 255 Characters  </td>
<td>This extension allows the sender to send a reference string which can be returned to the sender.  The default behaviour is that if a sender reference is received the receiving system should be capable of returning the reference to the sender.</td>
</tr>

<tr>
<td>LocalExtension</td>
<td>A local Handling Specification Key</td>
<td>This can be any type of value</td>
<td>This provides the flexibility of locally defined local Handling Specifications being used.</td>
</tr>
</table>


