# Phoneme Transport Architecture

## Status

Research direction connected to the text-first communication architecture.

This document preserves the idea that speech might be converted into a compact phonetic representation before transmission, and that the same or a related representation could support multilingual interaction.

It is deliberately exploratory.

## Core idea

Instead of treating speech as:

microphone → audio → network → speech recognition → text

investigate an alternative pipeline:

microphone → speech/phonetic analysis → phoneme representation → network → linguistic reconstruction

A related architecture could operate in both directions:

speech → phonemes → language representation → text/speech

and:

text/language representation → phonemes → speech synthesis

## Why this is interesting

The proposed representation could potentially separate:

- physical speech signal;
- phonetic content;
- language identification;
- lexical interpretation;
- text;
- synthesized speech.

That separation could allow the network to carry a compact linguistic representation instead of continuous audio.

## Important distinction

A phoneme sequence is not automatically equivalent to text.

Phonemes do not necessarily preserve:

- word boundaries;
- spelling;
- punctuation;
- capitalization;
- homophones;
- morphology;
- speaker identity;
- prosody;
- emotion;
- timing;
- non-speech sounds.

Therefore the research must not assume that phoneme transmission is lossless.

## Multilingual possibility

A language-neutral phonetic notation could potentially provide an intermediate layer between languages.

However, "phoneme" is not completely language-independent. Phoneme inventories and phonological distinctions differ by language.

The research should therefore compare:

- language-specific phoneme sets;
- a universal phonetic representation;
- IPA-like representations;
- learned discrete speech units;
- ordinary text;
- structured semantic intents.

## Microphone-to-representation problem

The first difficult transition is:

microphone → linguistic representation

This requires speech processing before the compact representation can be transmitted.

Candidate approaches include:

1. local automatic speech recognition producing text;
2. local phoneme recognition;
3. local language/phonetic classification;
4. compressed speech transmission to a remote recognizer;
5. hybrid local feature extraction followed by remote interpretation.

The watch should not assume that phoneme extraction is computationally cheaper than speech-to-text until this is measured.

## Reverse direction

For responses, investigate:

text → linguistic representation → phonemes → speech

This could permit a common intermediate representation before speech synthesis.

A particularly interesting research question is whether the same intermediate layer can support multiple languages without requiring a separate complete voice pipeline for each language.

## Candidate data model

A phonetic message could contain:

- representation version;
- language or language-probability metadata;
- phonetic units;
- word/segment boundaries where known;
- timing information where necessary;
- confidence values;
- optional prosodic information;
- optional speaker-independent voice parameters.

The first prototype should omit everything not required for the task.

## Experiments

Compare:

### A. Audio
Microphone → compressed audio → network → remote ASR.

### B. Text
Microphone → local ASR → text → network.

### C. Phoneme
Microphone → local phoneme recognizer → phoneme sequence → network → reconstruction.

### D. Hybrid
Microphone → local features/phonetic units → network → remote linguistic model.

Measure:

- byte count;
- energy;
- latency;
- recognition accuracy;
- multilingual performance;
- robustness to accents;
- robustness to background noise;
- correction rate;
- CPU requirements;
- memory requirements.

## Critical research question

The strongest version of the hypothesis is not:

> "Phonemes are better than text."

It is:

> **"Is there an intermediate linguistic representation that is substantially smaller than audio, more language-flexible than ordinary text, and computationally practical for a low-power wearable?"**

That is a testable research question.

## Relationship to the watch project

This architecture should remain optional.

The first watch prototype should not depend on proving the phoneme hypothesis.

The text-first architecture can proceed independently. If phoneme transport demonstrates measurable advantages, it can become a later communication layer.

## Possible future research paper

Working title:

**"Compact Linguistic Representations for Low-Power Voice Interfaces: Comparing Audio, Text, Phoneme, and Structured-Intent Communication"**

Potential contribution:

A reproducible measurement framework comparing communication size, energy, latency, accuracy, and multilingual capability across representation layers.

## Design principle

> **Keep the representation layer replaceable. Prove its advantage experimentally before making it foundational.**
