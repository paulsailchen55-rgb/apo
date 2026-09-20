# Immediate Ingredient Transparency and Receipts

## Purpose

The mobile food-and-drink service should make ingredient information immediately available at the moment food is offered or distributed. A person should not have to wait for an operator to ask someone else in the kitchen, own a phone, use the internet, or accept food without knowing what it contains.

This is an operational design requirement, not merely an optional educational feature.

## Core service standard

> No food packet, prepared serving, or drink component should be distributed without an accessible way to identify its ingredients and relevant warnings.

The information must be available through at least one of these methods:

1. A printed ingredient receipt.
2. A phone-accessible page, QR code, NFC tag, or similar digital method.
3. Direct assistance from the operator using the same maintained information source.

Phone access is optional. The person receiving food may choose a printout, digital information, verbal assistance, or a combination.

## Receipt model

The receipt should identify the exact items selected or distributed. Where practical, it should be generated automatically from the dispensing or selection record.

Suggested receipt fields:

- Date and approximate service time.
- Service station or unit identifier.
- Product or packet name.
- Manufacturer or supplier, when applicable.
- Complete ingredient statement as supplied and verified.
- Major-allergen declaration.
- Cross-contact or shared-equipment warning, when documented.
- Batch, lot, or production identifier, when available.
- Storage, preparation, or dilution instructions, when relevant.
- Water session or batch identifier, when water is included.
- A short statement distinguishing ingredient facts from medical advice.
- A contact or referral resource for questions and healthcare assistance.

The receipt should be concise enough to print on a small thermal printer while allowing a longer digital page to provide additional detail.

## Immediate availability requirement

The operator should not need to leave the service station to discover what a packet contains. Ingredient records must be prepared and maintained before service begins. If the ingredient record is missing, unclear, outdated, or inconsistent with the package, that item should be withheld until verified.

The system should support:

- Selection of one ingredient or packet at a time.
- Printing only the information relevant to the person's selected items.
- Reprinting a receipt if it is lost or damaged.
- A plain-language version for people who want basic information.
- Assistance for people with limited literacy, visual limitations, language barriers, or no phone access.
- A record of which supplier lot or batch was used.

## Information levels

### Basic receipt

The default printout should provide the essential facts needed immediately:

- What the item is.
- What ingredients it contains.
- Major allergens identified by the supplier.
- Relevant preparation and safety warnings.
- How to obtain more information.

### Expanded information

If requested, the phone page or a longer printout may include:

- Ingredient definitions and alternate names.
- Supplier documentation.
- Batch and traceability details.
- Storage and shelf-life information.
- Cross-contact controls.
- Water testing and verification records, where applicable.
- Non-diagnostic educational information about allergies, intolerances, and possible reactions.
- Local healthcare and allergy-testing referrals.

## Health and allergy limitations

Ingredient transparency is essential, but it cannot guarantee that a food is safe for every individual. A person may have an allergy or sensitivity not covered by a standard major-allergen declaration. Supplier information may also fail to capture every cross-contact risk unless controls are documented.

The system must not present a receipt as a medical clearance or claim that a person is safe to eat an item merely because the listed ingredients do not include a known allergen. The operator should encourage professional medical evaluation for suspected allergies and provide emergency guidance consistent with the service's training and local requirements.

A future rapid allergy-testing device may be researched, but it must not be assumed to exist, be accurate, or replace clinical evaluation unless independently validated and authorized for the intended use.

## Human operator responsibility

The person stationed beside the unit is responsible for helping make the information usable, not for making medical decisions for participants. Duties may include:

- Confirming that the receipt matches the selected item.
- Helping a person read or understand the information.
- Pointing out documented warnings without exaggerating them.
- Avoiding unsupported medical claims.
- Withholding an item when the ingredient record is incomplete or contradictory.
- Recording corrections, complaints, suspected reactions, and supplier issues through a privacy-conscious incident process.

## Design principle

The service should provide immediate transparency with optional deeper access:

> A person can receive the food promptly, see what is in it immediately, retain a physical record if desired, and access additional information without being required to own a phone.

This standard is intended to prevent the recurring situation in which a meal provider cannot identify ingredients even after being asked. The information should be built into the system before distribution, rather than depending on memory or a last-minute search in the kitchen.

## Open implementation questions

- Which compact printer is reliable, inexpensive, refillable, and suitable for outdoor service?
- Should the receipt use a QR code, NFC tag, short URL, or all three for expanded information?
- How will supplier ingredient records be reviewed and updated?
- How will prepared foods with changing recipes be tracked?
- What accessibility and language formats are needed locally?
- What food-service, labeling, privacy, and record-retention requirements apply in the pilot location?
- How should receipts identify water without exposing unnecessary personal information?
