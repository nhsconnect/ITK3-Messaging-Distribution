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
<th>Example Value</th>
</tr>

<tr>
<td>BUSACK</td>
<td>Populated when sender requires a business acknowledgement to be returned</td>
<td>true or false</td>
<td>true</td>
</tr>

<tr>
<td>INFACK</td>
<td>Populated when sender requires an infrastructure acknowledgement to be returned</td>
<td>true or false</td>
<td>true</td>
</tr>

<tr>
<td>INTID</td>
<td>Informs the receiver of the interaction identifier associated with the message flow</td>
<td>Any valid interaction identifier</td>
<td>DOC-ToC-Primary-Recipient-eDischarge-1</td>
</tr>

<tr>
<td>PID</td>
<td>Informs the receiver of the message specification identifier and version that the sending system is built from or conforms to.</td>
<td>Any valid message profile identifier</td>
<td>eDischarge 1.0.0-alpha.1</td>
</tr>

<tr>
<td>SNDO</td>
<td>Informs the receiver of the message that this is a send only transaction i.e. this is an asynchronous message flow.</td>
<td>true</td>
<td>true</td>
</tr>

<tr>
<td>SNDREC</td>
<td>Informs the receiver of the message that this is a send and receive transaction i.e. this is an synchronous message flow.</td>
<td>true</td>
<td>true</td>
</tr>

<tr>
<td>SNDSRVC</td>
<td>Informs the receiver of the message the service being used for this message</td>
<td>Any Service identifier</td>
<td>SendDocument-v1-0</td>
</tr>

</table>


An example of how this works is for  when an infrastructure acknowledgement is required by a sender of a message. The sender would send a code of "INFACK" with a boolean value of "true".

<script src="https://gist.github.com/IOPS-DEV/0967d8a887fca4fa918d07ab623d1968.js"></script>

## senderReference Extension ##

This extension allows the sender to send a reference string which can be returned to the sender when there are issues. The default behaviour is that if a sender reference is received the receiving system should be capable of returning the reference to the sender.

