---
title: FHIR Receiver Requirements
keywords: explore Reference
tags: [explore,fhir]
sidebar: overview_sidebar
permalink: explore_rec_req.html
summary: "Architectural Layers ensures that fault handling is handled in line with the layer that the fault occurs.
This means that fault processing can halt and report at the appropriate point of “fault/error”, all errors are regarded as fatal and there will only be a maximum of 2 Message Responses, each containing a maximum of one Response Code.
"
---

{% include custom/search.warnbanner.html %}

## Recipient – Header Validation ##

Receiving systems must apply basic header validation to check that the system is the intended recipient.

<table style="width:100%;max-width: 100%;">
<tr>
<th width="20%">ID</th>
<th width="60%">Description</th>
<th width="10%">Sender</th>
<th width="10%">Receiver</th>
</tr>
<tr>
<td bgcolor="#dfefff"><b>FHIR-RR-01</b></td>
<td>The system <b>MUST</b> validate "recipient" information contained in the Document "header" information to check that the identified recipient organisation, or person is supported by the system.</td>
<td bgcolor="#dfefff">N</td>
<td bgcolor="#dfefff">Y</td>
</tr>
<tr>
<td>1</td>
<td colspan="3">The system <b>MUST</b> where requested either :<br/>
<ul>
<li>Reject the message with an appropriate response code</li>
<li>Accept the message and pass it through to the clinical application for processing</li>
</ul>
</td>
</tr>
<tr>
<td>NB</td>
<td colspan="3">The sending of responses is controlled using the appropriate flag in the ITK3 MessageHeader- ITKMessageHandling extension on the incoming FHIR document bundle.</td>
</tr>
</table> 


## Recipient – Patient Validation ##

<table style="width:100%;max-width: 100%;">
<tr>
<th width="20%">ID</th>
<th width="60%">Description</th>
<th width="10%">Sender</th>
<th width="10%">Receiver</th>
</tr>
<tr>
<td bgcolor="#dfefff"><b>FHIR-RR-01</b></td>
<td>A description of the requirement</td>
<td bgcolor="#dfefff">N</td>
<td bgcolor="#dfefff">Y</td>
</tr>
</table> 


## Coded Clinical Content ##

<table style="width:100%;max-width: 100%;">
<tr>
<th width="20%">ID</th>
<th width="60%">Description</th>
<th width="10%">Sender</th>
<th width="10%">Receiver</th>
</tr>
<tr>
<td bgcolor="#dfefff"><b>FHIR-RR-01</b></td>
<td>A description of the requirement</td>
<td bgcolor="#dfefff">N</td>
<td bgcolor="#dfefff">Y</td>
</tr>
</table> 


## Patient Transfer Specific Requirements ##

<table style="width:100%;max-width: 100%;">
<tr>
<th width="20%">ID</th>
<th width="60%">Description</th>
<th width="10%">Sender</th>
<th width="10%">Receiver</th>
</tr>
<tr>
<td bgcolor="#dfefff"><b>FHIR-RR-01</b></td>
<td>A description of the requirement</td>
<td bgcolor="#dfefff">N</td>
<td bgcolor="#dfefff">Y</td>
</tr>
</table> 


## Duplicate Documents ##

<table style="width:100%;max-width: 100%;">
<tr>
<th width="20%">ID</th>
<th width="60%">Description</th>
<th width="10%">Sender</th>
<th width="10%">Receiver</th>
</tr>
<tr>
<td bgcolor="#dfefff"><b>FHIR-RR-01</b></td>
<td>A description of the requirement</td>
<td bgcolor="#dfefff">N</td>
<td bgcolor="#dfefff">Y</td>
</tr>
</table> 



