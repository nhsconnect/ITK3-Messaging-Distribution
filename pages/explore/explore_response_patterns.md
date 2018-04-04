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

The following are the response patterns supported by ITK3. These are dependant on the domain specification and the  response types requested.

## Full Acknowledgement ## 

This uses both acknowledgement flags in the handling specification extension set to "true". This is the most rigorous response framework.

There are 3 possible flows:

**Flow where issue is detected at infrastructure (technical) level**


<img src="images/explore/full_ack_1.png" style="width: 45%;max-width: 45%;"/>


**Flow where issues are detected at business level**

<img src="images/explore/full_ack_2.png"/>


**Flow where no issues are detected** 

<img src="images/explore/full_ack_3.png"/> 

## Technical Acknowledgement Only ## 

This uses only the infrastructure acknowledgement flag set to true.

**Flow where issue is detected at infrastructure (technical) level**

<img src="images/explore/full_ack_1.png" style="width: 45%;max-width: 45%;"/>

**Flow where no issues are detected** 

<img src="images/explore/full_ack_4.png" style="width: 45%;max-width: 45%;"/> 

## Fire and Forget ##
 
This type has both flags set to false and would normally never return any response, however in some error circumstances where the flags cannot be read a response as illustrated will be returned.  

<img src="images/explore/full_ack_5.png" style="width: 45%;max-width: 45%;"/>


