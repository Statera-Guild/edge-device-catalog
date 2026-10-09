# PAI-SG Edge Device Validation Package v0.1

This package defines **workflows and empty data templates**, not completed datasheet validation. 60 inventory IDs are prepopulated as `unchecked` / `not_started` until verified against repository contents and official manufacturer evidence.

Start with `docs/05_IMPLEMENTATION_PLAN.md`; review the four technical specifications in order. Fill CSV templates and use the JSON schema for public structured component records. Never commit private supplier or raw test evidence to the public catalog.

Suggested public repository destination: `validation_framework/docs`, `validation_framework/templates`, `validation_framework/schemas`. Preserve existing README and append a link to this framework rather than replacing the catalog index.
