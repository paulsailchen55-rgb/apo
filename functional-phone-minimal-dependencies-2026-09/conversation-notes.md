# Conversation Notes

## Context

The phone-setup work grew out of a desire for a simpler, less exhausting device. The user explicitly wanted a functional phone with minimal dependencies rather than a large, highly connected ecosystem.

The user does not need cloud photo storage, cloud document synchronization, or a large collection of accounts. They want local-first files and a small number of necessary services.

## Working decisions

### Keyboard and voice input

Voice typing speed is a major requirement. The user previously tried FUTO Keyboard and had experienced update/voice-transcription problems on an older phone. The concern was not primarily that voice data must remain offline; the critical requirement was that dictation be fast enough not to break conversational flow.

The current experiment therefore starts with FUTO Keyboard because it combines keyboard input and voice input rather than requiring a separate speech-recognition stack.

The intended test is practical: speak naturally for a while and observe whether transcription is acceptably responsive. Keep the previous keyboard available until the replacement is verified.

### Home screen and local apps

Fossify Launcher was installed and tested as the home screen. Fossify Gallery was installed for local media. Fossify Messages was already being used for SMS/MMS.

The user liked the general direction: a phone that feels like a tool instead of a constantly connected service platform.

### Browser

Firefox is the preferred browser because the user wanted a non-Google browser and did not want to replace Google Chromium with another Chromium-based browser merely for the appearance of independence.

### Gmail

The Gmail app is not considered necessary merely because the user has a Gmail address. A simple alternative is to access Gmail through Firefox. A separate mail client can be considered later if browser access proves inconvenient.

The principle is to retain the Gmail account where needed without making the Gmail app a central part of the phone.

### Documents

Microsoft Office/OneDrive was deliberately deferred. The user does not want to create a Microsoft account merely to edit documents.

Collabora Office was identified as a later option for local Office-compatible document editing without requiring a cloud account for ordinary local-file use.

### Password manager

KeePassDX was discussed but intentionally not installed yet. It is not necessary to solve every possible infrastructure question at once.

## Speech Services / text-to-speech discussion

The user disabled Google's Speech Services after deciding they did not appear to use the feature and were concerned about its role in the phone's accessibility/speech stack.

Important distinction preserved here:

- disabling a service can be a reasonable minimization experiment if the user does not need it;
- that does not by itself demonstrate that the service is malicious, a backdoor, or a vulnerability being exploited;
- accessibility services are powerful because they need to assist users, and privileged components can be security-relevant, but security relevance is not evidence of active compromise.

The practical approach is to observe what actually breaks after a change and restore a component if a needed function depends on it.

## Security reasoning

The conversation included a hypothesis that accessibility and other privileged operating-system components could be attractive targets because they have broad capabilities. That idea is preserved as a **hypothesis/intuition**, not as an established fact about this phone or Android generally.

The useful operational rule adopted was:

> If a powerful system feature is not needed, avoid granting unnecessary access to it; if it is core infrastructure, do not disable it merely because it looks powerful.

This avoids turning a security concern into unsupported claims about hidden compromise.

## Broader philosophy

The phone should not become a project that consumes more time than it saves.

A good result is not the phone with the fewest packages. A good result is the phone that:

1. does the things the user actually needs;
2. has few unnecessary apps and accounts;
3. keeps important files local when practical;
4. does not require constant troubleshooting;
5. can be understood and changed one component at a time.

## Pause point

After roughly an hour and a half of setup and discussion, the user chose to stop and take a break. The archive should preserve that pause as part of the process rather than implying that every remaining issue needs to be solved immediately.
