# Qualcomm Dragonwing IQ9 Series — IQ-9075 — PAI-SG Component Card

```yaml
component_id: CMP-EAM-0008
guild: CMP
class: EAM
manufacturer: Qualcomm
product_name: "Dragonwing IQ9 Series — IQ-9075"
exact_part_number: TBD
status: documented
supplier_id: TBD
last_reviewed: 2026-10-09
```

**Documentation status:** `documented` means public manufacturer material was reviewed; it does not mean independent PAI-SG validation, qualification, or certification. **Device form:** Industrial SoC; IQ-9075 EVK is a separate development kit. **PAI-SG categories:** E02, E04, E05, E06 (candidate mappings).

## Hardware and AI specification — manufacturer-reported / configuration-dependent

| Field | Information | Evidence boundary |
|---|---|---|
| Compute | 8-core Kryo; Adreno GPU; Hexagon AI acceleration; four real-time subsystem cores | Confirm exact SKU and board revision |
| AI performance | 50 or up to 100 dense TOPS variants; PMIC configuration differs; not a benchmark | Marketing peak is not measured robot throughput |
| Memory / storage | LPDDR5 support; board memory capacity and storage depend on design | Check production hardware BOM |
| Sensors / connectivity | Industrial interfaces and high GPIO availability; check pin mux, industrial buses and carrier schematic | SoC support is not equivalent to exposed board connectors |
| Software | Linux Yocto and Ubuntu vendor support; confirm version-specific BSP and acceleration toolchain | Check BSP, driver and license matrix |
| Power | Idle, sustained and peak system power: TBD | Measure at supply input, including cooling and sensors |
| Thermal / mechanics | Dimensions, heatsink, vibration and temperature qualification: TBD | Variant-specific engineering evidence required |
| Supply | Price, MOQ, lead time, EOL and supplier ID: TBD | Do not publish internal quotations |

## PAI-SG candidate workloads

This is a candidate for camera-based detection (YOLO/DETR), segmentation, multi-object tracking, and edge sensor fusion subject to deployment feasibility. SLAM, local planning, multi-camera synchronization, video transformers, VLM/VLA and real-time control require **separate** compatibility and latency testing; no support is inferred merely from nominal AI compute. Record workload, model version, dataset, precision, batch size, FPS, p50/p95/p99 latency, peak memory, average/peak power, temperature and throttling state.

**Safety architecture:** AI inference and ordinary application control must not replace an independently engineered safety function. Hardware real-time features do not alone establish IEC 61508, ISO 13849, IEC 62443 or other certification.

## Preliminary vendor and design risks

| Risk area | Concern / mitigation |
|---|---|
| Platform specificity | 50/100 TOPS variant confusion; SoC junction-temperature versus system ambient; safety-feature versus certification; custom carrier/PMIC integration; BSP maturity. Freeze exact SKU and carrier revision before design selection. |
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

1. https://www.qualcomm.com/internet-of-things/products/iq9-series/iq-9075
2. https://docs.qualcomm.com/bundle/publicresource/87-83840-1_REV_A_Qualcomm_IQ9_Series_Product_Brief.pdf

## Publication boundary

Public card: vendor-published facts, explicit unknowns and engineering hypotheses. Private SSOT: supplier quotations, internal BOM, raw tests and proprietary implementation details. Do not interpret `documented` as endorsed or independently verified.
