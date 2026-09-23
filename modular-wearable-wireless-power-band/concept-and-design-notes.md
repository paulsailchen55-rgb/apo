# Concept and Design Notes

## Core Idea

Develop a wearable power band that can provide supplemental wireless energy to a smartwatch, Fitbit, sleep tracker, or similar device while the primary device remains on the wrist.

The band may be flexible, modular, puck-based, or built around a slap-wrap metal band. It should be removable and independently rechargeable.

## Operating Modes

### Wear-and-assist
The band is worn beside or around the watch and transfers energy wirelessly. Practical implementation may require a dedicated receiver, compatible charging standard, controlled alignment, and thermal monitoring.

### Remove-and-charge
The band can be removed and charged through USB-C, a wireless charging pad, a dock, or a modular puck charger.

### Modular puck system
Several small battery pucks may connect mechanically, electrically, or through a common power-management system. Users could carry one puck for everyday use and several for travel.

### Slap-wrap system
A flexible metal-band structure could use the slap-wrap principle associated with older slap bracelets. Design work must address edge protection, pinch points, fatigue, battery containment, puncture resistance, and thermal management.

## Adjustable and Cleanable Band Standard

A related standard would allow the band to move up and down the wrist or arm so the wearer can clean and dry the skin and underside of the band, then reposition and secure it.

Potential mechanisms include sliding sections, adjustable tension zones, a releasable cinch, linked flexible segments, or a band-within-a-band structure.

The design must avoid circulation restriction, moisture trapping, pressure points, and interference with wearable sensors.

## Solar-Assisted Exterior

A flexible photovoltaic exterior could provide supplemental trickle charging. It should not be assumed to replace normal charging until measured under indoor, outdoor, shaded, and moving conditions.

Research should examine usable photovoltaic area, output in ordinary light, efficiency, heat, durability, bending, cleaning, and whether solar energy charges the internal battery or directly supports the wearable.

## Energy and Capacity

A stated capacity such as 5,000 mAh is incomplete without voltage. For example, 5,000 mAh at 3.7 V is approximately 18.5 Wh before conversion losses.

Design evaluation must consider:

- Battery chemistry and voltage.
- Total watt-hours.
- Weight and volume.
- Wireless transfer losses.
- Heat generation.
- Battery-management and protection circuitry.
- Body contact and comfort.
- Airline and travel rules.
- Crushing, bending, puncture, and short-circuit protection.

## Research Questions

1. Which wireless power standards could support wearable-to-wearable charging?
2. Can a receiver be integrated into a watch band or case?
3. What alignment and transfer distance are practical during movement?
4. Can multiple pucks share a protected power-management system?
5. What battery geometry is safest for flexible or slap-wrap use?
6. How much energy can a solar exterior collect during a normal day?
7. What charging power can be delivered without uncomfortable heat?
8. Could the concept become an open physical and electrical interface standard?
9. What travel restrictions apply to modular wearable battery systems?
10. What testing is required before use with health-monitoring or medical wearables?

## Design Principles

- The watch remains independently usable.
- The power band is optional, removable, replaceable, and inspectable.
- Wireless charging stops or limits output when alignment or temperature is unsafe.
- Battery modules are protected against puncture, bending, moisture, and short circuits.
- The band supports cleaning and repositioning.
- The system does not require a phone to operate.
- Repairability and responsible end-of-life handling are considered from the beginning.
- The wearer can remove the power source quickly.
