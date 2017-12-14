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

This is a complex extension which consists of a coded key using an extensible value set and an associated value which can be a boolean or a string. The table below shows the values which should be assigned to the key / value pairs. 

**Important Note 2: As this value set is extensible other keys and values may be used by local agreement.**


<table width="100%">
<tr>
<th>Key</th>
<th>Usage</th>
<th>Allowable Values</th>
<th>Comments</th>
<!--<th>Example Value</th>-->
</tr>

<tr>
<td>BUSACK</td>
<td>Populated when sender requires a business acknowledgement to be returned</td>
<td>true or false</td>
<td>-</td>
</tr>

<tr>
<td>INFACK</td>
<td>Populated when sender requires an infrastructure acknowledgement to be returned</td>
<td>true or false</td>
<td>-</td>
</tr>


<!--<tr>
<td>RecipientType</td>
<td>Indicates the type of recipient</td>
<td>
FA -  For Action - the recipient has been sent the payload for action.
<br>FI - For information
</td>
<td>
The action required by the recipient will be either explicit in the payload or there will be a business rule defined.
<br>No Action is required by the recipient and they may process the payload as they see fit.
</td>
</tr>-->

<tr>
<td>RecipientType</td>
<td>Indicates the type of recipient</td>
<td>
<ul>
<li>FA -  For Action - the recipient has been sent the payload for action.</li>  
<li>FI - For information</li>
</td>
<td>
<ul>
<li>FA - The action required by the recipient will be either explicit in the payload or there will be a business rule defined.</li>  
<li>FI - No Action is required by the recipient and they may process the payload as they see fit.</li>
</td>
</tr>

<tr>
<td>Priority</td>
<td>Indicates the priority that processing of the payload should be given by the recipient</td>
<td>
<ul>
<li>routine - The request has normal priority</li>
<li>urgent - The request should be actioned promptly - higher priority than routine</li>
<li>asap - The request should be actioned as soon as possible - higher priority than urgent</li>
<li>stat - The request should be actioned immediately - highest possible priority. E.g. an emergency</li>
</ul>
</td>
<td>These codes are taken from the valueset https://fhir.nhs.uk/STU3/ValueSet/ITK-Priority-1. This valueset is derived from the FHIR value set  http://hl7.org/fhir/ValueSet/request-priority. </td>
</tr>

<tr>
<td>MessageDefinition Reference</td>
<td>A reference to a URL for the MessageDefinition for the payload  </td>
<td>URL</td>
<td>This MessageDefinition will detail the information to allow correct processing of the payload. Such as profiles used, message event type, profiles used, responses allowed/ required etc...</td>
</tr>

<tr>
<td>SenderReference </td>
<td>A reference that the sender includes and wants returned in any response. </td>
<td>Any String up to 255 Characters  </td>
<td>This is a NHS 111 requirement.  This extension allows the sender to send a reference string which can be returned to the sender when there are issues.  The default behaviour is that if a sender reference is received the receiving system should be capable of returning the reference to the sender.  Note, in the previous release of this specification this was a separate extension.</td>
</tr>

<!--<tr>
<td>?</td>
<td>?</td>
<td>?</td>
<td>?</td>
</tr>-->


</table>


An example of how this works is for  when an infrastructure acknowledgement is required by a sender of a message. The sender would send a code of "INFACK" with a boolean value of "true".

<script src="https://gist.github.com/IOPS-DEV/0967d8a887fca4fa918d07ab623d1968.js"></script>

