# NXP i.MX 8M Plus — PAI-SG Component Card

- **Component ID:** CMP-EAM-0011
- **Guild / class:** Compute (CMP) / Edge AI Module (EAM)
- **Manufacturer:** NXP
- **Product:** i.MX 8M Plus
- **Device form:** SoC
- **Exact part number / revision:** TBD (device family; do not equate evaluation boards with production devices)
- **Supplier ID:** TBD
- **Status:** documented (manufacturer documentation, **not** independent PAI-SG validation)
- **Last reviewed:** 2026-10-09
- **PAI-SG categories:** E01 Low-Power Edge AI; E02 Vision AI

## Hardware and AI specifications

| Field | Manufacturer-documented / engineering description | Evidence boundary |
|---|---|---|
| Processing | Quad Arm Cortex-A53 up to 1.8 GHz plus Cortex-M7 up to 800 MHz | Confirm exact SKU and clock/power mode |
| AI acceleration | Integrated NPU rated up to 2.3 TOPS (vendor peak) | Peak claims are not end-to-end throughput |
| Interfaces | Integrated ISP, MIPI CSI-2, display and industrial connectivity; exact carrier-board I/O varies | SoC/SOM capability differs from development-board connectors |
| Software | Linux BSP / eIQ ML software; verify release and model operator coverage | Pin versions before integration |
| RAM / storage | TBD for selected SKU and board | Do not infer capacity from reference design |
| Power | Idle, typical, peak, input voltage: TBD | Measure at board/system boundary |
| Thermal / mechanical | Dimensions, heatsink, operating temperature: TBD | Obtain part-specific datasheet |

## PAI-SG design suitability

**Candidate workloads:** Low-power camera inference, defect detection, HMI and supervisory perception. These are engineering candidates, not tested integration results. Robot motion safety, emergency stop and hard real-time guarantees require separately engineered and validated systems.

## Preliminary vendor and integration risks

| Risk | Design consequence | Required verification / mitigation |
|---|---|---|
| Hardware and ecosystem | 2.3 TOPS is not FPS; memory and thermal depend on board; M7 is not an independently certified safety controller | Confirm part number, lifecycle, reference design and supported toolchain |
| Peak AI rating versus application performance | Theoretical compute cannot predict robot FPS or P95/P99 latency | Run model-specific, sustained-load benchmarks including preprocessing |
| Software and BSP lifecycle | Drivers, kernels, inference runtimes and ROS 2 can be incompatible | Record exact version matrix; pin container and firmware releases |
| Thermal, power and sensor integration | Sustained performance and field reliability can degrade | Test actual carrier, camera/LiDAR, enclosure and ambient temperature |
| Procurement and supply | Pricing, MOQ, lead time, country of origin and EOL are unknown | Confirm distributor and production lifecycle independently |
| Cybersecurity / functional safety | AI capability does not imply safety certification | Perform threat analysis and independent safety architecture review |

## Mandatory Component Card completion tracking

| Category | State / next evidence |
|---|---|
| Identity and part number | Vendor/product documented; exact orderable SKU and board revision TBD |
| CPU / GPU / NPU and precision | High-level architecture documented; detailed precision and benchmark conditions TBD |
| Memory / storage | SKU-specific capacity, bandwidth and storage TBD |
| Power / thermal | Idle, typical, peak and throttling measurements TBD |
| Mechanical / environmental | Dimensions, temperature, vibration, shock and ingress rating TBD |
| Sensor and control I/O | Pinout, carrier design, camera compatibility, CAN/EtherCAT availability TBD |
| Software / security | BSP, kernel, ROS 2, SDK versions, secure boot and patch policy TBD |
| AI workloads | Detection, tracking, segmentation, SLAM and VLM feasibility require model-specific tests |
| Procurement | Supplier ID, price, MOQ, lead time and lifecycle TBD |
| Validation | Dataset, model revision, accuracy, FPS, P95/P99 latency, power, raw evidence: **not tested** |

## Official manufacturer and software references

1. [NXP product documentation](https://www.nxp.com/products/i.MX8MPLUS)
2. [Vendor software / developer documentation](https://www.nxp.com/design/design-center/software/embedded-software/eiq-ml-development-environment:EIQ-ML-DEVELOPMENT-ENVIRONMENT)

## Publication and governance notes

Public reference card only. `documented` indicates a source-backed draft, not certification, endorsement, or procurement approval. The cited manufacturer pages should be rechecked against exact SKU and revision before procurement. Internal BOM, quotations, supplier assessments and proprietary test evidence belong in the private/core SSOT, not this public repository.
