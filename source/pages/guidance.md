---
title: General Guidance
layout: default
active: terminology
---

This section outlines important definitions and interpretations and requirements common to all Immunization Decision Support Forecast actors used in this guide.
The conformance verbs used are defined in [FHIR Conformance Rules].

---

<!-- TOC  the css styling for this is \pages\assets\css\project.css under 'markdown-toc'-->
**Contents**

* Do not remove this line (it will not be displayed)
{:toc}

---

<!-- end TOC -->

## Background

Clinical Decision Support for Immunizations is increasingly being used in health information systems to indicate which vaccinations a patient is due for next. Many of these expert systems are built as stand-alone systems that respond to web service requests. While these independent systems have similar requirements and outputs they use different web service standards. This project aims to create a common FHIR implementation guide that these expert systems may use to provide a common consistent interface. This common interface will be used for two main purposes:

- Provide a common interface that health information systems may write to and gain access to their choice of CDS engines.
- Provide a common interface that may be used for testing and verifying the output of CDS engines.

<p>&nbsp;</p>

## Patient Demographics

The Patient profile requires support for a much broader range of demographics data elements than is typically required by an immunization CDS engine. Often, the engine only needs the patient gender and date of birth (along with the patient's immunization history) to produce an evaluated history and forecast. To minimize the amount of personal data being exchanged, CDS engines may require the use of data absent reason extensions for specific sensitive fields while still fulfilling the profile requirements for supporting all of the demographic elements required by the profile. Alternatively, a CDS engine may require additional demographics data so that it can access additional clinical data on the patient (eg. allergies, problems, etc) to provide a more personalized forecast - *note that accessing additional data beyond that contained in the operation is beyond the scope of this implementation guide*. As part of the implementation, the minimum necessary demographics payload should be determined.

<p>&nbsp;</p>

## Immunization Data Elements

The US Core Immunization profile used by this implementation guide only requires key data elements related to the immunization event, however depending on engine functionality other elements may assist the CDS engine in creating the best possible evaluation and forecast. As part of the implementation, the following data elements should be considered and exchanged if they can be used by the CDS engine:

- manufacturer
- lotNumber
- expirationDate
- site
- route
- doseQuantity
- isSubpotent
- subpotentReason
- reaction

<p>&nbsp;</p>

------------------------------------------------------------------------

{% include link-list.md %}
