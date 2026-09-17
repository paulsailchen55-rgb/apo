# Setup Plan

## Goal

Build a simple Android phone configuration with minimal user-facing dependencies and no requirement for routine cloud synchronization.

## Current stack

| Function | Current choice | Account/cloud dependency | Status |
|---|---|---|---|
| AI / research / writing | ChatGPT | ChatGPT account | Keep |
| Keyboard / voice typing | FUTO Keyboard | Designed for offline voice input; verify performance on this device | Installed/test |
| Home screen | Fossify Launcher | No Fossify account required | Installed/test |
| Photos / video | Fossify Gallery | Local-first; no Fossify account | Installed |
| SMS / MMS | Fossify Messages | Carrier service for SMS/MMS; no Fossify account | Installed |
| Web | Firefox | No browser account required for basic use | Preferred |
| Banking | Bank app | Bank account required | Keep |
| Email | Gmail through Firefox | Gmail account required; no Gmail app required | Preferred first test |
| Local documents | Collabora Office | Local files can be used without a cloud account | Deferred |
| Passwords | KeePassDX | Local vault; no cloud account required | Deferred |

## Intentionally deferred

- Microsoft 365 / Word / Excel / PowerPoint;
- OneDrive;
- Google Photos;
- Google Drive for routine storage;
- additional cloud-sync applications;
- a separate mail client;
- KeePassDX;
- more Fossify apps unless a concrete need appears;
- alternative Android/Linux operating systems;
- aggressive removal of Android system packages.

## Testing method

Change one thing at a time. After each change, use the phone normally enough to determine whether a needed capability changed.

### FUTO Keyboard test

1. Keep the old keyboard available until FUTO is verified.
2. Set FUTO as the keyboard for a trial period.
3. Use natural speech rather than short test phrases.
4. Observe transcription latency and accuracy.
5. If the result is unacceptable, investigate the next option rather than installing several speech systems simultaneously.

### Speech Services test

Google Speech Services has been disabled because the user did not think they used it. If a needed Android function stops working, identify that function before deciding whether to restore the service.

Do not infer compromise from a broken feature or from the existence of a privileged accessibility/speech component.

## Gmail minimization

The first low-dependency approach is:

**Firefox → Gmail website**

This avoids making the Gmail app a permanent part of the device merely to read or send Gmail.

If browser access proves insufficient, consider a third-party mail client later.

## Documents

When document editing becomes necessary, try Collabora Office with local files first. Keep document storage local unless a specific collaboration or backup need justifies a cloud service.

## Stopping rule

If the phone is functioning acceptably, stop changing it.

The project succeeds when the phone becomes boring and predictable, not when every package has been analyzed.
