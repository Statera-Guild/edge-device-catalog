# CMP-EAM-0022 — MediaTek Genio 1200

## Component identity and governance

| Field | Value |
|---|---|
| Component ID | `CMP-EAM-0022` |
| Guild / class | Compute (`CMP`) / Edge AI Module (`EAM`) |
| Manufacturer | MediaTek |
| Product / family | Genio 1200 |
| Device form | Edge AI SoC |
| Exact part number | TBD — MediaTek Genio 1200 platform; module/SKU TBD |
| Status | `documented` (public manufacturer information only; PAI-SG not validated) |
| Supplier ID | TBD |
| Last reviewed | 2026-10-09 |
| Evidence tier | Manufacturer information; application performance not independently tested |

## Hardware and performance profile

| Property | Manufacturer-based description / open question |
|---|---|
| Processing architecture | Octa-core Arm application processor with integrated GPU and AI processing unit; module memory, storage and interfaces depend on carrier |
| AI throughput | Vendor AI performance claims require exact APU precision, runtime and SKU; do not treat as measured FPS |
| RAM and storage | TBD per exact SoC, module, carrier and BOM; no module specification inferred from chip |
| Power | Idle / typical / sustained peak and complete-board input watts TBD by measurement |
| Camera and sensor I/O | Interface counts, lanes, voltage and supported sensor drivers TBD for chosen SKU and board |
| Robot control I/O | CAN/CAN-FD, UART, SPI, GPIO, Ethernet and timing behavior require carrier-specific verification |
| Software | Linux/BSP, AI runtime, compiler, driver and ROS 2 compatibility matrix TBD |
| Security / safety | Secure boot, update strategy, watchdog and safety claims must be checked for exact device |
| Environmental | Temperature range, vibration, shock, EMC and lifecycle evidence TBD |

## PAI-SG integration assessment

**Candidate workloads:** Multi-camera vision, perception gateways, embedded inference, ROS 2 experimentation where BSP supported. These are design hypotheses, not measured real-time capability or approved robot safety functions.

**Boundary:** AI inference and perception are separate from emergency stop, functional safety and hard real-time motor control. Any safety-related claim requires a separate hazard analysis and appropriate controller architecture.

## Preliminary vendor and integration risks

| Risk theme | Engineering concern | Evidence / mitigation to collect |
|---|---|---|
| Ecosystem / SDK | Vendor BSP/Android-Linux availability; APU SDK portability; long-term support; carrier and sensor drivers | Obtain official SDK, licensing, compiler/operator and lifecycle documentation |
| Model portability | Model operators, quantization and runtime may not translate from PyTorch/ONNX/TFLite | Maintain reference models; record conversion errors and unsupported operations |
| Sustained performance | Peak accelerator claims are not end-to-end robot throughput | Measure accuracy, FPS, P95/P99 latency, memory, temperature and watts |
| Sensor integration | Camera, IMU, LiDAR and network paths can be carrier/BSP specific | Verify actual part numbers, driver versions, sync and timestamping |
| Production / supply | Chip, SOM, development kit and commercial carrier are not interchangeable | Identify orderable SKU, supplier ID, MOQ, lead time and EOL policy |
| Security and reliability | Patch cadence, secure boot, thermal derating and environmental tests remain unknown | Maintain SBOM, BSP pinning and test reports in private evidence store |

## Component Card completeness

| Requirement | Status |
|---|---|
| Identity, manufacturer and class | Documented at family level; exact SKU TBD |
| Compute architecture | Partial — verify official part-specific datasheet |
| AI TOPS / precision / sparsity | Partial or TBD; not directly comparable across vendors |
| RAM, storage, physical size and cooling | TBD |
| I/O, camera and control compatibility | TBD for exact module/carrier |
| Software versions and licenses | TBD |
| Safety, security, reliability and lifecycle | TBD |
| Price, supplier, MOQ and lead time | TBD; internal commercial evidence not public |
| Benchmark dataset, accuracy, FPS, P95/P99 latency, power | Not tested |

## Official manufacturer reference

- https://www.mediatek.com/products/iot/genio-iot/genio-1200

## Publication boundary

Public catalog entry only. `documented` means the product is described from available manufacturer materials, **not** PASG-verified, certified, recommended or production-qualified. Do not publish private quotations, internal BOMs or raw proprietary validation evidence in this repository.
