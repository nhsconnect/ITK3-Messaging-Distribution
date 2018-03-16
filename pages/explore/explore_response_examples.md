---
title: ITK3 Response Examples
keywords: explore Reference
tags: [explore,fhir,error codes]
sidebar: overview_sidebar
permalink: explore_response_examples.html
summary: "Response code examples."
---

{% include custom/search.warnbanner.html %}

## Error Scenario Examples ##


## Infrastructure Level Response: OK ##

<script src="https://gist.github.com/IOPS-DEV/b6678b59daaa95a18fd4f808b0e8f32d.js"></script>

## Infrastructure Level Response: Fatal-Error - Payload Validation Failure ##

<script src="https://gist.github.com/IOPS-DEV/ff82904e958c68c28db73139a47b6911.js"></script>

## Infrastructure Level Response: Fatal-Error - Handling Specification Error ##

<script src="https://gist.github.com/IOPS-DEV/ae61ef54e2827502cf382e3a6e19a986.js"></script>

## Infrastructure Level Response: Fatal-Error - Processing Error ##

<script src="https://gist.github.com/IOPS-DEV/313aeb38232f92aacdbabf235f24b0af.js"></script>

## Infrastructure Level Response: Fatal-Error - Unrecognised Recipient Person Error ##

<script src="https://gist.github.com/IOPS-DEV/a50afeaaa7cfeb3e14bf91ae20821590.js"></script>

## Infrastructure Level Response: Fatal-Error - Unrecognised Sender ##

<script src="https://gist.github.com/IOPS-DEV/429ae1f41bafecf32f07d5140a639090.js"></script>

## Infrastructure Level Response: Fatal-Error - Non Approved File Type Received as an Attachment Error ##

<script src="https://gist.github.com/IOPS-DEV/1e4e2a8bfb439756062248fb4ffb8743.js"></script>

## Infrastructure Level Response: Fatal-Error - Attachment File Type Invalid ##

<script src="https://gist.github.com/IOPS-DEV/d0fd48f3c19e498218f06f025295b9fc.js"></script>

## Infrastructure Level Response: Fatal-Error - Unrecognised Recipient Organisation Error ##

<script src="https://gist.github.com/IOPS-DEV/5eef74d5e9207ffc206e1cbd66db137d.js"></script>

## Infrastructure Level Response: Fatal-Error - Unauthorised Sender Error ##

<script src="https://gist.github.com/IOPS-DEV/43445fc1ed2e3761da20f45d8cacfc23.js"></script>

## Infrastructure Level Response: Fatal-Error - Duplicate Message Received Error ##

<script src="https://gist.github.com/IOPS-DEV/30971d3a9dc414caea8db1b0dd339f7d.js"></script>

## Infrastructure Level Response: Fatal-Error - Duplicate Document Received Error ##

<script src="https://gist.github.com/IOPS-DEV/c87f2fc1d4aa11f4c9edf69e7873ece5.js"></script>

## Infrastructure Level Response: Fatal-Error - Unreadable Message Received ##

When a system receives a message which is totally unreadable due to it being corrupted or malformed, there is a default behaviour defined which systems should support. This behaviour for information unobtainable from the handling keys and header elements is listed below:

----------

**Issue** - Unable to ascertain if an acknowledgement has been requested.

**Default Behaviour** - An acknowledgement must always be returned to the sender.

----------

**Issue** - Unable to ascertain sender person or organisation.

**Default Behaviour** - Return acknowledgement to MESH mailbox original message was sent from and original sending system will have to deal with acknowledgement the best it can. 

----------

**Issue** - Unable to ascertain whether original message was for action or only for information.

**Default Behaviour** - Assume for action and return acknowledgement.

----------

**Issue** - Unable to ascertain priority of original message.

**Default Behaviour** - Return acknowledgement as soon as possible once error is detected. 

----------

**Issue** - Unable to ascertain any other information

**Default Behaviour** - Return acknowledgement as soon as possible once error is detected. 

----------

**Issue** - Unable to ascertain the identifier of the original message.

**Default Behaviour** - return the fixed string of "UNREADABLE-IN-ORIGINAL-MESSAGE"

Note: If only certain elements are missing or unreadable then the error codes associated with that key or element should be returned instead wherever possible.

<script src="https://gist.github.com/IOPS-DEV/88e98b35e38e00d6f9f4f2ed0f898137.js"></script>


----------

## Business Level Response: OK - Patient Known Here ##

This uses the MessageHeader and the OperationOutcome resources.

<script src="https://gist.github.com/IOPS-DEV/846a7953fe122b9f811e14f06a5752c1.js"></script>

## Business Level Response: Fatal-Error - Patient not Known Here ##

This uses the MessageHeader and the OperationOutcome resources

<script src="https://gist.github.com/IOPS-DEV/7591e3aa10e414b600ac2d786f6f33c2.js"></script>

## Business Level Response: Fatal-Error - Patient no Longer at this Clinical Setting Error ##

This uses the MessageHeader and the OperationOutcome resources

<script src="https://gist.github.com/IOPS-DEV/3cc67a3a8bc9b78222c3a36177a68b14.js"></script>