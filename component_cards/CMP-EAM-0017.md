# AM69A — PAI-SG Component Card

- **Component ID:** CMP-EAM-0017
- **Guild / class:** Compute (CMP) / Edge AI Module (EAM)
- **Manufacturer:** Texas Instruments
- **Product:** AM69A
- **Device form:** SoC
- **Exact part number / revision:** TBD — family or evaluation configuration, not a unique orderable SKU
- **Supplier ID:** TBD
- **Status:** documented (manufacturer sources; **not** independent PAI-SG validation)
- **Last reviewed:** 2026-10-09
- **PAI-SG categories:** E02 Vision AI; E03 Autonomous Navigation; E05 Industrial Edge Computing

## Hardware and AI specifications

| Field | Manufacturer-documented / engineering description | Evidence boundary |
|---|---|---|
| Processing / acceleration | Up to eight Cortex-A72 at 2 GHz; up to four deep-learning accelerators; Cortex-R5F and VPAC | Check exact SKU and accelerator enablement |
| AI performance | Up to 32 TOPS total manufacturer peak; not robot throughput | Peak arithmetic capability is not sustained robot FPS |
| Memory / storage | External memory and board-specific storage TBD | Record installed RAM and storage of chosen device |
| Sensor / control I/O | Camera pipelines, ISP, Ethernet, PCIe and other SoC I/O; carrier-level pinout TBD | SoC pin capabilities are not guaranteed on all boards |
| Software / SDK | TI Processor SDK / Edge AI tools; model/operator and SDK version TBD | Verify exact BSP, OS, kernel, compiler and runtime |
| Power | Idle, typical, peak, input voltage: TBD | Measure device and full robot separately |
| Thermal / physical | Package or board size, heatsink, temperature, shock, vibration: TBD | Source exact hardware revision |
| Security / safety | Security features and certifications: TBD for exact SKU | Never infer complete-system safety certification |

## PAI-SG design suitability

**Candidate workloads:** Multi-camera perception, detection, tracking, segmentation and AMR sensor fusion. These are potential integration scenarios, **not** measured accuracy, FPS, deterministic latency, ROS 2 interoperability or production readiness. Detection, tracking, segmentation, SLAM and VLM/VLA capability must be evaluated per model and hardware configuration.

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
| Device-specific boundary | TI product page notes third-party partner support; confirm technical support channel | Check datasheet, part number, SDK and production integration |

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

1. [Texas Instruments product information](https://www.ti.com/product/AM69A)

## Publication and governance notes

Public reference card only. `documented` means manufacturer-backed description, **not** verified, certified, recommended or PASG-approved. No proprietary supplier quotations, internal BOM or raw private evidence should be published. Recheck the exact part number and datasheet revision before procurement.
