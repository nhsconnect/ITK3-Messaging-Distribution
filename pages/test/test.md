---
title: Test Overview
keywords: test
tags: [overview]
sidebar: foundations_sidebar
permalink: test.html
summary: "These pages assist with requirements gathering and mapping stages of an ITK3 Messaging Solution development process."
---

## Overview ##


|   | [**Procedure - Profiled using CareConnect-NHSD-Procedure-1**](https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-NHSD-Procedure-1) |  |  |  |  |
|  :------ | :------ | ------ | ------ | ------ | ------ |
|   | **Name** | **Card.** | **Conformance** | **Type** | **Description/Constraints For This Implemenation** |
|  > | Procedure | ​ |  |  | An action that is being or was performed on a patient<br/>Constraint (dom-2): If the resource is contained in another resource, it SHALL NOT contain nested Resources<br/>Constraint (dom-1): If the resource is contained in another resource, it SHALL NOT contain any narrative<br/>Constraint (dom-4): If a resource is contained in another resource, it SHALL NOT have a meta.versionId or a meta.lastUpdated<br/>Constraint (dom-3): If the resource is contained in another resource, it SHALL be referred to from elsewhere in the resource<br/>Constraint (pro-1): Reason not done is only permitted if notDone indicator is true |
|  >> | Procedure.id | 0..1 | Not Used | [Id](http://hl7.org/fhir/stu3/datatypes.html#id) | Logical id of this artifact |
|  >> | meta | 0..1 | Mandatory | [Meta](http://hl7.org/fhir/stu3/resource.html#Meta) | Metadata about the resource |
|  >> | implicitRules | 0..1 | Not Used | [Uri](http://hl7.org/fhir/stu3/datatypes.html#uri) | A set of rules under which this content was created |
|  >> | language | 0..1 | Not Used | [Code](http://hl7.org/fhir/stu3/datatypes.html#code) | [Language of the resource content Binding (extensible): A human language. (http://hl7.org/fhir/stu3/valueset-languages.html)](http://hl7.org/fhir/stu3/valueset-languages.html) |
|  >> | text | 0..1 | Not Used | [Narrative](http://hl7.org/fhir/stu3/narrative.html#Narrative) | Text summary of the resource, for human interpretation |
|   | contained | 0..* | Not Used | [Resource](http://hl7.org/fhir/stu3/resource.html) | Contained, inline Resources |
|  >> | extension (anaestheticIssues) | 0..1 | Required | [Extension](http://hl7.org/fhir/stu3/extensibility.html#Extension) | [Details of any adverse reaction to any anaesthetic agents. Constraint (ext-1): Must have either extensions or value[x], not both URL: https://fhir.hl7.org.uk/STU3/StructureDefinition/Extension-CareConnect-AnaestheticIssues-1](https://fhir.hl7.org.uk/STU3/StructureDefinition/Extension-CareConnect-AnaestheticIssues-1) |
|  >> | modifierExtension | 0..* | Not Used | [Extension](http://hl7.org/fhir/stu3/extensibility.html#Extension) | Extensions that cannot be ignored<br/>Constraint (ext-1): Must have either extensions or value[x], not both<br/>Slicing: Description: Extensions are always sliced by (at least) url, Discriminator: url, Ordering: false, Rules: Open |
|  >>> | identifier | 0..* | Mandatory | [Identifier](http://hl7.org/fhir/stu3/datatypes.html#identifier) | External Identifiers for this procedure |
|  >>>> | use | 0..1 | Optional | [Code](http://hl7.org/fhir/stu3/datatypes.html#code) | [usual : official  : temp : secondary (If known).Binding (required): Identifies the purpose for this identifier, if known .(http://hl7.org/fhir/stu3/valueset-identifier-use.html )](http://hl7.org/fhir/stu3/valueset-identifier-use.html) |
|  >>>> | type | 0..1 | Optional | [CodeableConcept](http://hl7.org/fhir/stu3/datatypes.html#codeableconcept) | Description of identifier<br/>Binding (extensible): A coded type for an identifier that can be used to determine which identifier to use for a specific purpose. ( http://hl7.org/fhir/stu3/valueset-identifier-type.html ) |
|  >>>>> | coding | 0..* | Optional | [Coding](http://hl7.org/fhir/stu3/datatypes.html#coding) | Code defined by a terminology system |
|  >>>>> | system | 0..1 | Optional | [Uri](http://hl7.org/fhir/stu3/datatypes.html#uri) | Identity of the terminology system |
|  >>>>> | version | 0..1 | Optional | [String](http://hl7.org/fhir/stu3/datatypes.html#string) | Version of the system - if relevant |
|  >>>>> | code | 0..1 | Optional | [Code](http://hl7.org/fhir/stu3/datatypes.html#code) | Symbol in syntax defined by the system |
|  >>>>> | display | 0..1 | Optional | [String](http://hl7.org/fhir/stu3/datatypes.html#string) | Representation defined by the system |
|  >>>>> | userSelected | 0..1 | Not Used | [Boolean](http://hl7.org/fhir/stu3/datatypes.html#boolean) | If this coding was chosen directly by the user |
|  >>>> | text | 0..1 | Not Used | [String](http://hl7.org/fhir/stu3/datatypes.html#string) | Plain text representation of the concept |
|  >>> | system | 1..1 | Not Used | [Uri](http://hl7.org/fhir/stu3/datatypes.html#uri) | The namespace for the identifier value |
|  >>> | value | 1..1 | Optional | [String](http://hl7.org/fhir/stu3/datatypes.html#string) | The value that is unique |
|  >>> | period | 0..1 | Optional | [Period](http://hl7.org/fhir/stu3/datatypes.html#period) | Time period when id is/was valid for use<br/>Constraint (per-1): If present, start SHALL have a lower value than end |
|  >>>> | start | 0..1 | Not Used | [dateTime](http://hl7.org/fhir/stu3/datatypes.html#datetime) | Starting time with inclusive boundary |
|  >>>> | end | 0..1 | Not Used | [dateTime](http://hl7.org/fhir/stu3/datatypes.html#datetime) | End time with inclusive boundary, if not ongoing |
|  >>> | assigner | 0..1 | Required | [Reference ( CareConnect-Organization-1 )](https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-Organization-1) | Organization that issued id (may be just text)<br/>Constraint (ref-1): SHALL have a contained resource if a local reference is provided |
|  >>>> | reference | 0..1 | Not Used | [String](http://hl7.org/fhir/stu3/datatypes.html#string) | Literal reference, Relative, internal or absolute URL |
|  >>>> | identifier | 0..1 | Mandatory | [Identifier](http://hl7.org/fhir/stu3/datatypes.html#identifier) | Logical reference, when literal reference is not known |
|  >>>> | display | 0..1 | Optional | [String](http://hl7.org/fhir/stu3/datatypes.html#string) | Text alternative for the resource |
|  >>> | definition | 0..* | Optional | Reference | Instantiates protocol or definition. Constraint (ref-1): SHALL have a contained resource if a local reference is provided |
|   |  |  | Not Used | [PlanDefinition](http://hl7.org/fhir/stu3/plandefinition.html) |  |
|   |  |  | Not Used | [ActivityDefinition](http://hl7.org/fhir/stu3/activitydefinition.html) |  |
|   |  |  | Required | [CareConnect-NHSD-HealthcareService-1](https://fhir.nhs.uk/STU3/StructureDefinition/DCH-HealthcareService-1) |  |
|  >>>> | reference | 0..1 | Mandatory | [String](http://hl7.org/fhir/stu3/datatypes.html#string) | Literal reference, Relative, internal or absolute URL |
|  >>>> | identifier | 0..1 | Not Used | [Identifier](http://hl7.org/fhir/stu3/datatypes.html#identifier) | Logical reference, when literal reference is not known |
|  >>>> | display | 0..1 | Not Used | [String](http://hl7.org/fhir/stu3/datatypes.html#string) | Text alternative for the resource |
|  >>> | basedOn | 0..* | Not Used | Reference | A request for this procedure<br/>Constraint (ref-1): SHALL have a contained resource if a local reference is provided |
|   |  |  | Not Used | [CarePlan](https://www.hl7.org/fhir/stu3/careplan.html) |  |
|   |  |  | Not Used | [ProcedureRequest](https://www.hl7.org/fhir/stu3/procedurerequest.html) |  |
|   |  |  | Not Used | [ReferralRequest](https://www.hl7.org/fhir/stu3/referralrequest.html) |  |
|   | reference | 0..1 | Not Used | [String](http://hl7.org/fhir/stu3/datatypes.html#string) | Literal reference, Relative, internal or absolute URL |
|   | identifier | 0..1 | Not Used | [Identifier](http://hl7.org/fhir/stu3/datatypes.html#identifier) | Logical reference, when literal reference is not known |
|   | display | 0..1 | Not Used | [String](http://hl7.org/fhir/stu3/datatypes.html#string) | Text alternative for the resource |
|   | partOf | 0..* | Required | [Reference](http://hl7.org/fhir/stu3/references.html) | Part of referenced event<br/>Constraint (ref-1): SHALL have a contained resource if a local reference is provided |
|   |  |  | Not Used | [MedicationAdministration](http://hl7.org/fhir/stu3/medicationadministration.html) |  |
|   |  |  | Required | [CareConnect-Procedure-1](https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-Procedure-1) |  |
|   |  |  | Required | [CareConnect-Observation-1](https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-Observation-1) |  |
|   | reference | 0..1 | Mandatory | [String](http://hl7.org/fhir/stu3/datatypes.html#string) | Literal reference, Relative, internal or absolute URL |
|   | identifier | 0..1 | Not Used | [Identifier](http://hl7.org/fhir/stu3/datatypes.html#identifier) | Logical reference, when literal reference is not known |
|   | display | 0..1 | Not Used | [String](http://hl7.org/fhir/stu3/datatypes.html#string) | Text alternative for the resource |
|   | status | 1..1 | Mandatory | [Code](http://hl7.org/fhir/stu3/datatypes.html#code) | preparation : in-progress : suspended : aborted : completed : entered-in-error : unknown. Binding (required): A code specifying the state of the procedure. ( http://hl7.org/fhir/stu3/valueset-event-status.html ) |
|   | notDone | 0..1 | Optional | [Boolean](http://hl7.org/fhir/stu3/datatypes.html#boolean) | True if procedure was not performed as scheduled<br/>Default Value: false |
|   | notDoneReason | 0..1 | Optional | [CodeableConcept](http://hl7.org/fhir/stu3/datatypes.html#codeableconcept) | Reason procedure was not performed. Binding (example): A code that identifies the reason a procedure was not performed. (http://hl7.org/fhir/stu3/valueset-procedure-not-performed-reason.html ) |
|   | coding | 0..* | Optional | [Coding](http://hl7.org/fhir/stu3/datatypes.html#coding) | Code defined by a terminology system |
|   | system | 0..1 | Optional | [Uri](http://hl7.org/fhir/stu3/datatypes.html#uri) | Identity of the terminology system |
|   | version | 0..1 | Optional | [String](http://hl7.org/fhir/stu3/datatypes.html#string) | Version of the system - if relevant |
|   | code | 0..1 | Optional | [Code](http://hl7.org/fhir/stu3/datatypes.html#code) | Symbol in syntax defined by the system |
|   | display | 0..1 | Optional | [String](http://hl7.org/fhir/stu3/datatypes.html#string) | Representation defined by the system |
|   | userSelected | 0..1 | Optional | [Boolean](http://hl7.org/fhir/stu3/datatypes.html#boolean) | If this coding was chosen directly by the user |
|   | text | 0..1 | Optional | [String](http://hl7.org/fhir/stu3/datatypes.html#string) | Plain text representation of the concept |
|   | category | 0..1 | Optional | [CodeableConcept](http://hl7.org/fhir/stu3/datatypes.html#codeableconcept) | Classification of the procedure<br/>Binding (example): A code that classifies a procedure for searching, sorting and display purposes. (http://hl7.org/fhir/stu3/valueset-procedure-category.html ) |
|   | coding | 0..* | Mandatory | [Coding](http://hl7.org/fhir/stu3/datatypes.html#coding) | Code defined by a terminology system |
|   | system | 0..1 | Mandatory | [Uri](http://hl7.org/fhir/stu3/datatypes.html#uri) | Identity of the terminology system |
|   | version | 0..1 | Not Used | [String](http://hl7.org/fhir/stu3/datatypes.html#string) | Version of the system - if relevant |
|   | code | 0..1 | Mandatory | [Code](http://hl7.org/fhir/stu3/datatypes.html#code) | Symbol in syntax defined by the system |
|   | display | 0..1 | Mandatory | [String](http://hl7.org/fhir/stu3/datatypes.html#string) | Representation defined by the system |
|   | userSelected | 0..1 | Not Used | [Boolean](http://hl7.org/fhir/stu3/datatypes.html#boolean) | If this coding was chosen directly by the user |
|   | text | 0..1 | Optional | [String](http://hl7.org/fhir/stu3/datatypes.html#string) | Plain text representation of the concept |
|   | code | 0..1 | Mandatory | [CodeableConcept](http://hl7.org/fhir/stu3/datatypes.html#codeableconcept) | [Identification of the procedure. Binding (preferred): A code to identify a specific procedure. ( http://hl7.org/fhir/stu3/valueset-procedure-code.html )](https://www.hl7.org/fhir/stu3/procedure.html) |
|   | coding | 0..* | Mandatory | [Coding](http://hl7.org/fhir/stu3/datatypes.html#coding) | Code defined by a terminology system<br/>Slicing: Discriminator: system, Ordering: false, Rules: Open |
|   | coding (snomedCT) | 0..1 | Mandatory | [Coding](http://hl7.org/fhir/stu3/datatypes.html#coding) | Code defined by a terminology system. Binding (extensible): A code from the SNOMED Clinical Terminology UK. (https://fhir.hl7.org.uk/STU3/ValueSet/CareConnect-ProcedureCode-1 ) |
|   | extension (snomedCTDescriptionID) | 0..1 | Optional | [Extension](http://hl7.org/fhir/stu3/extensibility.html#Extension) | The SNOMED CT Description ID for the display. Constraint (ext-1): Must have either extensions or value[x], not both. URL: https://fhir.hl7.org.uk/STU3/StructureDefinition/Extension-coding-sctdescid |
|   | system | 1..1 | Mandatory | [Uri](http://hl7.org/fhir/stu3/datatypes.html#uri) | Identity of the terminology system. Fixed Value: http://snomed.info/sct |
|   | code | 1..1 | Mandatory | [Code](http://hl7.org/fhir/stu3/datatypes.html#code) | Symbol in syntax defined by the system |
|   | display | 1..1 | Mandatory | [String](http://hl7.org/fhir/stu3/datatypes.html#string) | Representation defined by the system |
|   | userSelected | 0..1 | Not Used | [Boolean](http://hl7.org/fhir/stu3/datatypes.html#boolean) | If this coding was chosen directly by the user |
|   | text | 0..1 | Optional | [String](http://hl7.org/fhir/stu3/datatypes.html#string) | Plain text representation of the concept |
|   | subject | 1..1 | Mandatory | Reference | Who the procedure was performed on<br/>Constraint (ref-1): SHALL have a contained resource if a local reference is provided |
|   |  |  | Not Used | [Group](http://hl7.org/fhir/stu3/group.html) |  |
|   |  |  | Mandatory | [CareConnect-Patient-1](https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-Patient-1) |  |
|   | reference | 0..1 | Mandatory | [String](http://hl7.org/fhir/stu3/datatypes.html#string) | Literal reference, Relative, internal or absolute URL |
|   | identifier | 0..1 | Not Used | [Identifier](http://hl7.org/fhir/stu3/datatypes.html#identifier) | Logical reference, when literal reference is not known |
|   | display | 0..1 | Not Used | [String](http://hl7.org/fhir/stu3/datatypes.html#string) | Text alternative for the resource |
|   | context | 0..1 | Mandatory | Reference | Encounter or episode associated with the procedure<br/>Constraint (ref-1): SHALL have a contained resource if a local reference is provided |
|   |  |  | Not Used | [EpisodeOfCare](http://hl7.org/fhir/stu3/episodeofcare.html) |  |
|   |  |  | Mandatory | [CareConnect-Encounter-1](https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-Encounter-1) |  |
|   | reference | 0..1 | Mandatory | [String](http://hl7.org/fhir/stu3/datatypes.html#string) | Literal reference, Relative, internal or absolute URL |
|   | identifier | 0..1 | Not Used | [Identifier](http://hl7.org/fhir/stu3/datatypes.html#identifier) | Logical reference, when literal reference is not known |
|   | display | 0..1 | Not Used | [String](http://hl7.org/fhir/stu3/datatypes.html#string) | Text alternative for the resource |
|   | performed[x] | 0..1 | Required | [dateTime](http://hl7.org/fhir/stu3/datatypes.html#dateTime) | Date the procedure was performed |
|   |  |  | Required | [Period](http://hl7.org/fhir/stu3/datatypes.html#Period) | The Period the procedure was performed |
|   | performer | 0..* | Required | [BackboneElement](http://hl7.org/fhir/stu3/backboneelement.html) | The people who performed the procedure |
|   | modifierExtension | 0..* | Not Used | [Extension](http://hl7.org/fhir/stu3/extensibility.html#Extension) | Extensions that cannot be ignored<br/>Constraint (ext-1): Must have either extensions or value[x], not both |
|   | role | 0..1 | Required | [CodeableConcept](http://hl7.org/fhir/stu3/datatypes.html#codeableconcept) | The role the actor was in. Binding (example): A code that identifies the role of a performer of the procedure. (http://hl7.org/fhir/stu3/valueset-performer-role.html ) |
|   | coding | 0..* | Mandatory | [Coding](http://hl7.org/fhir/stu3/datatypes.html#coding) | Code defined by a terminology system |
|   | system | 0..1 | Mandatory | [Uri](http://hl7.org/fhir/stu3/datatypes.html#uri) | Identity of the terminology system |
|   | version | 0..1 | Not Used | [String](http://hl7.org/fhir/stu3/datatypes.html#string) | Version of the system - if relevant |
|   | code | 0..1 | Mandatory | [Code](http://hl7.org/fhir/stu3/datatypes.html#code) | Symbol in syntax defined by the system |
|   | display | 0..1 | Mandatory | [String](http://hl7.org/fhir/stu3/datatypes.html#string) | Representation defined by the system |
|   | userSelected | 0..1 | Not Used | [Boolean](http://hl7.org/fhir/stu3/datatypes.html#boolean) | If this coding was chosen directly by the user |
|   | text | 0..1 | Optional | [String](http://hl7.org/fhir/stu3/datatypes.html#string) | Plain text representation of the concept |
|   | actor | 1..1 | Mandatory | Reference | The reference to the practitioner<br/>Constraint (ref-1): SHALL have a contained resource if a local reference is provided |
|   |  |  | Not Used | [RelatedPerson](http://hl7.org/fhir/stu3/relatedperson.html) |  |
|   |  |  | Not Used | [Device](http://hl7.org/fhir/stu3/device.html) |  |
|   |  |  | Not Used | [CareConnect-Organization-1](https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-Organization-1) |  |
|   |  |  | Not Used | CareConnect-Patient-1 |  |
|   |  |  | Mandatory | [CareConnect-Practitioner-1](https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-Practitioner-1) |  |
|   | reference | 0..1 | Mandatory | [String](http://hl7.org/fhir/stu3/datatypes.html#string) | Literal reference, Relative, internal or absolute URL |
|   | identifier | 0..1 | Not Used | [Identifier](http://hl7.org/fhir/stu3/datatypes.html#identifier) | Logical reference, when literal reference is not known |
|   | display | 0..1 | Not Used | [String](http://hl7.org/fhir/stu3/datatypes.html#string) | Text alternative for the resource |
|   | onBehalfOf | 0..1 | Required | [Reference ( CareConnect-Organization-1 )](https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-Organization-1) | Organization the device or practitioner was acting for<br/>Constraint (ref-1): SHALL have a contained resource if a local reference is provided |
|   | reference | 0..1 | Mandatory | [String](http://hl7.org/fhir/stu3/datatypes.html#string) | Literal reference, Relative, internal or absolute URL |
|   | identifier | 0..1 | Not Used | [Identifier](http://hl7.org/fhir/stu3/datatypes.html#identifier) | Logical reference, when literal reference is not known |
|   | display | 0..1 | Not Used | [String](http://hl7.org/fhir/stu3/datatypes.html#string) | Text alternative for the resource |
|   | location | 0..1 | Required | [Reference ( CareConnect-Location-1 )](https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-Location-1) | Where the procedure happened<br/>Constraint (ref-1): SHALL have a contained resource if a local reference is provided |
|   | reference | 0..1 | Mandatory | [String](http://hl7.org/fhir/stu3/datatypes.html#string) | Literal reference, Relative, internal or absolute URL |
|   | identifier | 0..1 | Not Used | [Identifier](http://hl7.org/fhir/stu3/datatypes.html#identifier) | Logical reference, when literal reference is not known |
|   | display | 0..1 | Not Used | [String](http://hl7.org/fhir/stu3/datatypes.html#string) | Text alternative for the resource |
|   | reasonCode | 0..* | Optional | [CodeableConcept](http://hl7.org/fhir/stu3/datatypes.html#codeableconcept) | Coded reason procedure performed. Binding (example): A code that identifies the reason a procedure is required. (http://hl7.org/fhir/stu3/valueset-procedure-reason.html ) |
|   | coding | 0..* | Mandatory | [Coding](http://hl7.org/fhir/stu3/datatypes.html#coding) | Code defined by a terminology system |
|   | system | 0..1 | Mandatory | [Uri](http://hl7.org/fhir/stu3/datatypes.html#uri) | Identity of the terminology system |
|   | version | 0..1 | Not Used | [String](http://hl7.org/fhir/stu3/datatypes.html#string) | Version of the system - if relevant |
|   | code | 0..1 | Mandatory | [Code](http://hl7.org/fhir/stu3/datatypes.html#code) | Symbol in syntax defined by the system |
|   | display | 0..1 | Mandatory | [String](http://hl7.org/fhir/stu3/datatypes.html#string) | Representation defined by the system |
|   | userSelected | 0..1 | Not Used | [Boolean](http://hl7.org/fhir/stu3/datatypes.html#boolean) | If this coding was chosen directly by the user |
|   | text | 0..1 | Optional | [String](http://hl7.org/fhir/stu3/datatypes.html#string) | Plain text representation of the concept |
|   | reasonReference | 0..* | Required | [Reference](http://hl7.org/fhir/stu3/references.html) | Condition that is the reason the procedure performed<br/>Constraint (ref-1): SHALL have a contained resource if a local reference is provided |
|   |  |  | Optional | [CareConnect-Observation-1](https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-Observation-1) |  |
|   |  |  | Optional | [CareConnect-Condition-1](https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-Condition-1) |  |
|   | reference | 0..1 | Mandatory | [String](http://hl7.org/fhir/stu3/datatypes.html#string) | Literal reference, Relative, internal or absolute URL |
|   | identifier | 0..1 | Not Used | [Identifier](http://hl7.org/fhir/stu3/datatypes.html#identifier) | Logical reference, when literal reference is not known |
|   | display | 0..1 | Not Used | [String](http://hl7.org/fhir/stu3/datatypes.html#string) | Text alternative for the resource |
|   | bodySite | 0..* | Required | [CodeableConcept](http://hl7.org/fhir/stu3/datatypes.html#codeableconcept) | [Target body sites. Binding (example): Codes describing anatomical locations. May include laterality. (http://hl7.org/fhir/stu3/valueset-body-site.html )](http://hl7.org/fhir/stu3/valueset-body-site.html) |
|   | coding | 0..* | Mandatory | [Coding](http://hl7.org/fhir/stu3/datatypes.html#coding) | Code defined by a terminology system<br/>Slicing: Discriminator: system, Ordering: false, Rules: Open |
|   | coding (snomedCT) | 0..1 | Mandatory | [Coding](http://hl7.org/fhir/stu3/datatypes.html#coding) | Code defined by a terminology system. Binding (extensible): A code from the SNOMED Clinical Terminology UK. (https://fhir.hl7.org.uk/STU3/ValueSet/CareConnect-BodySite-1 ) |
|   | extension (snomedCTDescriptionID) | 0..1 | Optional | [Extension](http://hl7.org/fhir/stu3/extensibility.html#Extension) | [The SNOMED CT Description ID for the display. Constraint (ext-1): Must have either extensions or value[x], not both. URL: https://fhir.hl7.org.uk/STU3/StructureDefinition/Extension-coding-sctdescid](https://fhir.hl7.org.uk/STU3/StructureDefinition/Extension-coding-sctdescid) |
|   | system | 1..1 | Mandatory | [Uri](http://hl7.org/fhir/stu3/datatypes.html#uri) | Identity of the terminology system<br/>Fixed Value: http://snomed.info/sct |
|   | code | 1..1 | Mandatory | [Code](http://hl7.org/fhir/stu3/datatypes.html#code) | Symbol in syntax defined by the system |
|   | display | 1..1 | Mandatory | [String](http://hl7.org/fhir/stu3/datatypes.html#string) | Representation defined by the system |
|   | userSelected | 0..1 | Not Used | [Boolean](http://hl7.org/fhir/stu3/datatypes.html#boolean) | If this coding was chosen directly by the user |
|   | text | 0..1 | Optional | [String](http://hl7.org/fhir/stu3/datatypes.html#string) | Plain text representation of the concept |
|   | outcome | 0..1 | Required | [CodeableConcept](http://hl7.org/fhir/stu3/datatypes.html#codeableconcept) | [The result of procedure. Binding (example): An outcome of a procedure - whether it was resolved or otherwise. (http://hl7.org/fhir/stu3/valueset-procedure-outcome.html )](http://hl7.org/fhir/stu3/valueset-procedure-outcome.html) |
|   | coding | 0..* | Mandatory | [Coding](http://hl7.org/fhir/stu3/datatypes.html#coding) | Code defined by a terminology system |
|   | system | 0..1 | Mandatory | [Uri](http://hl7.org/fhir/stu3/datatypes.html#uri) | Identity of the terminology system |
|   | version | 0..1 | Not Used | [String](http://hl7.org/fhir/stu3/datatypes.html#string) | Version of the system - if relevant |
|   | code | 0..1 | Mandatory | [Code](http://hl7.org/fhir/stu3/datatypes.html#code) | Symbol in syntax defined by the system |
|   | display | 0..1 | Mandatory | [String](http://hl7.org/fhir/stu3/datatypes.html#string) | Representation defined by the system |
|   | userSelected | 0..1 | Not Used | [Boolean](http://hl7.org/fhir/stu3/datatypes.html#boolean) | If this coding was chosen directly by the user |
|   | text | 0..1 | Optional | [String](http://hl7.org/fhir/stu3/datatypes.html#string) | Plain text representation of the concept |
|   | report | 0..* | Required | [Reference ( DiagnosticReport)](http://hl7.org/fhir/stu3/diagnosticreport.html) | Any report resulting from the procedure<br/>Constraint (ref-1): SHALL have a contained resource if a local reference is provided |
|   | reference | 0..1 | Mandatory | [String](http://hl7.org/fhir/stu3/datatypes.html#string) | Literal reference, Relative, internal or absolute URL |
|   | identifier | 0..1 | Not Used | [Identifier](http://hl7.org/fhir/stu3/datatypes.html#identifier) | Logical reference, when literal reference is not known |
|   | display | 0..1 | Not Used | [String](http://hl7.org/fhir/stu3/datatypes.html#string) | Text alternative for the resource |
|   | complication | 0..* | Required | [CodeableConcept](http://hl7.org/fhir/stu3/datatypes.html#codeableconcept) | [Complication following the procedure. Binding (example): Codes describing complications that resulted from a procedure. (http://hl7.org/fhir/stu3/valueset-condition-code.html )](http://hl7.org/fhir/stu3/valueset-condition-code.html) |
|   | coding | 0..* | Mandatory | [Coding](http://hl7.org/fhir/stu3/datatypes.html#coding) | Code defined by a terminology system<br/>Slicing: Discriminator: system, Ordering: false, Rules: Open |
|   | coding (snomedCT) | 0..1 | Mandatory | [Coding](http://hl7.org/fhir/stu3/datatypes.html#coding) | [Code defined by a terminology system. Binding (required): A code from the SNOMED Clinical Terminology UK. (https://fhir.hl7.org.uk/STU3/ValueSet/CareConnect-ConditionCode-1 )](https://fhir.hl7.org.uk/STU3/ValueSet/CareConnect-ConditionCode-1) |
|   | extension (snomedCTDescriptionID) | 0..1 | Not Used | [Extension](http://hl7.org/fhir/stu3/extensibility.html#Extension) | [The SNOMED CT Description ID for the display. Constraint (ext-1): Must have either extensions or value[x], not both. URL: https://fhir.hl7.org.uk/STU3/StructureDefinition/Extension-coding-sctdescid](https://fhir.hl7.org.uk/STU3/StructureDefinition/Extension-coding-sctdescid) |
|   | system | 1..1 | Mandatory | [Uri](http://hl7.org/fhir/stu3/datatypes.html#uri) | Identity of the terminology system<br/>Fixed Value: http://snomed.info/sct |
|   | code | 1..1 | Mandatory | [Code](http://hl7.org/fhir/stu3/datatypes.html#code) | Symbol in syntax defined by the system |
|   | display | 1..1 | Mandatory | [String](http://hl7.org/fhir/stu3/datatypes.html#string) | Representation defined by the system |
|   | userSelected | 0..1 | Not Used | [Boolean](http://hl7.org/fhir/stu3/datatypes.html#boolean) | If this coding was chosen directly by the user |
|   | text | 0..1 | Optional | [String](http://hl7.org/fhir/stu3/datatypes.html#string) | Plain text representation of the concept |
|   | complicationDetail | 0..* | Optional | [Reference ( CareConnect-Condition-1 )](https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-Condition-1) | A condition that is a result of the procedure<br/>Constraint (ref-1): SHALL have a contained resource if a local reference is provided |
|   | reference | 0..1 | Mandatory | [String](http://hl7.org/fhir/stu3/datatypes.html#string) | Literal reference, Relative, internal or absolute URL |
|   | identifier | 0..1 | Not Used | [Identifier](http://hl7.org/fhir/stu3/datatypes.html#identifier) | Logical reference, when literal reference is not known |
|   | display | 0..1 | Not Used | [String](http://hl7.org/fhir/stu3/datatypes.html#string) | Text alternative for the resource |
|   | followUp | 0..* | Required | [CodeableConcept](http://hl7.org/fhir/stu3/datatypes.html#codeableconcept) | [Instructions for follow up. Binding (example): Specific follow up required for a procedure e.g. removal of sutures. (http://hl7.org/fhir/stu3/valueset-procedure-followup.html )](http://hl7.org/fhir/stu3/valueset-procedure-followup.html) |
|   | coding | 0..* | Mandatory | [Coding](http://hl7.org/fhir/stu3/datatypes.html#coding) | Code defined by a terminology system |
|   | system | 0..1 | Mandatory | [Uri](http://hl7.org/fhir/stu3/datatypes.html#uri) | Identity of the terminology system |
|   | version | 0..1 | Not Used | [String](http://hl7.org/fhir/stu3/datatypes.html#string) | Version of the system - if relevant |
|   | code | 0..1 | Mandatory | [Code](http://hl7.org/fhir/stu3/datatypes.html#code) | Symbol in syntax defined by the system |
|   | display | 0..1 | Mandatory | [String](http://hl7.org/fhir/stu3/datatypes.html#string) | Representation defined by the system |
|   | userSelected | 0..1 | Not Used | [Boolean](http://hl7.org/fhir/stu3/datatypes.html#boolean) | If this coding was chosen directly by the user |
|   | text | 0..1 | Optional | [String](http://hl7.org/fhir/stu3/datatypes.html#string) | Plain text representation of the concept |
|   | note | 0..* | Optional | [Annotation](http://hl7.org/fhir/stu3/datatypes.html#annotation) | Additional information about the procedure |
|   | author[x] | 0..1 | Required | [Reference](http://hl7.org/fhir/stu3/references.html) | Individual responsible for the annotation<br/>Constraint (ref-1): SHALL have a contained resource if a local reference is provided |
|   |  |  | Not Used | [RelatedPerson](http://hl7.org/fhir/stu3/relatedperson.html) |  |
|   |  |  | Not Used | [CareConnect-Patient-1](https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-Patient-1) |  |
|   |  |  | Mandatory | [CareConnect-Practitioner-1](https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-Practitioner-1) |  |
|   |  |  | Not Used | [String](http://hl7.org/fhir/stu3/datatypes.html#string) |  |
|   | time | 0..1 | Optional | [dateTime](http://hl7.org/fhir/stu3/datatypes.html#datetime) | When the annotation was made |
|   | text | 1..1 | Mandatory | [String](http://hl7.org/fhir/stu3/datatypes.html#string) | The annotation - text content |
|   | focalDevice | 0..* | Optional | [BackboneElement](http://hl7.org/fhir/stu3/backboneelement.html) | Device changed in procedure |
|   | modifierExtension | 0..* | Not Used | [Extension](http://hl7.org/fhir/stu3/extensibility.html#Extension) | Extensions that cannot be ignored<br/>Constraint (ext-1): Must have either extensions or value[x], not both |
|   | action | 0..1 | Not Used | [CodeableConcept](http://hl7.org/fhir/stu3/datatypes.html#codeableconcept) | [Kind of change to device. Binding (preferred): A kind of change that happened to the device during the procedure. (http://hl7.org/fhir/stu3/valueset-device-action.html )](http://hl7.org/fhir/stu3/valueset-device-action.html) |
|   | coding | 0..* | Not Used | [Coding](http://hl7.org/fhir/stu3/datatypes.html#coding) | Code defined by a terminology system |
|   | system | 0..1 | Not Used | [Uri](http://hl7.org/fhir/stu3/datatypes.html#uri) | Identity of the terminology system |
|   | version | 0..1 | Not Used | [String](http://hl7.org/fhir/stu3/datatypes.html#string) | Version of the system - if relevant |
|   | code | 0..1 | Not Used | [Code](http://hl7.org/fhir/stu3/datatypes.html#code) | Symbol in syntax defined by the system |
|   | display | 0..1 | Not Used | [String](http://hl7.org/fhir/stu3/datatypes.html#string) | Representation defined by the system |
|   | userSelected | 0..1 | Not Used | [Boolean](http://hl7.org/fhir/stu3/datatypes.html#boolean) | If this coding was chosen directly by the user |
|   | text | 0..1 | Not Used | [String](http://hl7.org/fhir/stu3/datatypes.html#string) | Plain text representation of the concept |
|   | manipulated | 1..1 | Not Used | [Reference ( Device )](http://hl7.org/fhir/stu3/device.html) | Device that was changed<br/>Constraint (ref-1): SHALL have a contained resource if a local reference is provided |
|   | reference | 0..1 | Not Used | [String](http://hl7.org/fhir/stu3/datatypes.html#string) | Literal reference, Relative, internal or absolute URL |
|   | identifier | 0..1 | Not Used | [Identifier](http://hl7.org/fhir/stu3/datatypes.html#identifier) | Logical reference, when literal reference is not known |
|   | display | 0..1 | Not Used | [String](http://hl7.org/fhir/stu3/datatypes.html#string) | Text alternative for the resource |
|   | usedReference | 0..* | Optional | Reference ( Device <code>&amp;#124;</code>Substance <code>&amp;#124;</code> CareConnect-Medication-1 ) | Items used during procedure<br/>Constraint (ref-1): SHALL have a contained resource if a local reference is provided |
|   |  |  | Optional | [Device](http://hl7.org/fhir/stu3/device.html) |  |
|   |  |  | Optional | [Substance](http://hl7.org/fhir/stu3/substance.html) |  |
|   |  |  | Optional | [CareConnect-Medication-1](https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-Medication-1) |  |
|   | reference | 0..1 | Mandatory | [String](http://hl7.org/fhir/stu3/datatypes.html#string) | Literal reference, Relative, internal or absolute URL |
|   | identifier | 0..1 | Not Used | [Identifier](http://hl7.org/fhir/stu3/datatypes.html#identifier) | Logical reference, when literal reference is not known |
|   | display | 0..1 | Not Used | [String](http://hl7.org/fhir/stu3/datatypes.html#string) | Text alternative for the resource |
|   | usedCode | 0..* | Required | [CodeableConcept](http://hl7.org/fhir/stu3/datatypes.html#codeableconcept) | [Coded items used during the procedure. Binding (example): Codes describing items used during a procedure ( http://hl7.org/fhir/stu3/valueset-device-kind.html )](http://hl7.org/fhir/stu3/valueset-device-kind.html) |
|   | coding | 0..* | Mandatory | [Coding](http://hl7.org/fhir/stu3/datatypes.html#coding) | Code defined by a terminology system |
|   | system | 0..1 | Mandatory | [Uri](http://hl7.org/fhir/stu3/datatypes.html#uri) | Identity of the terminology system |
|   | version | 0..1 | Not Used | [String](http://hl7.org/fhir/stu3/datatypes.html#string) | Version of the system - if relevant |
|   | code | 0..1 | Mandatory | [Code](http://hl7.org/fhir/stu3/datatypes.html#code) | Symbol in syntax defined by the system |
|   | display | 0..1 | Mandatory | [String](http://hl7.org/fhir/stu3/datatypes.html#string) | Representation defined by the system |
|   | userSelected | 0..1 | Not Used | [Boolean](http://hl7.org/fhir/stu3/datatypes.html#boolean) | If this coding was chosen directly by the user |
|   | text | 0..1 | Optional | [String](http://hl7.org/fhir/stu3/datatypes.html#string) | Plain text representation of the concept |