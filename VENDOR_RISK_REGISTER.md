# Vendor Risk Register — Edge Device Catalog

**Status:** preliminary risk hypotheses; no vendor defect or ranking asserted.
**Date:** 2026-10-09

## Vendor risk notes

### NVIDIA

CUDA/TensorRT and JetPack dependency; module/carrier-board compatibility; peak power, cooling and thermal throttling; development-kit versus production-module confusion; export controls, availability and lifecycle changes; safety qualification must be assessed at the full-system level.

### Qualcomm

BSP/SDK access and licensing; partner-dependent module and carrier availability; ROS 2/Linux integration maturity; NPU compiler/operator coverage; camera interfaces and thermal design; exact IQ-family SKU and shipping status require verification.

### Intel

NPU driver/runtime availability varies by generation and OS; OpenVINO model coverage; power and cooling of x86 systems; industrial SKU longevity versus consumer SKU churn; peripheral and real-time I/O often depend on board vendors.

### AMD / Xilinx

FPGA toolchain complexity and engineering cost; device-specific acceleration flows; long implementation/verification cycles; board-level thermal and power requirements; development kit not equal to deployable SOM; software lifecycle and IP licensing.

### NXP

BSP support duration, industrial I/O integration, NPU operator coverage, module/carrier sourcing and lifecycle confirmation.

### Texas Instruments

TIDL model conversion coverage, processor SDK version dependencies, camera pipeline integration, industrial real-time partitioning and thermal validation.

### Hailo

Host CPU requirement, model compiler/operator coverage, memory limits, software version pinning and board-level power/thermal verification.

### Rockchip

Board-vendor BSP quality, upstream Linux support, NPU runtime compatibility, long-term security updates and sourcing variability.

### Raspberry Pi

AI accelerator dependency, production I/O/carrier qualification, industrial environmental suitability, real-time limitations and supply lifecycle.

### MediaTek / Renesas / Ambarella / Google Coral / Kneron / MemryX / BrainChip / SiMa.ai / Axelera AI / Sophgo

For each manufacturer separately confirm publicly documented SKU availability, software SDK/BSP access, model/operator coverage, regional distribution, export constraints, lifecycle, security patch policy and real sustained performance. These are verification checkpoints, not demonstrated vendor shortcomings.

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

## Governance

These are preliminary risk hypotheses. Assess each product using documented evidence and deployment context. Do not publish confidential supplier quotations or proprietary BOMs.
