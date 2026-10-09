# PAI-SG Edge Device Master List and Component Card Requirements

**Repository target:** `Statera-Guild/edge-device-catalog`  
**Document status:** Initial catalog / candidate inventory; not a verified procurement list  
**Date:** 2026-10-09  
**Scope:** All vendors and device families identified in the initial PAI-SG Edge Device discussion, with vendor-level risks and required Component Card fields.

## 1. Classification and priority

| Code | Category | Design use |
|---|---|---|
| E01 | Low-Power Edge AI | Small AMR, embedded sensing |
| E02 | Vision AI | Detection, tracking, segmentation |
| E03 | Autonomous Navigation | SLAM, sensor fusion, planning |
| E04 | High-Performance Physical AI | VLM, VLA, world models |
| E05 | Industrial Edge Computing | Industrial robots, IPC |
| E06 | Real-Time Control | Motor control, deterministic I/O |
| E07 | AI Acceleration Module | Host-attached inference acceleration |
| E08 | Edge AI Gateway | Fleet, on-premises edge, OPL |

**P1:** first registration; **P2:** extension; **P3:** legacy/research. Priorities are cataloging priorities, not recommendations to purchase. Device families may have multiple roles. A chip, SOM, SBC, developer kit, and production IPC are distinct deliverables and must not be treated as interchangeable SKUs.

## 2. Master device inventory

### 2.1 NVIDIA

| Device / family | PAI-SG application | Priority |
|---|---|---|
| Jetson Orin Nano 4GB / 8GB | Small vision AI, education AMR | P1 |
| Jetson Orin Nano Super Developer Kit | Low-cost Physical AI prototyping | P1 |
| Jetson Orin NX 8GB / 16GB | AMR, multicamera, SLAM | P1 |
| Jetson AGX Orin 32GB / 64GB | Autonomous navigation, sensor fusion | P1 |
| Jetson AGX Orin Industrial | Industrial robots | P1 |
| Jetson Thor T4000 / T5000 | VLM, VLA, high-performance Physical AI | P1 |
| NVIDIA IGX Platform | Industrial AI, safety-oriented integration | P2 |
| Jetson Xavier / TX2 / Nano legacy | Existing-platform compatibility | P3 |

**Vendor risks:** CUDA/TensorRT and JetPack dependency; module/carrier-board compatibility; peak power, cooling and thermal throttling; development-kit versus production-module confusion; export controls, availability and lifecycle changes; safety qualification must be assessed at the full-system level.

### 2.2 Qualcomm

| Device / family | PAI-SG application | Priority |
|---|---|---|
| QRB5165 / Robotics RB5 | Camera-rich mobile robot, drone | P1 |
| QRB2210 / Robotics RB1 | Entry-level small robot | P2 |
| QRB4210 / Robotics RB2 | Service robot, sensor AI | P2 |
| Robotics RB3 Gen 2 | Vision AI, midrange AMR | P1 |
| Robotics RB6 | Advanced robotics AI | P1 |
| Dragonwing IQ8 family | Industrial/robotic AI candidate | P1 candidate |
| Dragonwing IQ9 family | High-performance robotics candidate | P1 candidate |
| Dragonwing IQ10 / robotics reference design | Humanoid, advanced AMR candidate | P1 candidate |
| Qualcomm AI Hub-supported platforms | Model conversion and NPU deployment | P2; software ecosystem, not a separate device |

**Vendor risks:** BSP/SDK access and licensing; partner-dependent module and carrier availability; ROS 2/Linux integration maturity; NPU compiler/operator coverage; camera interfaces and thermal design; exact IQ-family SKU and shipping status require verification.

### 2.3 Intel

| Device / family | PAI-SG application | Priority |
|---|---|---|
| Core Ultra Series 1 | CPU/GPU/NPU edge AI | P1 |
| Core Ultra Series 2 | AI AMR, industrial IPC | P1 |
| Subsequent industrial Core Ultra families | New edge PC design | P1 candidate |
| Atom x7000E / x7000RE | Low-power industrial controller | P1 |
| Intel Processor N Series | Educational/lightweight robot | P2 |
| 12th / 13th Gen Embedded Core | Existing x86 robot platforms | P2 |
| Intel Arc GPU edge PCs | Multivision AI acceleration | P2 |
| Xeon edge servers | Fleet and on-premises OPL | P2 |

**Vendor risks:** NPU driver/runtime availability varies by generation and OS; OpenVINO model coverage; power and cooling of x86 systems; industrial SKU longevity versus consumer SKU churn; peripheral and real-time I/O often depend on board vendors.

### 2.4 AMD / Xilinx

| Device / family | PAI-SG application | Priority |
|---|---|---|
| Kria K26 SOM | Industrial vision/robot AI | P1 |
| Kria KV260 Vision AI Starter Kit | Vision AI development | P1 |
| KR260 Robotics Starter Kit | Robotics I/O and prototyping | P1 |
| Ryzen AI Embedded P100 | x86 industrial edge AI | P1 |
| Ryzen Embedded V / R Series | Industrial robot controller | P2 |
| Zynq UltraScale+ MPSoC | Sensor fusion and control | P1 |
| Versal AI Edge Series | AI + programmable logic | P1 |
| Versal AI Edge Gen 2 | Next-generation edge AI/control | P1 |
| AMD Embedded+ | Combined processor and adaptive compute | P2 |

**Vendor risks:** FPGA toolchain complexity and engineering cost; device-specific acceleration flows; long implementation/verification cycles; board-level thermal and power requirements; development kit not equal to deployable SOM; software lifecycle and IP licensing.

### 2.5 NXP and Texas Instruments

| Vendor | Device / family | PAI-SG application | Priority |
|---|---|---|---|
| NXP | i.MX 8M Plus | Small vision AI, HMI | P1 |
| NXP | i.MX 93 | Low-power inference | P2 |
| NXP | i.MX 95 | Industrial edge AI, vision | P1 |
| NXP | S32G Series | Robot/vehicle gateway | P2 |
| Texas Instruments | TDA4VM / TDA4VH | Multicamera autonomous systems | P1 |
| Texas Instruments | AM62A / AM62P | Low-power vision AI | P1 |
| Texas Instruments | AM67A / AM68A / AM69A | Vision and sensor fusion | P1 |
| Texas Instruments | AM64x / AM243x | Industrial communication and real-time control | P1 |
| Texas Instruments | C2000 Series | Motor and joint control | P2 |

**NXP risks:** NPU/accelerator tool support by SKU; camera and multimedia pipeline integration; BSP versioning; industrial temperature variants and lifecycle; compute capacity for large models.

**Texas Instruments risks:** heterogeneous accelerator programming complexity; SDK/model conversion compatibility; family-to-family differences in memory and I/O; development board versus production board; real-time control and functional safety need separate evidence.

### 2.6 Hailo, Rockchip and Raspberry Pi

| Vendor | Device / family | PAI-SG application | Priority |
|---|---|---|---|
| Hailo | Hailo-8 | Vision AI accelerator | P1 |
| Hailo | Hailo-8L | Low-power inference accelerator | P1 |
| Hailo | Hailo-10H | Generative AI accelerator candidate | P1 |
| Hailo | Hailo-15 Series | Smart-camera AI | P2 |
| Rockchip | RK3588 / RK3588S | Low-cost multicamera SBC | P1 |
| Rockchip | RK3576 | Midrange edge AI | P1 |
| Rockchip | RK3568 | Low-power mobile robot | P2 |
| Raspberry Pi | Compute Module 5 | Robot communication/control host | P1 |
| Raspberry Pi | Raspberry Pi 5 + AI HAT+ | Educational vision AI | P1 |
| Raspberry Pi | Raspberry Pi 5 + AI HAT+ 2 | Generative AI prototyping candidate | P2 |

**Hailo risks:** requires compatible host for accelerator SKUs; operator/model compiler restrictions; memory and workload limitations; host PCIe and thermal integration; compare actual latency rather than nominal TOPS.

**Rockchip risks:** board-vendor BSP quality and kernel maintenance; NPU toolkit portability; camera driver consistency; thermal and industrial lifecycle uncertainty; community versus production software support.

**Raspberry Pi risks:** not inherently industrial/safety-rated; microSD/storage reliability; I/O determinism; power and thermal constraints; AI HAT model and software compatibility; external MCU recommended for hard real-time control.

### 2.7 Other major vendors

| Vendor | Device / family | PAI-SG application | Priority |
|---|---|---|---|
| MediaTek | Genio 520 / 720 / 1200 | Low-power multimedia/vision AI | P2 |
| Renesas | RZ/V2H / RZ/V2N | Robot vision, industrial inference | P2 |
| Ambarella | CV2 / CV5 / CV7 families | Camera-centric robot vision | P2 |
| Google Coral | Edge TPU | Compact object detection | P2 |
| Kneron | KL520 / KL720 / KL730 | Ultra-low-power inference | P2 |
| MemryX | MX3 family | Host-attached AI acceleration | P2 |
| BrainChip | Akida family | Neuromorphic edge AI research | P3 |
| SiMa.ai | MLSoC family | Industrial edge ML | P2 |
| Axelera AI | Metis family | Vision inference acceleration | P2 |
| Sophgo | BM1684X family | Multistream vision inference | P2 |

**MediaTek risks:** BSP availability via module partners; NPU SDK and model portability; long-term supply and industrial qualification.

**Renesas risks:** proprietary accelerator toolchain and supported model set; performance on complex AI pipelines; device-specific BSP integration.

**Ambarella risks:** partner/OEM access to SDKs and hardware; vision-focused model coverage; sourcing and support terms.

**Google Coral risks:** Edge TPU model/quantization constraints; limited memory and model architecture flexibility; product availability/lifecycle uncertainty.

**Kneron risks:** compiler/operator restrictions; development ecosystem and supplier availability; limited workload breadth.

**MemryX risks:** host dependence; framework conversion maturity; long-term module availability and production support.

**BrainChip risks:** neuromorphic model-development overhead; limited conventional AI portability; benchmark and production maturity validation.

**SiMa.ai risks:** proprietary SDK/compiler dependency; supply chain and regional support; independent workload benchmarks needed.

**Axelera AI risks:** SDK/operator maturity; board/module supply and host integration; production lifecycle verification.

**Sophgo risks:** export/trade restrictions and regional supply-chain exposure; SDK documentation/support; cybersecurity and deployment governance checks.

## 3. Robot-type mapping (initial candidate mapping, not validation)

| Robot type | AI compute candidates | Separate control candidate |
|---|---|---|
| Educational AGV | Raspberry Pi 5, RK3588 | MCU / STM32 |
| General AMR | Jetson Orin NX, Intel Core Ultra | TI AM64x / STM32 |
| Industrial AMR | AGX Orin Industrial, Ryzen AI Embedded | NXP / TI / PLC |
| Outdoor UGV | AGX Orin, Qualcomm IQ9 | MCU / FPGA |
| Robot arm | Intel Core Ultra, AMD Kria | EtherCAT controller |
| Mobile manipulator | AGX Orin, Jetson Thor | Dedicated motion controller |
| Humanoid | Jetson Thor, Qualcomm IQ10 | Distributed real-time controllers |
| Cargo UAV | Orin NX, Qualcomm RB5 | Independent flight controller |
| Multi-robot gateway | Intel Core Ultra, Ryzen Embedded | Network and communication devices |

## 4. Required fields for the design Component Card

The following fields are **required schema fields**. Unknown values must be recorded as `TBD`, `Not disclosed`, or `Not applicable`, never guessed. Every quantitative claim should carry a source and test condition.

| Field group | Required fields | Recording rule |
|---|---|---|
| Identification | Vendor, product family, exact model, part number, hardware revision, card ID | Separate device from developer kit and module |
| Device type | SoC, SOM, SBC, development kit, IPC, accelerator, gateway | Multiple types only when clearly explained |
| Compute | CPU architecture/cores, GPU, NPU, DSP, FPGA, accelerator memory | Record actual SKU-specific capabilities |
| AI performance | TOPS/TFLOPS, numeric precision, sparsity, clock/power condition | Do not compare unlike metrics directly |
| Memory | RAM capacity/type, bandwidth, onboard storage, storage interfaces | Include shared versus dedicated memory |
| Power | Idle, typical workload, peak, configurable power modes, TDP/TGP | Specify measurement boundary and workload |
| Physical | Dimensions, mass, mounting, heatsink/fan, cooling requirements | Distinguish module from full system |
| Sensors | MIPI CSI, GMSL via carrier, USB, Ethernet, LiDAR connectivity | Mark native versus carrier-dependent |
| Control I/O | CAN/CAN-FD, GPIO, SPI, UART, I2C, EtherCAT availability | Mark native versus external controller |
| Software | OS, kernel, BSP, ROS 2, CUDA/TensorRT/OpenVINO/other SDK, tool versions | Specify exact supported versions |
| AI compatibility | Detection, tracking, segmentation, SLAM, VLM, VLA, world model | Status: documented / tested / candidate / unsupported |
| Safety/security | Secure Boot, TPM/TEE, watchdog, functional-safety evidence | No implied system certification |
| Reliability | Temperature, vibration/shock, MTBF where supplied, product lifecycle | Link to datasheet/test report |
| Procurement | Indicative price, currency/date, MOQ, lead time, distributor, availability | Public/private publication flag |
| Validation | Model and version, input size, batch, FPS, latency, memory, system power, thermal behavior | Attach reproducible evidence |
| Vendor risk | SDK lock-in, lifecycle, sourcing, geopolitical/export, support, integration, safety gaps | Evidence-based risk level and mitigation |
| Provenance | Manufacturer datasheet URL, SDK URL, source date, last reviewed, reviewer | Flag unverified claims |

### 4.1 Vendor risk assessment schema

| Field | Definition |
|---|---|
| Risk ID | Stable identifier per vendor/product risk |
| Risk category | Supply / lifecycle / software / compatibility / security / regulatory / thermal / cost |
| Risk statement | Specific potential failure or limitation |
| Likelihood | Low / Medium / High / Unknown |
| Impact | Low / Medium / High / Unknown |
| Evidence | Source URL, test report, or `Unverified` |
| Mitigation | Alternative device, software abstraction, test, contract, inventory plan |
| Owner and review date | Responsible guild reviewer and next review |

The risk notes in Section 2 are **risk hypotheses for review**, not factual findings of failure by any manufacturer. Do not assign numerical vendor rankings without documented evidence.

## 5. Publication and governance notes

All vendor/device catalog entries can be published in the Guild as factual, source-linked component metadata. Keep confidential supplier quotations, negotiated prices, internal BOMs, unpublished benchmark evidence, credentials and proprietary architecture in the private/core SSOT; expose only approved summaries or public evidence in Guild cards. Mark product launch status, active supply, SDK availability and certification evidence as **unverified until checked against manufacturer documents**.

**Recommended card relationship:** `Robot requirement → Algorithm/workload → Edge device → Validation evidence → Design decision`.

**Next phase:** Verify official manufacturer part numbers, product lifecycle, official datasheets and BSP/SDK versions; then split this master list into individual SKU-level cards.
