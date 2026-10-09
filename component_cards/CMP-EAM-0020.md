# Raspberry Pi 5 + AI HAT+ — PAI-SG Component Card

- **Component ID:** CMP-EAM-0020
- **Guild / class:** Compute (CMP) / Edge AI Module (EAM)
- **Manufacturer:** Raspberry Pi
- **Product:** Raspberry Pi 5 + AI HAT+
- **Device form:** Integrated evaluation configuration (SBC + PCIe AI HAT)
- **Exact part number / revision:** TBD — family or evaluation configuration, not a unique orderable SKU
- **Supplier ID:** TBD
- **Status:** documented (manufacturer sources; **not** independent PAI-SG validation)
- **Last reviewed:** 2026-10-09
- **PAI-SG categories:** E01 Low-Power Edge AI; E02 Vision AI; E03 Autonomous Navigation

## Hardware and AI specifications

| Field | Manufacturer-documented / engineering description | Evidence boundary |
|---|---|---|
| Processing / acceleration | Raspberry Pi 5 host: Broadcom BCM2712 quad Cortex-A76; HAT+: Hailo-8L or Hailo-8 | Check exact SKU and accelerator enablement |
| AI performance | 13 TOPS INT8 (Hailo-8L) or 26 TOPS INT8 (Hailo-8), variant-specific | Peak arithmetic capability is not sustained robot FPS |
| Memory / storage | Host RAM is Raspberry Pi 5 RAM; AI HAT+ does not provide independent 8GB model RAM | Record installed RAM and storage of chosen device |
| Sensor / control I/O | AI HAT+ attaches over Raspberry Pi 5 PCIe; CSI cameras on host; robot I/O requires peripherals | SoC pin capabilities are not guaranteed on all boards |
| Software / SDK | Raspberry Pi OS, rpicam-apps/Picamera2 and Hailo runtime; exact releases TBD | Verify exact BSP, OS, kernel, compiler and runtime |
| Power | Idle, typical, peak, input voltage: TBD | Measure device and full robot separately |
| Thermal / physical | Package or board size, heatsink, temperature, shock, vibration: TBD | Source exact hardware revision |
| Security / safety | Security features and certifications: TBD for exact SKU | Never infer complete-system safety certification |

## PAI-SG design suitability

**Candidate workloads:** Low-cost detection, segmentation, pose estimation and robotics prototype. These are potential integration scenarios, **not** measured accuracy, FPS, deterministic latency, ROS 2 interoperability or production readiness. Detection, tracking, segmentation, SLAM and VLM/VLA capability must be evaluated per model and hardware configuration.

**Architecture boundary:** Safety-critical motion, emergency stop and braking remain on separately engineered and validated control systems; inference output is advisory unless a system safety case demonstrates otherwise.

## Preliminary vendor and integration risks

| Risk | Design consequence | Required verification / mitigation |
|---|---|---|
| Peak TOPS versus sustained inference | Vendor TOPS cannot predict FPS or end-to-end latency | Benchmark exact model, dataset, pre/postprocessing, FPS, P95/P99 and watts |
| BSP / SDK dependency | Model operators, quantization and OS support may differ | Pin versions; maintain ONNX export and conversion test matrix |
| Thermal and power | Throttling or brownouts may affect robot perception | Measure idle/typical/peak, enclosure temperature and sustained load |
| Sensor / robot interfaces | Camera, LiDAR, CAN and time synchronization may need external hardware | Validate actual carrier board and sensor SKUs |
| Supply / lifecycle | Module variants, lead time, EOL and price are unknown | Confirm orderable SKU, vendor lifecycle and supplier quote |
| Security and functional safety | AI inference is not a safety-rated controller | Use separate validated safety chain and threat modeling |
| Device-specific boundary | AI HAT+ is not AI HAT+ 2: latter uses Hailo-10H and supports distinct GenAI workloads | Check datasheet, part number, SDK and production integration |

## Mandatory Component Card completion tracking

| Category | State / next evidence |
|---|---|
| Identity and part number | Vendor/product documented; orderable SKU, board revision, supplier ID TBD |
| CPU / GPU / NPU and precision | Architecture documented; precision, sparsity and TOPS methodology need part-specific confirmation |
| Memory / storage | Installed capacity, bandwidth and endurance TBD |
| Power / thermal | Idle, typical, peak and throttling measurements TBD |
| Mechanical / environmental | Dimensions, temperature, vibration, shock, ingress and mounting TBD |
| Sensor and control I/O | Carrier pinout, camera/LiDAR, CAN, EtherCAT and synchronization TBD |
| Software / security | OS, kernel, ROS 2, BSP, SDK, boot security and update policy TBD |
| AI workloads | Model conversion, accuracy, FPS, P95/P99 latency and sustained load: not tested |
| Procurement | Price, MOQ, lead time, lifecycle, regional availability TBD |
| Validation | Dataset, model revision, power, raw evidence and repeatability: **not tested** |

## Official manufacturer references

1. [Raspberry Pi product information](https://www.raspberrypi.com/documentation/accessories/ai-hat-plus.html)

## Publication and governance notes

Public reference card only. `documented` means manufacturer-backed description, **not** verified, certified, recommended or PASG-approved. No proprietary supplier quotations, internal BOM or raw private evidence should be published. Recheck the exact part number and datasheet revision before procurement.
