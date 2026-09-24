# PMAOS

**PMAOS** stands for **Personal Mobile AI Operating Systems**.

PMAOS Mobile is a low-resource AI-native operating system and application platform for feature phones and resource-constrained devices.

PMAOS Mobile targets feature phones and low-resource communication terminals. It is designed to deliver a complete mobile experience — communications, media, applications and AI connectivity — on hardware with severely constrained memory and compute resources.

## Publicly Validated Production Platform

The primary mass-production platform currently validated in public:

| Platform | RAM | Status |
|---|---|---|
| UNISOC T127 | 64MB total device RAM | Production / initial commercial deployment |

Note: "64MB" refers to **total device RAM**. It is not free RAM, and it is not AI model memory.

## Publicly Documented Production Capability Scope

On the documented UNISOC T127 / 64MB configuration, the publicly documented production capability scope includes:

- Communications
- Media
- Multiple applications
- Application runtime
- System services
- AI connectivity

## AI

In the documented 64MB configuration, PMAOS uses an on-device AI runtime, lightweight neural networks and device-cloud routing. Complex semantic processing is handled by cloud-based general-purpose language models.

- **AI Runtime status: POC / continuing iteration** — see [AI Runtime](docs/ai-runtime.md) and [Release Status](docs/release-status.md).

## Documentation

| Documentation | Purpose |
|---|---|
| [Hardware Support](docs/hardware-support.md) | Publicly validated hardware platforms |
| [64MB Test Method](docs/64mb-test-method.md) | Test boundaries and documented internal test results |
| [AI Runtime](docs/ai-runtime.md) | Device-cloud AI architecture and current maturity |
| [Low-Memory Architecture](docs/low-memory-architecture.md) | Public low-resource design mechanisms |
| [Release Status](docs/release-status.md) | Production / POC status boundaries |

Technical status last reviewed: September 2026
