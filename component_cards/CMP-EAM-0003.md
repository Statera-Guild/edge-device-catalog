# NVIDIA Jetson AGX Orin — PAI-SG Component Card

- **Component ID:** CMP-EAM-0003
- **Guild / Class:** Compute (CMP) / Edge AI Module (EAM)
- **Manufacturer:** NVIDIA
- **Product / variants:** Jetson AGX Orin 32GB / 64GB
- **Device class:** SOM
- **Status:** documented (published manufacturer data, not engineering validation)
- **Supplier ID / exact part number / revision:** TBD
- **Last reviewed:** 2026-10-09

## Hardware and AI specifications

| Field | Manufacturer information / qualification |
|---|---|
| AI peak | 32GB: up to 200 sparse INT8 TOPS; 64GB: up to 275 sparse INT8 TOPS |
| GPU | 32GB: 1792 CUDA / 56 Tensor; 64GB: 2048 CUDA / 64 Tensor (Ampere) |
| CPU | 32GB: 8-core; 64GB: 12-core Arm Cortex-A78AE |
| RAM | 32GB / 64GB LPDDR5 |
| Memory bandwidth | Up to 204.8 GB/s |
| Power | 15–60 W family module modes, not total system power |
| Software | JetPack / Jetson Linux / CUDA / TensorRT |

Peak AI metrics use differing precisions, sparsity assumptions and power modes. They are not directly comparable across vendors or with measured application FPS. Module versus development-kit interfaces must be distinguished.

## PAI-SG applicability

E02 Vision AI; E03 Navigation; E04 high-performance inference. These are workload candidates, not verified algorithm support or benchmark results. Functional safety and deterministic motor control require separate controllers and evidence.

## Vendor and design risk register (preliminary)

| Risk | Design implication | Evidence / mitigation |
|---|---|---|
| Ecosystem / SDK lock-in | Vendor runtimes, BSP and model conversions can constrain portability | Keep model interchange artifacts; test deployment runtime and licenses |
| Hardware lifecycle and supply | Availability and lead times can affect production | Confirm SKU lifecycle, authorized distributors and alternate sourcing |
| Thermal and energy budget | Published power modes do not represent complete robot consumption | Test sustained clocks, temperatures, idle/peak wall power |
| Sensor and carrier integration | Camera, LiDAR and control buses vary by board and software | Validate exact sensor, carrier, driver and firmware revisions |
| Model performance gap | Peak compute does not establish multi-model real-time operation | Measure model accuracy, FPS, p95/p99 latency and RAM under concurrent loads |
| Security and safety | No implied functional-safety certification | Document boot/update security, watchdogs and independent safety controller |
| Industrial reliability | Development board may lack industrial qualification | Request environmental and production hardware evidence |
| JetPack/CUDA version dependence | Upgrades may alter driver and framework compatibility | Pin tested JetPack, CUDA, TensorRT and ROS 2 versions |

**Risk probability / severity:** TBD; not assessed without target deployment. No defect claim or supplier approval is implied.

## Mandatory Component Card data — completeness

| Domain | Mandatory fields | Current status |
|---|---|---|
| Identification | Vendor, model, exact SKU, revision, supplier ID | Partial; exact SKU and supplier TBD |
| Compute | CPU, GPU, NPU/DSP/FPGA, precision and sparsity | Partially documented |
| Memory / storage | Capacity, bandwidth, flash and boot media | Partial; configuration dependent |
| Power / thermal | Idle/typical/peak, supply voltage, cooling, throttling | Not tested |
| Mechanical | Dimensions, mass, connectors, mounting | TBD for exact carrier/module |
| Sensor interfaces | MIPI, USB, Ethernet, GMSL, LiDAR compatibility | TBD for exact carrier |
| Control interfaces | CAN, CAN-FD, SPI, UART, GPIO, EtherCAT | TBD; do not assume native EtherCAT |
| Software | OS, kernel, BSP, SDK, drivers, ROS 2, licenses | Version matrix TBD |
| Algorithms | Detection, tracking, segmentation, SLAM, VLM, VLA | Candidates; not tested |
| Safety / cybersecurity | Secure boot, watchdog, TPM, safety evidence | TBD |
| Reliability | Temperature, shock, vibration, MTBF, lifecycle | TBD |
| Procurement | Price, MOQ, lead time, authorized supplier | TBD; private quotes excluded |
| Validation | Dataset, model, precision, FPS, p95/p99, memory, watts | Not tested |

## Official manufacturer sources

1. https://www.nvidia.com/en-us/autonomous-machines/embedded-systems/jetson-orin/
2. https://www.nvidia.com/content/dam/en-zz/Solutions/gtcf21/jetson-orin/nvidia-jetson-agx-orin-technical-brief.pdf

## Publication and governance

This public card is a manufacturer-sourced engineering reference, not a certification, procurement approval, endorsement or PASG-verified design. Keep proprietary BOM, nonpublic quotations and raw internal validation evidence in private SSOT.
