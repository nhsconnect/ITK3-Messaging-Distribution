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

This diagram gives an overview of the typical interaction between a sender and receiver system using the ITK3 Response message over MESH. The actual flow between the systems will be dependant on factors such:

- What responses have been requested (handling specification extension values sent)
- If an issue is detected, the type of issue and when it is reported

<a href="images/explore/Typical_sequence.pdf" target="_blank" style="width: 100%;max-width: 100%;"><b>Click to open in new window</b></a>

<img src="images/explore/Typical_sequence.pdf" style="width: 100%;max-width: 100%;"/>

The following sections details the response patterns supported by ITK3. The pattern used is dependant on the specification for the payload and the response types requested.

**Note: All diagrams show typical flows which may vary slightly due to such things as MESH configuration.**

## Full Acknowledgement ## 

This requires both acknowledgement flags in the handling specification extension to be set to "true". This is the most rigorous response framework supported by ITK3.

There are 3 possible flows:

**Flow where an issue is detected at infrastructure(technical) level**

<a href="images/explore/Typical_sequence_1.png" target="_blank" style="width: 100%;max-width: 100%;"><b>Click to open in new window</b></a>

<img src="images/explore/Typical_sequence_1.png" style="width: 100%;max-width: 100%;"/>


**Flow where an issue is detected at business level**


<a href="images/explore/Typical_sequence_3.png" target="_blank" style="width: 100%;max-width: 100%;"><b>Click to open in new window</b></a>

<img src="images/explore/Typical_sequence_3.png" style="width: 100%;max-width: 100%;"/>


**Flow where no issue is detected** 

<a href="images/explore/Typical_sequence_2.png" target="_blank" style="width: 100%;max-width: 100%;"><b>Click to open in new window</b></a>

<img src="images/explore/Typical_sequence_2.png" style="width: 100%;max-width: 100%;"/>

## Technical Acknowledgement Only ## 

This requires only the infrastructure acknowledgement flag in the handling specification extension to be set to "true". The business acknowledgement flag in the handling specification extension may be set to "false" or not present.

**Flow where an issue is detected at infrastructure (technical) level**

<a href="images/explore/Typical_sequence_1.png" target="_blank" style="width: 100%;max-width: 100%;"><b>Click to open in new window</b></a>

<img src="images/explore/Typical_sequence_1.png" style="width: 100%;max-width: 100%;"/>


**Flow where no issue is detected** 

<a href="images/explore/Typical_sequence_4.png" target="_blank" style="width: 100%;max-width: 100%;"><b>Click to open in new window</b></a>

<img src="images/explore/Typical_sequence_4.png" style="width: 100%;max-width: 100%;"/>


## Fire and Forget ##
 
This requires that both the acknowledgement flags in the handling specification extension are set to "false" or not to be present. This would normally never return any response, however in some error circumstances where the acknowledgement flags cannot be read a response as illustrated will be returned.  

<a href="images/explore/Typical_sequence_1.png" target="_blank" style="width: 100%;max-width: 100%;"><b>Click to open in new window</b></a>

<img src="images/explore/Typical_sequence_1.png" style="width: 100%;max-width: 100%;"/>


