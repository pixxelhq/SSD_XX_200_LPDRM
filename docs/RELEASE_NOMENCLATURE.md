# Release Nomenclature

This document defines the **standard release naming scheme** used across Pixxel KiCAD PCB repositories.  
Every hardware release tag follows the format:

```text
BoardName-A.x.y.z


┌───────────────────────────────────────────────┐
│                Release Tag                    │
│        BoardName - A . x . y . z              │
│                     │   │   │   │             │
│                     │   │   │   └─► z → Symbol / Parameter-level change
│                     │   │   └─────► y → Schematic / BoM / Assembly change
│                     │   └─────────► x → PCB Layout-level change
│                     └─────────────► A → Revision Stage (A–G)
└───────────────────────────────────────────────┘
```

| Segment       | Example                                | Description                                                        |
| ------------- | -------------------------------------- | ------------------------------------------------------------------ |
| **BoardName** | `HPDRM`, `OBC`, `GIT` | Name of the PCB or subsystem. Usually matches the repository name. |
| **A**         | `A` → `G`                              | Alphabetic release stage defining maturity level.                  |
| **x**         | `0 → n`                                | Increments for **layout-level** changes.                           |
| **y**         | `0 → n`                                | Increments for **schematic or BoM-level** changes.                 |
| **z**         | `0 → n`                                | Increments for **symbol or metadata-level** changes.               |

## Alphabetic Revision Meaning

| Alphabet | Category                           | Typical Purpose                                                            |
| -------- | ---------------------------------- | -------------------------------------------------------------------------- |
| **A–D**  | **Prototype Revisions**            | Early bring-up builds used for validation and debugging.                   |
| **E**    | **Engineering Model (EM)**         | Functionally complete boards used for qualification testing.               |
| **F**    | **Flight Model (FM)**              | Hardware cleared for flight. Fully qualified and configuration-controlled. |
| **G**    | **Ground Support Equipment (GSE)** | Boards used for ground test setups or simulators.                          |

## Incrementing Rules
1. **Major Layout Change → increment x**:   
   For example:
    * Copper or routing changes.
    * New component footprints or outline modifications.
    * Layer stack-up or mechanical changes.
> Example Increment: EPS_MAIN-E.2.0.0 → EPS_MAIN-E.3.0.0

2. **Schematic / BoM / Assembly Change → increment y**   
   For example:  
    *  Component reference or value changes.
    *  Updated Pick-and-Place or assembly variant.
    *  Updated BoM for sourcing or part substitutions.
> Example Increment: EPS_MAIN-E.3.0.0 → EPS_MAIN-E.3.1.0

3. **Symbol / Parameter Change → increment z**   
   For example:  
    * Updated thermal resistance, power rating, or mass.
    * Metadata-only updates in symbol libraries.
    * Non-functional design data corrections.
> Example: EPS_MAIN-E.3.1.0 → EPS_MAIN-E.3.1.1

---

## Example Release Tags

| Release Tag   | Meaning                                                  |
| ------------- | -------------------------------------------------------- |
| `OBC-A.0.0.0` | First prototype OBC board. Initial schematic and layout. |
| `OBC-B.0.2.0` | Second prototype with BoM changes.                       |
| `OBC-E.1.0.0` | Engineering model, first layout iteration.               |
| `OBC-F.1.0.3` | Flight model with metadata corrections.                  |

---
_Last Updated: 23-10-2025 - Pixxel EEE Team_