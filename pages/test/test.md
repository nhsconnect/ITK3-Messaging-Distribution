---
title: Test Overview
keywords: test
tags: [overview]
sidebar: foundations_sidebar
permalink: test.html
summary: "These pages assist with requirements gathering and mapping stages of an ITK3 Messaging Solution development process."
---

## Overview ##

|  Element Name | **Conformance** | Description & Constraints for XXXX |
|  ------ | ------ | ------ |
|   |  |  |
|  identifier | Mandatory | Identifier(s) by which this encounter is known |
|  status | Mandatory | planned <code>&amp;#124;</code> arrived <code>&amp;#124;</code> triaged <code>&amp;#124;</code> in-progress <code>&amp;#124;</code> onleave <code>&amp;#124;</code> finished <code>&amp;#124;</code> cancelled + |
|   |  | EncounterStatus (Required) |
|  statusHistory | Not Used | List of past encounter statuses |
|  status | Not Used | planned <code>&amp;#124;</code> arrived <code>&amp;#124;</code> triaged <code>&amp;#124;</code> in-progress <code>&amp;#124;</code> onleave <code>&amp;#124;</code> finished <code>&amp;#124;</code> cancelled + |
|   |  | EncounterStatus (Required) |
|  period | Not Used | The time that the episode was in the specified status |
|  class | Optional | inpatient <code>&amp;#124;</code> outpatient <code>&amp;#124;</code> ambulatory <code>&amp;#124;</code> emergency + |
|   |  | ActEncounterCode (Extensible) |
|  classHistory | Not Used | List of past encounter classes |
|  class | Not Used | inpatient <code>&amp;#124;</code> outpatient <code>&amp;#124;</code> ambulatory <code>&amp;#124;</code> emergency + |
|   |  | ActEncounterCode (Extensible) |
|  period | Not used | The time that the episode was in the specified class |
|  type | Mandatory | Specific type of encounter |
|   |  | NHSD-Encounter-Type-1 |
|  priority | Required | Indicates the urgency of the encounter |
|   |  | v3 Code System ActPriority (Example) |
|  subject | Mandatory | [CareConnectPatient-1](https://data.developer.nhs.uk/specifications/sc-fhir-5/Profile.ADW-DischargeNotice/careconnect-patient-1.html) |



