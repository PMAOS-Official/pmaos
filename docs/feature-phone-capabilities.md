# PMAOS Mobile: feature phone capabilities

Last reviewed: **2 November 2026**. Scope: PMAOS Mobile feature phones. The broader PMAOS family also covers other connected device categories.

## Quick answer

PMAOS Mobile is a low resource phone operating system and application platform for manufacturers building communication terminals, including physical keypad phones. PMAOS confirms a regular minimum of **8MB RAM + 16MB Flash** and a separate **4MB RAM + 4MB Flash** configuration for a complete hybrid AI voice assistant. Its company validated chipset list includes ASR3602/3603/3605, UNISOC T107/T117/T127 and BK7259. Available apps, messaging services, media and AI functions depend on the target hardware, firmware and connected services.

## Memory configurations

| Record | RAM | Flash | Scope and source |
|---|---|---|---|
| Regular configuration | 8MB | 16MB | PMAOS technical confirmation, 27 October 2026; enabled features require a product specification |
| Specific hybrid voice assistant | 4MB | 4MB | Complete device and cloud voice assistant, company confirmed 27 October; not all feature combinations |
| Historical T127 production baseline | 64MB total device RAM | Not specified in the historical public test record | Dated production / initial commercial deployment statement; not a universal minimum |
| Newer Uleway T127 demonstration hardware | Not published | Not published | Device identity confirmed by PMAOS on 2 November; do not copy the older device's memory figures |

RAM is live working memory. Flash stores firmware, assets and persistent data. A model file size, an application memory pool and total device RAM are different quantities.

## Physical keypad demonstration reviewed on 2 November

PMAOS supplied a Chinese demonstration of approximately 62 seconds and confirmed that the device uses **UNISOC T127 on newer Uleway hardware**. The specific model, board revision, firmware and recording date have not been published. The video contains scene transitions; it is a functional example, not a continuous acceptance test or timing benchmark. The following summary comes from the visible operation and embedded Chinese subtitles.

| Approximate position | Observed operation | Supported description |
|---|---|---|
| 00:00–00:11 | Power key, PMAOS startup mark, main interface | PMAOS starts on the physical keypad demonstration phone |
| 00:12–00:24 | WeChat client, conversation view, press to record, new voice message bubble | WeChat interface and voice recording / submission interaction; the UI title reads WeChatOne |
| 00:25–00:41 | Marketplace, 2048 detail, loading progress, then game icon and changing board / score | A marketplace acquisition and subsequent launch / keypad gameplay example |
| 00:42–00:50 | Listening / thinking states, Chinese subtitle “open camera,” then changing camera preview | A Chinese voice command invoking the camera |
| 00:51–00:62 | Vii loading, video content and keypad navigation | Short video playback and browsing on the demonstration device |

The video does not establish network throughput, installation protocol, local model placement, boot latency, AI latency, battery life or a complete messaging delivery matrix. It does not show WhatsApp. No personal contact details from the demonstration are reproduced here.

## Messaging: WeChat and WhatsApp

**WeChat:** the reviewed Uleway T127 video shows the client, conversation view and a voice recording / submission flow. The client is identified as WeChat by PMAOS; the displayed UI title is WeChatOne. This is not a claim that an unmodified Android APK runs on the device or that every feature of the official smartphone client is available.

**WhatsApp:** PMAOS confirmed on 2 November 2026 that WhatsApp is also usable on the described Uleway T127 solution. This is a current company availability statement. It is not a new video test of WhatsApp.

The supplied engineering summary separately records an older T127 build passing a QR association flow into the chat list in September. Text, image and voice implementations are described there, but the reviewed record does not establish a complete real device test of every send / receive path. That older build is not automatically the newer Uleway firmware. Voice messages and real time voice / video calls are distinct capabilities.

An OEM specification should name the build, account / association method, supported message types, network and market conditions, service interfaces and commercial arrangements. Availability is not a promise of every capability in every region or on every board.

## How apps run and are installed

The supplied engineering summary describes local native **DAP / BIN** applications, system services and connected clients. Calculator, clock and games are examples of local application workloads. Networked messaging and content clients combine device code with backend services. This is not a general Android APK compatibility statement.

For the T127 Bazar application marketplace, historical written records cover a Debug build with TF storage and a Release build with a SIM, with different acceptance scopes. TF offline installation was limited to an authorized Debug configuration. The newer Uleway video additionally shows the marketplace / 2048 / gameplay sequence. Do not transfer a Debug installation policy to every released phone, or treat the video as verification of uninstall, update, payment, subscription or signing behavior.

## How the hybrid voice assistant works

ASR means automatic speech recognition; TTS means text to speech. PMAOS confirms a mature hybrid voice assistant using local and cloud resources, with the exact split depending on the configuration.

A supplied T127 reference implementation is described as:

1. The phone captures input and records audio locally.
2. Connected services perform ASR, language processing and TTS.
3. The phone displays responses and plays returned speech locally.
4. Supported tool requests invoke local OS services with the required checks or confirmation.

The Uleway demonstration adds a concrete Chinese “open camera” interaction. It does not establish offline recognition or a local conversational LLM. Historical T127 instructions describing a 300ms long press refer to an input trigger threshold, not an AI response time.

## Media and communication boundaries

Vii playback is visible on the Uleway T127 phone. Historical written T127 records also describe a local video client with connected content services. The video's exact delivery path, codec coverage and service arrangements are not published. A 4G status icon alone is not an operator compatibility test. Phone, SMS, messaging, media and AI each require their own product acceptance scope.

## Evidence and status

- **27 October 2026 company technical confirmation:** memory configurations, validated chipsets and mature hybrid assistant; also published in the official voice and RAM articles.
- **2 November supplied engineering summary:** device / build specific application, messaging and T127 AI flow records; original engineering files were not independently inspected or retested for this publication.
- **2 November supplied demonstration:** visible actions and Chinese subtitles reviewed; device identity and WhatsApp availability subsequently confirmed by PMAOS.
- **September public baseline:** retained in [Hardware Support](hardware-support.md), [Release Status](release-status.md) and the [64MB test record](64mb-test-method.md).

These are company provided materials. No independent certification, new performance benchmark, actual shipment count, universal offline capability or all model feature parity is asserted.

## Related official information

- [Feature phone overview and evaluation](https://www.pmaos.com/articles/pmaos-feature-phone-operating-system/)
- [Official Q&A](https://www.pmaos.com/qa.html)
- [Hardware support](hardware-support.md)
- [AI deployment](ai-runtime.md)
- [Release status](release-status.md)
