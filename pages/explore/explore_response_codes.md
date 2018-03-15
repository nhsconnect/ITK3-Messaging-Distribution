---
title: ITK3 Response Codes
keywords: explore Reference
tags: [explore,fhir,error codes]
sidebar: overview_sidebar
permalink: explore_response_codes.html
summary: "Response codes, their associated elements and value sets."
---

{% include custom/search.warnbanner.html %}

## Overview ##

Response information in the ITK Response message is carried in the MessageHeader Resource and the OperationOutcome Resource. There are several elements and their value sets used to carry error information in these resources. The ITK Payload Specifications may define the error handling behaviour of the clinical application/system and communicates responses using the ITK Response message. The are conceptionally two levels of validation, technical(infrastructure) and business. One or both of these types of validation may result in a negative or positive response from the receiving system. Although there is no mandated sequence to validate or process received messages logically there is a certain order to do the validation, for example the values of certain XML elements or attributes can only be validated aftyer in has be determined the the XML is well-formed. Care Professionals may also need to be informed that a Document has not reached its intended recipients. 

This page describes how response information is carried within the ITK Response message structure. The example fragments are used to illustrate the elements and value sets used and are not complete messages. 

## Response Code Types ##  
 
There will be two types of response codes:
- Positive Response codes
- Negative Response codes

**Note:** All Negative response codes are deemed to be fatal and no further processing will be carried out on the message. There will be no further response message following the response message that contains the negative response code regardless of what acknowledgement flags are set. 

## The ITK3 Response Codes ##

<table width="100%">
<tr>
<th>Response Code</th>
<th>Display Name</th>
<th>Description</th>
</tr>
<tr
<td>10001</td>
<td>Handling Specification Error</td>	
<td>A generic error code which gives a minimum level of assurance that systems can share the minimum information relating to Handling Specification faults.</td>
</tr>
<tr>
<td>10002</td>
<td>Infrastructure Level Response Value - Processing Error</td>
<td>The handling specification for infrastructure level response is present but cannot be processed. For example, may be unreadable or contain an incorrect value.</td>
</tr>
<tr>
<td>10003</td>
<td>Business Level Response Value - Processing Error</td>
<td>The handling specification for Business level response is present but cannot be processed. For example, may be unreadable or contain an incorrect value.</td>
</tr>
<tr>
<td>10004</td>
<td>Message Definition Value – Processing Error	The handling specification for Message Definition is present but cannot be processed. For example, may be unreadable or contain an incorrect value. This may also be returned when the message type is not supported (known) by the receiving system.</td>
</tr>
<tr>
<td>10005</td>
<td>Message Definition Version Value – Processing Error	The handling specification for Message Definition is present but the version is not supported by the receiving system.</td>
</tr>
<tr>
<td>10006</td>
<td>Priority Value - Processing Error</td>
<td>The handling specification for Priority is present but cannot be processed. For example, may be unreadable or contain an incorrect value.</td>
</tr>
<tr>
<td>10007</td>
<td>Sender Reference Value - Processing Error</td>
<td>The handling specification for Sender Reference is present but cannot be processed. For example, may be unreadable, contain an incorrect value or the use of Sender Reference is not supported by receiving system</td>
</tr>
<tr>
<td>10008</td>
<td>Handling Specification Business Rule Error</td>
<td>The Handling Specification usage does not match business rules for included payload (message definition). For example, an acknowledgement flag defined as mandatory by the payload specification is missing.</td>
</tr>
<tr>
<td>10009</td>
<td>Unreadable message received</td>	
<td>A message has been received that is either corrupted or malformed and cannot be read by the receiving system.</td>
</tr>
<tr>
<td>20001</td>
<td>Unrecognised Recipient Person</td>	
<td>The person referred to as the recipient in the ITK Message header is not recognised.</td>
</tr>
<tr>
<td>20002</td>
<td>Unrecognised Recipient Organisation</td>	
<td>The organization referred to as the recipient in the ITK Message header is not recognised.</td>
</tr>
<tr>
<td>20003</td>
<td>Unrecognised Sender</td>
<td>The organization or person referred to as the sender in the ITK Message header is not recognised. Note: This code should not be used where the domain makes use of the “GP look-up” functionally in MESH.</td>
</tr>
<tr>
<td>20004</td>
<td>Non-Approved file type received as an attachment</td>	
<td>The Receiving system has received an attached file whose file type is not approved for the business domain.</td>
</tr>
<tr> 
<td>20005</td>
<td>Unsupported file type received as an attachment</td> 	
<td>The Receiving system has received an attached file which it does not supported.</td>
</tr>
<tr>
<td>20006</td>
<td>ITK header validation failure</td>	
<td>The ITK header resources or elements are not correct or understandable. For example, ITK Bundle or ITK Message Header.</td>
</tr>
<tr>
<td>20007</td>
<td>Duplicate Message received</td>
<td>Bundle with this message identifier has already been processed. A payload with this message.header identifier has already been received and processed by this recipient.</td>
</tr>
<tr>
<td>20008</td>	
<td>Duplicate Document received</td>	
<td>Bundle with this document identifier has already been processed. A payload with this document identifier has already been received and processed by this recipient.</td>
</tr>
<tr>
<td>20009</td>
<td>Payload validation failure>/td>
<td>Payload content validation has failed.</td>
</tr>
<tr>
<td>20010</td>
<td>Unrecognised Payload Recipient Organisation</td>	
<td>The Recipient Organisation identified in the payload, is not supported by this End Point (Receiving System).</td>
<tr>
</tr>
<td>20011</td>
<td>Unrecognised Payload Recipient Person</td>	
<td>The Recipient person identified in the payload, is not supported by this End Point (Receiving System).</td>
</tr>
<tr>
<td>20012</td>
<td>Unauthorised Sender</td>	
<td>The Receiving system identified in the payload is configured to reject messages from unauthorised senders. This code should not be used where the domain makes use of the “GP look-up” functionally in MESH.</td>
</tr>
<tr>
<td>20013</td>
<td>Success</td>	
<td>The Message has been processed successfully at the infrastructure level. A response will be returned stating the fact. However, the message may still fail after further processing and result in another response if the business acknowledgment request flag has been sent to “true”.</td>
</tr>
<tr>
<td>30001</td>
<td>Patient known here. (e.g. Patient is registered here)</td>
<td></td>	
</tr>
<tr>
<td>30002</td>	
<td>Patient not known here. (aka ‘patient record not present in system’)</td>
<td></td>
</tr>
<tr>
<td>30003</td>	
<td>Patient no longer at this clinical setting</td>
<td></td>
</tr>
</table>	


## Elements And Value Sets Used To Carry Error and Response Information ##

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
<a href="https://fhir.nhs.uk/ValueSet/itk-response-codes-1" target="_blank">itk-response-codes</a>
</td>
</tr>
</table>

The MessageHeader carries a code to indicate success or failure. The ITK response codes must be mapped to the high-level element codes carried in the severity, code and details elements of the OperationOutcome. The mapping Table below shows how the three levels of codes should be utilised. 

**Note**: When a bundle is incorrectly constructed or received so that the value of the acknowledgement flags cannot be determined, receiving systems SHOULD default to always returning a response wherever possible. 

## Mapping FHIR Error or Warning Codes to ITK3 Response Codes ##

## Handling Specification Responses ##

These Responses should be returned to the sender using the ITK Response message.

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
<td>10001</td>
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
<td colspan="5"><b>A code from the list below which is applicable for the handling specification which has an error. Example usage is for incorrect or unreadable values.</b>
</td>
</tr>	
<tr>
<td>issue.details.code</td>	
<td>ITK-Response</td>
<td>10002</td>
<td>Infrastructure Acknowledgement Flag - Processing Error</td>
<td>The handling specification flag for infrastructure level acknowledgement is present but cannot be processed. For example may be unreadable or contain an incorrect value</td>
</tr>
<tr>
<td>issue.details.code</td>	
<td>ITK-Response</td>
<td>10003</td>
<td>Business Acknowledgement Flag - Processing Error</td>
<td>The handling specification flag for business level acknowledgement is present but cannot be processed. For example may be unreadable or contain an incorrect value</td>
</tr>
<tr>
<td>issue.details.code</td>	
<td>ITK-Response</td>
<td>10004</td>
<td>Message Definition Value – Processing Error</td>
<td>The handling specification value for Message Definition is present but cannot be processed. For example may be unreadable or contain an incorrect value. The handling specification for Message Definition is present but cannot be processed. For example, may be unreadable or contain an incorrect value. This may also be returned when the message type is not supported (known) by the receiving system.</td>
</tr>
<tr>
<td>issue.details.code</td>	
<td>ITK-Response</td>
<td>10005</td>
<td>Message Definition Version Value – Processing Error</td>
<td>The handling specification for Message Definition is present but the version is not supported by the receiving system.</td>
</tr>
<tr>
<td>issue.details.code</td>	
<td>ITK-Response</td>
<td>10006</td>
<td>Priority Value - Processing Error</td>
<td>The handling specification code for Priority is present but cannot be processed. For example may be unreadable or contain an incorrect value</td>
</tr>
<tr>
<td>issue.details.code</td>	
<td>ITK-Response</td>
<td>10007</td>
<td>Sender Reference Value - Processing Error</td>
<td>The handling specification string for Sender Reference is present but cannot be processed. For example may be unreadable, contain an incorrect value or the use of Sender Reference is not supported by receiving system</td>
</tr>
<tr>
<td>issue.details.code</td>	
<td>ITK-Response</td>
<td>10008</td>
<td>Handling Specification Business Rule Error</td>
<td>The Handling Specification usage does not match business rules for included payload (message definition). For example an acknowledgement flag defined as mandatory by the payload specification is missing.</td>
</tr>
<tr>
<td>issue.details.code</td>	
<td>ITK-Response</td>
<td>10009</td>
<td>Unreadable message received</td>
<td>A message has been received that is either corrupted or malformed and cannot be read by the receiving system.</td>
</tr>		
</table>

## Bundle and Payload Validation Response Codes ##

These response codes should be returned to the sender using the ITK Response message.

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
<td>20011</td> 
<td>Success</td>
<td>The Message has been processed successfully. An response will be returned stating the fact. However, the message may still fail after further processing and result in another response if the business acknowledgment request flag has been sent to “true”.</td>
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
<td>transient-error</td>
<td>Transient Error</td>
<td>Some internal unexpected error occurred - wait and try again. <b>Note 1:</b>This is usually used for things like database unavailable, which may be expected to resolve, though human intervention may be required. <b>Note 2:</b> If a subsequent resubmission fails then, the receiving site should be contacted to resolve the issue as it may be due to a underlying problem such as a configuration issue.</td>
</tr>	
<tr>	
<th colspan="5" align="left">OperationOutcome</th>
</tr>
<tr>
<td>issue.severity.code</td> 	
<td>IssueSeverity</td>	
<td>error</td>
<td>Error</td>
<td>The issue is sufficiently important to cause the action to fail.</td>
</tr>
<tr>	
<td>issue.code</td>	
<td>IssueType</td>	
<td>transient</td>
<td>Transient Issue</td>	
<td>Transient processing issues. The system receiving the error may be able to resubmit the same content once an underlying issue is resolved.</td>
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


## Error Scenario Examples ##




## Infrastructure Acknowledgement: OK ##

This uses the MessageHeader resource to carry the code.

<script src="https://gist.github.com/IOPS-DEV/b6678b59daaa95a18fd4f808b0e8f32d.js"></script>

## Infrastructure Acknowledgement: Fatal-Error - Payload Validation Failure ##

This uses the MessageHeader and the OperationOutcome resources.

<script src="https://gist.github.com/IOPS-DEV/ff82904e958c68c28db73139a47b6911.js"></script>

## Infrastructure Acknowledgement: Fatal-Error - Handling Specification Error ##

This uses the MessageHeader and the OperationOutcome resources

<script src="https://gist.github.com/IOPS-DEV/ae61ef54e2827502cf382e3a6e19a986.js"></script>

## Infrastructure Acknowledgement: Fatal-Error - Processing Error ##

This uses the MessageHeader and the OperationOutcome resources

<script src="https://gist.github.com/IOPS-DEV/313aeb38232f92aacdbabf235f24b0af.js"></script>

## Infrastructure Acknowledgement: Fatal-Error - Unrecognised Recipient Person Error ##

This uses the MessageHeader and the OperationOutcome resources

<script src="https://gist.github.com/IOPS-DEV/a50afeaaa7cfeb3e14bf91ae20821590.js"></script>

## Infrastructure Acknowledgement: Fatal-Error - Unrecognised Sender ##

This uses the MessageHeader and the OperationOutcome resources

<script src="https://gist.github.com/IOPS-DEV/429ae1f41bafecf32f07d5140a639090.js"></script>

## Infrastructure Acknowledgement: Fatal-Error - Non Approved File Type Received as an Attachment Error ##

This uses the MessageHeader and the OperationOutcome resources

<script src="https://gist.github.com/IOPS-DEV/1e4e2a8bfb439756062248fb4ffb8743.js"></script>

## Infrastructure Acknowledgement: Fatal-Error - Attachment File Type Invalid ##

This uses the MessageHeader and the OperationOutcome resources

<script src="https://gist.github.com/IOPS-DEV/d0fd48f3c19e498218f06f025295b9fc.js"></script>

## Infrastructure Acknowledgement: Fatal-Error - Unrecognised Recipient Organisation Error ##

This uses the MessageHeader and the OperationOutcome resources

<script src="https://gist.github.com/IOPS-DEV/5eef74d5e9207ffc206e1cbd66db137d.js"></script>

## Infrastructure Acknowledgement: Fatal-Error - Unauthorised Sender Error ##

This uses the MessageHeader and the OperationOutcome resources

<script src="https://gist.github.com/IOPS-DEV/43445fc1ed2e3761da20f45d8cacfc23.js"></script>

## Infrastructure Acknowledgement: Fatal-Error - Duplicate Message Received Error ##

This uses the MessageHeader and the OperationOutcome resources

<script src="https://gist.github.com/IOPS-DEV/30971d3a9dc414caea8db1b0dd339f7d.js"></script>

## Infrastructure Acknowledgement: Fatal-Error - Duplicate Document Received Error ##

This uses the MessageHeader and the OperationOutcome resources

<script src="https://gist.github.com/IOPS-DEV/c87f2fc1d4aa11f4c9edf69e7873ece5.js"></script>

## Infrastructure Acknowledgement: Fatal-Error - Service Failure Error ##

This uses the MessageHeader and the OperationOutcome resources

<script src="https://gist.github.com/IOPS-DEV/123c48d13168f0de90663ff01f8d224b.js"></script>

## Infrastructure Acknowledgement: Fatal-Error - Unreadable Message Received ##

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

## Business Acknowledgement: OK - Patient Known Here ##

This uses the MessageHeader and the OperationOutcome resources.

<script src="https://gist.github.com/IOPS-DEV/846a7953fe122b9f811e14f06a5752c1.js"></script>

## Business Acknowledgement: Fatal-Error - Patient not Known Here ##

This uses the MessageHeader and the OperationOutcome resources

<script src="https://gist.github.com/IOPS-DEV/7591e3aa10e414b600ac2d786f6f33c2.js"></script>

## Business Acknowledgement: Fatal-Error - Patient no Longer at this Clinical Setting Error ##

This uses the MessageHeader and the OperationOutcome resources

<script src="https://gist.github.com/IOPS-DEV/3cc67a3a8bc9b78222c3a36177a68b14.js"></script>
