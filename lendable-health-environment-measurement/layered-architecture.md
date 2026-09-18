# Layered Architecture

Status: conceptual architecture / thought experiment.

1. Physical measurement
-----------------------
Health candidates include blood pressure, pulse/heart rate, temperature, oxygen saturation, weight, and other validated home measurements.

Home/environment candidates include humidity, temperature, particulate matter, CO2, carbon monoxide, radon, noise, light, moisture, electrical consumption, and other housing-condition measurements.

A first-generation device should be self-guiding: turn on, understand what it measures, position it, measure, recognize success/failure, repeat, and save/export a result without requiring a class.

2. Borrower's phone
-------------------
Preferred conceptual flow:

device -> local storage or short-range connection -> borrower's phone -> private record.

The phone is a possible bridge, not necessarily a cloud gateway.

3. Health pathway
-----------------
Possible simple path:

device -> phone -> report/PDF -> MyChart attachment.

Possible structured path:

device -> approved app/integration -> patient-generated data -> OCHIN/Epic clinical record.

The structured path must be verified with OCHIN rather than assumed from general Epic capability.

4. Environmental pathway
------------------------
Environmental measurements should have a separate record from the clinical chart. A record may contain device/model, measurement type, timestamps, duration, calibration/provenance information, data gaps, and user notes.

5. Voluntary sharing
--------------------
Do not use one blanket "share everything" permission. Possible separate choices include keeping measurements private, sending selected health information to healthcare, contributing de-identified environmental measurements to research, contributing aggregated community statistics, or sharing a specific environmental record with an authorized agency.

6. Community/public data
------------------------
Removing a name is not necessarily sufficient anonymization. Exact location, timestamps, household patterns, device identifiers, photographs, notes, and linkage with public records can create re-identification risks.

Cross-cutting identity separation
----------------------------------
Conceptually separate borrower identity, library account, device identity, loan identity, measurement/dataset identifier, health-record identity, and environmental/public identifier.

Zero-trust interpretation
--------------------------
Zero trust means verifying access rather than trusting a component merely because it is inside the system. The design question is which component needs which permission.

The library may need to know that an item exists, is lendable, and is returned. A device-management service may need device status. A healthcare destination may need patient-authorized health data. An environmental repository may need measurement provenance but not the borrower's library history.

Threat model
------------
Consider stolen physical devices, copied measurement files, compromised phones, insecure Bluetooth/Wi-Fi/cloud interfaces, manufacturer data retention, unauthorized database access, re-identification, false measurements, outdated firmware/calibration, and accidental or coercive sharing.

A central design question is: "Why does this device need Internet access?" Offline or user-initiated transfer may remove exposure that continuous cloud monitoring would create.
