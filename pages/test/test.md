---
title: Test Overview
keywords: test
tags: [overview]
sidebar: foundations_sidebar
permalink: test.html
summary: "These pages assist with requirements gathering and mapping stages of an ITK3 Messaging Solution development process."
---

## Overview ##

|   |  |  |  |  |  |  |
|  ------ | ------ | ------ | ------ | ------ | ------ | ------ |
|  **Name** | **Base Card.** | **Imple Card.** | **Conformance** | **Type** | **Description & Constraints** | **Additional Constraints For This Implementation** |
|  Procedure |  |  |  | DomainResource | An action that is being or was performed on a patient<br/>+ Reason not done is only permitted if notDone indicator is true<br/>Elements defined in Ancestors: id, meta, implicitRules, language, text, contained, extension, modifierExtension |  |
|  identifier | 0..* | 0..* | Mandatory | Identifier | External Identifiers for this procedure |  |
|  definition | 0..* | 0..* | Not Used | Reference(PlanDefinition <code>&amp;#124;</code> ActivityDefinition <code>&amp;#124;</code> HealthcareService) | Instantiates protocol or definition |  |
|  basedOn | 0..* | 0..* | Select | Reference(CarePlan <code>&amp;#124;</code> ProcedureRequest <code>&amp;#124;</code> ReferralRequest) | A request for this procedure |  |
|  partOf | 0..* | 0..* | Select | Reference(Procedure <code>&amp;#124;</code> Observation <code>&amp;#124;</code> MedicationAdministration) | Part of referenced event |  |
|  status | 1..1 | 1..1 | Select | code | preparation <code>&amp;#124;</code> in-progress <code>&amp;#124;</code> suspended <code>&amp;#124;</code> aborted <code>&amp;#124;</code> completed <code>&amp;#124;</code> entered-in-error <code>&amp;#124;</code> unknown<br/>EventStatus (Required) |  |
|  notDone | 0..1 | 0..1 | Select | boolean | True if procedure was not performed as scheduled |  |
|  notDoneReason | 0..1 | 0..1 | Select | CodeableConcept | Reason procedure was not performed<br/>Procedure Not Performed Reason (SNOMED-CT) (Example) |  |
|  category | 0..1 | 0..1 | Select | CodeableConcept | Classification of the procedure<br/>Procedure Category Codes (SNOMED CT) (Example) |  |
|  code | 0..1 | 0..1 | Select | CodeableConcept | Identification of the procedure<br/>Procedure Codes (SNOMED CT) (Example) |  |
|  subject | 1..1 | 1..1 | Select | Reference(Patient <code>&amp;#124;</code> Group) | Who the procedure was performed on |  |
|  context | 0..1 | 0..1 | Select | Reference(Encounter <code>&amp;#124;</code> EpisodeOfCare) | Encounter or episode associated with the procedure |  |
|  performed[x] | 0..1 | 0..1 | Select |  | Date/Period the procedure was performed |  |
|  performedDateTime |  |  | Select | dateTime |  |  |
|  performedPeriod |  |  | Select | Period |  |  |
|  performer | 0..* | 0..* | Select | BackboneElement | The people who performed the procedure |  |
|  role | 0..1 | 0..1 | Select | CodeableConcept | The role the actor was in<br/>Procedure Performer Role Codes (Example) |  |
|  actor | 1..1 | 1..1 | Select | Reference(Practitioner <code>&amp;#124;</code> Organization <code>&amp;#124;</code> Patient <code>&amp;#124;</code> RelatedPerson <code>&amp;#124;</code> Device) | The reference to the practitioner |  |
|  onBehalfOf | 0..1 | 0..1 | Select | Reference(Organization) | Organization the device or practitioner was acting for |  |
|  location | 0..1 | 0..1 | Select | Reference(Location) | Where the procedure happened |  |
|  reasonCode | 0..* | 0..* | Select | CodeableConcept | Coded reason procedure performed<br/>Procedure Reason Codes (Example) |  |
|  reasonReference | 0..* | 0..* | Select | Reference(Condition <code>&amp;#124;</code> Observation) | Condition that is the reason the procedure performed |  |
|  bodySite | 0..* | 0..* | Select | CodeableConcept | Target body sites<br/>SNOMED CT Body Structures (Example) |  |
|  outcome | 0..1 | 0..1 | Select | CodeableConcept | The result of procedure<br/>Procedure Outcome Codes (SNOMED CT) (Example) |  |
|  report | 0..* | 0..* | Select | Reference(DiagnosticReport) | Any report resulting from the procedure |  |
|  complication | 0..* | 0..* | Select | CodeableConcept | Complication following the procedure<br/>Condition/Problem/Diagnosis Codes (Example) |  |
|  complicationDetail | 0..* | 0..* | Select | Reference(Condition) | A condition that is a result of the procedure |  |
|  followUp | 0..* | 0..* | Select | CodeableConcept | Instructions for follow up<br/>Procedure Follow up Codes (SNOMED CT) (Example) |  |
|  note | 0..* | 0..* | Select | Annotation | Additional information about the procedure |  |
|  focalDevice | 0..* | 0..* | Select | BackboneElement | Device changed in procedure |  |
|  action | 0..1 | 0..1 | Select | CodeableConcept | Kind of change to device<br/>Procedure Device Action Codes (Preferred) |  |
|  manipulated | 1..1 | 1..1 | Select | Reference(Device) | Device that was changed |  |
|  usedReference | 0..* | 0..* | Select | Reference(Device <code>&amp;#124;</code> Medication <code>&amp;#124;</code> Substance) | Items used during procedure |  |
|  usedCode | 0..* | 0..* | Select | CodeableConcept | Coded items used during the procedure<br/>FHIR Device Types (Example) |  |



