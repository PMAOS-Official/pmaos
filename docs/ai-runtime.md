# PMAOS AI runtime and deployment model

Last reviewed: **2 November 2026**.

## Current assistant status

PMAOS confirmed on **27 October 2026** that its AI voice assistant is mature. The company confirms a regular 8MB RAM + 16MB Flash configuration and a separate 4MB RAM + 4MB Flash configuration supporting a complete hybrid voice assistant. These are company statements, not independent benchmarks or a claim that every runtime component is production ready.

ASR (automatic speech recognition), language processing and TTS (text to speech) use local and cloud resources according to the build. A complete assistant can span both locations. It does not imply a general purpose LLM runs entirely in 4MB or 8MB RAM.

## Concrete T127 examples

The supplied T127 engineering summary describes local input, audio recording, response display, audio playback and OS service execution, with connected ASR, language processing and TTS. Local action execution does not establish offline speech understanding.

A company supplied demonstration reviewed on **2 November 2026**, identified by PMAOS as newer **Uleway / UNISOC T127 hardware**, shows listening and thinking states followed by a camera preview after a Chinese “open camera” command. The specific firmware, latency and local / cloud allocation are not published. See [Feature phone capabilities](feature-phone-capabilities.md).

Historical T127 instructions describe a 300ms long press as the activation threshold. That number is not response latency. A demo action does not validate every command, general conversation, wake word path, offline model or all supported chipsets.

## Reading older documentation

The **POC / continuing iteration** label below describes the September 2026 overall runtime baseline. It must not be used as a current blanket label for the company confirmed mature assistant. Conversely, the newer assistant confirmation does not turn each old component or additional board into a production claim. See [Release status](release-status.md).

## Historical architecture: September 2026

The on-device components of the PMAOS AI runtime include:

- Local rules
- Lightweight neural networks
- Session context
- Model routing
- Cloud connectivity
- Permission checks
- Capability discovery
- Interface/version checks

Uses described for the historical on-device lightweight neural networks:

- Wake-word detection
- Voice activity detection (VAD)
- Fixed-intent classification
- Simple routing

Security-related behavior is described only at this level. Implementation details of security checks are not publicly documented.

## Public Processing Flow

For requests resolvable on-device:

```
User Input
    ↓
On-device Lightweight Processing
    ↓
Local Rule / Fixed Intent?
    ↓
Yes → Authorized Device Capability
    ↓
Execution
```

For low-confidence or complex semantic requests:

```
Low-confidence / Complex Semantic Request
    ↓
Model Routing
    ↓
Cloud General-Purpose LLM
    ↓
Response to Device
    ↓
Local Permission / Capability Check
    ↓
System Service / Application
```

In words: local rules and lightweight on-device neural networks handle wake-word detection, voice activity detection, fixed-intent classification and simple routing. Low-confidence or complex semantic requests are routed, via model routing, to cloud-based general-purpose language models. Responses are subject to local permission and capability checks before being delivered to system services or applications.

## Scope Boundary

PMAOS does not claim that a general-purpose LLM runs locally within the documented 64MB configuration.

## Related

- [Low-Memory Architecture](low-memory-architecture.md)
- [64MB Test Method](64mb-test-method.md)

Historical architecture last reviewed: September 2026
