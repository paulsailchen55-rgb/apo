# Simple Voice Link

**Author:** Paul Statchen  
**Date:** 2026-09-18  
**Status:** Early-stage accessibility and communication technology concept; not a finished product or validated deployment design.

## Purpose

Develop a simple, independently connected phone/device that can make reliable voice communication easier for people who have difficulty using an ordinary smartphone.

The original use case was a person living in a group-home setting who needed a very simple way to call a designated person. The concept is intentionally broader: the same system could potentially serve people in group homes, shelters, assisted living, supported housing, hospitals, or other settings where ordinary smartphone interfaces create barriers.

The central idea is not a particular brand of phone or carrier. It is a reusable system for configuring supported Android phones into a dedicated communication device.

## Core user experience

The initial target is deliberately small:

- one supported Android phone model;
- its own cellular service and phone number;
- one large, obvious call control;
- one designated contact;
- simple incoming-call handling;
- accessibility settings appropriate to the user;
- strong attention to transmitted voice quality in noisy environments;
- minimal opportunities for accidental changes to the configuration.

The system should remain a real phone, with the underlying operating-system components required for security, updates, cellular service, recovery, and maintenance.

## Voice quality and noise

A major research requirement is the quality of the voice transmitted to the person receiving the call, not merely how well the user hears the other person.

Group-home and shared environments can contain nearby conversations and other background sounds. The project should therefore test whether a selected phone, microphone arrangement, operating-system feature, or calling application can reduce unwanted background speech and preserve the user's voice.

This must be tested in actual environments rather than assumed from marketing descriptions.

Useful tests could include:

- quiet-room baseline;
- ordinary room noise;
- nearby conversation;
- television or music;
- movement around the phone;
- speakerphone versus handset/headset modes;
- outgoing voice recorded at the receiving end;
- repeatable before/after comparisons.

## Connectivity

The device should have its own independently connected cellular service and number rather than depending entirely on another person's phone.

A low-cost service such as the previously discussed Tello option can be investigated, but carrier compatibility, SIM/eSIM support, emergency-calling requirements, coverage, device compatibility, and current pricing must be verified before deployment.

## Installation paths

A reusable system needs to recognize that donated or existing phones arrive in different conditions.

### Path A — clean conversion

A supported phone can be factory-reset and configured specifically for the communication system.

### Path B — preserve existing data

Where appropriate and authorized, the system can be installed without erasing the person's existing information.

### Path C — reject or repair

A phone that is damaged, unsupported, insecure, or unreliable should not be forced into service merely because it is available.

## Interface and device control

Simple app pinning may help prevent accidental navigation, but it is not necessarily equivalent to a fully managed kiosk or dedicated-device configuration.

The project should investigate Android accessibility features, launcher configurations, app pinning, managed-device/device-owner mechanisms, and other supported approaches.

Developer mode should not be treated as equivalent to administrative control.

The goal is a minimal user experience without removing system functions needed for security, updates, calling, emergency access, recovery, and legitimate maintenance.

## First prototype milestone

Start with one known Android model rather than attempting to support every phone.

The first milestone is:

1. configure one phone;
2. provide one large call button;
3. call one designated contact;
4. establish reliable cellular calling;
5. test outgoing voice under realistic background-noise conditions;
6. document what works and what fails;
7. determine whether the configuration can be maintained and recovered by another person.

## Accessibility and dignity

The system should reduce unnecessary complexity without treating the user as incapable.

A dedicated interface can be useful when a conventional smartphone exposes too many controls or requires skills that are difficult for a particular person.

The same design should be adaptable to different users rather than assuming that every person needs exactly the same interface.

Possible users include people with disabilities, older adults, people in supported living, people experiencing homelessness, people with cognitive or motor barriers, and people who simply need a highly simplified communication device.

## Privacy, consent, and control

The system should be designed so that the person using it, or an authorized decision-maker where legally appropriate, understands:

- what information the device collects;
- what information is transmitted;
- which services have access to communications data;
- who can administer the device;
- how the configuration can be changed;
- how the phone can be recovered or reset.

The project should avoid unnecessary surveillance or collection of personal information.

## Open research questions

- Which affordable Android models provide the necessary microphone and accessibility capabilities?
- Which Android versions support the required dedicated-device controls?
- Which calling applications provide useful voice isolation or noise suppression?
- How well do these features work when the unwanted sound is another person's speech?
- Which cellular carriers support the selected devices and desired service configuration?
- What emergency-calling behavior and legal requirements apply to a dedicated device?
- How can a caregiver or technician restore the device after an update, failure, or accidental configuration change?
- Can the same configuration be reproduced reliably across multiple supported phones?
- What should happen when a phone is lost, stolen, damaged, or no longer supported?
- What is the simplest interface that still preserves security and legitimate control?

## Design principle

**Make communication simple without making the person dependent on a fragile or opaque system.**

The project should favor reliability, accessibility, privacy, maintainability, and recoverability.