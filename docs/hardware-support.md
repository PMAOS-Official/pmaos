# PMAOS hardware support matrix

Last reviewed: **2 November 2026**. Scope: PMAOS Mobile feature phones. Chipset validation, a device demonstration and production acceptance are separate records.

## Current company confirmed chipset list

PMAOS confirmed the following validated chipsets on **27 October 2026**:

| Family | Chipsets | Scope |
|---|---|---|
| ASR | ASR3602, ASR3603, ASR3605 | Company confirmed platform validation; features and memory depend on the board / build |
| UNISOC | T107, T117, T127 | Company confirmed platform validation; T127 also has the separately documented records below |
| Beken | BK7259 | Company confirmed validation; no specific feature phone device memory or delivery stage published here |

This list does not assign 64MB RAM, the same peripheral support, the same application features or the same production status to every chipset. A missing device level record does not revoke the company's platform confirmation.

## Configuration statements

| Configuration | Company confirmed scope |
|---|---|
| 8MB RAM + 16MB Flash | Regular PMAOS minimum, 27 October 2026; feature set is product dependent |
| 4MB RAM + 4MB Flash | Separate complete hybrid voice assistant configuration; not every feature combination |

Neither is an independent all board qualification matrix. See [Feature phone capabilities](feature-phone-capabilities.md).

## Device and build records

| Device / record | Documented status and scope | Boundary |
|---|---|---|
| Newer Uleway T127 hardware | Company supplied demonstration reviewed 2 November: startup, WeChat interaction, marketplace / 2048, Chinese voice command opening camera and Vii playback. WhatsApp separately confirmed usable. | Specific model, RAM / Flash, board revision and firmware not published; do not inherit old device parameters |
| Historical T127 / 64MB | Company reported production / initial commercial deployment; communications, media, applications, runtime, system services and AI connectivity | Historical configuration; not universal minimum or proof of every new feature |
| T127 reference assistant build | Supplied written summary records a September 2026 voice / TTS / tool action acceptance scope | A separate reference build; no automatic association with the newer Uleway video |
| ASR3605 reference device | Supplied summary records an October application launch / return regression for calculator, clock, SMS UI and recorder | Does not establish SMS delivery, recorder business acceptance or every newer ASR3605 variant |
| New ASR3603 port | Supplied summary describes UI / key integration and work on additional connectivity | Do not transfer T127 connected app results or a generic chipset confirmation into this specific build |

## September historical baseline

The September public matrix listed **UNISOC T127 / 64MB total device RAM** as production / initial commercial deployment and **ASR3605** as POC completed, with no ASR RAM figure. Those statements describe the then documented baseline. They are retained as history, not a complete current chipset list. [Original matrix at the prior public revision](https://github.com/PMAOS-Official/pmaos/blob/852b01fef5af0858ff8f3fd14353ab04a704845c/docs/hardware-support.md).

64MB means total device RAM, not free RAM or AI model memory. It is **not a universal PMAOS minimum**. Hardware support depends on the BSP, drivers, display, keypad, audio, modem and enabled services of the intended product.

## Related

- [Feature phone capabilities](feature-phone-capabilities.md)
- [Release status](release-status.md)
- [Historical 64MB test method](64mb-test-method.md)
