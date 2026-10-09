# CMP-EAM-0060 — Ambarella CV3

## Component identity and governance

| Field | Value |
|---|---|
| Component ID | `CMP-EAM-0060` |
| Guild / class | Compute (`CMP`) / Edge AI Module (`EAM`) catalog class |
| Manufacturer | Ambarella |
| Product / family | CV3 |
| Device form | Automotive AI vision SoC family |
| Exact orderable part number | TBD — distinguish chip, module, evaluation board and production SKU |
| Status | `listed` — preliminary discovery entry; exact part documentation not audited |
| Supplier ID | TBD |
| Last reviewed | 2026-10-09 |
| Evidence tier | Manufacturer discovery URL only; no datasheet or measured performance verification |

## Hardware and performance profile

| Property | Engineering description / evidence gap |
|---|---|
| Compute / AI architecture | Automotive perception and AI vision SoC family; exact variant and interface TBD |
| AI throughput | TBD for exact SKU, numerical precision, sparsity, compiler and power mode; do not equate peak TOPS with application FPS |
| Memory and storage | RAM type/capacity, on-chip SRAM, flash, boot media and bandwidth TBD |
| Power and thermals | Idle, typical and sustained peak power, complete-system watts, cooling and derating TBD |
| Sensor / camera I/O | Verify native camera lanes, ISP, PCIe, USB, Ethernet, time sync and carrier exposure |
| Robot control I/O | CAN / CAN-FD, UART, SPI, GPIO, PWM, EtherCAT support and timing TBD; no safety-control claim |
| Software and toolchain | Official BSP, Linux/RTOS, inference SDK, ONNX/TFLite support, kernel and licenses TBD |
| Security and safety | Secure boot, signed update, watchdog, cybersecurity support and any functional safety evidence TBD |
| Environmental and lifecycle | Temperature, vibration, EMC, long-term supply and EOL information TBD |

## PAI-SG integration assessment

**Candidate workloads:** Multi-camera perception and autonomous robot sensing. Candidate only; no PAI-SG algorithm, accuracy, latency or throughput verification is implied.

**Product-specific boundary:** Distinguish automotive silicon platform from an orderable robotics SOM. Select exact SKU and deployment board before drawing interface, memory or power conclusions.

**Safety boundary:** AI inference, sensor fusion and network gateway functions do not replace an independent safety-rated emergency stop or verified deterministic motor controller. Functional-safety status requires product- and application-specific evidence.

## Preliminary vendor and integration risks

| Risk theme | Engineering concern | Evidence / mitigation |
|---|---|---|
| Product identity | Family, silicon, SOM, evaluation kit and production carrier may differ | Collect exact part number, schematic, revisions and ordering information |
| Model conversion | Quantization, unsupported operators, pre/post-processing and runtime differences | Compile representative ONNX / TFLite models; record failure and accuracy delta |
| Performance | Marketing compute metrics do not establish end-to-end throughput | Measure sustained FPS, P95/P99 latency, CPU utilization, RAM, thermals and total watts |
| Sensor and networking | Camera drivers, synchronization, DMA and timestamps depend on BSP and board | Verify actual sensors, firmware, kernel, timing and concurrency |
| SDK and maintenance | Compiler, runtime, licensing and support windows can constrain deployment | Record version matrix, software bill of materials and patch cadence |
| Procurement | Availability, authorized distributors, MOQ, lead time and lifecycle unconfirmed | Store private quotations and supplier evidence in private SSOT |
| Security / safety | Secure updates and safety claims may lack applicable proof | Request manufacturer documents and perform independent risk analysis |

## Component Card completeness

| Requirement | Current status |
|---|---|
| Manufacturer, family and catalog class | Listed; exact SKU / revision TBD |
| Official part-specific datasheet and dated source | Pending verification |
| CPU, GPU, NPU / FPGA / DSP and precision | Preliminary description only; exact configuration TBD |
| Memory, storage, dimensions and cooling | TBD |
| Camera, network and robot control interfaces | TBD for selected module / board |
| BSP, SDK, ROS 2 and model conversion matrix | TBD |
| Cybersecurity, functional safety, environmental and lifecycle | TBD |
| Supplier, MOQ, price and lead time | TBD; confidential evidence excluded |
| Dataset, accuracy, sustained FPS, P95/P99 latency and system power | Not tested |

## Manufacturer reference — initial discovery link

- https://www.ambarella.com/

## Publication boundary

This is a public `listed` entry, not PAI-SG verification, certification, recommendation, or production qualification. Do not publish private quotations, BOMs, raw engineering logs or internal architecture. Upgrade to `documented` only after official product-specific documentation and exact variant have been reviewed.
