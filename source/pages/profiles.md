---
title: Profiles and Extensions
layout: default
active: profiles
topofpage: true
r4: http://hl7.org/fhir/R4/
us_r4: http://hl7.org/fhir/us/core/
---

## Profiles

The following Profiles have been identified for use with this implementation guide. Where possible, US Core have been used as the basis for this implementation guide. The use of QI-Core profiles was considered but ultimately, those profiles contained additional constraints which were not needed for the use cases of this document.

|Resource Type|Profile Name|Link to R4 Profile|
|---|---|---|
|Patient|ImmDS Patient Profile|[ImmDS Patient (R4)]|
|Immunization|US Core Immunization Profile|[US Core Immunization (R4)]|
|ImmunizationEvaluation|ImmDS ImmunizationEvaluation Profile|[ImmDS ImmunizationEvaluation (R4)]|
|ImmunizationRecommendation|ImmDS ImmunizationRecommendation Profile|[ImmDS ImmunizationRecommendation (R4)]|


<!-- Uncomment when profiles are defined
The following Profiles and have been defined for this implementation guide.

include list-simple-profiles.xhtml
-->

<br />

## Extensions

The following [Extensions]({{site.data.fhir.path}}extensibility.html) have been explicitly identified for use with the Immunization Decision Support (ImmDS) Forecast implementation Guide from the [registry of standard extensions]({{site.data.fhir.path}}extensibility-registry.html) in the FHIR specification. Additional extensions may be registered and found on the HL7 FHIR registry at http://hl7.org/fhir/registry.

|Extension Name|Link to R4 Extension|
|---|---|
|Data Absent Reason|[FHIR Data Absent Reason (R4)]|

<!-- Uncomment when ImmDS extensions are defined
The following [Extensions]({{site.data.fhir.path}}extensibility.html) have been defined as part of the Immunization Decision Support Forecast implementation Guide. A [registry of standard extensions]({{site.data.fhir.path}}extensibility-registry.html) can be found in the FHIR specification and additional extensions may be registered on the HL7 FHIR registry at http://hl7.org/fhir/registry.

include list-simple-extensions.xhtml
-->

{% include link-list.md %}

<br />
