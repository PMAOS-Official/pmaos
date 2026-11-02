# PMAOS release status

Last reviewed: **2 November 2026**. Status is tracked per capability, device and release. A dated POC label is not a current blanket assessment of the product family.

## Current statements and demonstration scope

| Component / capability | Current public statement | Evidence scope |
|---|---|---|
| PMAOS Mobile | Feature phone OS and application platform; historical T127 production baseline retained | Company reported production record, not a claim of all board feature parity |
| AI voice assistant | Mature, company confirmed 27 October 2026 | Hybrid local and cloud configuration; does not reclassify every runtime component as production |
| Regular configuration | 8MB RAM + 16MB Flash | Company confirmation; exact enabled product features must be specified |
| Specific complete hybrid assistant | 4MB RAM + 4MB Flash | Company confirmation for that assistant configuration |
| Newer Uleway T127 | Functional device demonstration reviewed 2 November | Startup, keypad interaction, WeChat, marketplace / 2048, voice opening camera, Vii playback |
| WhatsApp on the described Uleway T127 solution | Available, company confirmed 2 November | Not shown in the reviewed video; specific messages, calling, account and regional scope require a build specification |
| ASR3602/3603/3605, T107/T117/T127, BK7259 | Company confirmed validated chipsets | Board / build / feature and commercial status remain separate |
| General purpose conversational LLM entirely local in the confirmed small memory configurations | Not claimed | Complete hybrid experience does not mean all processing is local |

## Historical public baseline: September 2026

| Component / platform | Status recorded then |
|---|---|
| PMAOS Mobile on UNISOC T127 / 64MB total device RAM | Production / initial commercial deployment |
| Overall PMAOS AI Runtime | POC / continuing iteration |
| ASR3605 platform integration | POC completed |
| General purpose LLM locally on documented 64MB configuration | Not claimed |

[Original release record at the prior public revision](https://github.com/PMAOS-Official/pmaos/blob/852b01fef5af0858ff8f3fd14353ab04a704845c/docs/release-status.md). Retain these historical statements when interpreting old articles. The current mature assistant confirmation and demonstration are additional evidence, not a retroactive change to the old tests or proof that every component is production ready.

## Status definitions

- **Company confirmed:** a technical or availability statement from PMAOS; attribute it as such.
- **Demonstrated:** an observed operation on a specific device; scene transitions and untested functions remain outside scope.
- **Written acceptance record:** the supplied record states that a particular check passed on a particular build. It is not a new independent test.
- **Production:** the component has shipped in a specific production configuration. Do not infer this from a demonstration alone.
- **POC:** a technical path was validated at the recorded point in time; it is not a production deployment claim.
- **Development / planned:** integration work or a future goal; not evidence of delivered capability.

The newer Uleway video's model, firmware, memory and recording date are not published. No new actual shipment count, performance benchmark, safety certification, payment, subscription, OTA or full offline AI claim is added.

## Related

- [Feature phone capabilities](feature-phone-capabilities.md)
- [Hardware support](hardware-support.md)
- [AI runtime](ai-runtime.md)
