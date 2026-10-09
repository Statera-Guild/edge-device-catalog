# CMP-EAM-0030 — Sophgo BM1684X

## Component identity and governance

| Field | Value |
|---|---|
| Component ID | `CMP-EAM-0030` |
| Guild / class | Compute (`CMP`) / Edge AI Module (`EAM`) |
| Manufacturer | Sophgo |
| Product / family | BM1684X |
| Device form | AI inference SoC / accelerator |
| Exact part number | TBD — BM1684X chip versus commercial board / SOM / PCIe card SKU TBD |
| Status | `listed` (manufacturer/product identity; specification validation pending) |
| Supplier ID | TBD |
| Last reviewed | 2026-10-09 |
| Evidence tier | Public product information; SKU-specific specifications and application performance not independently verified |

## Hardware and performance profile

| Property | Manufacturer-based description / open question |
|---|---|
| Processing architecture | Sophgo TPU inference architecture; integrated host resources and I/O depend on board |
| AI throughput | TBD for exact SKU, numeric precision, sparsity, compiler version and operating point; no cross-vendor TOPS ranking |
| RAM and storage | TBD per exact chip/module/board; distinguish onboard accelerator memory from host RAM |
| Power | Idle / typical / sustained peak watts and complete-system input watts TBD by measurement |
| Camera and sensor I/O | Check whether interfaces are native to chip or supplied by external host/carrier |
| Robot control I/O | CAN/CAN-FD, UART, SPI, GPIO and deterministic timing TBD; do not assume from accelerator name |
| Software | Sophgo TPU-MLIR / runtime toolchain and supported Linux distributions; license and driver provenance TBD |
| Security / safety | Secure boot, signed firmware, update path, watchdog and safety claims TBD for exact deployment |
| Environmental | Operating temperature, thermal derating, shock/vibration, EMC and product lifecycle TBD |

## PAI-SG integration assessment

**Candidate workloads:** Multi-camera perception and edge inference where supported runtime and carrier are available. These are design hypotheses, not measured FPS, latency, accuracy or real-time guarantees.

**Integration boundary:** Verify export restrictions, distribution and lifecycle by region; no unverified availability claim. Perception accelerators do not replace an independently validated emergency-stop and safety-control system.

## Preliminary vendor and integration risks

| Risk theme | Engineering concern | Evidence / mitigation to collect |
|---|---|---|
| Device identity | Silicon, reference board, module and accelerator card may have different interfaces and support | Obtain exact ordering part number, hardware revision and carrier schematic |
| SDK / compiler | Proprietary runtime, operator gaps, quantization effects and BSP version coupling | Export common ONNX test models; compile and log unsupported operators |
| Model portability | Detection, tracking and segmentation pipelines can include unsupported pre/post-processing | Measure accuracy delta, conversion failures and host CPU load |
| Sustained performance | Marketing TOPS does not establish end-to-end robot throughput | Benchmark FPS, P95/P99 latency, thermals, memory and system watts |
| Host and sensor integration | PCIe/USB/camera driver, DMA, timestamps and sync may require platform-specific work | Verify physical interface, Linux kernel/driver and actual sensor part numbers |
| Procurement and lifecycle | Supply, MOQ, EOL, support contracts and regional distribution unconfirmed | Request supplier evidence privately and publish only permitted summary |
| Security / reliability | Firmware provenance, patch cadence, boot chain and operating environment need assessment | Pin versions, maintain SBOM, run reliability and cybersecurity tests |

## Component Card completeness

| Requirement | Status |
|---|---|
| Identity, manufacturer and class | Listed; exact SKU/revision TBD |
| Compute architecture | Preliminary; part-specific datasheet required |
| AI throughput, precision and sparsity | TBD — no unsupported benchmark claims |
| RAM, storage, physical dimensions and cooling | TBD |
| Host interface, camera and robot control I/O | TBD for exact board |
| Software versions, licenses and ROS 2 integration | TBD |
| Security, reliability and lifecycle | TBD |
| Price, supplier, MOQ and lead time | TBD; internal commercial evidence kept private |
| Dataset, accuracy, FPS, P95/P99 latency, power | Not tested |

## Manufacturer reference (verify exact SKU before upgrading status)

- https://www.sophgo.com/

## Publication boundary

This public catalog entry is `listed`, not PASG-verified, certified, recommended or production-qualified. Do not publish private supplier quotations, internal BOMs or proprietary test evidence. Upgrade to `documented` only after checking the exact product's official datasheet and traceable specification sources.
