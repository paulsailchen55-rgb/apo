# Phone Cleanup and Component Review

## Purpose

A calm, component-by-component review of installed Android/Motorola/carrier software. The goal was not to make the phone "as empty as possible," but to make it **quiet when not being asked to work and responsive when it is**.

The review used an exported installed/system-app list and, for selected packages, more detailed package reports. Decisions were made conservatively: understand a component's role before disabling it.

## General method

For each component, ask:

1. What is it?
2. What does the package report actually show?
3. Is it core infrastructure, an optional feature, a consumer of system services, or part of provisioning/distribution?
4. What can safely be changed through ordinary Android controls?
5. If uncertain, can it be observed rather than disabled?

A recurring principle was: **don't attack the pipe; determine who keeps opening the valve.** A system service existing is not by itself evidence that it is currently causing a particular behavior.

## Components reviewed

### Mobile Applications Manager — `com.inmobi.installer`

**Working decision: DISABLE** when carrier app recommendations/automatic provisioning are not wanted; if ordinary Disable is unavailable, background restriction was considered the fallback.

The detailed report identified it as a preloaded system component, currently disabled, signed by Swish/InMobi. It had Internet, boot, network-state, wake-lock, foreground-service, and package-query capabilities in the report. Importantly, the report did **not** show `INSTALL_PACKAGES` as granted. Therefore the record does not establish that this package can arbitrarily install applications by itself.

The component remains disabled in the reviewed state.

### Mobile Device Information Provider — `com.amazon.appmanager`

**Working decision: RESTRICT.**

The report showed a preloaded, enabled, Amazon-signed system component with Internet, network-state, and wake-lock permissions. It exposed an uploader service and application/lifecycle information providers, while explicit Amazon metrics permissions were not shown as granted.

Restriction was preferred over removal because it is a system component and the exact dependency chain was not fully established.

### Mobile Services — `com.tmobile.dm.ms.services`

**Working decision: LEAVE ALONE FOR NOW / INVESTIGATE.**

This is a carrier/system component with subscription, VoWiFi, SIM-change, carrier configuration/provisioning, notification, Firebase/FCM, analytics, and WorkManager-related pieces. It is enabled and Android did not provide the ordinary Disable/Force Stop controls in the observed configuration.

The user reported a recurring experience in which unwanted applications appeared to download/install when certain Mobile Services settings were not shut off. That is recorded here as a **user observation**, not as proof that Mobile Services itself performed every such installation.

The inspected report showed Internet, boot, foreground-service, network-state, package-query, and wake-lock permissions, but did not show the normal application-install permissions as granted. Many other privileged permissions were also not granted. This makes the exact installation pathway an unresolved research question rather than an established conclusion.

A screenshot of Mobile Services Additional Settings showed version 3.4.2-O, an update-check time of 09/11/26 at 11:14:44 PM, an "App Update → Update now" control, and an "App cleanup suggestions" Usage Access toggle visibly off. The latter therefore was not a demonstrated explanation for the reported behavior.

### Moto Installer — `com.motorola.installer`

**Working decision: INVESTIGATE BEFORE DISABLING.**

The installed report showed an enabled, preloaded system component with activities related to notifications, licensing, about/help, full-screen/dialog presentation, and Google API handling. It also contained services named `StartUpService`, `DownloadService`, `PackageInstallerService`, an analytics WebService, and `MotoInstallerService`, plus package-installer/startup receivers.

The report showed Internet, boot, network-state, package-query, and wake-lock permissions. It did **not** show `INSTALL_PACKAGES` or `INSTALL_PACKAGE_UPDATES` as granted in this particular report. Consequently, the presence of a service named `PackageInstallerService` is evidence of installer-related machinery, but is not by itself proof that this installed build can silently install arbitrary applications.

The "View Network" idea was identified as a potentially useful security-research observation point: the useful question is what this particular build can actually see, communicate with, download, or cause, rather than assuming capability from names alone.

### Device Configuration — `android.autoinstalls.config.motorola.layout`

**Working decision: LEAVE ALONE.**

Despite `autoinstalls` appearing in its package name, the inspected package looked like a configuration package: enabled, preloaded/Play-updated, no listed activities or permissions, no services/providers, and a `DummyReceiver`. The package name alone was not treated as evidence that it installs applications.

This is an important example of avoiding inference from naming.

### Moto AI Services — `com.motorola.aiservices`

**Working decision: LEAVE ALONE / OBSERVE.**

The report described Motorola AI/context functionality including model training, context awareness, app-use analysis, location/context detection, geofencing, sleep-pattern detection, battery information, activity/context detection, semantic/location processing, AI Zoom, and offline audio transcription. It also showed boot/background jobs and services.

Some potentially sensitive permissions were not granted in the report, including Wi-Fi state/change, Bluetooth connect, package-usage statistics, and a Motorola context-engine permission.

The existence of these functions does not establish that the phone is continuously tracking location or Bluetooth activity. The working approach was to leave it enabled while looking for measurable evidence of actual background behavior.

### Fused Location — `com.android.location.fused`

**Working decision: CORE INFRASTRUCTURE / LEAVE ALONE.**

The package is the system fused-location plumbing. The report showed the fused and GNSS overlay location services and did not show ordinary location permissions granted to the package itself.

The key distinction established during the discussion was:

- Observation: a fused-location component exists and participates in location plumbing.
- Possible inference: it is involved when location is requested.
- Stronger claim: it is currently tracking the user.
- Stronger still: it is responsible for a particular harm.

Those statements are not equivalent. The more useful research question is which components request location, when, for what purpose, and what observable effects follow.

### Network Stack — `com.google.android.networkstack`

**Working decision: LEAVE ALONE / CORE NETWORK INFRASTRUCTURE.**

The report identified NetworkStack as enabled system/preloaded infrastructure with Internet, network-state, and wake-lock permissions and NetworkStack/maintenance services. It was treated as networking plumbing rather than an optional app.

### Tethering — `com.google.android.networkstack.tethering`

**Working decision: LEAVE ALONE / CORE NETWORK INFRASTRUCTURE.**

The package provides tethering infrastructure. The report showed an enabled system/preloaded component and a `TetheringService`. It was not treated as an optional target for cleanup.

### Network overlays — `com.google.android.networkstack.overlay` and `com.google.android.networkstack.tethering.overlay`

**Working decision: LEAVE ALONE.**

Both were enabled/preloaded resource-overlay packages with no meaningful application components or granted permissions shown in the report. They were treated as infrastructure configuration rather than targets for disabling.

### TfnRemoteSimlockService — `com.mediatek.rsu.tfn`

**Working decision: LEAVE ALONE.**

Enabled/preloaded system component, Motorola platform-signed, with wake-lock granted and a specific remote-SIM-lock permission/service. It was treated as carrier/device infrastructure.

### eSIM setup overlay — `com.motorola.setup.overlay.primaryesim`

**Working decision: LEAVE ALONE.**

Enabled/preloaded Motorola system overlay with no listed activities, permissions, services, or providers in the report. It was not treated as a cleanup target.

## Other already-disabled software

Many optional or carrier applications were already disabled and were generally left disabled, including examples such as Android Auto, AT&T Cloud, AppAdvisor/carrier-promotion components, Google Assistant, Chrome (where Firefox is the chosen browser), Google Calendar (where Fossify Calendar is used), Google Contacts/legacy Contacts (where Fossify Contacts is used), Google Drive, Glance, Google Maps (when not used), Meet, Google Messages (where Fossify Messages is used), Google Photos (where Fossify Gallery is used), YouTube, YouTube Music, Google TV, various Verizon setup/extension/cloud components, T-Mobile diagnostics, visual voicemail components, and other carrier-specific packages.

Core components such as Android System, System UI, Settings, Phone Services, Google Play services, Google Services Framework, NetworkStack, Bluetooth, Wi-Fi, SIM/eSIM infrastructure, MTP, NFC, Telephony, Permission Controller, Package Installer, and related Mainline components were intentionally left alone.

## Current conceptual map

The reviewed system was grouped into layers:

1. **Infrastructure** — location, networking, Bluetooth, telephony, SIM/eSIM. Usually leave alone.
2. **Consumers** — AI/context, location history, Smart 5G, Device Care, apps requesting system services. Investigate relationships and actual use.
3. **Distribution/provisioning** — Moto Installer, Mobile Services, Mobile Applications Manager, configuration packages, carrier content/provisioning. Investigate when the question is "why did software appear?"

This layered model is a working research aid, not a claim about how every package is internally connected.

## Design principle carried forward

The cleanup was not about eliminating software for its own sake. The desired endpoint was a phone that is **quiet when it isn't being asked to work, and responsive when it is**.

The observer project described in the companion notes is intended to make future decisions from measurements rather than assumptions.
