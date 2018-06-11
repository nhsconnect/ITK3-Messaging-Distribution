---
title: FHIR Document Sender Requirements 
keywords: explore Reference
tags: [explore,fhir]
sidebar: overview_sidebar
permalink: explore_sender_reqs.html
summary: "A Sender needs to be aware of a number of constraints associated with sending documents, generally considered in two categories, payload constraints and a patients’ consent and preferences."
---

{% include custom/search.warnbanner.html %}

## Number of Payloads Constraint ##

<table style="width:100%;max-width: 100%;">
<tr>
<th width="20%">ID</th>
<th width="60%">Description</th>
<th width="10%">Sender</th>
<th width="10%">Receiver</th>
</tr>
<tr>
<td bgcolor="#dfefff"><b>FHIR-PAY-01</b></td>
<td>A sending system <b>MUST</b> only send one document per transmission.</td>
<td bgcolor="#dfefff">Y</td>
<td bgcolor="#dfefff">N</td>
</tr>
</table> 

<table style="width:100%;max-width: 100%;">
<tr>
<th width="20%">ID</th>
<th width="60%">Description</th>
<th width="10%">Sender</th>
<th width="10%">Receiver</th>
</tr>
<tr>
<td bgcolor="#dfefff"><b>FHIR-PAY-02</b></td>
<td>Attachments <b>MUST</b> be included within the same FHIR Bundle.</td>
<td bgcolor="#dfefff">Y</td>
<td bgcolor="#dfefff">N</td>
</tr>
<tr>
<td>NB</td>
<td colspan="3">There will not be any external references via URL.</td>
</tr>
</table> 

## Demographic and Consent Preconditions ##

It is essential that the identity of the patient is consistently represented by systems that are interacting with one another and that a patients’ preferences are recognised.

## PDS Connected Systems ##

Where sending systems are connected to PDS, full PDS Synchronisation will be carried out prior to any messaging interaction and therefore the locally held serial change number will be up-to-date.  If the sending system is not connected directly to PDS and synchronises with PDS periodically, e.g. using the PDS Batch service, the latest details should be sent. 

<table style="width:100%;max-width: 100%;">
<tr>
<th width="20%">ID</th>
<th width="60%">Description</th>
<th width="10%">Sender</th>
<th width="10%">Receiver</th>
</tr>
<tr>
<td bgcolor="#dfefff"><b>FHIR-PDS-01</b></td>
<td>Sending systems <b>SHOULD</b> synchronise the document with the PDS record.</td>
<td bgcolor="#dfefff">Y</td>
<td bgcolor="#dfefff">N</td>
</tr>
</table> 

<table style="width:100%;max-width: 100%;">
<tr>
<th width="20%">ID</th>
<th width="60%">Description</th>
<th width="10%">Sender</th>
<th width="10%">Receiver</th>
</tr>
<tr>
<td bgcolor="#dfefff"><b>FHIR-PDS-02</b></td>
<td>The Sender MUST include additional patient demographics if the patient’s NHS number is not included or the NHS number has not been "verified".</td>
<td bgcolor="#dfefff">Y</td>
<td bgcolor="#dfefff">N</td>
</tr>
<tr>
<td>1.</td>
<td colspan="3">The Sender MUST include additional patient demographics if the patient’s NHS number is not "verified":
<ul>
<li>First Given Name</li>
<li>Surname</li>
<li>Gender</li>
<li>Date of Birth</li>
<li>Address</li>
<li>Postcode</li>
</ul>
</td>
</tr>
</table>

<table style="width:100%;max-width: 100%;">
<tr>
<th width="20%">ID</th>
<th width="60%">Description</th>
<th width="10%">Sender</th>
<th width="10%">Receiver</th>
</tr>
<tr>
<td bgcolor="#dfefff"><b>FHIR-PDS-03</b></td>
<td>If the Sender is connected to PDS, prior to sending a document, the originating system <b>SHOULD</b> check the PDS ‘flagged’ status of the Patient’s record.</td>
<td bgcolor="#dfefff">Y</td>
<td bgcolor="#dfefff">N</td>
</tr>
</table> 

<table style="width:100%;max-width: 100%;">
<tr>
<th width="20%">ID</th>
<th width="60%">Description</th>
<th width="10%">Sender</th>
<th width="10%">Receiver</th>
</tr>
<tr>
<td bgcolor="#dfefff"><b>FHIR-PDS-04</b></td>
<td>Where a record is marked as "S" (Sensitive) on the PDS, following an appropriate safety evaluation (by the local user organisation as data controller) the Sender <b>MAY</b> include Patient address or contact details in the additional demographic data, these items are (PDS data items):
<ul>
<li>Addresses</li>
<li>Telecom Addresses</li>
<li>Patient Care (All types)</li>
<li>Alternative Contacts</li>
</td>
<td bgcolor="#dfefff">Y</td>
<td bgcolor="#dfefff">N</td>
</tr>
</table> 

<table style="width:100%;max-width: 100%;">
<tr>
<th width="20%">ID</th>
<th width="60%">Description</th>
<th width="10%">Sender</th>
<th width="10%">Receiver</th>
</tr>
<tr>
<td bgcolor="#dfefff"><b>FHIR-PDS-05</b></td>
<td>Where an NHS number is known to be invalid on PDS (error code "22" upon a PDS Retrieval), the Document <b>SHOULD NOT</b> be sent until the issue has been resolved.</td>
<td bgcolor="#dfefff">Y</td>
<td bgcolor="#dfefff">N</td>
</tr>
</table> 

<table style="width:100%;max-width: 100%;">
<tr>
<th width="20%">ID</th>
<th width="60%">Description</th>
<th width="10%">Sender</th>
<th width="10%">Receiver</th>
</tr>
<tr>
<td bgcolor="#dfefff"><b>FHIR-PDS-06</b></td>
<td>Where an NHS number is known to be invalid on the PDS (error code "22" upon a PDS Retrieval), documents <b>MUST NOT</b> contain the patient’s NHS number.</td>
<td bgcolor="#dfefff">Y</td>
<td bgcolor="#dfefff">N</td>
</tr>
</table> 

<table style="width:100%;max-width: 100%;">
<tr>
<th width="20%">ID</th>
<th width="60%">Description</th>
<th width="10%">Sender</th>
<th width="10%">Receiver</th>
</tr>
<tr>
<td bgcolor="#dfefff"><b>FHIR-PDS-07</b></td>
<td>Where an NHS number is known to be invalid on the PDS (error code "22" upon a PDS Retrieval), if the Document is sent (and this can only be done with ITK3 Message Specifications) other (non- NHS number) demographic details <b>MUST</b> be included.
<ul>
<li>First Given Name</li>
<li>Surname</li>
<li>Gender</li>
<li>Date of Birth</li>
<li>Address</li>
<li>Postcode</li>
</td>
<td bgcolor="#dfefff">Y</td>
<td bgcolor="#dfefff">N</td>
</tr>
</table> 

<table style="width:100%;max-width: 100%;">
<tr>
<th width="20%">ID</th>
<th width="60%">Description</th>
<th width="10%">Sender</th>
<th width="10%">Receiver</th>
</tr>
<tr>
<td bgcolor="#dfefff"><b>FHIR-PDS-08</b></td>
<td>Where a record is marked as "B" (formerly meaning "Business Flagged" prior to 2008-B but now meaning "Under Data Quality Investigation" from spine release 2008-B onwards) on PDS, documents <b>MUST</b> still be sent.</td>
<td bgcolor="#dfefff">Y</td>
<td bgcolor="#dfefff">N</td>
</tr>
</table> 

<table style="width:100%;max-width: 100%;">
<tr>
<th width="20%">ID</th>
<th width="60%">Description</th>
<th width="10%">Sender</th>
<th width="10%">Receiver</th>
</tr>
<tr>
<td bgcolor="#dfefff"><b>FHIR-PDS-09</b></td>
<td>Where a Patient dissents from sharing their detailed care records and the document is a routine clinical communication, the originating system <b>SHOULD</b> still send documents for that Patient to the Patient’s GP Practice.</td>
<td bgcolor="#dfefff">Y</td>
<td bgcolor="#dfefff">N</td>
</tr>
</table> 

<table style="width:100%;max-width: 100%;">
<tr>
<th width="20%">ID</th>
<th width="60%">Description</th>
<th width="10%">Sender</th>
<th width="10%">Receiver</th>
</tr>
<tr>
<td bgcolor="#dfefff"><b>FHIR-PDS-10</b></td>
<td>The verification status code (an NHS Extension) <b>MUST</b> be populated in the Patient Profile.</td>
<td bgcolor="#dfefff">Y</td>
<td bgcolor="#dfefff">N</td>
</tr>
</table> 

## xxx  ##

<table style="width:100%;max-width: 100%;">
<tr>
<th width="20%">ID</th>
<th width="60%">Description</th>
<th width="10%">Sender</th>
<th width="10%">Receiver</th>
</tr>
<tr>
<td bgcolor="#dfefff"><b>FHIR-XX-n</b></td>
<td>A description of the requirement</td>
<td bgcolor="#dfefff">Yes or No</td>
<td bgcolor="#dfefff">Yes or No</td>
</tr>
</table>  