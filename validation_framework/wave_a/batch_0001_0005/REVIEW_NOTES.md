# Wave A / Batch 1 — source and claim extraction (CMP-EAM-0001–0005)

This is **source extraction, not completed datasheet verification or independent testing**. CSV `source_checked` means official page was located; no second reviewer approval. Do not change catalog statuses yet.

## Initial findings
- 0001: NVIDIA official product specification gives 67 INT8 TOPS, 8GB RAM, 102 GB/s bandwidth, and 7–25W configurable module power. The latter is not total system draw. Sparse/dense comparison requires a separate precision/sparsity source.
- 0002: NVIDIA family comparison page located; 8GB and 16GB must become separate SKU claims. No quantitative claims entered yet.
- 0003: NVIDIA AGX Orin technical brief Table 1 provides 32GB and 64GB module variants, 200 and 275 INT8 TOPS respectively. Peak figures are not sustained robot inference. Check source revision against latest family specifications.
- 0004: NVIDIA Thor family and module datasheet references found; verify exact T4000/T5000 revision and stable public datasheet URL before extracting values. No numeric claims entered.
- 0005: Qualcomm official RB5 hardware guide identifies QRB5165 SoM plus development mainboard; Qualcomm QRB5165 page lists 15 TOPS. Do not confuse QRB5165 silicon with complete RB5 kit.

## Open issues
- 0001: verify exact kit ordering SKU, Super software version, board revision and performance conditions.
- 0002: split 8GB/16GB variants, verify power and TOPS precision/sparsity.
- 0003: distinguish developer kit from production modules; check sparse conditions.
- 0004: datasheet version and model-specific numbers pending.
- 0005: SoM and carrier hardware variants; AI engine performance conditions pending.

All `reviewer`/`reviewed_at` fields are TBD because no independent engineering review has occurred. Source URLs are links only; no vendor PDFs are redistributed.
