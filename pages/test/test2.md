---
title: Test Overview
keywords: test
tags: [overview]
sidebar: foundations_sidebar
permalink: test.html
summary: "These pages assist with requirements gathering and mapping stages of an ITK3 Messaging Solution development process."
---

## Mapping table ##



|  [**Procedure - Profiled using CareConnect-NHSD-Procedure-1**](https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-NHSD-Procedure-1) |  |  |  |  |
|  ------ | ------ | ------ | ------ | ------ |
|  **Elemernt Name** | **Card.** | **Conformance** | **Type** | **Mapping Constraints For This Implemenation** |
|  Procedure | ​ |  |  | An action that is being or was performed on a patient<br/>Constraint (dom-2): If the resource is contained in another resource, it SHALL NOT contain nested Resources<br/>Constraint (dom-1): If the resource is contained in another resource, it SHALL NOT contain any narrative<br/>Constraint (dom-4): If a resource is contained in another resource, it SHALL NOT have a meta.versionId or a meta.lastUpdated<br/>Constraint (dom-3): If the resource is contained in another resource, it SHALL be referred to from elsewhere in the resource<br/>Constraint (pro-1): Reason not done is only permitted if notDone indicator is true |
|  - meta | 0..1 | Mandatory | [Meta](http://hl7.org/fhir/stu3/resource.html#Meta) | Profile element MUST conrtain the value <br/>https://fhir.nhs.uk/StructureDefinition/CareConnect-NHSD-Procedure-1 |
|  - extension (anaestheticIssues) | 0..1 | Required | [Extension](http://hl7.org/fhir/stu3/extensibility.html#Extension) | [Details of any adverse reaction to any anaesthetic agents. Constraint (ext-1): Must have either extensions or value[x], not both. See extension mapping table for more information. URL: https://fhir.hl7.org.uk/STU3/StructureDefinition/Extension-CareConnect-AnaestheticIssues-1](https://fhir.hl7.org.uk/STU3/StructureDefinition/Extension-CareConnect-AnaestheticIssues-1) |
|  - identifier | 0..* | Mandatory | [Identifier](http://hl7.org/fhir/stu3/datatypes.html#identifier) | External Identifiers for this procedure |
|  - - system | 1..1 | Mandatory | [Uri](http://hl7.org/fhir/stu3/datatypes.html#uri) | The namespace for the identifier value - MUST contain the URI  https://tools.ietf.org/html/rfc4122 |
|  - - value | 1..1 | Mandatory | [String](http://hl7.org/fhir/stu3/datatypes.html#string) | The value that is unique - MUST contain a UUID |
|   |  | Optional | [`CareConnect-Procedure-1`](https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-Procedure-1) | A refernce to a Procedure which this procedure is a part of. |
|   |  | Optional | [`CareConnect-Observation-1`](https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-Observation-1) | A refernce to a Observation which this procedure is a part of. |
|  - - - reference | 0..1 | Mandatory | [String](http://hl7.org/fhir/stu3/datatypes.html#string) | The UUID of the referred to resource instant in the message bundle |
|  - - status | 1..1 | Mandatory | [Code](http://hl7.org/fhir/stu3/datatypes.html#code) | preparation : in-progress : suspended : aborted : completed : entered-in-error : unknown. Binding (required): A code specifying the state of the procedure. MUST be fixed to completed ( http://hl7.org/fhir/stu3/valueset-event-status.html ) |
|  - - code | 0..1 | Mandatory | [CodeableConcept](http://hl7.org/fhir/stu3/datatypes.html#codeableconcept) | A SNOMED CT Concept to describe the procedure performed. |
|  - - - coding | 0..* | Mandatory | [Coding](http://hl7.org/fhir/stu3/datatypes.html#coding) | Code defined by a terminology system<br/>Slicing: Discriminator: system, Ordering: false, Rules: Open |
|  - - - coding (snomedCT) | 0..1 | Mandatory | [Coding](http://hl7.org/fhir/stu3/datatypes.html#coding) | Code defined by a terminology system. Binding (extensible): A code from the SNOMED Clinical Terminology UK. (https://fhir.hl7.org.uk/STU3/ValueSet/CareConnect-ProcedureCode-1 ) |
|  - - - - extension (snomedCTDescriptionID) | 0..1 | Optional | [Extension](http://hl7.org/fhir/stu3/extensibility.html#Extension) | The SNOMED CT Description ID for the display. Constraint (ext-1): Must have either extensions or value[x], not both. URL: https://fhir.hl7.org.uk/STU3/StructureDefinition/Extension-coding-sctdescid |
|  - - - - system | 1..1 | Mandatory | [Uri](http://hl7.org/fhir/stu3/datatypes.html#uri) | Identity of the terminology system. MUST contain the fixed Value: http://snomed.info/sct |
|  - - - - code | 1..1 | Mandatory | [Code](http://hl7.org/fhir/stu3/datatypes.html#code) | Must contain a SNOMED CT concept that conforms to the following expression:<br/>"<<71388002 &#124;<code>&amp;#124;</code>Procedure<code>&amp;#124;</code> OR<br/><<129125009 &#124;<code>&amp;#124;</code>Procedure with explicit context<code>&amp;#124;</code>  <br/>" |
|  - - - - display | 1..1 | Mandatory | [String](http://hl7.org/fhir/stu3/datatypes.html#string) | The prefferred term for the SNOMED CT concept |
|  - - - - userSelected | 0..1 | Optional | [Boolean](http://hl7.org/fhir/stu3/datatypes.html#boolean) | If this coding was chosen directly by the user |
|  - - subject | 1..1 | Mandatory | [Reference](http://hl7.org/fhir/stu3/references.html) | Who the procedure was performed on<br/>Constraint (ref-1): SHALL have a contained resource if a local reference is provided |
|   |  | Mandatory | [`CareConnect-Patient-1`](https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-Patient-1) |  |
|  - - - reference | 0..1 | Mandatory | [String](http://hl7.org/fhir/stu3/datatypes.html#string) | Literal reference, Relative, internal or absolute URL |
|  - - context | 0..1 | Mandatory | [Reference](http://hl7.org/fhir/stu3/references.html) | Encounter or episode associated with the procedure<br/>Constraint (ref-1): SHALL have a contained resource if a local reference is provided |
|   |  | Mandatory | [CareConnect-Encounter-1](https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-Encounter-1) |  |
|  - - - reference | 0..1 | Mandatory | [String](http://hl7.org/fhir/stu3/datatypes.html#string) | Literal reference, Relative, internal or absolute URL |
|  - - performed[x] | 0..1 | Required | [dateTime](http://hl7.org/fhir/stu3/datatypes.html#dateTime) | Date the procedure was performed |
|   |  | Required | [Period](http://hl7.org/fhir/stu3/datatypes.html#Period) | The Period the procedure was performed |
|  - - performer | 0..* | Required | [BackboneElement](http://hl7.org/fhir/stu3/backboneelement.html) | The people who performed the procedure |
|  - - - role | 0..1 | Required | [CodeableConcept](http://hl7.org/fhir/stu3/datatypes.html#codeableconcept) | The role the actor was in. Binding (example): A code that identifies the role of a performer of the procedure. (http://hl7.org/fhir/stu3/valueset-performer-role.html ) |
|  - - - - coding | 0..* | Mandatory | [Coding](http://hl7.org/fhir/stu3/datatypes.html#coding) | Code defined by a terminology system |
|  - - - - system | 0..1 | Mandatory | [Uri](http://hl7.org/fhir/stu3/datatypes.html#uri) | Identity of the terminology system |
|  - - - - code | 0..1 | Mandatory | [Code](http://hl7.org/fhir/stu3/datatypes.html#code) | Symbol in syntax defined by the system |
|  - - - - display | 0..1 | Mandatory | [String](http://hl7.org/fhir/stu3/datatypes.html#string) | Representation defined by the system |
|  - - - text | 0..1 | Optional | [String](http://hl7.org/fhir/stu3/datatypes.html#string) | Plain text representation of the concept |
|  - - actor | 1..1 | Mandatory | [Reference](http://hl7.org/fhir/stu3/references.html) | The reference to the practitioner<br/>Constraint (ref-1): SHALL have a contained resource if a local reference is provided |
|   |  | Mandatory | [`CareConnect-Practitioner-1`](https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-Practitioner-1) |  |
|  - - - reference | 0..1 | Mandatory | [String](http://hl7.org/fhir/stu3/datatypes.html#string) | Literal reference, Relative, internal or absolute URL |
|  - - onBehalfOf | 0..1 | Required | [Reference ( CareConnect-Organization-1 )](https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-Organization-1) | Organization the device or practitioner was acting for<br/>Constraint (ref-1): SHALL have a contained resource if a local reference is provided |
|  - - - reference | 0..1 | Mandatory | [String](http://hl7.org/fhir/stu3/datatypes.html#string) | Literal reference, Relative, internal or absolute URL |
|  - - location | 0..1 | Required | [Reference ( CareConnect-Location-1 )](https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-Location-1) | Where the procedure happened<br/>Constraint (ref-1): SHALL have a contained resource if a local reference is provided |
|  - - - reference | 0..1 | Mandatory | [String](http://hl7.org/fhir/stu3/datatypes.html#string) | Literal reference, Relative, internal or absolute URL |
|  - - reasonCode | 0..* | Optional | [CodeableConcept](http://hl7.org/fhir/stu3/datatypes.html#codeableconcept) | Coded reason procedure performed. Binding (example): A code that identifies the reason a procedure is required. (http://hl7.org/fhir/stu3/valueset-procedure-reason.html ) |
|  - - - coding | 0..* | Mandatory | [Coding](http://hl7.org/fhir/stu3/datatypes.html#coding) | Code defined by a terminology system |
|  - - - - system | 0..1 | Mandatory | [Uri](http://hl7.org/fhir/stu3/datatypes.html#uri) | Identity of the terminology system |
|  - - - - code | 0..1 | Mandatory | [Code](http://hl7.org/fhir/stu3/datatypes.html#code) | Symbol in syntax defined by the system |
|  - - - - display | 0..1 | Mandatory | [String](http://hl7.org/fhir/stu3/datatypes.html#string) | Representation defined by the system |
|  - - - text | 0..1 | Optional | [String](http://hl7.org/fhir/stu3/datatypes.html#string) | Plain text representation of the concept |
|  - - reasonReference | 0..* | Required | [Reference](http://hl7.org/fhir/stu3/references.html) | Condition that is the reason the procedure performed<br/>Constraint (ref-1): SHALL have a contained resource if a local reference is provided |
|   |  | Optional | [`CareConnect-Observation-1`](https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-Observation-1) |  |
|   |  | Optional | [`CareConnect-Condition-1`](https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-Condition-1) |  |
|  - - - reference | 0..1 | Mandatory | [String](http://hl7.org/fhir/stu3/datatypes.html#string) | Literal reference, Relative, internal or absolute URL |
|  - - bodySite | 0..* | Required | [CodeableConcept](http://hl7.org/fhir/stu3/datatypes.html#codeableconcept) | [Target body sites. Binding (example): Codes describing anatomical locations. May include laterality. (http://hl7.org/fhir/stu3/valueset-body-site.html )](http://hl7.org/fhir/stu3/valueset-body-site.html) |
|  - - - coding | 0..* | Mandatory | [Coding](http://hl7.org/fhir/stu3/datatypes.html#coding) | Code defined by a terminology system<br/>Slicing: Discriminator: system, Ordering: false, Rules: Open |
|  - - - - coding (snomedCT) | 0..1 | Mandatory | [Coding](http://hl7.org/fhir/stu3/datatypes.html#coding) | Code defined by a terminology system. Binding (extensible): A code from the SNOMED Clinical Terminology UK. (https://fhir.hl7.org.uk/STU3/ValueSet/CareConnect-BodySite-1 ) |
|  - - - - extension (snomedCTDescriptionID) | 0..1 | Optional | [Extension](http://hl7.org/fhir/stu3/extensibility.html#Extension) | [The SNOMED CT Description ID for the display. Constraint (ext-1): Must have either extensions or value[x], not both. URL: https://fhir.hl7.org.uk/STU3/StructureDefinition/Extension-coding-sctdescid](https://fhir.hl7.org.uk/STU3/StructureDefinition/Extension-coding-sctdescid) |
|  - - - - system | 1..1 | Mandatory | [Uri](http://hl7.org/fhir/stu3/datatypes.html#uri) | Identity of the terminology system<br/>Fixed Value: http://snomed.info/sct |
|  - - - - code | 1..1 | Mandatory | [Code](http://hl7.org/fhir/stu3/datatypes.html#code) | Symbol in syntax defined by the system |
|  - - - - display | 1..1 | Mandatory | [String](http://hl7.org/fhir/stu3/datatypes.html#string) | Representation defined by the system |
|  - - - text | 0..1 | Optional | [String](http://hl7.org/fhir/stu3/datatypes.html#string) | Plain text representation of the concept |
|  - - outcome | 0..1 | Required | [CodeableConcept](http://hl7.org/fhir/stu3/datatypes.html#codeableconcept) | [The result of procedure. Binding (example): An outcome of a procedure - whether it was resolved or otherwise. (http://hl7.org/fhir/stu3/valueset-procedure-outcome.html )](http://hl7.org/fhir/stu3/valueset-procedure-outcome.html) |
|  - - - coding | 0..* | Mandatory | [Coding](http://hl7.org/fhir/stu3/datatypes.html#coding) | Code defined by a terminology system |
|  - - - - system | 0..1 | Mandatory | [Uri](http://hl7.org/fhir/stu3/datatypes.html#uri) | Identity of the terminology system |
|  - - - - code | 0..1 | Mandatory | [Code](http://hl7.org/fhir/stu3/datatypes.html#code) | Symbol in syntax defined by the system |
|  - - - - display | 0..1 | Mandatory | [String](http://hl7.org/fhir/stu3/datatypes.html#string) | Representation defined by the system |
|  - - - text | 0..1 | Optional | [String](http://hl7.org/fhir/stu3/datatypes.html#string) | Plain text representation of the concept |
|  - - report | 0..* | Required | [Reference ( DiagnosticReport)](http://hl7.org/fhir/stu3/diagnosticreport.html) | Any report resulting from the procedure<br/>Constraint (ref-1): SHALL have a contained resource if a local reference is provided |
|  - - - reference | 0..1 | Mandatory | [String](http://hl7.org/fhir/stu3/datatypes.html#string) | Literal reference, Relative, internal or absolute URL |
|  - - complication | 0..* | Required | [CodeableConcept](http://hl7.org/fhir/stu3/datatypes.html#codeableconcept) | [Complication following the procedure. Binding (example): Codes describing complications that resulted from a procedure. (http://hl7.org/fhir/stu3/valueset-condition-code.html )](http://hl7.org/fhir/stu3/valueset-condition-code.html) |
|  - - - coding | 0..* | Mandatory | [Coding](http://hl7.org/fhir/stu3/datatypes.html#coding) | Code defined by a terminology system<br/>Slicing: Discriminator: system, Ordering: false, Rules: Open |
|  - - - coding (snomedCT) | 0..1 | Mandatory | [Coding](http://hl7.org/fhir/stu3/datatypes.html#coding) | [Code defined by a terminology system. Binding (required): A code from the SNOMED Clinical Terminology UK. (https://fhir.hl7.org.uk/STU3/ValueSet/CareConnect-ConditionCode-1 )](https://fhir.hl7.org.uk/STU3/ValueSet/CareConnect-ConditionCode-1) |
|  - - - - system | 1..1 | Mandatory | [Uri](http://hl7.org/fhir/stu3/datatypes.html#uri) | Identity of the terminology system<br/>Fixed Value: http://snomed.info/sct |
|  - - - - code | 1..1 | Mandatory | [Code](http://hl7.org/fhir/stu3/datatypes.html#code) | Symbol in syntax defined by the system |
|  - - - - display | 1..1 | Mandatory | [String](http://hl7.org/fhir/stu3/datatypes.html#string) | Representation defined by the system |
|  - - - text | 0..1 | Optional | [String](http://hl7.org/fhir/stu3/datatypes.html#string) | Plain text representation of the concept |
|  - - complicationDetail | 0..* | Optional | [Reference ( CareConnect-Condition-1 )](https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-Condition-1) | A condition that is a result of the procedure<br/>Constraint (ref-1): SHALL have a contained resource if a local reference is provided |
|  - - - reference | 0..1 | Mandatory | [String](http://hl7.org/fhir/stu3/datatypes.html#string) | Literal reference, Relative, internal or absolute URL |
|  - - followUp | 0..* | Required | [CodeableConcept](http://hl7.org/fhir/stu3/datatypes.html#codeableconcept) | [Instructions for follow up. Binding (example): Specific follow up required for a procedure e.g. removal of sutures. (http://hl7.org/fhir/stu3/valueset-procedure-followup.html )](http://hl7.org/fhir/stu3/valueset-procedure-followup.html) |
|  - - - - coding | 0..* | Mandatory | [Coding](http://hl7.org/fhir/stu3/datatypes.html#coding) | Code defined by a terminology system |
|  - - - - system | 0..1 | Mandatory | [Uri](http://hl7.org/fhir/stu3/datatypes.html#uri) | Identity of the terminology system |
|  - - - - code | 0..1 | Mandatory | [Code](http://hl7.org/fhir/stu3/datatypes.html#code) | Symbol in syntax defined by the system |
|  - - - - display | 0..1 | Mandatory | [String](http://hl7.org/fhir/stu3/datatypes.html#string) | Representation defined by the system |
|  - - - text | 0..1 | Optional | [String](http://hl7.org/fhir/stu3/datatypes.html#string) | Plain text representation of the concept |
|  - - note | 0..* | Optional | [Annotation](http://hl7.org/fhir/stu3/datatypes.html#annotation) | Additional information about the procedure |
|  - - - author[x] | 0..1 | Required | [Reference](http://hl7.org/fhir/stu3/references.html) | Individual responsible for the annotation<br/>Constraint (ref-1): SHALL have a contained resource if a local reference is provided |
|   |  | Mandatory | [`CareConnect-Practitioner-1`](https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-Practitioner-1) |  |
|  - - - time | 0..1 | Optional | [dateTime](http://hl7.org/fhir/stu3/datatypes.html#datetime) | When the annotation was made |
|  - - - text | 1..1 | Mandatory | [String](http://hl7.org/fhir/stu3/datatypes.html#string) | The annotation - text content |
|  - - focalDevice | 0..* | Optional | [BackboneElement](http://hl7.org/fhir/stu3/backboneelement.html) | Device changed in procedure |
|  - - usedReference | 0..* | Optional | [Reference](http://hl7.org/fhir/stu3/references.html) | Items used during procedure<br/>Constraint (ref-1): SHALL have a contained resource if a local reference is provided |
|   |  | Optional | [`Device`](http://hl7.org/fhir/stu3/device.html) |  |
|   |  | Optional | [`Substance`](http://hl7.org/fhir/stu3/substance.html) |  |
|   |  | Optional | [`CareConnect-Medication-1`](https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-Medication-1) |  |
|  - - - reference | 0..1 | Mandatory | [String](http://hl7.org/fhir/stu3/datatypes.html#string) | Literal reference, Relative, internal or absolute URL |
|  - - usedCode | 0..* | Required | [CodeableConcept](http://hl7.org/fhir/stu3/datatypes.html#codeableconcept) | [Coded items used during the procedure. Binding (example): Codes describing items used during a procedure ( http://hl7.org/fhir/stu3/valueset-device-kind.html )](http://hl7.org/fhir/stu3/valueset-device-kind.html) |
|  - - - coding | 0..* | Mandatory | [Coding](http://hl7.org/fhir/stu3/datatypes.html#coding) | Code defined by a terminology system |
|  - - - -  system | 0..1 | Mandatory | [Uri](http://hl7.org/fhir/stu3/datatypes.html#uri) | Identity of the terminology system |
|  - - - - code | 0..1 | Mandatory | [Code](http://hl7.org/fhir/stu3/datatypes.html#code) | Symbol in syntax defined by the system |
|  - - - - display | 0..1 | Mandatory | [String](http://hl7.org/fhir/stu3/datatypes.html#string) | Representation defined by the system |
|  - - - text | 0..1 | Optional | [String](http://hl7.org/fhir/stu3/datatypes.html#string) | Plain text representation of the concept |