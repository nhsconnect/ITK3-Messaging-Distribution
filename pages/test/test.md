---
title: Test Overview
keywords: test
tags: [overview]
sidebar: foundations_sidebar
permalink: test.html
summary: "These pages assist with requirements gathering and mapping stages of an ITK3 Messaging Solution development process."
---

## Overview ##

|  [**Procedure - Profiled using CareConnect-NHSD-Procedure-1**](https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-NHSD-Procedure-1) |  |  |  |  |
|  :------ | ------ | ------ | :------ | ------ |
|  **Name** | **Card.** | **Conformance** | **Type** | **Description/Constraints For This Implemenation** |
|  [Procedure](https://fhir.hl7.org.uk/STU3/StructureDefinition/details.html#Procedure) | ​ |  |  | An action that is being or was performed on a patient<br/>Constraint (dom-2): If the resource is contained in another resource, it SHALL NOT contain nested Resources<br/>Constraint (dom-1): If the resource is contained in another resource, it SHALL NOT contain any narrative<br/>Constraint (dom-4): If a resource is contained in another resource, it SHALL NOT have a meta.versionId or a meta.lastUpdated<br/>Constraint (dom-3): If the resource is contained in another resource, it SHALL be referred to from elsewhere in the resource<br/>Constraint (pro-1): Reason not done is only permitted if notDone indicator is true |
|  [id](https://fhir.hl7.org.uk/STU3/StructureDefinition/details.html#Procedure.id) | 0..1 |  | [Id](http://hl7.org/fhir/stu3/datatypes.html#id) | Logical id of this artifact |
|  [meta](https://fhir.hl7.org.uk/STU3/StructureDefinition/details.html#Procedure.meta) | 0..1 |  | [Meta](http://hl7.org/fhir/stu3/resource.html#Meta) | Metadata about the resource |
|  [implicitRules](https://fhir.hl7.org.uk/STU3/StructureDefinition/details.html#Procedure.implicitRules) | 0..1 | Select | [Uri](http://hl7.org/fhir/stu3/datatypes.html#uri) | A set of rules under which this content was created |
|  [language](https://fhir.hl7.org.uk/STU3/StructureDefinition/details.html#Procedure.language) | 0..1 | Select | [Code](http://hl7.org/fhir/stu3/datatypes.html#code) | [Language of the resource content Binding (extensible): A human language. (http://hl7.org/fhir/stu3/valueset-languages.html)](http://hl7.org/fhir/stu3/valueset-languages.html) |
|  [text](https://fhir.hl7.org.uk/STU3/StructureDefinition/details.html#Procedure.text) | 0..1 | Select | [Narrative](http://hl7.org/fhir/stu3/narrative.html#Narrative) | Text summary of the resource, for human interpretation |
|  [contained](https://fhir.hl7.org.uk/STU3/StructureDefinition/details.html#Procedure.contained) | 0..* | Select | [Resource](http://hl7.org/fhir/stu3/resource.html) | Contained, inline Resources |
|  [extension (anaestheticIssues)](https://fhir.hl7.org.uk/STU3/StructureDefinition/details.html#Procedure.extension(anaestheticIssues)) | 0..1 | Select | [Extension](http://hl7.org/fhir/stu3/extensibility.html#Extension) | [Details of any adverse reaction to any anaesthetic agents. Constraint (ext-1): Must have either extensions or value[x], not both URL: https://fhir.hl7.org.uk/STU3/StructureDefinition/Extension-CareConnect-AnaestheticIssues-1](https://fhir.hl7.org.uk/STU3/StructureDefinition/Extension-CareConnect-AnaestheticIssues-1) |
|  [modifierExtension](https://fhir.hl7.org.uk/STU3/StructureDefinition/details.html#Procedure.modifierExtension) | 0..* | Select | [Extension](http://hl7.org/fhir/stu3/extensibility.html#Extension) | Extensions that cannot be ignored<br/>Constraint (ext-1): Must have either extensions or value[x], not both<br/>Slicing: Description: Extensions are always sliced by (at least) url, Discriminator: url, Ordering: false, Rules: Open |
|  identifier | 0..* | Select | [Identifier](http://hl7.org/fhir/stu3/datatypes.html#identifier) | External Identifiers for this procedure |
|  use | 0..1 | Select | [Code](http://hl7.org/fhir/stu3/datatypes.html#code) | [usual : official  : temp : secondary (If known).Binding (required): Identifies the purpose for this identifier, if known .(http://hl7.org/fhir/stu3/valueset-identifier-use.html )](http://hl7.org/fhir/stu3/valueset-identifier-use.html) |
|  type | 0..1 | Select | [CodeableConcept](http://hl7.org/fhir/stu3/datatypes.html#codeableconcept) | Description of identifier<br/>Binding (extensible): A coded type for an identifier that can be used to determine which identifier to use for a specific purpose. ( http://hl7.org/fhir/stu3/valueset-identifier-type.html ) |
|  coding | 0..* | Select | [Coding](http://hl7.org/fhir/stu3/datatypes.html#coding) | Code defined by a terminology system |
|  system | 0..1 | Select | [Uri](http://hl7.org/fhir/stu3/datatypes.html#uri) | Identity of the terminology system |
|  version | 0..1 | Select | [String](http://hl7.org/fhir/stu3/datatypes.html#string) | Version of the system - if relevant |
|  code | 0..1 | Select | [Code](http://hl7.org/fhir/stu3/datatypes.html#code) | Symbol in syntax defined by the system |
|  display | 0..1 | Select | [String](http://hl7.org/fhir/stu3/datatypes.html#string) | Representation defined by the system |
|  userSelected | 0..1 | Select | [Boolean](http://hl7.org/fhir/stu3/datatypes.html#boolean) | If this coding was chosen directly by the user |
|  text | 0..1 | Select | String | Plain text representation of the concept |
|  system | 1..1 | Select | Uri | The namespace for the identifier value |
|  value | 1..1 | Select | String | The value that is unique |
|  period | 0..1 | Select | Period | Time period when id is/was valid for use<br/>Constraint (per-1): If present, start SHALL have a lower value than end |
|  start | 0..1 | Select | dateTime | Starting time with inclusive boundary |
|  end | 0..1 | Select | dateTime | End time with inclusive boundary, if not ongoing |
|  assigner | 0..1 | Select | Reference ( CareConnect-Organization-1 ) | Organization that issued id (may be just text)<br/>Constraint (ref-1): SHALL have a contained resource if a local reference is provided |
|  reference | 0..1 | Select | String | Literal reference, Relative, internal or absolute URL |
|  identifier | 0..1 | Select | Identifier | Logical reference, when literal reference is not known |
|  display | 0..1 | Select | String | Text alternative for the resource |
|  definition | 0..* | Select | Reference ( PlanDefinition <code>&amp;#124;</code>ActivityDefinition <code>&amp;#124;</code>HealthcareService ) | Instantiates protocol or definition<br/>Constraint (ref-1): SHALL have a contained resource if a local reference is provided |
|  reference | 0..1 | Select | String | Literal reference, Relative, internal or absolute URL |
|  identifier | 0..1 | Select | Identifier | Logical reference, when literal reference is not known |
|  display | 0..1 | Select | String | Text alternative for the resource |
|  basedOn | 0..* | Select | Reference ( CarePlan <code>&amp;#124;</code>ProcedureRequest <code>&amp;#124;</code>ReferralRequest ) | A request for this procedure<br/>Constraint (ref-1): SHALL have a contained resource if a local reference is provided |
|  reference | 0..1 | Select | String | Literal reference, Relative, internal or absolute URL |
|  identifier | 0..1 | Select | Identifier | Logical reference, when literal reference is not known |
|  display | 0..1 | Select | String | Text alternative for the resource |
|  partOf | 0..* | Select | Reference (MedicationAdministration <code>&amp;#124;</code>CareConnect-Procedure-1 <code>&amp;#124;</code>CareConnect-Observation-1 ) | Part of referenced event<br/>Constraint (ref-1): SHALL have a contained resource if a local reference is provided |
|  reference | 0..1 | Select | String | Literal reference, Relative, internal or absolute URL |
|  identifier | 0..1 | Select | Identifier | Logical reference, when literal reference is not known |
|  display | 0..1 | Select | String | Text alternative for the resource |
|  status | 1..1 | Select | Code | preparation <code>&amp;#124;</code> in-progress <code>&amp;#124;</code> suspended <code>&amp;#124;</code> aborted <code>&amp;#124;</code> completed <code>&amp;#124;</code> entered-in-error <code>&amp;#124;</code> unknown<br/>Binding (required): A code specifying the state of the procedure. ( http://hl7.org/fhir/stu3/valueset-event-status.html ) |
|  notDone | 0..1 | Select | Boolean | True if procedure was not performed as scheduled<br/>Default Value: false |
|  notDoneReason | 0..1 | Select | CodeableConcept | Reason procedure was not performed<br/>Binding (example): A code that identifies the reason a procedure was not performed. (http://hl7.org/fhir/stu3/valueset-procedure-not-performed-reason.html ) |
|  coding | 0..* | Select | Coding | Code defined by a terminology system |
|  system | 0..1 | Select | Uri | Identity of the terminology system |
|  version | 0..1 | Select | String | Version of the system - if relevant |
|  code | 0..1 | Select | Code | Symbol in syntax defined by the system |
|  display | 0..1 | Select | String | Representation defined by the system |
|  userSelected | 0..1 | Select | Boolean | If this coding was chosen directly by the user |
|  text | 0..1 | Select | String | Plain text representation of the concept |
|  category | 0..1 | Select | CodeableConcept | Classification of the procedure<br/>Binding (example): A code that classifies a procedure for searching, sorting and display purposes. (http://hl7.org/fhir/stu3/valueset-procedure-category.html ) |
|  coding | 0..* | Select | Coding | Code defined by a terminology system |
|  system | 0..1 | Select | Uri | Identity of the terminology system |
|  version | 0..1 | Select | String | Version of the system - if relevant |
|  code | 0..1 | Select | Code | Symbol in syntax defined by the system |
|  display | 0..1 | Select | String | Representation defined by the system |
|  userSelected | 0..1 | Select | Boolean | If this coding was chosen directly by the user |
|  text | 0..1 | Select | String | Plain text representation of the concept |
|  code | 0..1 | Select | CodeableConcept | Identification of the procedure<br/>Binding (preferred): A code to identify a specific procedure. ( http://hl7.org/fhir/stu3/valueset-procedure-code.html ) |
|  coding | 0..* | Select | Coding | Code defined by a terminology system<br/>Slicing: Discriminator: system, Ordering: false, Rules: Open |
|  coding (snomedCT) | 0..1 | Select | Coding | Code defined by a terminology system<br/>Binding (extensible): A code from the SNOMED Clinical Terminology UK. (https://fhir.hl7.org.uk/STU3/ValueSet/CareConnect-ProcedureCode-1 ) |
|  extension (snomedCTDescriptionID) | 0..1 | Select | Extension | The SNOMED CT Description ID for the display<br/>Constraint (ext-1): Must have either extensions or value[x], not both<br/>URL: https://fhir.hl7.org.uk/STU3/StructureDefinition/Extension-coding-sctdescid |
|  system | 1..1 | Select | Uri | Identity of the terminology system<br/>Fixed Value: http://snomed.info/sct |
|  code | 1..1 | Select | Code | Symbol in syntax defined by the system |
|  display | 1..1 | Select | String | Representation defined by the system |
|  userSelected | 0..1 | Select | Boolean | If this coding was chosen directly by the user |
|  text | 0..1 | Select | String | Plain text representation of the concept |
|  subject | 1..1 | Select | Reference ( Group <code>&amp;#124;</code>CareConnect-Patient-1 ) | Who the procedure was performed on<br/>Constraint (ref-1): SHALL have a contained resource if a local reference is provided |
|  reference | 0..1 | Select | String | Literal reference, Relative, internal or absolute URL |
|  identifier | 0..1 | Select | Identifier | Logical reference, when literal reference is not known |
|  display | 0..1 | Select | String | Text alternative for the resource |
|  context | 0..1 | Select | Reference ( EpisodeOfCare <code>&amp;#124;</code>CareConnect-Encounter-1 ) | Encounter or episode associated with the procedure<br/>Constraint (ref-1): SHALL have a contained resource if a local reference is provided |
|  reference | 0..1 | Select | String | Literal reference, Relative, internal or absolute URL |
|  identifier | 0..1 | Select | Identifier | Logical reference, when literal reference is not known |
|  display | 0..1 | Select | String | Text alternative for the resource |
|  performed[x] | 0..1 | Select | dateTime <code>&amp;#124;</code> Period | Date/Period the procedure was performed |
|  performer | 0..* | Select | BackboneElement | The people who performed the procedure |
|  modifierExtension | 0..* | Select | Extension | Extensions that cannot be ignored<br/>Constraint (ext-1): Must have either extensions or value[x], not both |
|  role | 0..1 | Select | CodeableConcept | The role the actor was in<br/>Binding (example): A code that identifies the role of a performer of the procedure. (http://hl7.org/fhir/stu3/valueset-performer-role.html ) |
|  coding | 0..* | Select | Coding | Code defined by a terminology system |
|  system | 0..1 | Select | Uri | Identity of the terminology system |
|  version | 0..1 | Select | String | Version of the system - if relevant |
|  code | 0..1 | Select | Code | Symbol in syntax defined by the system |
|  display | 0..1 | Select | String | Representation defined by the system |
|  userSelected | 0..1 | Select | Boolean | If this coding was chosen directly by the user |
|  text | 0..1 | Select | String | Plain text representation of the concept |
|  actor | 1..1 | Select | Reference ( RelatedPerson <code>&amp;#124;</code>Device <code>&amp;#124;</code> CareConnect-Organization-1 <code>&amp;#124;</code> CareConnect-Patient-1 <code>&amp;#124;</code> CareConnect-Practitioner-1 ) | The reference to the practitioner<br/>Constraint (ref-1): SHALL have a contained resource if a local reference is provided |
|  reference | 0..1 | Select | String | Literal reference, Relative, internal or absolute URL |
|  identifier | 0..1 | Select | Identifier | Logical reference, when literal reference is not known |
|  display | 0..1 | Select | String | Text alternative for the resource |
|  onBehalfOf | 0..1 | Select | Reference ( CareConnect-Organization-1 ) | Organization the device or practitioner was acting for<br/>Constraint (ref-1): SHALL have a contained resource if a local reference is provided |
|  reference | 0..1 | Select | String | Literal reference, Relative, internal or absolute URL |
|  identifier | 0..1 | Select | Identifier | Logical reference, when literal reference is not known |
|  display | 0..1 | Select | String | Text alternative for the resource |
|  location | 0..1 | Select | Reference ( CareConnect-Location-1 ) | Where the procedure happened<br/>Constraint (ref-1): SHALL have a contained resource if a local reference is provided |
|  reference | 0..1 | Select | String | Literal reference, Relative, internal or absolute URL |
|  identifier | 0..1 | Select | Identifier | Logical reference, when literal reference is not known |
|  display | 0..1 | Select | String | Text alternative for the resource |
|  reasonCode | 0..* | Select | CodeableConcept | Coded reason procedure performed<br/>Binding (example): A code that identifies the reason a procedure is required. (http://hl7.org/fhir/stu3/valueset-procedure-reason.html ) |
|  coding | 0..* | Select | Coding | Code defined by a terminology system |
|  system | 0..1 | Select | Uri | Identity of the terminology system |
|  version | 0..1 | Select | String | Version of the system - if relevant |
|  code | 0..1 | Select | Code | Symbol in syntax defined by the system |
|  display | 0..1 | Select | String | Representation defined by the system |
|  userSelected | 0..1 | Select | Boolean | If this coding was chosen directly by the user |
|  text | 0..1 | Select | String | Plain text representation of the concept |
|  reasonReference | 0..* | Select | Reference ( CareConnect-Observation-1 <code>&amp;#124;</code> CareConnect-Condition-1 ) | Condition that is the reason the procedure performed<br/>Constraint (ref-1): SHALL have a contained resource if a local reference is provided |
|  reference | 0..1 | Select | String | Literal reference, Relative, internal or absolute URL |
|  identifier | 0..1 | Select | Identifier | Logical reference, when literal reference is not known |
|  display | 0..1 | Select | String | Text alternative for the resource |
|  bodySite | 0..* | Select | CodeableConcept | Target body sites<br/>Binding (example): Codes describing anatomical locations. May include laterality. (http://hl7.org/fhir/stu3/valueset-body-site.html ) |
|  coding | 0..* | Select | Coding | Code defined by a terminology system<br/>Slicing: Discriminator: system, Ordering: false, Rules: Open |
|  coding (snomedCT) | 0..1 | Select | Coding | Code defined by a terminology system<br/>Binding (extensible): A code from the SNOMED Clinical Terminology UK. (https://fhir.hl7.org.uk/STU3/ValueSet/CareConnect-BodySite-1 ) |
|  extension (snomedCTDescriptionID) | 0..1 | Select | Extension | The SNOMED CT Description ID for the display<br/>Constraint (ext-1): Must have either extensions or value[x], not both<br/>URL: https://fhir.hl7.org.uk/STU3/StructureDefinition/Extension-coding-sctdescid |
|  system | 1..1 | Select | Uri | Identity of the terminology system<br/>Fixed Value: http://snomed.info/sct |
|  code | 1..1 | Select | Code | Symbol in syntax defined by the system |
|  display | 1..1 | Select | String | Representation defined by the system |
|  userSelected | 0..1 | Select | Boolean | If this coding was chosen directly by the user |
|  text | 0..1 | Select | String | Plain text representation of the concept |
|  outcome | 0..1 | Select | CodeableConcept | The result of procedure<br/>Binding (example): An outcome of a procedure - whether it was resolved or otherwise. (http://hl7.org/fhir/stu3/valueset-procedure-outcome.html ) |
|  coding | 0..* | Select | Coding | Code defined by a terminology system |
|  system | 0..1 | Select | Uri | Identity of the terminology system |
|  version | 0..1 | Select | String | Version of the system - if relevant |
|  code | 0..1 | Select | Code | Symbol in syntax defined by the system |
|  display | 0..1 | Select | String | Representation defined by the system |
|  userSelected | 0..1 | Select | Boolean | If this coding was chosen directly by the user |
|  text | 0..1 | Select | String | Plain text representation of the concept |
|  report | 0..* | Select | Reference ( DiagnosticReport) | Any report resulting from the procedure<br/>Constraint (ref-1): SHALL have a contained resource if a local reference is provided |
|  reference | 0..1 | Select | String | Literal reference, Relative, internal or absolute URL |
|  identifier | 0..1 | Select | Identifier | Logical reference, when literal reference is not known |
|  display | 0..1 | Select | String | Text alternative for the resource |
|  complication | 0..* | Select | CodeableConcept | Complication following the procedure<br/>Binding (example): Codes describing complications that resulted from a procedure. (http://hl7.org/fhir/stu3/valueset-condition-code.html ) |
|  coding | 0..* | Select | Coding | Code defined by a terminology system<br/>Slicing: Discriminator: system, Ordering: false, Rules: Open |
|  coding (snomedCT) | 0..1 | Select | Coding | Code defined by a terminology system<br/>Binding (required): A code from the SNOMED Clinical Terminology UK. (https://fhir.hl7.org.uk/STU3/ValueSet/CareConnect-ConditionCode-1 ) |
|  extension (snomedCTDescriptionID) | 0..1 | Select | Extension | The SNOMED CT Description ID for the display<br/>Constraint (ext-1): Must have either extensions or value[x], not both<br/>URL: https://fhir.hl7.org.uk/STU3/StructureDefinition/Extension-coding-sctdescid |
|  system | 1..1 | Select | Uri | Identity of the terminology system<br/>Fixed Value: http://snomed.info/sct |
|  code | 1..1 | Select | Code | Symbol in syntax defined by the system |
|  display | 1..1 | Select | String | Representation defined by the system |
|  userSelected | 0..1 | Select | Boolean | If this coding was chosen directly by the user |
|  text | 0..1 | Select | String | Plain text representation of the concept |
|  complicationDetail | 0..* | Select | Reference ( CareConnect-Condition-1 ) | A condition that is a result of the procedure<br/>Constraint (ref-1): SHALL have a contained resource if a local reference is provided |
|  reference | 0..1 | Select | String | Literal reference, Relative, internal or absolute URL |
|  identifier | 0..1 | Select | Identifier | Logical reference, when literal reference is not known |
|  display | 0..1 | Select | String | Text alternative for the resource |
|  followUp | 0..* | Select | CodeableConcept | Instructions for follow up<br/>Binding (example): Specific follow up required for a procedure e.g. removal of sutures. (http://hl7.org/fhir/stu3/valueset-procedure-followup.html ) |
|  coding | 0..* | Select | Coding | Code defined by a terminology system |
|  system | 0..1 | Select | Uri | Identity of the terminology system |
|  version | 0..1 | Select | String | Version of the system - if relevant |
|  code | 0..1 | Select | Code | Symbol in syntax defined by the system |
|  display | 0..1 | Select | String | Representation defined by the system |
|  userSelected | 0..1 | Select | Boolean | If this coding was chosen directly by the user |
|  text | 0..1 | Select | String | Plain text representation of the concept |
|  note | 0..* | Select | Annotation | Additional information about the procedure |
|  author[x] | 0..1 | Select | Reference ( RelatedPerson <code>&amp;#124;</code>CareConnect-Patient-1 <code>&amp;#124;</code>CareConnect-Practitioner-1 ) <code>&amp;#124;</code>String | Individual responsible for the annotation<br/>Constraint (ref-1): SHALL have a contained resource if a local reference is provided |
|  time | 0..1 | Select | dateTime | When the annotation was made |
|  text | 1..1 | Select | String | The annotation - text content |
|  focalDevice | 0..* | Select | BackboneElement | Device changed in procedure |
|  modifierExtension | 0..* | Select | Extension | Extensions that cannot be ignored<br/>Constraint (ext-1): Must have either extensions or value[x], not both |
|  action | 0..1 | Select | CodeableConcept | Kind of change to device<br/>Binding (preferred): A kind of change that happened to the device during the procedure. (http://hl7.org/fhir/stu3/valueset-device-action.html ) |
|  coding | 0..* | Select | Coding | Code defined by a terminology system |
|  system | 0..1 | Select | Uri | Identity of the terminology system |
|  version | 0..1 | Select | String | Version of the system - if relevant |
|  code | 0..1 | Select | Code | Symbol in syntax defined by the system |
|  display | 0..1 | Select | String | Representation defined by the system |
|  userSelected | 0..1 | Select | Boolean | If this coding was chosen directly by the user |
|  text | 0..1 | Select | String | Plain text representation of the concept |
|  manipulated | 1..1 | Select | Reference ( Device ) | Device that was changed<br/>Constraint (ref-1): SHALL have a contained resource if a local reference is provided |
|  reference | 0..1 | Select | String | Literal reference, Relative, internal or absolute URL |
|  identifier | 0..1 | Select | Identifier | Logical reference, when literal reference is not known |
|  display | 0..1 | Select | String | Text alternative for the resource |
|  usedReference | 0..* | Select | Reference ( Device <code>&amp;#124;</code>Substance <code>&amp;#124;</code> CareConnect-Medication-1 ) | Items used during procedure<br/>Constraint (ref-1): SHALL have a contained resource if a local reference is provided |
|  reference | 0..1 | Select | String | Literal reference, Relative, internal or absolute URL |
|  identifier | 0..1 | Select | Identifier | Logical reference, when literal reference is not known |
|  display | 0..1 | Select | String | Text alternative for the resource |
|  usedCode | 0..* | Select | CodeableConcept | Coded items used during the procedure<br/>Binding (example): Codes describing items used during a procedure ( http://hl7.org/fhir/stu3/valueset-device-kind.html ) |
|  coding | 0..* | Select | Coding | Code defined by a terminology system |
|  system | 0..1 | Select | Uri | Identity of the terminology system |
|  version | 0..1 | Select | String | Version of the system - if relevant |
|  code | 0..1 | Select | Code | Symbol in syntax defined by the system |
|  display | 0..1 | Select | String | Representation defined by the system |
|  userSelected | 0..1 | Select | Boolean | If this coding was chosen directly by the user |
|  text | 0..1 | Select | String | Plain text representation of the concept |