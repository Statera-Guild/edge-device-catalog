# CMP-EAM-0021 — Renesas RZ/V2H

## Component identity and governance

| Field | Value |
|---|---|
| Component ID | `CMP-EAM-0021` |
| Guild / class | Compute (`CMP`) / Edge AI Module (`EAM`) |
| Manufacturer | Renesas |
| Product / family | RZ/V2H |
| Device form | Vision AI SoC |
| Exact part number | TBD — Renesas RZ/V2H family; exact ordering part number TBD |
| Status | `documented` (public manufacturer information only; PAI-SG not validated) |
| Supplier ID | TBD |
| Last reviewed | 2026-10-09 |
| Evidence tier | Manufacturer information; application performance not independently tested |

## Hardware and performance profile

| Property | Manufacturer-based description / open question |
|---|---|
| Processing architecture | Arm Cortex-A55 application cores, Cortex-R8 real-time cores and DRP-AI3 accelerator; exact clocks and configurations depend on SKU |
| AI throughput | DRP-AI3 vendor literature cites up to 80 TOPS in selected conditions; precision, sparsity and test assumptions must be recorded before comparisons |
| RAM and storage | TBD per exact SoC, module, carrier and BOM; no module specification inferred from chip |
| Power | Idle / typical / sustained peak and complete-board input watts TBD by measurement |
| Camera and sensor I/O | Interface counts, lanes, voltage and supported sensor drivers TBD for chosen SKU and board |
| Robot control I/O | CAN/CAN-FD, UART, SPI, GPIO, Ethernet and timing behavior require carrier-specific verification |
| Software | Linux/BSP, AI runtime, compiler, driver and ROS 2 compatibility matrix TBD |
| Security / safety | Secure boot, update strategy, watchdog and safety claims must be checked for exact device |
| Environmental | Temperature range, vibration, shock, EMC and lifecycle evidence TBD |

## PAI-SG integration assessment

**Candidate workloads:** Vision processing, multi-camera perception, detection and segmentation; real-time control must be independently engineered. These are design hypotheses, not measured real-time capability or approved robot safety functions.

**Boundary:** AI inference and perception are separate from emergency stop, functional safety and hard real-time motor control. Any safety-related claim requires a separate hazard analysis and appropriate controller architecture.

## Preliminary vendor and integration risks

| Risk theme | Engineering concern | Evidence / mitigation to collect |
|---|---|---|
| Ecosystem / SDK | DRP-AI3 compiler/toolchain portability; BSP maturity; camera interface and sensor support; power and thermal envelopes | Obtain official SDK, licensing, compiler/operator and lifecycle documentation |
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

- https://www.renesas.com/en/products/microcontrollers-microprocessors/rz-mpus/rzv2h-high-performance-ai-mpu

## Publication boundary

Public catalog entry only. `documented` means the product is described from available manufacturer materials, **not** PASG-verified, certified, recommended or production-qualified. Do not publish private quotations, internal BOMs or raw proprietary validation evidence in this repository.
