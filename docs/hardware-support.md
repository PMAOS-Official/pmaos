# PMAOS Hardware Support Matrix

This page lists hardware platforms for PMAOS Mobile with their public validation status and publicly validated scope. See the [README](../README.md) for an overview of PMAOS, and [Release Status](release-status.md) for status definitions.

| Platform | RAM | Status | Publicly Validated Scope |
|---|---|---|---|
| UNISOC T127 | 64MB total device RAM | Production / initial commercial deployment | Communications, media, multiple applications, application runtime, system services, AI connectivity |
| ASR3605 | Not publicly specified | POC completed | Platform proof of concept |

## UNISOC T127

UNISOC T127 is the current primary mass-production platform for PMAOS Mobile.

For the documented T127 configuration:

- "64MB" is **total device RAM**.
- It is not free RAM.
- It is not AI model memory.
- It is not a universal PMAOS minimum requirement.

PMAOS does not claim that every T127 device supports the same set of PMAOS capabilities. Actual capabilities depend on the BSP, hardware configuration and product definition of the specific device.

## ASR3605

For the ASR3605 platform, the publicly disclosable statement is limited to: **POC completed**.

- This is not a production claim.
- No RAM figure is publicly specified for ASR3605.
- ASR3605 must not be assumed to use the 64MB configuration, or any configuration identical to the T127 platform, unless new publicly approved data becomes available.

## Related

- [64MB Test Method](64mb-test-method.md)
- [Release Status](release-status.md)

Last reviewed: September 2026
