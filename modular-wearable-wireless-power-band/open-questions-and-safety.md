# Open Questions and Safety

## Technical Questions

- Which wireless power protocol is suitable for low-power wearable charging?
- Does the watch require a dedicated receiver or modified case/band?
- How will alignment be maintained while walking, sleeping, and moving the wrist?
- What transfer efficiency is realistic across the required gap?
- How will charging be limited when the watch or band becomes warm?
- Can a modular puck system share power safely without creating a single point of failure?
- How will the system behave when a puck is removed or damaged?

## Wearability Questions

- What total weight is acceptable on the wrist or forearm?
- Can the band be repositioned without removing the watch?
- How can the skin contact area be cleaned and dried?
- Can the band avoid pressure points, moisture retention, and circulation problems?
- Does the slap-wrap mechanism create pinch points or fatigue risks?

## Battery Safety

- Use protected cells and an appropriate battery-management system.
- Provide overcharge, over-discharge, overcurrent, and thermal protection.
- Protect cells from puncture, crushing, bending beyond their rated limits, and short circuits.
- Keep battery cells and charging electronics separated from direct skin contact where appropriate.
- Do not treat a flexible form factor as automatically safe; flexible packaging can still fail.
- Do not use the concept with medical devices until compatibility and safety are validated.

## Solar Questions

- Measure output rather than assuming ambient light provides meaningful charging.
- Compare indoor, outdoor, shade, and motion conditions.
- Evaluate heat, waterproofing, bending, abrasion, and cleaning durability.

## Validation Plan

1. Begin with a benchtop, non-wearable power-transfer test.
2. Measure voltage, current, efficiency, temperature, and alignment tolerance.
3. Test fault conditions and automatic shutdown behavior.
4. Build a non-battery mechanical mockup for comfort and repositioning.
5. Test battery modules separately in a protected enclosure.
6. Combine subsystems only after individual safety checks.
7. Document all results using KNOWN, CALCULATED, TESTED, PROPOSED, SPECULATIVE, and UNKNOWN labels.
