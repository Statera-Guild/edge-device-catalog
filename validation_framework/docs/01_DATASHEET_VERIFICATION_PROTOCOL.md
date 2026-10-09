# Datasheet Verification Protocol v0.1

## Scope and gates
The inventory contains CMP-EAM-0001 through CMP-EAM-0060. A catalog row or card is **not** evidence that a product datasheet has been checked. Use `listed` or `documented` only for the public card status. Evidence review is a separate workflow (`not_started`, `in_review`, `source_checked`, `blocked`); `source_checked` is NOT a product certification.

1. Identify device family, exact orderable SKU, silicon revision, board/carrier, and region. Split incompatible variants rather than copying specifications across them.
2. Collect official manufacturer product page, downloadable datasheet, errata, hardware guide, BSP/SDK release notes and lifecycle statement. Record URL, title, publisher, publication/revision date, accessed date and page/table/section.
3. Extract each claim as an individual fact with units, conditions and scope. Unknown, unpublished and inapplicable are different states.
4. Check that the fact applies to the precise SKU and measurement boundary (chip/module/board/full system). Capture contradictory sources and resolve or leave disputed.
5. Have a second reviewer check critical claims: power, AI throughput, I/O, thermal range, safety/security and lifecycle.
6. Change card status to `documented` only when official public documentation actually supports the card's substantive statements. Do not claim PAI-SG testing.

## Evidence hierarchy
A: Manufacturer official SKU datasheet / errata; B: Manufacturer hardware/SDK documentation; C: Manufacturer marketing product page (qualified); D: Distributor or partner documentation; E: third-party community. C–E alone are insufficient for hard industrial/safety claims. Record license/publication restrictions; do not redistribute copyrighted datasheets.

## Required claim fields
`claim_id`, `component_id`, `sku`, `field_path`, `value`, `unit`, `precision`, `sparsity`, `power_mode`, `temperature`, `boundary`, `source_id`, `locator`, `review_state`, `reviewer`, `reviewed_at`.

## Hard stops
Do not infer safety certification from a safety-oriented platform. Do not treat a development kit as a production SoM. Do not compare TOPS across precisions, sparsity or power modes. Never publish supplier quotes, proprietary BOM, restricted manuals or private test logs.

## Initial review order
Wave A: 0001–0015 (15); Wave B: 0016–0030 (15); Wave C: 0031–0045 (15); Wave D: 0046–0060 (15). Within each wave prioritize exact SKU identity, NPU presence, SDK availability, power and camera/control I/O. Each wave exits only after unresolved claims are explicitly flagged, not silently filled.
