# CMP-EAM-0040 — AMD Kria K24

## Component identity and governance

| Field | Value |
|---|---|
| Component ID | `CMP-EAM-0040` |
| Guild / class | Compute (`CMP`) / Edge AI Module (`EAM`) catalog class |
| Manufacturer | AMD |
| Product / family | Kria K24 |
| Device form | Adaptive SoM / production module family |
| Exact orderable part number | TBD — distinguish silicon, module, carrier and development board |
| Status | `listed` — initial catalog entry, no part-specific document audit completed |
| Supplier ID | TBD |
| Last reviewed | 2026-10-09 |
| Evidence tier | Manufacturer reference link provided; specifications and lifecycle not independently checked |

## Hardware and performance profile

| Property | Engineering description / evidence gap |
|---|---|
| CPU / AI architecture | Adaptive SoM / production module family; detailed cores, accelerator blocks and variants require official datasheet review |
| AI performance | TBD for exact SKU, model, numeric precision, sparsity, compiler, clocks and power mode; published peak metrics are not measured application throughput |
| Memory and storage | On-chip versus board RAM, flash, bandwidth and boot medium TBD |
| Power / thermals | Input voltage, idle / typical / sustained peak watts, cooling and derating TBD; complete-system watts require measurement |
| Camera / sensor I/O | Verify MIPI CSI-2, USB, Ethernet, PCIe, sensor synchronization and actual board connector availability |
| Robot control I/O | CAN / CAN-FD, UART, SPI, GPIO, PWM, industrial Ethernet and deterministic latency TBD per exact part and board |
| Software and toolchain | AMD Vitis, Vivado and Linux board support; exact image/runtime and licensing TBD |
| Security and functional safety | Secure boot, signed update, watchdog, lifecycle, safety manuals and certifications require explicit product-level evidence |
| Environmental / lifecycle | Operating temperature, shock/vibration, EMC, long-term availability and EOL policy TBD |

## PAI-SG integration assessment

**Candidate workloads:** Industrial vision, signal processing and adaptable sensor pipelines. These are potential engineering uses, not verified throughput, accuracy, real-time behavior or production qualification.

**Product-specific integration boundary:** Distinguish K24 SOM from KD240 drive starter kit; confirm FPGA fabric resource and deployment power. Confirm the precise orderable device, host board and software version before selecting an implementation.

**Control and safety boundary:** Perception and AI inference are not a substitute for independent emergency-stop, safety-rated motion control, or verified deterministic control. A product feature or safety-related marketing statement does not certify a complete robot.

## Preliminary vendor and integration risks

| Risk theme | Engineering concern | Required evidence / mitigation |
|---|---|---|
| Identity and variants | SoC, SoM, evaluation kit and production carrier have different BOM, I/O and operating limits | Obtain exact ordering code, board schematic and revision |
| AI model portability | Operator coverage, quantization, compiler and unsupported preprocessing can constrain workloads | Compile representative ONNX / framework models and record conversion errors |
| System performance | TOPS or device-only benchmark may not predict end-to-end robot inference | Test accuracy, sustained FPS, P95/P99 latency, CPU load, memory, temperature and wall power |
| Camera and networking | Sensor driver, timestamps, DMA, synchronization and network jitter vary by board/BSP | Validate real sensors and concurrent workloads on pinned BSP |
| SDK and licensing | Vendor toolchain, kernel and runtime versions can restrict maintainability | Record license, support window, release notes and software bill of materials |
| Supply and lifecycle | Production SKU, authorized channels, MOQ, EOL and lead times unconfirmed | Keep supplier quotes and confidential sourcing evidence in private SSOT |
| Cybersecurity / safety | Secure update, firmware provenance and safety functions unproven | Request documentation; conduct independent risk analysis and testing |

## Component Card completeness

| Requirement | Current status |
|---|---|
| Manufacturer, product and catalog class | Listed; exact SKU/revision TBD |
| Official part-specific datasheet and source date | Pending verification |
| CPU, GPU, NPU / programmable logic details | TBD for exact variant |
| Memory, storage, dimensions and cooling | TBD |
| Camera, network and control I/O | TBD for exact board |
| BSP, SDK, framework and ROS 2 version matrix | TBD |
| Security, functional safety, environmental and lifecycle evidence | TBD |
| Price, supplier, MOQ and lead time | TBD; confidential commercial evidence excluded |
| Dataset, accuracy, sustained FPS, P95/P99 latency and system watts | Not tested |

## Manufacturer reference — initial discovery link

- https://www.amd.com/en/products/system-on-modules/kria/k24.html

## Publication boundary

This is a public `listed` catalog entry, not a PAI-SG verification, certification, recommendation or production approval. Do not publish private quotations, BOMs, raw engineering logs or confidential architecture. Upgrade to `documented` only after a traceable manufacturer datasheet and exact device variant have been reviewed.
