# Implementation Roadmap and Acceptance Gates

**Phase 0 — Inventory integrity.** Confirm that all 60 `component_cards/CMP-EAM-XXXX.md` paths exist on GitHub, README links resolve, there are no duplicated IDs, and every card has one of `listed` or `documented`. README count alone does not prove files exist.

**Phase 1 — Evidence baseline (4 waves of 15).** Register official source documents and claims; resolve device family/SKU boundaries. Target 100% of 60 cards with an explicit evidence review state; do not imply 100% datasheet validation.

**Phase 2 — Normalization.** Fill structured variant and claim records. Check units, precision/sparsity, native-vs-carrier I/O, module-vs-wall power and software version keys. No unqualified cross-vendor TOPS ranking.

**Phase 3 — Algorithm matrix.** First 10 representative platforms across GPU, NPU, accelerator, MCU and FPGA families; run fixed small benchmark suite, then expand by workload need. Keep unknown as unknown.

**Phase 4 — Graph adapter.** Import manufacturer, component, variant, source, claim and compatibility nodes into staging graph; run referential-integrity and privacy checks; map to canonical S03 node/edge contracts.

**Phase 5 — Publication.** Publish approved normalized facts and evidence summaries only. Maintain private raw measurements, supplier terms and security-sensitive evidence in core SSOT.

## Acceptance criteria
- 60/60 file existence verified, not inferred from README.
- 60/60 assigned review state and explicit unresolved fields.
- Every published numeric spec traceable to a source locator and exact SKU/boundary.
- No algorithm marked reproduced without a version-pinned test run.
- All graph edges resolve and public export contains no restricted evidence.
