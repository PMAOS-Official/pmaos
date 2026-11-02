# PMAOS 64MB Evidence and Test Method

This page documents internal test observations from a production-device configuration based on the UNISOC T127 platform with 64MB total device RAM. See the [README](../README.md) for an overview of PMAOS, and [Hardware Support](hardware-support.md) for platform status.

## Current scope clarification: 2 November 2026

**64MB is not the universal PMAOS minimum.** PMAOS's 27 October company confirmation separately specifies a regular 8MB RAM + 16MB Flash configuration and a 4MB RAM + 4MB Flash complete hybrid assistant configuration. See [Current feature phone capabilities](feature-phone-capabilities.md).

This page preserves the older T127 test observations. No new timing, battery or stability measurement was made from the newer Uleway demonstration video. Its exact hardware revision, memory and firmware are not published. The figures below must not be transferred to that device, to the smaller configurations, or to other chipsets.

## Test Device

- Platform: UNISOC T127
- RAM: 64MB total device RAM
- Device type: Commercial production device
- PMAOS version: Not publicly disclosed
- Build ID / configuration: Not publicly disclosed
- Test baseline: Results recorded as of August 2026

## Historical internal test results: August 2026

### Cold Boot

Approximately 2 seconds. *(Internal test data)*

Measurement boundary: power-on → PMAOS ready for system interaction.

### Continuous Operation

Tens of hours, with current routine testing continuing until battery depletion without abnormal termination. *(Internal test data)*

Device sample count is not publicly disclosed. Testing coverage and accumulated duration continue to expand.

## Disclaimer

These figures are internal test observations for the documented T127 production configuration. They are not universal performance guarantees for every PMAOS device, every T127 device, or every 64MB device.

Original test record last reviewed: September 2026. Scope clarification added: 2 November 2026.
