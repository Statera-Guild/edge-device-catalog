# Edge Device Catalog

**Open engineering catalog of Edge AI computing devices for Physical AI and robotics.**

Maintained under [Statera-Guild](https://github.com/Statera-Guild). This repository is a **public engineering reference**, not a procurement approval list, product certification register, or authoritative definition of the Physical AI Spider Grid (PAI-SG) architecture. PAI-SG's internal design, supplier terms, BOM, and raw validation evidence belong in separately governed private systems.

## Catalog at a glance

- **60 public Component Cards**: `CMP-EAM-0001` through `CMP-EAM-0060` (as of 2026-10-09).
- **Guild / class:** Compute (`CMP`) / Edge AI Module (`EAM`). Component IDs are immutable.
- **Device forms:** SoC, SOM, SBC / development kit, industrial computing platform, and standalone AI accelerator. **These are not interchangeable**; see each card's device form and integration boundary.
- **Status vocabulary:** `listed` = initial product entry; `documented` = public manufacturer documentation has been recorded. **Neither means independently tested, verified, certified, recommended, or production-qualified.** See individual cards for current status.
- **Benchmark caution:** Published TOPS/TFLOPS may differ by precision, sparsity, power mode, and hardware variant. Compare only under a shared, documented workload and measurement protocol.

## Component index

| ID | Manufacturer | Device / family | Form / scope | Component Card |
|---|---|---|---|---|
| CMP-EAM-0001 | NVIDIA | Jetson Orin Nano Super | Developer kit | [Open](component_cards/CMP-EAM-0001.md) |
| CMP-EAM-0002 | NVIDIA | Jetson Orin NX | SOM family | [Open](component_cards/CMP-EAM-0002.md) |
| CMP-EAM-0003 | NVIDIA | Jetson AGX Orin | SOM family | [Open](component_cards/CMP-EAM-0003.md) |
| CMP-EAM-0004 | NVIDIA | Jetson Thor | Module / platform family | [Open](component_cards/CMP-EAM-0004.md) |
| CMP-EAM-0005 | Qualcomm | Robotics RB5 | Robotics platform | [Open](component_cards/CMP-EAM-0005.md) |
| CMP-EAM-0006 | Qualcomm | Robotics RB3 Gen 2 | Development kit / platform | [Open](component_cards/CMP-EAM-0006.md) |
| CMP-EAM-0007 | Qualcomm | Robotics RB6 | Robotics platform | [Open](component_cards/CMP-EAM-0007.md) |
| CMP-EAM-0008 | Qualcomm | Dragonwing IQ9 | SoC family | [Open](component_cards/CMP-EAM-0008.md) |
| CMP-EAM-0009 | Intel | Core Ultra Edge AI | Processor family | [Open](component_cards/CMP-EAM-0009.md) |
| CMP-EAM-0010 | AMD | Kria K26 | SOM | [Open](component_cards/CMP-EAM-0010.md) |
| CMP-EAM-0011 | NXP | i.MX 8M Plus | SoC | [Open](component_cards/CMP-EAM-0011.md) |
| CMP-EAM-0012 | Texas Instruments | TDA4VM | SoC | [Open](component_cards/CMP-EAM-0012.md) |
| CMP-EAM-0013 | Hailo | Hailo-8 | AI accelerator | [Open](component_cards/CMP-EAM-0013.md) |
| CMP-EAM-0014 | Rockchip | RK3588 | SoC | [Open](component_cards/CMP-EAM-0014.md) |
| CMP-EAM-0015 | Raspberry Pi | Compute Module 5 | SOM | [Open](component_cards/CMP-EAM-0015.md) |
| CMP-EAM-0016 | NXP | i.MX 95 | SoC | [Open](component_cards/CMP-EAM-0016.md) |
| CMP-EAM-0017 | Texas Instruments | AM69A | SoC | [Open](component_cards/CMP-EAM-0017.md) |
| CMP-EAM-0018 | Hailo | Hailo-10H | AI accelerator | [Open](component_cards/CMP-EAM-0018.md) |
| CMP-EAM-0019 | Rockchip | RK3576 | SoC | [Open](component_cards/CMP-EAM-0019.md) |
| CMP-EAM-0020 | Raspberry Pi | Raspberry Pi 5 + AI HAT+ | SBC + accelerator | [Open](component_cards/CMP-EAM-0020.md) |
| CMP-EAM-0021 | Renesas | RZ/V2H | SoC | [Open](component_cards/CMP-EAM-0021.md) |
| CMP-EAM-0022 | MediaTek | Genio 1200 | SoC | [Open](component_cards/CMP-EAM-0022.md) |
| CMP-EAM-0023 | Ambarella | CV5 | Vision SoC | [Open](component_cards/CMP-EAM-0023.md) |
| CMP-EAM-0024 | Google Coral | Edge TPU | AI accelerator | [Open](component_cards/CMP-EAM-0024.md) |
| CMP-EAM-0025 | SiMa.ai | MLSoC | SoC family | [Open](component_cards/CMP-EAM-0025.md) |
| CMP-EAM-0026 | Kneron | KL730 | Vision AI SoC | [Open](component_cards/CMP-EAM-0026.md) |
| CMP-EAM-0027 | MemryX | MX3 | AI accelerator | [Open](component_cards/CMP-EAM-0027.md) |
| CMP-EAM-0028 | BrainChip | Akida | Neuromorphic AI processor family | [Open](component_cards/CMP-EAM-0028.md) |
| CMP-EAM-0029 | Axelera AI | Metis | AI accelerator | [Open](component_cards/CMP-EAM-0029.md) |
| CMP-EAM-0030 | Sophgo | BM1684X | AI inference processor | [Open](component_cards/CMP-EAM-0030.md) |
| CMP-EAM-0031 | NVIDIA | Jetson AGX Orin Industrial | Industrial-grade Jetson system-on-module (SOM) variant | [Open](component_cards/CMP-EAM-0031.md) |
| CMP-EAM-0032 | NVIDIA | IGX Orin | Industrial edge AI platform / system family | [Open](component_cards/CMP-EAM-0032.md) |
| CMP-EAM-0033 | Qualcomm | Dragonwing IQ8 | Industrial IoT / edge AI SoC family | [Open](component_cards/CMP-EAM-0033.md) |
| CMP-EAM-0034 | AMD | Versal AI Edge | Adaptive SoC family with programmable logic and AI engines | [Open](component_cards/CMP-EAM-0034.md) |
| CMP-EAM-0035 | NXP | i.MX 93 | Applications processor / SoC family | [Open](component_cards/CMP-EAM-0035.md) |
| CMP-EAM-0036 | Texas Instruments | AM68A | Embedded vision AI processor / SoC | [Open](component_cards/CMP-EAM-0036.md) |
| CMP-EAM-0037 | Renesas | RZ/V2N | Vision AI MPU / SoC | [Open](component_cards/CMP-EAM-0037.md) |
| CMP-EAM-0038 | NXP | i.MX 8M Mini | Applications processor / SoC | [Open](component_cards/CMP-EAM-0038.md) |
| CMP-EAM-0039 | Hailo | Hailo-8L | Standalone neural-network inference accelerator | [Open](component_cards/CMP-EAM-0039.md) |
| CMP-EAM-0040 | AMD | Kria K24 | Adaptive SoM / production module family | [Open](component_cards/CMP-EAM-0040.md) |
| CMP-EAM-0041 | Texas Instruments | TDA4VL | Automotive / robotics vision SoC | [Open](component_cards/CMP-EAM-0041.md) |
| CMP-EAM-0042 | Texas Instruments | AM62A | Vision AI SoC | [Open](component_cards/CMP-EAM-0042.md) |
| CMP-EAM-0043 | Texas Instruments | AM67A | Vision AI SoC | [Open](component_cards/CMP-EAM-0043.md) |
| CMP-EAM-0044 | Renesas | RZ/V2L | Vision AI MPU | [Open](component_cards/CMP-EAM-0044.md) |
| CMP-EAM-0045 | Renesas | RZ/V2M | Vision AI MPU | [Open](component_cards/CMP-EAM-0045.md) |
| CMP-EAM-0046 | NXP | i.MX 8M Nano | Embedded application SoC / host processor | [Open](component_cards/CMP-EAM-0046.md) |
| CMP-EAM-0047 | NXP | i.MX 8ULP | Ultra-low-power application SoC | [Open](component_cards/CMP-EAM-0047.md) |
| CMP-EAM-0048 | NXP | i.MX 91 | Industrial embedded application SoC | [Open](component_cards/CMP-EAM-0048.md) |
| CMP-EAM-0049 | NXP | S32G3 | Vehicle network processor / gateway SoC | [Open](component_cards/CMP-EAM-0049.md) |
| CMP-EAM-0050 | STMicroelectronics | STM32MP257 | Industrial application MPU | [Open](component_cards/CMP-EAM-0050.md) |
| CMP-EAM-0051 | STMicroelectronics | STM32N6 | AI-capable microcontroller family | [Open](component_cards/CMP-EAM-0051.md) |
| CMP-EAM-0052 | STMicroelectronics | STM32H7 | High-performance microcontroller family | [Open](component_cards/CMP-EAM-0052.md) |
| CMP-EAM-0053 | Microchip | PolarFire SoC | FPGA SoC | [Open](component_cards/CMP-EAM-0053.md) |
| CMP-EAM-0054 | Microchip | SAM9X75 | Industrial MPU | [Open](component_cards/CMP-EAM-0054.md) |
| CMP-EAM-0055 | Intel | Atom x7000E Series | Embedded CPU family | [Open](component_cards/CMP-EAM-0055.md) |
| CMP-EAM-0056 | Intel | Core Ultra 200V | Mobile processor family / edge AI host | [Open](component_cards/CMP-EAM-0056.md) |
| CMP-EAM-0057 | AMD | Ryzen Embedded V3000 | Embedded processor family | [Open](component_cards/CMP-EAM-0057.md) |
| CMP-EAM-0058 | AMD | Versal AI Edge Series Gen 2 | Adaptive SoC family | [Open](component_cards/CMP-EAM-0058.md) |
| CMP-EAM-0059 | Hailo | Hailo-15 | Vision AI processor family | [Open](component_cards/CMP-EAM-0059.md) |
| CMP-EAM-0060 | Ambarella | CV3 | Automotive AI vision SoC family | [Open](component_cards/CMP-EAM-0060.md) |

## Reference documents

- [Edge Device Master List](EDGE_DEVICE_MASTER_LIST.md) — candidate devices and catalog expansion planning.
- [Vendor Risk Register](VENDOR_RISK_REGISTER.md) — preliminary risk themes; not vendor ratings or substantiated defect claims.
- [Component Card Schema](COMPONENT_CARD_SCHEMA.md) — minimum identity, technical, source, risk, and validation fields.
- [Component Cards](component_cards/) — public product-level records.

## PAI-SG workload categories

| Code | Category | Typical evaluation question |
|---|---|---|
| E01 | Low-Power Edge AI | Can the device sustain useful inference within the robot's energy and thermal budget? |
| E02 | Vision AI | Can detection, segmentation, and tracking meet accuracy and latency targets? |
| E03 | Autonomous Navigation | Can perception and mapping operate with synchronized sensors and bounded latency? |
| E04 | High-Performance Physical AI | Can multi-model / VLM / VLA workloads fit the available memory and compute budget? |
| E05 | Industrial Edge Computing | Does the deployed carrier or system meet lifecycle, environmental, and maintenance needs? |
| E06 | Real-Time Control | Which functions need a separate deterministic or safety-rated controller? |
| E07 | AI Acceleration Module | What host, runtime, model conversion, and I/O dependencies are required? |
| E08 | Edge AI Gateway | Can networking, telemetry, security, and fleet management be supported? |

These are **evaluation categories**, not claims that any listed device passes a qualification test.

## Contribution and evidence rules

1. Keep the Component ID stable; do not reuse an ID for a different product. Distinguish family-level cards from exact orderable SKUs and from carrier/development boards.
2. Use only `listed` or `documented` for public card status. Record official source URLs, source date, exact variant, and unresolved `TBD` fields.
3. Separate manufacturer peak specifications from measured results. Any performance evidence should name the model, dataset, precision, batch, software stack, thermal condition, sustained FPS, P95/P99 latency, and total system watts.
4. Describe supply, SDK, cybersecurity, and integration **risks as questions to investigate**, not as unsupported allegations. Do not claim functional-safety certification by inference.
5. Keep confidential quotations, internal supplier assessments, proprietary BOMs, raw logs, and private architecture in the governed private SSOT. Publish only approved, appropriately summarized evidence.

## Scope and disclaimer

Catalog inclusion is informational. It does not imply Statera-Guild or PAI-SG approval, supplier endorsement, safety certification, purchasing advice, or confirmed availability. Confirm the exact device revision, SDK support, lifecycle, and system-level requirements before use in a robot.
