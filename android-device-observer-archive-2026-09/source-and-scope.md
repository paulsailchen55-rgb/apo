# Source and Scope

## Repository role

The parent repository `apo` is an **Archive of Possibilities**. This folder is intentionally self-contained so it can be referenced independently without implying that it is the definitive project repository.

## Source material preserved

The work in this folder comes from a September 2026 conversation about cleaning up and understanding a Motorola Android phone, including package-by-package review of an installed-app export and detailed package reports for selected components.

One source export was identified during the work as:

- `20260912_003552.txt`
- Produced by **BAYTON PACKAGE SEARCH**
- The export contained 495 lines in the reviewed copy.

Selected package reports were then examined for package identity, enabled/disabled state, signing source, permissions, activities, services, receivers, and providers.

## Scope

This archive captures:

- the cleanup objective and decision method;
- selected package findings and working decisions;
- the emerging observer/logger concept;
- the distinction between infrastructure, consumers, and provisioning/distribution;
- unresolved questions about software installation and background behavior;
- the methodological principle that observation should not be silently converted into accusation.

## What is not claimed

This archive does **not** establish that:

- Motorola, T-Mobile, Amazon, Meta, InMobi, Google, or another company intentionally caused a particular unwanted behavior;
- any inspected component is malicious;
- the presence of a location, network, Bluetooth, installer, analytics, or provisioning component means that the component is actively performing a suspected behavior at all times;
- a package with an installer-related name necessarily has unrestricted package-installation authority;
- a correlation between two events proves causation.

Where the conversation included a user's experience or hypothesis, it is retained as such.

## Current unresolved questions

1. What exact pathway, if any, caused unwanted applications to appear on the device in the user's observed cases?
2. What authority does the installed Moto Installer build actually possess beyond the permissions shown in the package report?
3. How do Moto Installer, Mobile Services, carrier provisioning, Mobile Applications Manager, and configuration packages interact, if they interact at all?
4. Which components are actual consumers of location/network/Bluetooth infrastructure during observed background events?
5. Can a lightweight observer measure these relationships without materially changing the phone's behavior?

## Reproducibility note

Future experiments should record the device/software state, the precise package/build under test, the observation method, timestamps, changes made, and results. A finding should remain labeled as an observation, inference, hypothesis, or externally verified fact according to the evidence available at the time.

## Archive principle

**Preserve the possibility before deciding what it is.**
