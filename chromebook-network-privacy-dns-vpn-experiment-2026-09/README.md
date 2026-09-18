# Chromebook Network Privacy / DNS / VPN Experiment — 2026-09

## Status

Archive/reference package created 2026-09-18 from the network-privacy troubleshooting conversation.

This is a technical experiment and troubleshooting record, not a claim that a particular network operator is conducting surveillance or intentionally blocking the user's traffic.

## Purpose

Determine, using small reversible tests, which privacy and connectivity mechanisms work on the user's Chromebook and current network.

The experiment began with Proton VPN, Chrome Secure DNS, Quad9 DNS (9.9.9.9), Cloudflare DNS (1.1.1.1), and consideration of Encrypted Client Hello (ECH).

## Core rule

> Observe first. Change one thing at a time. Preserve a known-good configuration. Do not infer intent from a network symptom.

## Current observed state

The user reported that changing VPN/DNS configuration caused a connection failure and that the Cloudflare diagnostic page at 1.1.1.1/help could not be reached from the current configuration/network.

The exact network error should be recorded when available.

## Important distinctions

VPN, DNS-over-HTTPS, and ECH are different technologies. A working encrypted DNS connection does not prove that all network metadata is hidden. ECH does not by itself hide every destination, IP address, timing pattern, or other network metadata.

## Related archives

- functional-phone-minimal-dependencies-2026-09/
- internet-complexity-voice-and-knowledge-access/
- android-device-observer-archive-2026-09/

This folder remains separate because it records a concrete Chromebook/network experiment rather than a general device-minimization project.

## Non-conclusions

The archive does not establish that Comcast is monitoring the user's browsing, deliberately blocking encryption, that a San Francisco network location represents surveillance, or that a failed connection proves malicious behavior.
