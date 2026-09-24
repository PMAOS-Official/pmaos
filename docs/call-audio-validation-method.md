# PMAOS Call Audio Validation Method

This page documents the method PMAOS uses to validate call noise reduction and voice enhancement on feature phones. It was applied to the basic-tier call audio work on the [UNISOC T127 production-device configuration](64mb-test-method.md). See the [README](../README.md) for an overview of PMAOS and [Hardware Support](hardware-support.md) for platform status.

## Core Principle

Call audio quality is judged by **what the far end of the call actually receives** — not by local playback, and not by the local uplink signal. The person you are calling never hears your local signal, so any tuning or claim that is not verified at the far end is not verified.

Handheld (earpiece) and speakerphone modes are validated **separately**: speakerphone changes mouth-to-microphone distance, room echo, and gain requirements, so parameters tuned for one mode cannot be assumed to work for the other.

## Test Device

- Platform: UNISOC T127
- RAM: 64MB total device RAM
- Microphone: single microphone (single-mic design)
- Audio paths: separate audio modes for handheld and speakerphone calls
- Device type: production-device configuration
- PMAOS version: Not publicly disclosed
- Test baseline: Results recorded as of September 2026

## Method

1. **Establish the original baseline.** With the call network, volume, grip position, and far-end device fixed, record the far-end received audio in every scenario below, for both handheld and speakerphone modes. Confirm the effective device configuration rather than assuming source-level defaults — a tunable option in source is not proof of the value the shipped device uses.
2. **Change one attributable group of parameters at a time.** Each tuning round modifies a single group that can be reasoned about in isolation.
3. **Compare blind against the original recordings.** Baseline recordings are retained and used as the blind reference for every subsequent comparison.
4. **Keep the fallback path.** The platform's native call processing remains available as a fallback; processing-mode and scenario switching must be smooth, with no audible artifacts at transitions.

## Scenario Matrix

Every mode is evaluated across seven uplink scenarios:

| # | Scenario | Examples | Primary risk to guard against |
|---|----------|----------|-------------------------------|
| 1 | Steady noise | Fan, air conditioning, engine | Suppression that also eats word endings |
| 2 | Wind | Walking outdoors, gusts | Wind bursts clipping the whole signal |
| 3 | Transient sounds | Impacts, keyboard, friction | Over-reaction that deletes speech onsets |
| 4 | Traffic, crowd, TV | Street, open office | A muffled near-end voice the far end cannot follow |
| 5 | Soft speech, whisper | Quiet talkers | Soft speech classified as noise and removed |
| 6 | Speakerphone echo, double talk | Hands-free calls | Double-talk breakup; residual echo; lost interruptions |
| 7 | Shouting, close-range bursts | Excited speech, microphone near mouth | Clipping that no later stage can repair |

## Evaluation Dimensions

- **Intelligibility** — keyword or sentence correctness at the far end.
- **Listening quality** — blind listening with separate ratings for speech quality, background noise, and overall quality, following the rating-dimensions approach of [ITU-T P.835](https://www.itu.int/rec/T-REC-P.835/en).
- **Side effects** — clipped sentence onsets or lost word endings; deleted soft speech or whispers; double-talk breakup; residual echo; audible processing-switch artifacts.
- **Device cost** — added latency, call stability, processing time, memory, battery.

## Pass Rule

- In target noise scenarios, far-end intelligibility or overall listening quality must improve.
- In quiet environments, soft speech, and double-talk, there must be no perceptible regression.
- Quantitative improvement figures are reported only after baseline measurements are completed for a given configuration; estimated values are never reported as achieved results.

## Capability Status

| Tier | Scope | Status |
|------|-------|--------|
| Basic — platform parameter tuning | Per-mode tuning of native noise suppression, gain, limiting, and echo handling | Completed and validated on the production-device configuration *(Internal test status)* |
| Advanced — lightweight scene processing | Scene detection, adaptive suppression strength, weak-speech protection on the uplink PCM path | Under evaluation — depends on verified access to the uplink PCM path, which is not yet confirmed on this platform |
| High — complex-scenario enhancement | Stronger speech enhancement, target-speaker processing | Research direction; not a delivery commitment |

Public research context: [RNNoise](https://github.com/xiph/rnnoise) is a plausible reference candidate for the advanced tier (subject to verified sampling adaptation, memory, and per-frame timing on the target platform); whisper-enhancement research such as WESPER belongs to the high tier.

## Known Limitations

- A single microphone cannot reliably separate two speakers talking at similar volume at the same time.
- Speech already lost to clipping at capture, or a heavily occluded microphone port, cannot be reliably restored downstream.
- Stronger suppression is not inherently better: suppression strength trades directly against speech survival.

## Disclaimer

This method and its status descriptions apply to the documented T127 production-device configuration. They are not universal performance guarantees for every PMAOS device, every T127 device, or every single-microphone device.

Last reviewed: September 2026
