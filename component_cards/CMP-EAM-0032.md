# CMP-EAM-0032 — NVIDIA IGX Orin

## Component identity and governance

| Field | Value |
|---|---|
| Component ID | `CMP-EAM-0032` |
| Guild / class | Compute (`CMP`) / Edge AI Module (`EAM`) |
| Manufacturer | NVIDIA |
| Product / family | IGX Orin |
| Device form | Industrial edge AI platform / system family |
| Exact orderable SKU / revision | TBD — verify against official ordering guide |
| Status | `listed` (initial catalog entry; SKU-specific documentation review pending) |
| Supplier ID | TBD |
| Last reviewed | 2026-10-09 |
| Evidence tier | Preliminary manufacturer-family reference; no PAI-SG validation or benchmark evidence |

## Hardware and performance profile

| Property | Manufacturer-based description / open question |
|---|---|
| Processing architecture | Industrial edge AI platform / system family; exact CPU, accelerator and programmable components TBD by SKU |
| AI throughput | TBD — record precision, sparsity, power mode, compiler and variant before any comparison |
| RAM / storage | TBD for exact module, board or platform; do not confuse SoC capabilities with installed memory |
| Power / thermal | Idle, typical, sustained peak and full-system input watts TBD by measurement; cooling solution TBD |
| Camera / sensor I/O | Validate MIPI, PCIe, Ethernet, USB and sensor drivers for exact carrier / system |
| Robot control I/O | CAN / CAN-FD, UART, SPI, GPIO, EtherCAT and timing behavior TBD; safety control separate |
| Software | NVIDIA IGX software stack; verify supported OS, enterprise update and security features |
| Security / safety | Secure boot, firmware signing, key storage, patch policy, watchdog and safety evidence TBD |
| Industrial qualification | Published operating temperature, shock, vibration, EMC, lifecycle and MTBF TBD by orderable SKU |

## PAI-SG integration assessment

**Candidate workloads:** Industrial perception and high-availability edge processing. These are evaluation hypotheses, not confirmed model support, deterministic timing, sustained FPS or robot qualification.

**Integration boundary:** IGX platform must not be equated with Jetson SOM; validate chosen IGX system, I/O board and availability. Safety-rated stop and motion-control functions require independent system-level hazard analysis and appropriate hardware, regardless of AI capability.

## Preliminary vendor and integration risks

| Risk theme | Engineering concern | Evidence / mitigation to collect |
|---|---|---|
| Product identity | Silicon, SOM, development kit and complete industrial platform may differ | Record orderable SKU, revision, carrier schematic, connector and lifecycle |
| Toolchain and software | SDK/BSP/kernel versions, operator support, licensing and updates may constrain integration | Pin release matrix, compile ONNX test models and log unsupported operators |
| Model portability | Quantization, pre/post-processing and heterogeneous execution can alter results | Compare accuracy against reference framework and measure CPU offload |
| Sustained performance | Peak TOPS is not measured robot throughput | Log dataset, model, precision, P95/P99 latency, FPS, RAM, temperature and total watts |
| Industrial I/O | Sensor synchronization, fieldbus, driver and isolation requirements are system-dependent | Verify exact sensors, carrier, timing and EMC configuration |
| Reliability and security | Industrial-grade marketing does not establish a certified safety function | Obtain documented ratings, security advisories, SBOM and test evidence |
| Procurement | Supply, region, MOQ, support terms and end-of-life not established | Maintain confidential commercial evidence in private SSOT |

## Component Card completeness

| Requirement | Status |
|---|---|
| Manufacturer, family, device form | Listed; exact SKU / revision TBD |
| CPU, accelerator, precision and sparsity | TBD for selected SKU |
| RAM, storage, dimensions, cooling | TBD for selected board / system |
| Power and thermal operating points | Not tested |
| Sensor, network and robot control I/O | TBD; carrier-specific |
| OS, BSP, SDK, runtime and licenses | TBD; version matrix required |
| Security, safety, reliability and lifecycle | TBD; official evidence required |
| Supplier, price, MOQ and lead time | TBD; confidential quotes not public |
| Dataset, accuracy, FPS, P95/P99 latency and watts | Not tested |

## Manufacturer reference (confirm exact product before upgrading status)

- https://www.nvidia.com/en-us/edge-computing/products/igx/

## Publication boundary

This public record is `listed`, not independently tested, PAI-SG-verified, certified, recommended or production-qualified. Manufacturer-family references do not establish exact SKU features. Keep private supplier quotations, internal BOM, raw test logs and proprietary architecture in private SSOT.
