---
title: Message Header and Structure Definition - Versioning and Compatibility
keywords: explore Reference
tags: [explore,fhir]
sidebar: overview_sidebar
permalink: explore_version_compat.html
summary: "This section defines how versions at both MessageHeader level and StructureDefinition are implemented in ITK3."
---

{% include custom/search.warnbanner.html %}

## MessageDefinition versioning ##

A MessageDefnition will have a version number. This will be "up versioned" when there is a change of functionally which is deemed to be a breaking change.

## StructureDefinition versioning ##

For ITK3 the StructureDefinition is the XML representation of a FHIR resource that may be profiled within NHS Digital specifications. This section gives an overview of versioning of StructureDefinitions. These have a major version number in the name for example:
Composition-1
This will be "up versioned" when there is a change of functionally which is deemed to be a breaking change. This version number is carried in the XML instance within the meta.profile element as below:

&lt;meta&gt;
&lt;profile value="https://fhir.nhs.uk/StructureDefinition/xxxxxxxxxxxxxxxx-1" /&gt;
&lt;/meta>
The structure definition also has a version element internally, which can also be up versioned to indicate a minor change. This is not reflected in the XML instance. 


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

## Document Display ##

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

## Composition.type and Document Ontology ## 

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

## General Processing Requirements ##

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


