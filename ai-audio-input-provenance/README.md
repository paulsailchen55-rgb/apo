# AI Audio Input Provenance

## Status
Potential project / research and prototype concept.

## Purpose
Explore ways for AI assistants to distinguish live human speech from playback of previously recorded speech, while continuing to support both input types.

## Origin
The project emerged from an experiment using a Philips VoiceTracer. A recorded voice was played through the recorder's speaker while the ChatGPT microphone captured the playback. The experiment is part of a broader workflow for recording spoken notes outdoors and later transferring them to an AI assistant.

## Core questions
- Can an AI system distinguish live speech from recorded playback reliably?
- What acoustic, metadata, device, or user-provided signals could help?
- How should uncertainty be reported?
- Should recorded and live speech both remain usable?
- Could a common specification work across ChatGPT, Claude, Gemini, and other AI systems?
- What privacy and security risks arise from audio-source classification?

## Initial design principle
The system should report uncertainty rather than confidently claim to know whether speech is live when the available evidence is insufficient.

## Related experiments
1. VoiceTracer speaker playback into an AI microphone.
2. Direct transfer of the original audio file through cable or storage.
3. Comparison of transcription accuracy, context preservation, and ease of use.

## Scope boundary
This project is separate from the housing research discussed during the same recording session. The housing discussion may be linked as a use case but should be archived independently.
