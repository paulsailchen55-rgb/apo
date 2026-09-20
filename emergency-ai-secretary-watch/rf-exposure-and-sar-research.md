# RF Exposure and SAR Research

## Purpose

Establish a deliberately conservative RF-exposure design target for the Emergency AI Secretary Watch, with particular attention to use by children and other users who may wear the device close to the body for long periods.

This is a research plan, not a claim that any particular module or future watch is already safe, certified, or appropriate for children.

## Current hardware direction

The earlier hardware direction appears to have been the LTE Cat M1 / Cat-M class of cellular technology rather than simply "GSM."

One candidate family discussed for this type of low-power design is Quectel's BG95 series. The exact module must be selected based on carrier compatibility, voice requirements, power behavior, certification path, antenna design, and RF exposure testing.

## Key distinction: module compliance vs. finished-device compliance

A cellular module can have its own regulatory approvals or modular-certification pathway, but that does not automatically establish the SAR of the finished watch.

Final RF exposure depends on the complete implementation, including:

- cellular module;
- antenna type and location;
- antenna tuning and matching;
- enclosure and materials;
- battery and nearby conductive structures;
- simultaneous transmitters;
- maximum conducted/radiated power;
- supported frequency bands;
- user-to-antenna separation;
- body position and intended use;
- firmware-controlled transmit behavior;
- power-control algorithms;
- any motion/proximity-based power reduction;
- Bluetooth or other simultaneous radios.

FCC guidance addresses RF exposure for mobile and portable devices and requires the applicable exposure assessment to correspond to the actual device configuration. FCC guidance also recognizes that software can control RF operation and that authorized operation must remain within the certified configuration.

Therefore, SAR compliance is partly a hardware/RF-design problem and partly an operational/software-control problem, but it is ultimately a property of the authorized finished device and its tested operating conditions.

## Conservative design objective

The project should not merely ask:

> "Does it pass the legal SAR limit?"

It should additionally ask:

> "Can we design and test the device to produce substantially lower exposure than the applicable limit under the intended use conditions?"

The project should investigate whether a lower internal design target is practical without making unsupported health claims.

## Children

The intended design goal is to make the device appropriate for child use from an RF-exposure engineering perspective.

Do not assume that an adult-compliant device automatically has a special "child-safe" SAR classification. Instead investigate:

- applicable general-population/uncontrolled exposure limits;
- EU and U.S. measurement conventions;
- age/body-size considerations in applicable standards;
- intended body position;
- continuous vs. intermittent transmission;
- maximum and time-averaged power;
- distance between antenna and body;
- worst-case contact conditions;
- whether a child-specific conservative design target is technically achievable.

Any statement that the device is "safe for children" should ultimately be tied to documented testing, applicable standards, and qualified regulatory/safety review rather than a marketing assertion.

## Mudita comparison

Mudita Pure provides a useful reference point because Mudita publishes measured SAR values for both EU and U.S. exposure regimes. Its published specifications list:

- EU head SAR: 0.06 W/kg cellular;
- EU body SAR: 0.62 W/kg cellular;
- U.S. head SAR: 0.07 W/kg cellular;
- U.S. body SAR: 1.13 W/kg cellular.

These numbers demonstrate an important point: SAR is a property of a particular complete device and test configuration, not simply a number that can be copied from a cellular chipset.

The Mudita results should therefore be treated as a benchmark/reference, not as a target that automatically applies to the watch.

## Research questions

1. What SAR documentation is available for the selected Cat-M module?
2. What conditions were used for any module-level RF exposure testing?
3. What modular-approval conditions must be preserved by the host design?
4. What antenna configurations produce the lowest practical exposure?
5. Can the antenna be placed on the side of the watch away from the wrist/body?
6. Can transmit power be dynamically reduced when high power is unnecessary?
7. Can the device detect situations in which it is pressed directly against the body?
8. Can the firmware enforce a conservative maximum transmit-power profile?
9. What happens to exposure when Bluetooth or another radio operates simultaneously?
10. What testing is required for the final watch at the intended positions and distances?
11. What independent laboratory should perform the final SAR/RF exposure testing?
12. What additional conservative design margin is technically practical for a child-oriented device?

## Research output

Produce a technical comparison containing:

- candidate cellular module;
- maximum RF power;
- supported bands;
- module certification status;
- antenna configuration;
- intended separation distance;
- firmware power controls;
- simultaneous-radio conditions;
- measured SAR;
- applicable limits;
- measurement uncertainty;
- proposed internal design target;
- remaining certification requirements.

## Design principle

> **Do not design merely to pass the exposure limit. Design for the lowest practical exposure consistent with reliable operation, then verify the complete device independently.**
