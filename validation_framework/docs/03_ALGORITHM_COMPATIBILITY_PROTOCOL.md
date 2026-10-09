# Algorithm Compatibility Matrix and Test Protocol v0.1

## Two axes, not one label
Keep `evidence_state` (`unknown`, `candidate`, `vendor_claim`, `reproduced`, `failed`, `not_applicable`) separate from `execution_path` (`native_accelerator`, `cpu_fallback`, `gpu_fallback`, `host_offload`, `unsupported`, `unknown`). A CPU fallback is not proof of NPU operator support. `reproduced` is an internal test state and does not change the public card's `listed`/`documented` vocabulary.

## Workload families
Classification (ResNet18/MobileNet), detection (YOLO/DETR), semantic/instance segmentation, multi-object tracking (ByteTrack/DeepSORT plus detector), depth/pose, VIO/SLAM, sensor fusion, VLM, VLA, video transformer, and world model. Tracking and SLAM are pipelines, not always single accelerator models; record each stage and host CPU/GPU/NPU execution.

## Minimum experiment record
Component ID, exact SKU and carrier, OS/kernel/BSP, driver/runtime/compiler versions, framework, model and revision/hash, input resolution, batch, precision, quantization calibration dataset, test dataset license/version, camera/host path, warm-up, sample count, ambient, cooling, power mode, accuracy metric, throughput, median/P95/P99 end-to-end latency, sustained 30-min thermal/power measurements, RAM, unsupported operators, failures, log/evidence ID.

## Three-stage validation
1. `convert`: export and compile a small reference model; record unsupported operators and accuracy drift.
2. `run`: inference on fixed data; report both accelerator-only and full pipeline latency.
3. `integrate`: camera timestamps, ROS 2 nodes, concurrent workloads, host load and failover. A safety controller is evaluated separately.

## Suggested minimum acceptance logic
Define per-robot requirements before pass/fail (e.g. deadline, power, accuracy, temperature). Never set generic universal FPS thresholds. A test without a version-pinned model and reproducible configuration remains exploratory.
