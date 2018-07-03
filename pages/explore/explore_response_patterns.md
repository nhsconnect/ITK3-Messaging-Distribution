---
title: ITK3 Response Patterns
keywords: explore Reference
tags: [explore,fhir,error codes]
sidebar: overview_sidebar
permalink: explore_response_patterns.html
summary: "Response Patterns used in ITK3."
---

{% include custom/search.warnbanner.html %}

## Overview ##

This diagram gives an overview of the all possible interactions between a sender and receiver system using the ITK3 Response message. The first diagram shows just the ITK3 flows and the second diagram shown the MESH response as well. The actual flow between the systems will be dependent on factors such as:

- What responses have been requested (handling specification extension values sent)
- If an issue is detected, the type of issue and when it is reported
- How the MESH WorkflowID has been configured.

## All Possible Flows for ITK3 ##
<a href="images/explore/Typical_sequence_without_mesh.pdf" target="_blank" style="width: 100%;max-width: 100%;"><b>Click to open in new window</b></a>

<img src="images/explore/Typical_sequence_without_mesh.png" style="width: 100%;max-width: 100%;"/>

## All Possible Flows for ITK3 Including MESH Responses ##
<a href="images/explore/Typical_sequence.pdf" target="_blank" style="width: 100%;max-width: 100%;"><b>Click to open in new window</b></a>

<img src="images/explore/Typical_sequence.png" style="width: 100%;max-width: 100%;"/>

The following sections detail the response patterns supported by ITK3. The pattern used is dependent on the specification for the Payload and the response types requested.

For each pattern the mandated flows are documented in the table below the diagram.


## Full Acknowledgement ## 

This requires both acknowledgement flags in the handling specification extension to be set to "true". This is the most rigorous response framework supported by ITK3.

**There are 3 possible flows:**

**Flow where an issue is detected at infrastructure (technical) level**

<a href="images/explore/Typical_sequence_without_mesh_1.pdf" target="_blank" style="width: 100%;max-width: 100%;"><b>Click to open in new window</b></a>

<img src="images/explore/Typical_sequence_without_mesh_1.png" style="width: 100%;max-width: 100%;"/>

<table style="width:100%;max-width: 100%;">
	<thead>
		<tr>
			<th width="15%">Sender</th>
			<th width="35%">Flow</th>
			<th width="5%">Receiver</th>
		</tr>
	</thead>
	<tbody>
<tr>
<td><b>START</b></td>
<td></td>
<td></td>
</tr>
<tr>
<td>1..1</td>
<td>Send Payload</td>
<td><img src="images/explore/arrow.png" style="width: 50%;max-width: 50%;"/></td>
</tr>
<tr>
<td><img src="images/explore/arrow1.png" style="width: 25%;max-width: 50%;"/></td>
<td>Infrastructure Level Response</td>
<td>1..1</td>
</tr>
<tr>
<td></td>
<td></td>
<td><b>END</b></td>
</tr>
</tbody>
</table>		



**Flow where an issue is detected at infrastructure (technical) level with MESH responses**

<a href="images/explore/Typical_sequence_1.pdf" target="_blank" style="width: 100%;max-width: 100%;"><b>Click to open in new window</b></a>

<img src="images/explore/Typical_sequence_1.png" style="width: 100%;max-width: 100%;"/>

**Flow where an issue is detected at business level without MESH responses**


<a href="images/explore/Typical_sequence_without_mesh_3.pdf" target="_blank" style="width: 100%;max-width: 100%;"><b>Click to open in new window</b></a>

<img src="images/explore/Typical_sequence_without_mesh_3.png" style="width: 100%;max-width: 100%;"/>

<table style="width:100%;max-width: 100%;">
	<thead>
		<tr>
			<th width="15%">Sender</th>
			<th width="35%">Flow</th>
			<th width="5%">Receiver</th>
		</tr>
	</thead>
	<tbody>
<tr>
<td><b>START</b></td>
<td></td>
<td></td>
</tr>
<tr>
<td>1..1</td>
<td>Send Payload</td>
<td><img src="images/explore/arrow.png" style="width: 50%;max-width: 50%;"/></td>
</tr>
<tr>
<td><img src="images/explore/arrow1.png" style="width: 25%;max-width: 50%;"/></td>
<td>Infrastructure Level Response</td>
<td>1..1</td>
</tr>
<tr>
<td><img src="images/explore/arrow1.png" style="width: 25%;max-width: 50%;"/></td>
<td>Business Level Response</td>
<td>1..1</td>
</tr>
<tr>
<td>1..1</td>
<td>Infrastructure Level Response</td>
<td><img src="images/explore/arrow.png" style="width: 50%;max-width: 50%;"/></td>
</tr>
<tr>
<td></td>
<td></td>
<td><b>END</b></td>
</tr>
</tbody>
</table>	

**Flow where an issue is detected at business level with MESH responses**


<a href="images/explore/Typical_sequence_3.pdf" target="_blank" style="width: 100%;max-width: 100%;"><b>Click to open in new window</b></a>

<img src="images/explore/Typical_sequence_3.png" style="width: 100%;max-width: 100%;"/>


**Flow where no issue is detected without MESH responses** 

<a href="images/explore/Typical_sequence_2.pdf" target="_blank" style="width: 100%;max-width: 100%;"><b>Click to open in new window</b></a>

<img src="images/explore/Typical_sequence_2.png" style="width: 100%;max-width: 100%;"/>


<table style="width:100%;max-width: 100%;">
	<thead>
		<tr>
			<th width="15%">Sender</th>
			<th width="35%">Flow</th>
			<th width="5%">Receiver</th>
		</tr>
	</thead>
	<tbody>
<tr>
<td><b>START</b></td>
<td></td>
<td></td>
</tr>
<tr>
<td>1..1</td>
<td>Send Payload</td>
<td><img src="images/explore/arrow.png" style="width: 50%;max-width: 50%;"/></td>
</tr>
<tr>
<td><img src="images/explore/arrow1.png" style="width: 25%;max-width: 50%;"/></td>
<td>Infrastructure Level Response</td>
<td>1..1</td>
</tr>
<tr>
<td><img src="images/explore/arrow1.png" style="width: 25%;max-width: 50%;"/></td>
<td>Business Level Response</td>
<td>1..1</td>
</tr>
<tr>
<td>1..1</td>
<td>Infrastructure Level Response</td>
<td><img src="images/explore/arrow.png" style="width: 50%;max-width: 50%;"/></td>
</tr>
<tr>
<td></td>
<td></td>
<td><b>END</b></td>
</tr>
</tbody>
</table>

**Flow where no issue is detected with MESH responses** 	

<a href="images/explore/Typical_sequence_2.pdf" target="_blank" style="width: 100%;max-width: 100%;"><b>Click to open in new window</b></a>

<img src="images/explore/Typical_sequence_2.png" style="width: 100%;max-width: 100%;"/>

## Technical Acknowledgement Only ## 

This only requires the infrastructure acknowledgement flag in the handling specification extension to be set to "true". The business acknowledgement flag in the handling specification extension may be set to "false" or not present.

**Flow where an issue is detected at infrastructure (technical) level**

<a href="images/explore/Typical_sequence_1.pdf" target="_blank" style="width: 100%;max-width: 100%;"><b>Click to open in new window</b></a>

<img src="images/explore/Typical_sequence_1.png" style="width: 100%;max-width: 100%;"/>


**Flow where no issue is detected** 

<a href="images/explore/Typical_sequence_4.pdf" target="_blank" style="width: 100%;max-width: 100%;"><b>Click to open in new window</b></a>

<img src="images/explore/Typical_sequence_4.png" style="width: 100%;max-width: 100%;"/>


## Fire and Forget ##
 
This requires that both the acknowledgement flags in the handling specification extension are set to "false" or are not present. This would normally never return any response, however in some error circumstances where the acknowledgement flags cannot be read a response will be returned as illustrated.  

<a href="images/explore/Typical_sequence_1.pdf" target="_blank" style="width: 100%;max-width: 100%;"><b>Click to open in new window</b></a>

<img src="images/explore/Typical_sequence_1.png" style="width: 100%;max-width: 100%;"/>


