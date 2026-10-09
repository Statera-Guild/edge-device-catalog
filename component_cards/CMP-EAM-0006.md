# Qualcomm Robotics RB3 Gen 2 Development Kit (QCS6490) — PAI-SG Component Card

```yaml
component_id: CMP-EAM-0006
guild: CMP
class: EAM
manufacturer: Qualcomm
product_name: "Robotics RB3 Gen 2 Development Kit (QCS6490)"
exact_part_number: TBD
status: documented
supplier_id: TBD
last_reviewed: 2026-10-09
```

**Documentation status:** `documented` means public manufacturer material was reviewed; it does not mean independent PAI-SG validation, qualification, or certification. **Device form:** Development kit / QCS6490 SoC. **PAI-SG categories:** E01, E02, E03 (candidate mappings).

## Hardware and AI specification — manufacturer-reported / configuration-dependent

| Field | Information | Evidence boundary |
|---|---|---|
| Compute | Qualcomm Kryo 670 octa-core; Adreno 643; Hexagon AI engine | Confirm exact SKU and board revision |
| AI performance | Up to 12 dense INT8 TOPS is QCS6490 family claim; validate kit and model configuration | Marketing peak is not measured robot throughput |
| Memory / storage | Core and Vision kits differ; 6 GB LPDDR4x and 128 GB flash are documented for Core Kit; confirm selected revision | Check production hardware BOM |
| Sensors / connectivity | Wi-Fi 6E, Bluetooth 5.2; MIPI CSI; USB, PCIe, UART, SPI, I2C and Ethernet depend on carrier | SoC support is not equivalent to exposed board connectors |
| Software | Qualcomm Linux and Android; verify SDK, QNN/AI Hub, BSP and ROS 2 compatibility | Check BSP, driver and license matrix |
| Power | Idle, sustained and peak system power: TBD | Measure at supply input, including cooling and sensors |
| Thermal / mechanics | Dimensions, heatsink, vibration and temperature qualification: TBD | Variant-specific engineering evidence required |
| Supply | Price, MOQ, lead time, EOL and supplier ID: TBD | Do not publish internal quotations |

## PAI-SG candidate workloads

This is a candidate for camera-based detection (YOLO/DETR), segmentation, multi-object tracking, and edge sensor fusion subject to deployment feasibility. SLAM, local planning, multi-camera synchronization, video transformers, VLM/VLA and real-time control require **separate** compatibility and latency testing; no support is inferred merely from nominal AI compute. Record workload, model version, dataset, precision, batch size, FPS, p50/p95/p99 latency, peak memory, average/peak power, temperature and throttling state.

**Safety architecture:** AI inference and ordinary application control must not replace an independently engineered safety function. Hardware real-time features do not alone establish IEC 61508, ISO 13849, IEC 62443 or other certification.

## Preliminary vendor and design risks

| Risk area | Concern / mitigation |
|---|---|
| Platform specificity | Core vs Vision kit SKU ambiguity; QNN operator coverage; camera BSP; board-specific power; procurement. Freeze exact SKU and carrier revision before design selection. |
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

1. https://www.qualcomm.com/developer/hardware/rb3-gen-2-development-kit
2. https://docs.qualcomm.com/doc/87-79891-1/87-79891-1_REV_B_Qualcomm_Dragonwing_RB3_Gen_2_Core_Kit_Product_Brief.pdf
3. https://docs.qualcomm.com/doc/87-28733-1/87-28733-1_REV_F_QUALCOMM_QCS6490_QCM6490_Processors_Product_Brief.pdf

## Publication boundary

Public card: vendor-published facts, explicit unknowns and engineering hypotheses. Private SSOT: supplier quotations, internal BOM, raw tests and proprietary implementation details. Do not interpret `documented` as endorsed or independently verified.
