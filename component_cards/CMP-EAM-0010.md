# AMD Kria K26 System-on-Module — PAI-SG Component Card

```yaml
component_id: CMP-EAM-0010
guild: CMP
class: EAM
manufacturer: AMD
product_name: "Kria K26 System-on-Module"
exact_part_number: TBD
status: documented
supplier_id: TBD
last_reviewed: 2026-10-09
```

**Documentation status:** `documented` means public manufacturer material was reviewed; it does not mean independent PAI-SG validation, qualification, or certification. **Device form:** Production SOM family (commercial / industrial variants); KV260/KR260 are separate starter kits. **PAI-SG categories:** E02, E03, E05, E06 (candidate mappings).

## Hardware and AI specification — manufacturer-reported / configuration-dependent

| Field | Information | Evidence boundary |
|---|---|---|
| Compute | Quad Cortex-A53 application CPU; dual Cortex-R5F real-time CPU; programmable logic and DSP slices | Confirm exact SKU and board revision |
| AI performance | FPGA/DPU implementation-dependent; no universal TOPS value without bitstream, model and clock | Marketing peak is not measured robot throughput |
| Memory / storage | 4 GB DDR4 and 16 GB eMMC per AMD commercial K26 SOM specifications | Check production hardware BOM |
| Sensors / connectivity | Programmable-logic interfaces; MIPI and industrial I/O require compatible carrier/bitstream | SoC support is not equivalent to exposed board connectors |
| Software | AMD Vitis/Vivado/PetaLinux toolchain; version and accelerator image must be pinned | Check BSP, driver and license matrix |
| Power | Idle, sustained and peak system power: TBD | Measure at supply input, including cooling and sensors |
| Thermal / mechanics | Dimensions, heatsink, vibration and temperature qualification: TBD | Variant-specific engineering evidence required |
| Supply | Price, MOQ, lead time, EOL and supplier ID: TBD | Do not publish internal quotations |

## PAI-SG candidate workloads

This is a candidate for camera-based detection (YOLO/DETR), segmentation, multi-object tracking, and edge sensor fusion subject to deployment feasibility. SLAM, local planning, multi-camera synchronization, video transformers, VLM/VLA and real-time control require **separate** compatibility and latency testing; no support is inferred merely from nominal AI compute. Record workload, model version, dataset, precision, batch size, FPS, p50/p95/p99 latency, peak memory, average/peak power, temperature and throttling state.

**Safety architecture:** AI inference and ordinary application control must not replace an independently engineered safety function. Hardware real-time features do not alone establish IEC 61508, ISO 13849, IEC 62443 or other certification.

## Preliminary vendor and design risks

| Risk area | Concern / mitigation |
|---|---|
| Platform specificity | FPGA design effort; Vitis/PetaLinux version lock; PL timing closure; production carrier design; commercial vs industrial grade differences. Freeze exact SKU and carrier revision before design selection. |
| Toolchain lock-in | Export ONNX when practical; maintain reference CPU baseline and runtime compatibility tests. |
| Sensor interfaces | Verify camera/LiDAR/IMU part numbers, hardware timestamps, synchronization and driver versions. |
| AI performance | Benchmark actual deployed models at sustained thermal steady state; do not compare mixed precision TOPS. |
| Reliability and security | Evaluate secure boot, patch support, watchdogs, environmental qualification and threat model. |
| Procurement | Confirm manufacturer lifecycle, regional distributor, production SOM/SoC availability and change notices. |

## Mandatory card completion tracker

| Category | State / next action |
|---|---|
| Identification | Manufacturer and family documented; exact orderable part number / revision TBD |
| Device form | Identified above; board-specific variant still requires separate card |
| CPU / GPU / NPU / FPGA | Preliminary; per-SKU frequency and resources TBD |
| Precision / TOPS / model FPS | Vendor claim noted where available; end-to-end validation TBD |
| RAM / storage / memory bandwidth | Partial; exact SKU and carrier TBD |
| Idle / typical / peak power | TBD, instrumented test required |
| Physical / thermal / environmental | TBD, module vs enclosure separated |
| Camera / LiDAR / CAN / EtherCAT | Partial; verify real connector and driver |
| OS / BSP / ROS 2 / AI runtime | Partial; lock tested versions |
| Safety / cybersecurity | No PAI-SG certification claimed; evidence TBD |
| Supplier / price / MOQ / lead time / EOL | TBD; private sourcing evidence separate |
| Validation datasets / FPS / latency / watts | Not tested; evidence ID TBD |

## Manufacturer references

1. https://www.amd.com/ko/products/system-on-modules/kria/k26/k26c-commercial.html
2. https://docs.amd.com/r/en-US/ds987-k26-som
3. https://www.amd.com/content/dam/amd/en/documents/products/som/kria/k26/k26-product-brief.pdf

## Publication boundary

Public card: vendor-published facts, explicit unknowns and engineering hypotheses. Private SSOT: supplier quotations, internal BOM, raw tests and proprietary implementation details. Do not interpret `documented` as endorsed or independently verified.
