# PMAOS AI Runtime and Deployment Model

Status: **POC / continuing iteration**. This is not a production claim. See [Release Status](release-status.md) for status definitions, and the [README](../README.md) for an overview of PMAOS.

## Architecture

The on-device components of the PMAOS AI runtime include:

- Local rules
- Lightweight neural networks
- Session context
- Model routing
- Cloud connectivity
- Permission checks
- Capability discovery
- Interface/version checks

Publicly validated uses of the on-device lightweight neural networks:

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

Last reviewed: September 2026
