---
title: Verification and Validation
keywords: explore Reference
tags: [explore,fhir]
sidebar: overview_sidebar
permalink: explore_ver_and_val.html
summary: "Requirements for verification and validation"
---

{% include custom/search.warnbanner.html %}

## Verification and Validation ##

<table style="width:100%;max-width: 100%;">
<tr>
<th>ID</th>
<th>Description</th>
<th>Sender</th>
<th>Receiver</th>
</tr>
<tr>
<td bgcolor="#dfefff"><b>FHIR-V&V-01</b></td>
<td>Sending and Receiving systems <b>MUST</b> provide a means to assure the validity of the FHIR document.</td>
<td bgcolor="#dfefff">Y</td>
<td bgcolor="#dfefff">Y</td>
</tr>
<tr>
<td>1.</td>
<td colspan="3">If this validation fails, the system MUST- log the fault in the application or system logs as appropriate</td>
</tr>
</table> 


<table style="width:100%;max-width: 100%;">
<tr>
<th>ID</th>
<th>Description</th>
<th>Sender</th>
<th>Receiver</th>
</tr>
<tr>
<td bgcolor="#dfefff"><b>FHIR-V&V-02</b></td>
<td>Sending systems <b>SHOULD</b> provide facilities (e.g. a ‘verification’ step) to ensure the content of the FHIR Documents is checked/verified by the document author, or other approved user, prior to the sending of the Document.</td>
<td bgcolor="#dfefff">Y</td>
<td bgcolor="#dfefff">N</td>
</tr>
<tr>
<td>1.</td>
<td colspan="3">If this validation fails, the system MUST- log the fault in the application or system logs as appropriate</td>
</tr>
</table> 

