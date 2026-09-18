# Health Record Pathway: OCHIN / MyChart

Status: research question and architecture note; requires direct verification with OCHIN and the relevant clinical organization.

The user wants a low-friction path for home measurements to reach the appropriate healthcare record.

Two conceptual pathways
-----------------------
1. Simple user-controlled path: device -> phone -> report/PDF -> MyChart attachment.

2. Structured path: device -> approved phone/app integration -> structured patient-generated data -> clinical record.

The simple path may be easier to pilot because it does not require the lending program to become an EHR integration vendor.

The structured path could be more useful clinically, but must be verified for the actual OCHIN configuration, supported devices, accepted data types, patient authorization, clinical workflow, and data provenance.

Questions for OCHIN
-------------------
- Can patients upload home-device measurements in structured form?
- Which patient-generated data types are accepted?
- Is there a supported Bluetooth/device pathway?
- Can patients submit CSV, PDF, image, or other exports?
- Does data enter the chart as an attachment, flowsheet, observation, or another object?
- What device validation and metadata are required?
- How are patient-generated measurements distinguished from clinician-verified measurements?
- What clinical review occurs?
- Can a library lending program be a neutral equipment provider without becoming a healthcare provider or business associate?
- What security/privacy requirements apply to an external app or nonprofit integration?

Boundary
--------
A measurement reaching MyChart does not by itself establish a diagnosis, causation, or medical significance. Clinical interpretation belongs to the healthcare workflow.

This archive does not assume that general Epic capabilities are available in a particular OCHIN deployment until verified.
