# `archive/`
Preserves old or finalized **board revisions** such as:
- `Prototype`
- `EngineeringModel`
- `FlightModel`

Each subfolder should contain:
- Snapshot of the KiCAD project  
- Generated outputs (Gerbers, BoM, PDFs, etc.)
- Name the sub-folder as BoardName-E.0.0.0 or whatver the revision of the board is
- Refer to [Release Nomenclature](../docs/RELEASE_NOMENCLATURE.md) document for more info

> The main branch should only hold the **latest active design**. Every other revision should be zipped and stored inside the archive folder.

---