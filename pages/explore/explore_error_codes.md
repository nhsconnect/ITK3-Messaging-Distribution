---
title: ITK 3 Error Codes
keywords: explore Reference
tags: [explore,fhir,error codes]
sidebar: overview_sidebar
permalink: explore_error_codes.html
summary: "Error codes, their associated elements and value sets."
---

{% include custom/search.warnbanner.html %}

## Overview ##

Error information in the Acknowledgement Response messages is carried in the MessageHeader Resource and the OperationOutcome Resource. There are several elements and their value sets used to carry error information in these resources. The ITK Payload Specifications may define the error handling behaviour of the clinical application/system and communicates errors using the ITK Business Acknowledgements.

Care Professionals need to be informed that a Document has not reached, or is experiencing difficulty in reaching, its intended recipients. 
This page describes how error information is carried. The example fragments are used to illustrate the elements and value sets used and are not complete messages. 


## Elements And Value Sets Used To Carry Error Information ##

<table width="100%">
<tr>
<th>Resource</th>
<th>Element</th>
<th>Value Set</th>
</tr>
<tr>
<td>MessageHeader</td>
<td>response.code</td>
<td><a href="http://hl7.org/fhir/STU3/valueset-response-code.html" target="_blank">response-code</a></td>   
</tr>
<tr>
<td>OperationOutcome</td>
<td>issue.severity.code</td>
<td><a href="http://hl7.org/fhir/STU3/valueset-issue-severity.html" target="_blank">issue-severity</a></td>
</tr>
<tr>
<td>OperationOutcome</td>
<td>issue.code</td>
<td><a href="http://hl7.org/fhir/STU3/valueset-issue-type.html" target="_blank">issue-type</a></td>
</tr>
<tr>
<td>OperationOutcome</td>
<td>issue.details.code</td>
<td>
<a href="https://fhir.nhs.uk/ValueSet/itk-acknowledgement-1" target="_blank">itk-acknowledgement</a>
</td>
</tr>
</table>

The MessageHeader carries a code to indicate success or failure. The ITK error codes must be mapped to the high-level element codes carried in the severity, code and details elements of the OperationOutcome. The mapping Table below shows how the three levels of codes should be utilised. 

**Note**: When a bundle is incorrectly constructed or received so that the value of the infrastructure acknowledgement flag cannot be determined, receiving systems SHOULD default to always returning an acknowledgement wherever possible. 

## Mapping FHIR Error Codes to ITK3 Error Codes ##

## Distribution Level Errors ##

These errors should be returned to the sender using the Infrastructure Acknowledgement message.

**Minimum requirements that MUST be supported by receiving systems.**

<table width="100%">
<tr>
<th>Element</th>
<th>CodeSystem</th>	
<th>Value</th>
<th>Display</th>	
<th>Definition</th>
</tr>
<tr>
<th colspan="5" align="left">MessageHeader</th>
</tr>
<tr>
<td>response.code</td>	
<td>ResponseType</td>
<td>fatal-error</td>
<td>Fatal Error</td>
<td>The message was rejected because of a problem with the content. There is no point in re-sending without change.</td>
</tr>
<tr>
<th colspan="5" align="left">OperationOutcome elements</th>
</tr>
<tr>
<td>issue.severity</td>	
<td>IssueSeverity</td>
<td>fatal</td>
<td>Fatal</td>
<td>The issue caused the action to fail, and no further checking could be performed.</td>
</tr>
<tr>
<td>issue.code</td>	
<td>IssueType</td>
<td>processing</td>
<td>Processing Failure</td>
<td>Processing issues. These are expected to be final e.g. there is no point resubmitting the same content unchanged.</td>
</tr>	
<tr>
<td>issue.details.code</td>	
<td>ITK-Acknowledgement</td>
<td>RC001</td>
<td>Handling Specification Error</td>
<td>A generic error code which gives a minimum level 
of assurance that systems can share the minimum information 
relating to Handling Specification faults.</td>
</tr>		

</table>


**Requirement that SHOULD be supported by receiving systems.**

<table width="100%">
<tr>
<th>Element</th>
<th>CodeSystem</th>	
<th>Value</th>	
<th>Display</th>
<th>Definition</th>
</tr>
<tr>
<th colspan="5" align="left">MessageHeader</th>
</tr>
<tr>
<td>response.code</td>	
<td>ResponseType</td>
<td>fatal-error</td>
<td>Fatal Error</td>
<td>The message was rejected because of a problem with the content. There is no point in re-sending without change.</td>
</tr>
<tr>
<th colspan="5" align="left">OperationOutcome elements</th>
</tr>
<tr>
<td>issue.severity.code</td>	
<td>IssueSeverity</td>
<td>fatal</td>
<td>Fatal</td>
<td>	The issue caused the action to fail, and no further checking could be performed.</td>
</tr>
<tr>
<td>issue.code</td>	
<td>IssueType</td>
<td>processing</td>
<td>Processing Failure</td>
<td>Processing issues. These are expected to be final e.g. there is no point resubmitting the same content unchanged.</td>
</tr>
<tr>
<td colspan="5"><b>A code from the list below which is applicable for the handling specification which has an error. Example usage is for incorrect or unreadable values.</b>
</td>
</tr>	
<tr>
<td>issue.details.code</td>	
<td>ITK-Acknowledgement</td>
<td>RC002</td>
<td>Business Acknowledgement - Processing Error</td>
<td>The handling specification for Business Acknowledgement is present but cannot be processed. For example may be unreadable or contain an incorrect value</td>
</tr>
<tr>
<td>issue.details.code</td>	
<td>ITK-Acknowledgement</td>
<td>RC003</td>
<td>Infrastructure Acknowledgement - Processing Error</td>
<td>The handling specification for Infrastructure Acknowledgement is present but cannot be processed. For example may be unreadable or contain an incorrect value</td>
</tr>
<tr>
<td>issue.details.code</td>	
<td>ITK-Acknowledgement</td>
<td>RC004</td>
<td>Message Definition – Processing Error</td>
<td>The handling specification for Message Definition is present but cannot be processed. For example may be unreadable or contain an incorrect value. This may also be returned when the message type or version is not supported by the receiving system.</td>
</tr>
<tr>
<td>issue.details.code</td>	
<td>ITK-Acknowledgement</td>
<td>RC005</td>
<td>Priority - Processing Error</td>
<td>The handling specification for Priority is present but cannot be processed. For example may be unreadable or contain an incorrect value</td>
</tr>
<tr>
<td>issue.details.code</td>	
<td>ITK-Acknowledgement</td>
<td>RC006</td>
<td>Sender Reference - Processing Error</td>
<td>The handling specification for Sender Reference is present but cannot be processed. For example may be unreadable, contain an incorrect value or the use of Sender Reference is not supported by receiving system</td>
</tr>
<tr>
<td>issue.details.code</td>	
<td>ITK-Acknowledgement</td>
<td>RC999</td>
<td>Handling Specification Business Rule Error</td>
<td>The Handling Specification usage does not match business rules for included payload (message definition). For example an acknowledgement flag defined as mandatory by the payload specification is missing.</td>
</tr>		
</table>

## Payload Validation Error Codes ##
These error codes should be returned to the sender using the Infrastructure Acknowledgement message.

**The system SHOULD support the extension values as below**

<table width="100%">
<tr>
<th>Element</th>	
<th>CodeSystem</th>	
<th>Value</th>
<th>Display</th>	
<th>Definition</th>
</tr>
<tr>
<th colspan="5" align="left">MessageHeader</th>
</tr>
<tr>
<td>response.code</td>	
<td>ResponseType</td>	
<td>ok</td>
<td>OK</td>
<td>The message was accepted and processed without error.</td>
</tr>
<tr>	
<th colspan="5" align="left">OperationOutcome</th>
</tr>
<tr>
<td>issue.severity.code</td> 	
<td>IssueSeverity</td>	
<td>information</td>
<td>Information</td>
<td>The issue has no relation to the degree of success of the action.</td>
</tr>
<tr>
<td>issue.code</td>	
<td>IssueType</td>	
<td>informational</td>
<td>Informational Note</td>
<td>A message unrelated to the processing success of the completed operation</td>
</tr>
<tr>	
<td>issue.details.code</td>
<td>ITK-Acknowledgement</td>	
<td>51001</td> 
<td>Success</td>
<td>The Message has been processed successfully at the infrastructure level. Note: the message may still fail at the business level.</td>
</tr>
</table>

<table width="100%">
<tr>
<th>Element</th>	
<th>CodeSystem</th>	
<th>Value</th>
<th>Display</th>	
<th>Definition</th>
</tr>
<tr>	
<th colspan="5" align="left">MessageHeader</th>
</tr>
<tr>
<td>response.code</td>	
<td>ResponseType</td>	
<td>fatal-error</td>
<td>Fatal Error</td>
<td>The message was rejected because of a problem with the content. There is no point in re-sending without change.</td>
</tr>	
<tr>	
<th colspan="5" align="left">OperationOutcome</th>
</tr>
<tr>
<td>issue.severity.code</td> 	
<td>IssueSeverity</td>	
<td>fatal</td>
<td>Fatal</td>
<td>The issue caused the action to fail, and no further checking could be performed.</td>
</tr>
<tr>	
<td>issue.code</td>	
<td>IssueType</td>
<td>not-found</td>
<td>Not Found</td>
<td>The reference provided was not found. In a pure RESTful environment, this would be an HTTP 404 error, but this code may be used where the content is not found further into the application architecture.</td>
</tr>
<tr>
<td>issue.details.code</td>
<td>ITK-Acknowledgement</td>
<td>51002</td>
<td>Unrecognised Recipient Person</td>
<td>The Recipient Person is not recognised but the Recipient Organisation is.</td>
</tr>
</table>

<table width="100%">
<tr>
<th>Element</th>	
<th>CodeSystem</th>	
<th>Value</th>
<th>Display</th>	
<th>Definition</th>
</tr>
<tr>
<th colspan="5" align="left">MessageHeader</th>
</tr>
<tr>
<td>response.code</td>	
<td>ResponseType</td>	
<td>fatal-error</td>
<td>Fatal Error</td>
<td>The message was rejected because of a problem with the content. There is no point in re-sending without change.</td>
</tr>		
<tr>	
<th colspan="5" align="left">OperationOutcome</th>
</tr>
<tr>
<td>issue.severity.code</td> 	
<td>IssueSeverity</td>	
<td>fatal</td>
<td>Fatal</td>
<td>The issue caused the action to fail, and no further checking could be performed.</td>
</tr>
<tr>
<td>issue.code</td>
<td>IssueType</td>	
<td>not-found</td>
<td>Not Found</td>
<td>The reference provided was not found. In a pure RESTful environment, this would be an HTTP 404 error, but this code may be used where the content is not found further into the application architecture.</td>
</tr>
<tr>	
<td>issue.details.code</td>
<td>ITK-Acknowledgement</td>		
<td>51003</td>
<td>Unrecognised Sender</td>
<td>The Receiving system does not recognise the Sender but the message has been passed on for local (recipient) investigation / processing.</td>
</tr>
</table>

<table width="100%">
<tr>
<th>Element</th>	
<th>CodeSystem</th>	
<th>Value</th>
<th>Display</th>	
<th>Definition</th>
</tr>
<tr>
<th colspan="5" align="left">MessageHeader</th>
</tr>
<tr>
<td>response.code</td>	
<td>ResponseType</td>	
<td>fatal-error</td>
<td>Fatal Error</td>
<td>The message was rejected because of a problem with the content. There is no point in re-sending without change.</td>
</tr>	
<tr>	
<th colspan="5" align="left">OperationOutcome</th>
</tr>
<tr>
<td>issue.severity.code</td> 	
<td>IssueSeverity</td>	
<td>fatal</td>
<td>Fatal</td>
<td>The issue caused the action to fail, and no further checking could be performed.</td>
</tr>
<tr>
<td>issue.code</td>
<td>IssueType</td>	
<td>security</td>
<td>Security</td>
<td>An authentication/authorization/permissions issue of some kind.</td>
</tr>
<tr>	
<td>issue.details.code</td>
<td>ITK-Acknowledgement</td>		 
<td>51004</td>
<td>Non Approved file type received as an attachment</td>
<td>The Receiving system has received an attached file whose file type is on the Authorities ‘Black List’.</td>
</tr>
</table>


<table width="100%">
<tr>
<th>Element</th>	
<th>CodeSystem</th>	
<th>Value</th>
<th>Display</th>	
<th>Definition</th>
</tr>
<tr> 
<th colspan="5" align="left">MessageHeader</th>
</tr>
<tr>
<td>response.code</td>	
<td>ResponseType</td>	
<td>fatal-error</td>
<td>Fatal Error</td>
<td>The message was rejected because of a problem with the content. There is no point in re-sending without change.</td>
</tr>	
<tr>
<th colspan="5" align="left">OperationOutcome</th>
</tr>
<tr>
<td>issue.severity.code</td> 	
<td>IssueSeverity</td>	
<td>fatal</td>
<td>Fatal</td>
<td>The issue caused the action to fail, and no further checking could be performed.</td>
</tr>
<tr>	
<td>issue.code</td>
<td>IssueType</td>
<td>
<ul>
<li><b>invalid</b></li>
<li>structure</li>
<li>required</li>
<li>value</li>
<li>invariant</li>
<li>processing</li>
<li>not-supported</li>
<li>code-invalid</li>
<li>extension</li>
<li>business-rule</li>
</ul>
</td>
<td></td>
<td>Dependant of the type of content error. invalid is the high level code, lower level codes should be used to further identify the type of content validation error wherever possible. See <a href="http://hl7.org/fhir/codesystem-issue-type.html">IssueType</a> for further information.
</td>
</tr>
<tr>
<td>issue.details.code</td>
<td>ITK-Acknowledgement</td>
<td>51005</td> 
<td>Payload validation failure</td>
<td>Content validation has failed</td>
</tr>
</table>

<table width="100%">
<tr>
<th>Element</th>	
<th>CodeSystem</th>	
<th>Value</th>
<th>Display</th>	
<th>Definition</th>
</tr>
<tr>
<th colspan="5" align="left">MessageHeader</th>
</tr>
<tr>
<td>response.code</td>	
<td>ResponseType</td>	
<td>fatal-error</td>
<td>Fatal Error</td>
<td>The message was rejected because of a problem with the content. There is no point in re-sending without change.</td>
</tr>	
<tr>	
<th colspan="5" align="left">OperationOutcome</th>
</tr>
<tr>
<td>issue.severity.code</td> 	
<td>IssueSeverity</td>	
<td>fatal</td>
<td>Fatal</td>
<td>The issue caused the action to fail, and no further checking could be performed.</td>
</tr>
<tr>	
<td>issue.code</td>
<td>IssueType</td>
<td>
<ul>
<li><b>invalid</b></li>
<li>structure</li>
<li>required</li>
<li>value</li>
<li>invariant</li>
<li>processing</li>
<li>not-supported</li>
<li>code-invalid</li>
<li>extension</li>
<li>business-rule</li>
</ul>
</td>
<td></td>
<td>Dependant of the type of content error. invalid is the high level code, lower level codes should be used to further identify the type of content validation error wherever possible. See <a href="http://hl7.org/fhir/codesystem-issue-type.html">IssueType</a> for further information.
</td>
</tr>
<tr>
<td>issue.details.code</td>
<td>ITK-Acknowledgement</td>
<td>51006</td>
<td>Document content validation failure</td>
<td>Document Content validation has failed.</td>
</tr>
</table>

<table width="100%">
<tr>
<th>Element</th>	
<th>CodeSystem</th>	
<th>Value</th>
<th>Display</th>	
<th>Definition</th>
</tr>
<tr>
<th colspan="5" align="left">MessageHeader</th>
</tr>
<tr>
<td>response.code</td>	
<td>ResponseType</td>	
<td>fatal-error</td>
<td>Fatal Error</td>
<td>The message was rejected because of a problem with the content. There is no point in re-sending without change.</td>
</tr>	
<tr>	
<th colspan="5" align="left">OperationOutcome</th>
</tr>
<tr>
<td>issue.severity.code</td> 	
<td>IssueSeverity</td>	
<td>fatal</td>
<td>Fatal</td>
<td>The issue caused the action to fail, and no further checking could be performed.</td>
</tr>
<tr>	
<td>issue.code</td>
<td>IssueType</td>
<td>processing</td>
<td>Processing Failure</td>
<td>Processing issues. These are expected to be final e.g. there is no point resubmitting the same content unchanged.</td>
</tr>
<tr>	
<td>issue.details.code</td>
<td>ITK-Acknowledgement</td>
<td>51007</td>
<td>Attachment file type invalid</td>
<td>One or more attachments has an invalid file type.</td>
</tr>
</table>

<table width="100%">
<tr>
<th>Element</th>	
<th>CodeSystem</th>	
<th>Value</th>
<th>Display</th>	
<th>Definition</th>
</tr>
<tr>
<th colspan="5" align="left">MessageHeader</th>
</tr>
<tr>
<td>response.code</td>	
<td>ResponseType</td>	
<td>fatal-error</td>
<td>Fatal Error</td>
<td>The message was rejected because of a problem with the content. There is no point in re-sending without change.</td>
</tr>	
<tr>	
<th colspan="5" align="left">OperationOutcome</th>
</tr>
<tr>
<td>issue.severity.code</td> 	
<td>IssueSeverity</td>	
<td>fatal</td>
<td>Fatal</td>
<td>The issue caused the action to fail, and no further checking could be performed.</td>
</tr>
<tr>	
<td>issue.code</td>
<td>IssueType</td>
<td>not-found</td>
<td>Not Found</td>
<td>The reference provided was not found. In a pure RESTful environment, this would be an HTTP 404 error, but this code may be used where the content is not found further into the application architecture.</td>
</tr>
<tr>	
<td>issue.details.code</td>
<td>ITK-Acknowledgement</td>		 
<td>51008</td>
<td>Unrecognised Recipient Organisation</td>
<td>The Recipient Organisation identified, is not supported by this End Point (Receiving System).</td>
</tr>
</table>

<table width="100%">
<tr>
<th>Element</th>	
<th>CodeSystem</th>	
<th>Value</th>
<th>Display</th>	
<th>Definition</th>
</tr>
<tr>
<th colspan="5" align="left">MessageHeader</th>
</tr>
<tr>
<td>response.code</td>	
<td>ResponseType</td>	
<td>fatal-error</td>
<td>Fatal Error</td>
<td>The message was rejected because of a problem with the content. There is no point in re-sending without change.</td>
</tr>	
<tr>	
<th colspan="5" align="left">OperationOutcome</th>
</tr>
<tr>
<td>issue.severity.code</td> 	
<td>IssueSeverity</td>	
<td>fatal</td>
<td>Fatal</td>
<td>The issue caused the action to fail, and no further checking could be performed.</td>
</tr>
<tr>
<td>issue.code</td>
<td>IssueType</td>	
<td>security</td>
<td>Security Problem</td>
<td>An authentication/authorization/permissions issue of some kind.</td>
</tr>
<tr>	
<td>issue.details.code</td>
<td>ITK-Acknowledgement</td>		 
<td>51009</td> 
<td>Unauthorised Sender</td>
<td>The Receiving system identified in the document is configured to reject messages from unauthorised senders.</td>
</tr>
</table>

<table width="100%">
<tr>
<th>Element</th>	
<th>CodeSystem</th>	
<th>Value</th>
<th>Display</th>	
<th>Definition</th>
</tr>
<tr>
<th colspan="5" align="left">MessageHeader</th>
</tr>
<tr>
<td>response.code</td>	
<td>ResponseType</td>	
<td>fatal-error</td>
<td>Fatal Error</td>
<td>The message was rejected because of a problem with the content. There is no point in re-sending without change.</td>
</tr>	
<tr>	
<th colspan="5" align="left">OperationOutcome</th>
</tr>
<tr>
<td>issue.severity.code</td> 	
<td>IssueSeverity</td>	
<td>fatal</td>
<td>Fatal</td>
<td>The issue caused the action to fail, and no further checking could be performed.</td>
</tr>
<tr>
<td>issue.code</td>
<td>IssueType</td>	
<td>duplicate</td>
<td>Duplicate</td>
<td>An attempt was made to create a duplicate record.</td>
</tr>
<tr>
<td>issue.details.code</td>
<td>ITK-Acknowledgement</td>		 
<td>51010</td>
<td>Duplicate Message received</td>
<td>Bundle with this message identifier has already been processed.	A payload with this message identifier has already been received and processed by this recipient.</td>
</tr>
</table>

<table width="100%">
<tr>
<th>Element</th>	
<th>CodeSystem</th>	
<th>Value</th>
<th>Display</th>	
<th>Definition</th>
</tr>
<tr>
<th colspan="5" align="left">MessageHeader</th>
</tr>
<tr>
<td>response.code</td>	
<td>ResponseType</td>	
<td>fatal-error</td>
<td>Fatal Error</td>
<td>The message was rejected because of a problem with the content. There is no point in re-sending without change.</td>	
</tr>
<tr>	
<th colspan="5" align="left">OperationOutcome</th>
</tr>
<tr>
<td>issue.severity.code</td> 	
<td>IssueSeverity</td>	
<td>fatal</td>
<td>Fatal</td>
<td>The issue caused the action to fail, and no further checking could be performed.</td>
</tr>
<tr>
<td>issue.code</td>
<td>IssueType</td>
<td>duplicate</td>
<td>Duplicate</td>
<td>An attempt was made to create a duplicate record.</td>
</tr>
<tr>
<td>issue.details.code</td>
<td>ITK-Acknowledgement</td>		 
<td>51011</td>
<td>Duplicate Document received</td>
<td>Document with this identifier has already been processed. A payload with this composition identifier has already been received and processed by this recipient.</td>
</tr>
</table>

<table width="100%">
<tr>
<th>Element</th>	
<th>CodeSystem</th>	
<th>Value</th>
<th>Display</th>	
<th>Definition</th>
</tr>
<tr>
<th colspan="5" align="left">MessageHeader</th>
</tr>
<tr>
<td>response.code</td>	
<td>ResponseType</td>	
<td>fatal-error</td>
<td>Fatal Error</td>
<td>The message was rejected because of a problem with the content. There is no point in re-sending without change.</td>
</tr>	
<tr>	
<th colspan="5" align="left">OperationOutcome</th>
</tr>
<tr>
<td>issue.severity.code</td> 	
<td>IssueSeverity</td>	
<td>fatal</td>
<td>Fatal</td>
<td>The issue caused the action to fail, and no further checking could be performed.</td>
</tr>
<tr>	
<td>issue.code</td>	
<td>IssueType</td>	
<td>processing</td>
<td>Processing Failure</td>	
<td>Processing issues. These are expected to be final e.g. there is no point resubmitting the same content unchanged.</td>
</tr>
<tr>
<td>issue.details.code</td>
<td>ITK-Acknowledgement</td>
<td>51012</td>
<td>Service failure</td>
<td>Unexpected recoverable fault caught in Recipient System. Could not process this message at this time.</td>
</tr>
</table> 			



<table width="100%">
<tr>
<th>Element</th>	
<th>CodeSystem</th>	
<th>Value</th>
<th>Display</th>	
<th>Definition</th>
</tr>
<tr>
<th colspan="5" align="left">MessageHeader</th>
</tr>
<tr>
<td>response.code</td>	
<td>ResponseType</td>	
<td>fatal-error</td>
<td>Fatal Error</td>
<td>The message was rejected because of a problem with the content. There is no point in re-sending without change.</td>
</tr>	
<tr>	
<th colspan="5" align="left">OperationOutcome</th>
</tr>
<tr>
<td>issue.severity.code</td> 	
<td>IssueSeverity</td>	
<td>fatal</td>
<td>Fatal</td>
<td>The issue caused the action to fail, and no further checking could be performed.</td>
</tr>
<tr>	
<td>issue.code</td>	
<td>IssueType</td>	
<td>structure</td>
<td>Structural Issue</td>	
<td>A structural issue in the content such as wrong namespace, or unable to parse the content completely, or invalid json syntax.</td>
</tr>
<tr>
<td>issue.details.code</td>
<td>ITK-Acknowledgement</td>
<td>51013</td>
<td>Unreadable message received</td>
<td>A message has been received that is either corrupted or malformed and cannot be read by the receiving system</td>
</tr>
</table> 

## ITK Business Acknowledgement Report Codes ##

These errors should be returned to the sender using the Business Acknowledgement message.

**Minimum requirements that MUST be supported.**

<table>
<tr>
<th>Element</th>	
<th>CodeSystem</th>	
<th>Value</th>
<th>Display</th>	
<th>Definition</th>
</tr>
<tr>
<th colspan="5" align="left">MessageHeader</th>
</tr>
<tr>
<td>response.code</td>
<td>ResponseType</td>	
<td>ok</td>
<td>OK</td>
<td>The message was accepted and processed without error.</td>
</tr>
<tr>	
<th colspan="5" align="left">OperationOutcome</th> 
</tr>
<tr>
<td>issue.severity.code</td> 	
<td>IssueSeverity</td>
<td>information</td>
<td>Information</td>
<td>The issue has no relation to the degree of success of the action.</td>
</tr>
<tr>	
<td>issue.code</td>	
<td>IssueType</td>	
<td>informational</td>
<td>Informational Note</td>
<td>A message unrelated to the processing success of the completed operation.</td>
</tr>
<tr>	
<td>issue.details.code</td>
<td>ITK-Acknowledgement</td>		
<td>41001</td>
<td>Patient known here. (e.g. Patient is registered here)</td>
<td></td>	
</tr>
</table>

<table>
<tr>
<th>Element</th>	
<th>CodeSystem</th>	
<th>Value</th>
<th>Display</th>	
<th>Definition</th>
</tr>
<tr>
<th colspan="5" align="left">MessageHeader</th>
</tr>
<tr>
<td>response.code</td>	
<td>ResponseType</td>	
<td>fatal-error</td>
<td>Fatal Error</td>
<td>The message was rejected because of a problem with the content. There is no point in re-sending without change.</td>
</tr>
<tr>
<th colspan="5" align="left">OperationOutcome</th>
</tr>
<tr>
<td>issue.severity.code</td> 	
<td>IssueSeverity</td>
<td>fatal</td>
<td>Fatal</td>
<td>The issue caused the action to fail, and no further checking could be performed.</td>
</tr>
<tr>	
<td>issue.code</td>	
<td>IssueType</td>	
<td>not-found</td>
<td>Not Found</td>
<td>The reference provided was not found. In a pure RESTful environment, this would be an HTTP 404 error, but this code may be used where the content is not found further into the application architecture.</td>
</tr>
<tr>	
<td>issue.details.code</td>
<td>ITK-Acknowledgement</td>
<td>41002</td>	
<td>Patient not known here. (aka ‘patient record not present in system’)</td>
<td></td>
</tr>
</table>

<table>
<tr>
<th>Element</th>	
<th>CodeSystem</th>	
<th>Value</th>
<th>Display</th>	
<th>Definition</th>
</tr>
<tr>
<th colspan="5" align="left">MessageHeader</th>
</tr>
<tr>
<td>response.code</td>	
<td>ResponseType</td>	
<td>fatal-error</td>
<td>Fatal Error</td>
<td>The message was rejected because of a problem with the content. There is no point in re-sending without change.</td>
</tr>
<tr>	
<th colspan="5" align="left">OperationOutcome</th>
</tr>
<tr>
<td>issue.severity.code</td>
<td>IssueSeverity</td>	
<td>fatal</td>
<td>Fatal</td>
<td>The issue caused the action to fail, and no further checking could be performed.</td>
</tr>
<tr>	
<td>issue.code</td>
<td>IssueType</td>
<td>business-rule</td>
<td>Business Rule Violation</td>
<td>The content/operation failed to pass some business rule, and so could not proceed.</td>
</tr>
<tr>	
<td>issue.details.code</td>
<td>ITK-Acknowledgement</td>		
<td>41022</td>
<td>Patient no longer at this clinical setting</td>	
<td></td>
</tr>
</table>


# Error Scenarios #

## Scenario - OK at the Infrastructure Level ##

This uses the MessageHeader resource to carry the code.

<script src="https://gist.github.com/IOPS-DEV/b6678b59daaa95a18fd4f808b0e8f32d.js"></script>

## Scenario - Error at the Infrastructure Level ##

This uses the MessageHeader and the OperationOutcome resources.

<script src="https://gist.github.com/IOPS-DEV/ff82904e958c68c28db73139a47b6911.js"></script>

## Scenario - Ok at the Business Level ##

This uses the MessageHeader and the OperationOutcome resources.

<script src="https://gist.github.com/IOPS-DEV/846a7953fe122b9f811e14f06a5752c1.js"></script>

## Scenario - Error at the Business Level due to Patient not Registered ##

This uses the MessageHeader and the OperationOutcome resources

<script src="https://gist.github.com/IOPS-DEV/7591e3aa10e414b600ac2d786f6f33c2.js"></script>

## Scenario - Handling Specification Error ##

This uses the MessageHeader and the OperationOutcome resources

<script src="https://gist.github.com/IOPS-DEV/ae61ef54e2827502cf382e3a6e19a986.js"></script>

## Scenario - Infrastructure Acknowledgement - Processing Error ##

This uses the MessageHeader and the OperationOutcome resources

<script src="https://gist.github.com/IOPS-DEV/313aeb38232f92aacdbabf235f24b0af.js"></script>

## Scenario - Unrecognised Recipient Person Error - The Recipient Person is not Recognised but the Recipient Organisation is. ##

This uses the MessageHeader and the OperationOutcome resources

<script src="https://gist.github.com/IOPS-DEV/a50afeaaa7cfeb3e14bf91ae20821590.js"></script>

## Scenario - Unrecognised Sender - The Receiving System does not Recognise the Sender but the Message has been Passed on for Local (Recipient) Investigation / Processing. ##

This uses the MessageHeader and the OperationOutcome resources

<script src="https://gist.github.com/IOPS-DEV/429ae1f41bafecf32f07d5140a639090.js"></script>

## Scenario - Non Approved File Type Received as an Attachment Error ##

This uses the MessageHeader and the OperationOutcome resources

<script src="https://gist.github.com/IOPS-DEV/1e4e2a8bfb439756062248fb4ffb8743.js"></script>

## Scenario - Payload Validation Failure Error ##

This uses the MessageHeader and the OperationOutcome resources

<script src="https://gist.github.com/IOPS-DEV/1aed32d6c6446127883aa1e5a193ed26.js"></script>

## Scenario - Attachment File Type Invalid ##

This uses the MessageHeader and the OperationOutcome resources

<script src="https://gist.github.com/IOPS-DEV/d0fd48f3c19e498218f06f025295b9fc.js"></script>

## Scenario - Unrecognised Recipient Organisation Error ##

This uses the MessageHeader and the OperationOutcome resources

<script src="https://gist.github.com/IOPS-DEV/5eef74d5e9207ffc206e1cbd66db137d.js"></script>

## Scenario - Unauthorised Sender Error ##

This uses the MessageHeader and the OperationOutcome resources

<script src="https://gist.github.com/IOPS-DEV/43445fc1ed2e3761da20f45d8cacfc23.js"></script>

## Scenario - Duplicate Message Received Error ##

This uses the MessageHeader and the OperationOutcome resources

<script src="https://gist.github.com/IOPS-DEV/30971d3a9dc414caea8db1b0dd339f7d.js"></script>

## Scenario - Duplicate Document Received Error ##

This uses the MessageHeader and the OperationOutcome resources

<script src="https://gist.github.com/IOPS-DEV/c87f2fc1d4aa11f4c9edf69e7873ece5.js"></script>

## Scenario - Service Failure Error ##

This uses the MessageHeader and the OperationOutcome resources

<script src="https://gist.github.com/IOPS-DEV/123c48d13168f0de90663ff01f8d224b.js"></script>

## Scenario - Patient no Longer at this Clinical Setting Error ##

This uses the MessageHeader and the OperationOutcome resources

<script src="https://gist.github.com/IOPS-DEV/3cc67a3a8bc9b78222c3a36177a68b14.js"></script>

## Scenario - Unreadable Message Error Scenario ##

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

<script src="https://gist.github.com/IOPS-DEV/xxxxxxxxxxxxxxxxxxxx.js"></script>
