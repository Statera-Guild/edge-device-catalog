# PAI-SG Knowledge Graph Connection Design v0.1

## Public / private boundary
Public `Statera-Guild/edge-device-catalog` is a derived catalog, not the core engineering SSOT. Keep supplier quotes, internal BOM, raw traces, security findings and nonpublic architectures in private SSOT. Public graph nodes may point to an opaque evidence reference only when approved; no private URLs, credentials or raw log paths.

## Node types
`Component` (`CMP-EAM-0001`), `DeviceVariant`, `Manufacturer`, `DeviceForm`, `Interface`, `SoftwareRelease`, `Algorithm`, `ModelArtifact`, `Dataset`, `SpecClaim`, `SourceDocument`, `CompatibilityAssertion`, `TestRun`, `RobotRole`, `EvidenceRecord`.

## Directed edges
`MADE_BY`, `HAS_VARIANT`, `HAS_FORM`, `HAS_INTERFACE`, `RUNS_SOFTWARE`, `SUPPORTS_ALGORITHM`, `USES_MODEL`, `TESTED_ON_DATASET`, `HAS_CLAIM`, `SUPPORTED_BY_SOURCE`, `TESTED_IN`, `SUITABLE_CANDIDATE_FOR`, `DEPENDS_ON_HOST`, `REQUIRES_CARRIER`, `SUPERSEDES`.

## Assertion model
Never assert `SUPPORTS_ALGORITHM` as a timeless yes/no. Model it as a `CompatibilityAssertion` node keyed by component/variant, algorithm, model, SDK version, execution path and evidence state; connect the assertion to sources/tests. Conflicting claims coexist with timestamps and resolution status.

## Identity and provenance
Immutable component IDs; separate variant IDs and external product codes. Stable edge IDs, source URL+revision+locator, recorded_at, valid_from, reviewer, confidence and publication permission. JSON-LD/RDF or property-graph export is optional; start with auditable CSV/JSON files and stable IDs. Ensure one-to-one mapping to the established PASG S03 Node/Edge specification before production import; names here are a proposed adapter, not a change to S03 governance.

## Example path
`Component(CMP-EAM-0002)` -> `HAS_VARIANT` -> `DeviceVariant(Orin-NX-16GB)` -> `RUNS_SOFTWARE` -> `SoftwareRelease(JetPack-version-TBD)`; a separate `CompatibilityAssertion` links this combination to `Algorithm(Detection)` with evidence_state=`candidate` until a traceable vendor claim or reproducible test is attached.

## Integrity checks
All referenced IDs exist; no orphan evidence; each quantitative claim has source+scope; software/algorithm links include version; private/public access policy enforced; deleted/obsolete sources retained as historical provenance with status, not silently overwritten.
