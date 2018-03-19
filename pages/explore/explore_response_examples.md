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

## Infrastructure Level Response 10001: Fatal-Error - Handling Specification Error ##

<script src="https://gist.github.com/IOPS-DEV/ae61ef54e2827502cf382e3a6e19a986.js"></script>

## Infrastructure Level Response 10002: Fatal-Error - Infrastructure Response Value Processing Error ##

<script src="https://gist.github.com/IOPS-DEV/313aeb38232f92aacdbabf235f24b0af.js"></script>

## Infrastructure Level Response 10003: Fatal-Error - Business Level Response Value Processing Error ##

TO DO

## Infrastructure Level Response 10004: Fatal-Error - Message Definition Value Processing Error ##

TO DO

## Infrastructure Level Response 10005: Fatal-Error - Message Definition Version Value – Processing Error ##

TO DO

## Infrastructure Level Response 10006: Fatal-Error - Priority Value - Processing Error ##

TO DO

## Infrastructure Level Response 10007: Sender Reference Value - Processing Error ##

TO DO

## Infrastructure Level Response 10008: Handling Specification Business Rule Error ##

TO DO

## Infrastructure Level Response 10009: Fatal-Error - Unreadable Message Received ##

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


## Infrastructure Level Response 20001: Fatal-Error - Unrecognised Recipient Person ##

<script src="https://gist.github.com/IOPS-DEV/a50afeaaa7cfeb3e14bf91ae20821590.js"></script>

## Infrastructure Level Response 20002: Fatal-Error - Unrecognised Recipient Organisation ##

<script src="https://gist.github.com/IOPS-DEV/a50afeaaa7cfeb3e14bf91ae20821590.js"></script>

## Infrastructure Level Response 20003: Fatal-Error - Unrecognised Sender ##

<script src="https://gist.github.com/IOPS-DEV/429ae1f41bafecf32f07d5140a639090.js"></script>

## Infrastructure Level Response 20004: Fatal-Error - Non Approved File Type Received as an Attachment ##

<script src="https://gist.github.com/IOPS-DEV/1e4e2a8bfb439756062248fb4ffb8743.js"></script>

## Infrastructure Level Response 20005: Fatal-Error - Unsupported file type received as an attachment ##

<script src="https://gist.github.com/IOPS-DEV/1e4e2a8bfb439756062248fb4ffb8743.js"></script>

## Infrastructure Level Response 20006: Fatal-Error - ITK header validation failure ##

TO DO

## Infrastructure Level Response 20007: Fatal-Error - Duplicate Message Received ##

<script src="https://gist.github.com/IOPS-DEV/30971d3a9dc414caea8db1b0dd339f7d.js"></script>

## Infrastructure Level Response 20008: Fatal-Error - Duplicate Document Received ##

<script src="https://gist.github.com/IOPS-DEV/c87f2fc1d4aa11f4c9edf69e7873ece5.js"></script>

## Infrastructure Level Response 20009: Fatal-Error - Payload Validation Failure ##

<script src="https://gist.github.com/IOPS-DEV/ff82904e958c68c28db73139a47b6911.js"></script>

## Infrastructure Level Response 20010: Fatal-Error - Unrecognised Payload Recipient Organisation ##

<script src="https://gist.github.com/IOPS-DEV/5eef74d5e9207ffc206e1cbd66db137d.js"></script>

## Infrastructure Level Response 20011: Fatal-Error - Unrecognised Payload Recipient Person ##

TO DO

## Infrastructure Level Response 20012: Fatal-Error - Unauthorised Sender ##

<script src="https://gist.github.com/IOPS-DEV/43445fc1ed2e3761da20f45d8cacfc23.js"></script>

## Infrastructure Level Response 20013: OK ##

<script src="https://gist.github.com/IOPS-DEV/b6678b59daaa95a18fd4f808b0e8f32d.js"></script>

----------

## Business Level Response 30001:  - Patient Known Here ##

This uses the MessageHeader and the OperationOutcome resources.

<script src="https://gist.github.com/IOPS-DEV/846a7953fe122b9f811e14f06a5752c1.js"></script>

## Business Level Response 30002: Fatal-Error - Patient not Known Here ##

This uses the MessageHeader and the OperationOutcome resources

<script src="https://gist.github.com/IOPS-DEV/7591e3aa10e414b600ac2d786f6f33c2.js"></script>

## Business Level Response 30003: Fatal-Error - Patient no Longer at this Clinical Setting Error ##

This uses the MessageHeader and the OperationOutcome resources

<script src="https://gist.github.com/IOPS-DEV/3cc67a3a8bc9b78222c3a36177a68b14.js"></script>
