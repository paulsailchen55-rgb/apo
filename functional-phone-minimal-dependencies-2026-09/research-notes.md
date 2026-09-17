# Research Notes

## Scope

These notes capture the factual basis and uncertainty around the software choices. They are not a claim that every statement applies identically to every Android build.

## FUTO Keyboard

FUTO describes its keyboard as providing offline/private voice input. Its documentation also describes built-in voice input and long-form voice-input behavior. The important practical issue for this phone is performance: an offline speech engine can still be too slow on an older device, so the configuration must be tested rather than assumed to be fast.

Official sources:

- https://futo.org/keyboard/
- https://gitlab.futo.org/keyboard/keyboard-wiki/-/wikis/FUTO-Keyboard

## FUTO Voice Input

FUTO also provides a standalone Voice Input application intended to provide offline speech recognition and to integrate with keyboards that support Android voice-input APIs. This was identified as a possible fallback if the integrated FUTO Keyboard voice input does not perform well.

Official source:

- https://futo.org/voiceinput/

## HeliBoard

HeliBoard is an open-source Android keyboard based on AOSP/OpenBoard work and is designed to operate without an Internet permission. However, HeliBoard does not itself perform speech recognition; its voice-input button hands off to another voice-input provider.

Therefore HeliBoard was not selected as the first keyboard for this experiment because fast integrated dictation is a primary requirement.

Source:

- https://github.com/Helium314/HeliBoard

## Fossify

Fossify's project describes its apps as open-source Android utilities without ads/tracking and generally without requiring a Fossify account. Individual app policies document local-first behavior for applications such as Gallery, Messages, Phone, File Manager, Documents, Notes, and Launcher.

Sources:

- https://www.fossify.org/
- https://www.fossify.org/policy/gallery/
- https://www.fossify.org/policy/messages/
- https://www.fossify.org/policy/home/

## Firefox

Firefox was chosen because the user wanted a non-Google browser and did not want to replace one Chromium-based browser with another merely for branding differences.

Source:

- https://www.mozilla.org/firefox/android/

## Gmail without the Gmail app

A Gmail account can be accessed through a supported browser such as Firefox. The Gmail app is therefore not a technical requirement merely because the user has a Gmail account.

Source:

- https://support.google.com/mail/answer/6557

## Collabora Office

Collabora Office is an Android office suite based on LibreOffice technology. It supports common office document formats and can work with local files. Cloud/remote-storage features are separate from the basic local editing use case.

Sources:

- https://www.collaboraoffice.com/collabora-office-android-ios/
- https://www.collaboraonline.com/

## Android / Motorola support boundary

The Moto G Pure (2022) shipped with Android 12 and received later Android/security support. The support window should be treated as an important lifecycle constraint when evaluating whether the phone is suitable for long-term use. This archive does not treat an unsupported or aging device as inherently unsafe; it records the support boundary so future replacement decisions can be made deliberately.

Motorola support source:

- https://en-us.support.motorola.com/app/software-security-updates

## Speech Services / accessibility uncertainty

The user disabled Google's Speech Services because they did not believe they needed it. Android accessibility and speech components can have substantial system integration because their purpose requires interaction with other parts of the operating system.

However, the following are distinct claims and must not be conflated:

1. A component has powerful privileges.
2. A powerful component can be a security-relevant target.
3. A particular version contains a vulnerability.
4. A particular device is being exploited.
5. A particular actor is exploiting it.

Only the first two are general architectural observations. The others require device/version-specific evidence.

## Research rule

When investigating a suspected system behavior, prefer:

- package metadata;
- granted permissions;
- documented services/receivers/providers;
- observable network activity;
- reproducible behavior;
- before/after testing;
- vendor and Android security documentation;

over conclusions drawn from package names, service names, or intuition alone.
