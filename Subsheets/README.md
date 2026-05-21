# `Subsheets/`
Contains **all child schematic pages** (`.kicad_sch`) except the root schematic.  
Keeps the top-level clean and allows KiCAD to resolve hierarchical paths properly.

> Note: Only Sheets spawned in the Root Schematic need to be created with Subsheets/xyx.kicad_sch filename. Please avoid creating multiple instances of Subsheets inside this. I will personally hunt you down and hold you captive until you fix your schematic if there are multiple instances on your repo.  

---