# Workflow Archive — Community Tiny Pantry and Tiny Library Network Extension

## Archive metadata

- **Project:** Open Food Access & No-Line Pantry
- **Repository:** `paulsailchen55-rgb/apo`
- **Project folder:** `open-food-access-no-line-pantry/`
- **Date:** 2026-09-22
- **Status:** ARCHIVED CONCEPT / PROPOSED
- **Implementation status:** No working software prototype has been built.

## 1. New concept captured

The project should connect with an existing or emerging local network of community food access points, including:

- tiny pantries;
- tiny libraries that also function as tiny pantries;
- resident-authorized food-sharing boxes;
- temporary boxes placed out when a tree or garden harvest is available.

Some hosts may permit people to visit and select food directly. Others may place out a box only during a specific harvest period. The system must represent these differences rather than treating every location as a permanent pantry.

## 2. Proposed network function

A participating host may voluntarily register an access point. The platform can then provide a searchable directory and temporary SMS guidance that helps a person find an authorized nearby food source.

The platform is an access and discovery layer, not the owner of the resource. Hosts retain control over:

- whether their location is listed;
- what food may be taken;
- access hours or conditions;
- whether a listing is public, limited, or referral-only;
- whether exact location details may be disclosed;
- when a listing is paused, changed, or removed.

The network should interoperate with existing community directories when possible, rather than requiring every host to adopt new software.

## 3. Temporary text pathway

A person could send a text asking what food is available in a selected area. The system could respond with one or more participating access points, including the host-provided access rules and the last-confirmed availability status.

The response must clearly distinguish:

- registered location;
- currently open or accessible;
- expected harvest-box period;
- reported availability;
- locally confirmed availability;
- temporarily paused;
- expired or removed listing.

The system must not guarantee that food remains available after the last confirmation. It must not direct anyone to trespass, take restricted items, or disturb private property.

## 4. Safety and privacy boundaries

- Do not expose precise residential addresses unless the host explicitly authorizes that level of disclosure.
- Do not publish private-property harvest information without permission.
- Do not infer that an item is safe or edible solely because it appears in a photo, observation database, or AI-generated classification.
- Require host or authorized local confirmation before presenting a harvest as available for collection.
- Avoid collecting seeker identity or contact information beyond what is necessary for the temporary request.
- Do not use the network to profile individual food seekers.

## 5. Lived-experience provenance

The project is informed by the user's firsthand experience using informal and community-based survival pathways. This experience is preserved as project motivation and provenance, not as a universal claim about every person's needs or circumstances.

The design intention is to document practical pathways that may help people now while leaving room for future generations to improve, replace, or make such emergency systems less necessary. The project is therefore an archive of possibility and a transition-oriented proposal, not a declaration that scarcity or emergency food systems should remain permanent.

## 6. Evidence labels

- **KNOWN:** The existence or observation of community food-sharing practices as described or later verified locally.
- **PROPOSED:** A software and directory layer connecting voluntary hosts with temporary seekers.
- **UNKNOWN:** Which local networks already have usable directories, APIs, governance rules, or host-verification procedures.
- **TESTED:** Not yet established; requires a future small-scale pilot with host consent.

## 7. Follow-up questions

- Which Santa Cruz-area tiny pantry and tiny library networks already maintain public listings?
- What permission and verification process should be required before adding a host?
- Should a host disclose an exact address, a general area, or only a referral contact?
- How should temporary harvest boxes expire automatically?
- How can the system accept updates by SMS, web form, or human coordinator?
- What minimum information is needed to prevent unsafe or unauthorized collection?
