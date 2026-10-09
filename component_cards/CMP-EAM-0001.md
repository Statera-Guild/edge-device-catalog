# NVIDIA Jetson Orin Nano Super Developer Kit — PAI-SG Component Card

- **Status:** Research draft; official specifications checked; PAI-SG integration unverified
- **Reviewed:** 2026-10-09
- **Vendor:** NVIDIA
- **Product:** Jetson Orin Nano Super Developer Kit
- **Device class:** Developer kit (module plus reference carrier board); not an industrial production computer
- **PAI-SG categories:** E01 Low-Power Edge AI; E02 Vision AI; E03 Autonomous Navigation (candidate)
- **Priority:** P1

## Hardware and AI specifications

| Field | Value | Qualification |
|---|---|---|
| GPU | NVIDIA Ampere; 1,024 CUDA cores, 32 Tensor Cores | NVIDIA official |
| CPU | 6-core Arm Cortex-A78AE 64-bit; up to 1.7 GHz in Super configuration | NVIDIA official |
| AI performance | Up to 67 INT8 TOPS sparse; approximately 33 dense INT8 TOPS | Peak theoretical; not application FPS |
| Memory | 8 GB, 128-bit LPDDR5 | NVIDIA official |
| Memory bandwidth | Up to 102 GB/s | Super configuration |
| Power | Configurable module power 7–25 W | Not full robot system consumption |
| Storage | microSD; external NVMe via M.2 Key M | Development carrier |
| Networking | 1 × Gigabit Ethernet | Development carrier |
| USB | 4 × USB Type-A 3.2 Gen 2; USB-C device/recovery | Verify carrier revision |
| Camera | 2 × MIPI CSI-2 camera connectors | Sensor/driver compatibility must be checked |
| Expansion | 40-pin GPIO/UART/SPI/I2C/I2S header | Not a safety-rated control interface |
| Display | DisplayPort | Development carrier |
| Operating system / SDK | NVIDIA Jetson Linux / JetPack; CUDA; TensorRT; Isaac ROS ecosystem | Match software versions to BSP |

## PAI-SG design suitability

Candidate for YOLO/DETR inference, segmentation, multi-object tracking, single-robot perception and constrained SLAM workloads. Small VLM demonstrations are possible subject to quantization, memory and latency. This card does **not** claim validated real-time performance, multi-camera capacity, or compatibility with a specific ROS 2 release.

**Architecture rule:** Keep safety-critical motion control and emergency-stop functions on independently validated controllers. The developer kit is not a substitute for a certified functional-safety controller.

## Vendor and integration risk register (preliminary, not measured)

| Risk | Impact on robot design | Verification / mitigation |
|---|---|---|
| CUDA/TensorRT ecosystem dependency | Porting to non-NVIDIA hardware requires additional engineering | Maintain ONNX model exports and benchmark alternate runtimes |
| 8 GB shared memory ceiling | Simultaneous perception, mapping and VLM models may exceed memory | Profile peak RAM/VRAM, use quantization and workload partitioning |
| Peak TOPS versus sustained throughput | Published TOPS does not predict robot application FPS | Benchmark end-to-end FPS, P95/P99 latency and thermal throttling |
| Developer kit versus production SOM | Carrier, cooling, power and I/O differ in production | Create separate production-module and carrier-board cards |
| Camera and LiDAR driver compatibility | CSI/USB/network devices may need custom drivers | Validate actual sensor part numbers against JetPack/BSP |
| Thermal and power margin | 25 W module setting excludes other peripherals and conversion losses | Measure full-system input power under worst-case loads |
| Software version lifecycle | JetPack, kernel, CUDA and ROS 2 combinations may conflict | Pin BSP/container versions; maintain compatibility matrix |
| Industrial operating conditions | Development kit is not evidence of vibration, ingress or temperature qualification | Request module/carrier environmental data and perform validation |
| Supply / procurement | Price, regional availability and lifecycle may change | Verify distributor quotes and production-module lifecycle |

## Mandatory Component Card data — completion tracking

| Category | Required fields | Status |
|---|---|---|
| Identification | Vendor, product, part number, revision, device class | Partial — SKU/revision TBD |
| Compute | CPU, GPU, NPU/DSP/FPGA, precision and sparsity | Partial — no dedicated NPU specified |
| Memory | RAM capacity, type, bandwidth, storage | Documented |
| Power | Idle, typical, peak, input voltage, efficiency | Partial — only module power modes |
| Physical | Size, weight, thermal solution, mounting | TBD — carrier revision dependent |
| Sensor I/O | MIPI CSI, USB, Ethernet, LiDAR/GMSL compatibility | Partial |
| Control I/O | CAN, CAN-FD, GPIO, SPI, UART, EtherCAT | Partial — add-on interfaces not assumed |
| Software | Linux/JetPack/BSP, ROS 2, CUDA, TensorRT, drivers | Partial — versions TBD |
| AI compatibility | Detection, tracking, segmentation, SLAM, VLM, VLA | Candidate only; benchmarks TBD |
| Safety/security | Secure Boot, TPM, watchdog, safety certifications | TBD — do not infer certification |
| Reliability | Temperature, vibration, shock, MTBF, lifecycle | TBD |
| Procurement | Price, MOQ, lead time, supplier, EOL | TBD |
| Validation | Models, dataset, FPS, latency, memory, power, evidence | Not tested |

## Official sources

1. [NVIDIA Jetson Orin Nano Super product specifications](https://www.nvidia.com/en-us/autonomous-machines/embedded-systems/jetson-orin/nano-super-developer-kit/)
2. [NVIDIA technical blog — Super boost and sparse/dense performance](https://developer.nvidia.com/blog/?p=93942)
3. [NVIDIA Jetson Orin Nano Developer Kit user guide](https://docs.nvidia.com/jetson/orin-nano-devkit/user-guide/latest/)
4. [NVIDIA Jetson developer kits](https://developer.nvidia.com/embedded/jetson-developer-kits)
5. [NVIDIA carrier board specification](https://developer.nvidia.com/downloads/assets/embedded/secure/jetson/orin_nano/docs/jetson_orin_nano_devkit_carrier_board_specification_sp.pdf)

## Publication notes

This is a preliminary evidence-backed public component card, not a purchase recommendation or validation certificate. Vendor-published specifications are distinguished from engineering hypotheses and test results. Supplier quotations, internal BOM and proprietary test evidence should be maintained separately from the public card.
