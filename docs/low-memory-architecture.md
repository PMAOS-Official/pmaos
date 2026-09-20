# PMAOS Low-Memory Architecture

This page describes the public low-resource design mechanisms that allow PMAOS Mobile to operate within 64MB total device RAM on the documented UNISOC T127 production platform. See the [README](../README.md) for an overview of PMAOS, and [Release Status](release-status.md) for status definitions.

Mechanisms are described at the level of what each one does and why it matters on resource-constrained devices. Internal implementation details are not publicly documented.

## Compile-Time Trimming

Removes unused components at build time. On resource-constrained devices this keeps the system footprint proportional to what the product actually uses, instead of carrying generic overhead.

## Controlled Dynamic Memory Allocation

Constrains and supervises dynamic allocation at runtime. This limits heap fragmentation and makes memory exhaustion behavior predictable on devices with no swap space.

## Preallocated Resource Pools

Allocates fixed pools for known workload types up front. Pool-based reuse avoids repeated allocate/free cycles and bounds worst-case memory demand.

## Unified / Shared Buffers

Shares buffers across subsystems where safely possible. This reduces the total amount of memory that must be reserved for duplicated data movement paths.

## Zero-Copy Messaging

Passes messages between components by reference rather than by copying payloads. This reduces both peak memory usage and CPU time on low-bandwidth, low-memory hardware.

## Deterministic Memory Partitioning

Partitions memory into dedicated regions with defined owners and budgets. This makes per-component memory behavior observable and prevents unbounded cross-component growth.

## Process / Task Isolation

Separates system components into isolated processes or tasks. On constrained devices this contains faults and keeps memory accounting attributable, without requiring heavyweight virtualization.

## Related

- [AI Runtime](ai-runtime.md)
- [64MB Test Method](64mb-test-method.md)

Last reviewed: September 2026
