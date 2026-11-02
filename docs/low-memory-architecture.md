# PMAOS low memory architecture

Last reviewed: **2 November 2026**.

## Current memory statements

PMAOS confirms **8MB RAM + 16MB Flash** as its regular minimum and a separate **4MB RAM + 4MB Flash** complete hybrid voice assistant configuration (27 October 2026). Those configurations are not an independent per board qualification or a promise that all applications, cameras and media workloads run in the same footprint.

The older **T127 / 64MB total device RAM** record is a historical device configuration, not the universal OS minimum. RAM / Flash figures for the newer Uleway T127 demonstration have not been published; do not infer them from a chipset name or a previous board.

- RAM holds live stacks, heaps, audio, graphics and network buffers.
- Flash stores firmware, persistent assets and any local model data.
- Total device memory, an application memory pool, model file size and peak working memory are different measurements.
- A hybrid assistant uses remote resources where configured. The small memory figures do not establish an entirely local conversational LLM.

## Design mechanisms

The following public design description was documented for the historical T127 configuration. These mechanisms explain intended resource control, not a newly measured allocation or performance advantage for every current build. See [Feature phone capabilities](feature-phone-capabilities.md), [Hardware support](hardware-support.md) and [Historical 64MB test method](64mb-test-method.md).

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

Historical design description: September 2026. Current configuration review: 2 November 2026.
