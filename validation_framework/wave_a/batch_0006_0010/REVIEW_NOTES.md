# Wave A Batch 2 — manufacturer evidence extraction (CMP-EAM-0006–0010)

Date: 2026-10-09. **Evidence capture, NOT completed datasheet verification.** All extracted claims remain `in_review`; no public catalog status changes and no PAI-SG benchmarks claimed. Manufacturer links were reviewed as public evidence.

| ID | Identity and scope | Unresolved verification gates |
|---|---|---|
| 0006 | RB3 Gen 2 Core Kit uses QCS6490; Lite Core Kit uses QCS5430. Different configurations must not be merged. | Determine exact board/SoM ordering numbers, revisions, camera I/O and module versus board power. |
| 0007 | Robotics RB6 platform page specifies QRB5165, Kryo 585 and Adreno 650. | Confirm platform vs development board SKU; AI throughput precision and operating mode; software version. |
| 0008 | IQ9 Series marketing page advertises family-level 100 TOPS and names IQ-9075 module brief. | Verify precise IQ-9075 ordering SKU, precision/sparsity/power, and module-versus-platform scope from product brief. |
| 0009 | Intel Core Ultra for Edge is a multi-SKU processor family, not a single device. 15–65 W is a family/platform range, not a per-SKU power claim. | Select exact embedded SKU(s) and Intel ARK datasheets before device-level normalization. |
| 0010 | AMD DS987 v1.6 lists SM-K26-XCL2GC (commercial) and SM-K26-XCL2GI (industrial). | Verify each SKU's temperature limits, power, carrier and AI implementation; K26 is FPGA-based SOM, not a discrete GPU. |

## Important data integrity notes
- The source_registry `license_publication=link_only` means cite URLs only; no reproduction rights asserted.
- Manufacturer advertising is not a test result. `in_review` requires independent second-pass verification.
- A Core Ultra family page currently presents Series 3 SKUs; catalog card 0009 should be disambiguated rather than silently redefined.
- Qualcomm RB3 Gen 2 Core and Lite products are different variants, not interchangeable specs.
- No benchmarked YOLO, DETR, tracking, segmentation, SLAM, VLM or world-model compatibility is claimed.
