# Normalized Hardware and Software Specification v0.1

## Entities and granularity
`Component` is the immutable catalog ID and can represent a product family. `DeviceVariant` identifies an exact orderable SKU; `Board` represents a carrier/development kit and must not inherit native interfaces without evidence. `SpecClaim` is an attributed, condition-bearing statement, never an unqualified property.

## Common field groups
- Identity: component_id, manufacturer, family, sku, revision, device_form (`soc`, `som`, `sbc`, `devkit`, `ipc`, `accelerator`, `mcu`, `fpga_soc`, `platform`), availability_date, lifecycle_source.
- Compute: cpu_arch, cpu_cores, gpu_arch, npu_type, accelerator_count, memory_capacity_GiB, memory_type, bandwidth_GBps, storage_type.
- Peak AI: value, unit (`TOPS`/`TFLOPS`), dtype (`INT4`/`INT8`/`FP16` etc.), sparsity (`dense`/`sparse`/`unspecified`), clock, power_mode, ambient_C, manufacturer_claim flag.
- Electrical/thermal: voltage_V, idle_W, workload_W, sustained_peak_W, thermal_boundary, cooling, temp_min_C, temp_max_C.
- I/O: interface, lanes/ports, direction, `native`/`carrier`/`external`/`unknown`, tested_driver, protocol_revision.
- Software: OS, kernel, BSP, runtime, compiler, SDK version, model interchange, ROS2 version, license.
- Assurance: secure_boot, signed_updates, watchdog, safety_claim, standard, certificate_scope, provenance.

## Normalization rules
Store canonical SI units with original value/unit preserved. Record `unknown`, `not_applicable`, `not_disclosed`, `not_tested` as distinct reasons; never use numeric zero for missing data. Source each number. Keep advertised peak and measured workload data in separate entities. Record power at chip, module, board and wall separately. Treat firmware and runtime versions as part of compatibility keys. Avoid single numeric device score until a concrete robot mission and weighted acceptance criteria exist.

## Quality gates
Identity completeness, evidence coverage, scope consistency, unit consistency, contradictory claims, license/publication check and reproducibility are independent gates. The public `listed`/`documented` status is not a substitute for them.
