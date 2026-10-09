# Qualcomm Robotics RB5 — PAI-SG Component Card

- **Component ID:** CMP-EAM-0005
- **Guild / Class:** Compute (CMP) / Edge AI Module (EAM)
- **Manufacturer:** Qualcomm
- **Product / variants:** Robotics RB5 / QRB5165
- **Device class:** Robotics development platform + SoM
- **Status:** documented (published manufacturer data, not engineering validation)
- **Supplier ID / exact part number / revision:** TBD
- **Last reviewed:** 2026-10-09

## Hardware and AI specifications

| Field | Manufacturer information / qualification |
|---|---|
| AI peak | Up to 15 TOPS (Qualcomm AI Engine manufacturer claim; precision/measurement conditions require verification) |
| CPU | Octa-core Qualcomm Kryo 585 |
| GPU | Qualcomm Adreno 650 |
| DSP / accelerator | Hexagon DSP and Hexagon Tensor Accelerator |
| Vision | Spectra 480 ISP; up to seven concurrent cameras supported at platform level, configuration dependent |
| Connectivity | 4G/5G via companion module; Wi-Fi support varies by development configuration |
| Software | Linux / Ubuntu / ROS 2 support described by manufacturer; BSP and ROS 2 version compatibility TBD |

Peak AI metrics use differing precisions, sparsity assumptions and power modes. They are not directly comparable across vendors or with measured application FPS. Module versus development-kit interfaces must be distinguished.

## PAI-SG applicability

E01 low-power edge inference; E02 multi-camera vision; E03 robotics perception. These are workload candidates, not verified algorithm support or benchmark results. Functional safety and deterministic motor control require separate controllers and evidence.

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
| BSP and ecosystem accessibility | Vendor SDK access and ROS 2 combinations may require partner support | Confirm SDK entitlement, Linux support matrix and BSP maintenance |

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

1. https://www.qualcomm.com/content/dam/qcomm-martech/dm-assets/documents/qualcomm-robotics-rb5-platform-product-brief.pdf
2. https://www.qualcomm.com/internet-of-things/products/q5-series/qrb5165
3. https://docs.qualcomm.com/bundle/publicresource/topics/80-88500-5/platform_hardware_overview.html

## Publication and governance

This public card is a manufacturer-sourced engineering reference, not a certification, procurement approval, endorsement or PASG-verified design. Keep proprietary BOM, nonpublic quotations and raw internal validation evidence in private SSOT.
