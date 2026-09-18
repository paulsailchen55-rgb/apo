# Privacy, Security, Provenance, and Lost/Stolen Devices

Status: conceptual threat model / research framework.

Central tension
---------------
The project wants privacy while retaining enough provenance to establish that equipment and datasets originated from a legitimate lending program.

Separate these questions:
- Is the borrower anonymous?
- Is the measurement confidential?
- What is the identity of the physical device?
- What is the provenance of the dataset?
- Who is authorized to access it?
- Is the public release actually de-identified?

Lost/stolen-device concept
--------------------------
A lending device could have a program-controlled identifier and a status such as active, maintenance, lost, or stolen. Conceptually:

device connects -> identity verified -> status checked -> access permitted or denied.

This could allow recognition of a stolen device without publishing the borrower's identity. It is a design hypothesis, not a claim about current device capabilities.

Security layers to investigate
------------------------------
Encryption; authentication; authorization; pseudonymization; de-identification; aggregation; data minimization; provenance; chain of custody; audit logging.

These solve different problems and should be proportionate to risk.

Privacy-first hierarchy
-----------------------
Level 0: completely offline measurement.

Level 1: local connection to the borrower's phone.

Level 2: user-initiated upload.

Level 3: user-selected authorized destination.

Level 4: continuous cloud monitoring.

The thought experiment should test how much useful functionality can be achieved at Levels 0-2 before accepting the larger exposure surface of continuous cloud monitoring.

Surveillance concern
--------------------
The conversation raised concern that public infrastructure can become another ubiquitous data-collection system, including concerns about Wi-Fi exposure, FLoC-like profiling, hacking, and inference from seemingly innocuous signals. These are threat-model concerns, not claims that a particular library, utility, manufacturer, or other institution is presently conducting surveillance.

A central test is:
"What information should the system be technically incapable of collecting?"

Another is:
"Why does this device need network access?"

The design goal is privacy by architecture rather than reliance only on institutional promises.

Community tool shed comparison
------------------------------
A neighborhood tool shed can provide shared equipment but may have less standardized calibration, maintenance, documentation, provenance, security, and scaling. It remains a separate alternative model.
