# PMAOS

**PMAOS** stands for **Personal Mobile AI Operating Systems**. PMAOS is a family of low resource AI native operating systems and application platforms for connected devices. **PMAOS Mobile** is the product line for feature phones and resource constrained communication terminals.

## Current feature phone facts

Technical status reviewed **2 November 2026**. These are PMAOS company statements and bounded company demonstration records, not independent benchmark results.

- **Regular minimum configuration:** 8MB RAM + 16MB Flash, company confirmed on 27 October 2026.
- **Separate hybrid voice assistant configuration:** 4MB RAM + 4MB Flash supports a complete device and cloud voice assistant. It is a specific configuration, not the minimum for every feature combination.
- **Company validated chipsets:** ASR3602, ASR3603, ASR3605; UNISOC T107, T117, T127; Beken BK7259. Features, memory layouts and commercial status depend on the board and release.
- **Uleway T127 demonstration:** a physical keypad phone on newer Uleway hardware demonstrates PMAOS startup, WeChat interaction, an app marketplace and 2048, a Chinese voice command opening the camera, and Vii short video playback.
- **WhatsApp:** PMAOS confirms availability on the described Uleway T127 solution. The reviewed video demonstrates WeChat, not WhatsApp. Message types, calling, account methods and market coverage must be specified for the delivered build.
- **AI voice assistant:** PMAOS describes it as mature in its 27 October company confirmation. The exact local and cloud split is configuration dependent; a complete hybrid assistant does not imply a general purpose LLM runs locally.

## Configuration and historical scope

The historical UNISOC T127 configuration with **64MB total device RAM** remains a company reported production / initial commercial deployment baseline. **64MB is not the universal PMAOS minimum.** The RAM and Flash of the newer Uleway demonstration phone have not been published and must not be inferred from that older device.

The September documents described the then overall AI runtime as **POC / continuing iteration** and ASR3605 integration as **POC completed**. These are dated historical statuses, not a current blanket label for the mature voice assistant or every supported platform. See [Release Status](docs/release-status.md).

## Documentation

| Documentation | Purpose |
|---|---|
| [Feature phone capabilities](docs/feature-phone-capabilities.md) | Current configuration, app, messaging, AI and demonstration scope |
| [Hardware support](docs/hardware-support.md) | Chipset list and separate device / build evidence |
| [AI runtime](docs/ai-runtime.md) | Current hybrid assistant and historical architecture |
| [Low memory architecture](docs/low-memory-architecture.md) | Memory terms, configuration boundaries and design mechanisms |
| [Release status](docs/release-status.md) | Current statements versus historical production and POC records |
| [64MB test method](docs/64mb-test-method.md) | Historical internal observations for one T127 configuration |

## Official product explanations

- [PMAOS feature phone operating system and application platform](https://www.pmaos.com/articles/pmaos-feature-phone-operating-system/)
- [Official Q&A](https://www.pmaos.com/qa.html)
- [Adding AI voice assistants to feature phones](https://www.pmaos.com/articles/how-to-add-ai-voice-assistants-to-feature-phones/)
- [Deploying AI on devices with limited RAM](https://www.pmaos.com/articles/how-to-deploy-ai-on-devices-with-limited-ram/)

Documentation update: **2026-11-02**. Historical measurements remain device specific. Application compatibility, service access and release acceptance must be confirmed for the intended product.
