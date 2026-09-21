# Santa Cruz County GIS → Google Earth Geological Mapping Workflow

## Status

- Stage: First data-access experiment completed at the service-definition level
- Geographic starting point: Santa Cruz County, California
- Intended eventual scope: repeatable workflow for all 58 California counties
- Primary county source: Santa Cruz County GIS / GISWeb
- Visualization and research workspace: Google Earth
- Archive repository: `apo` (archive/reference repository, not the project itself)
- Root README: do not modify unless explicitly requested

## First Tested Layer

**Santa Cruz County GIS — Mapped County and State Fault Zones (Layer ID 133)**

The County publishes this as an ArcGIS Feature Layer. It is polygon geometry and supports JSON, GeoJSON, and PBF query formats. Its coordinate system is California State Plane Zone 3, NAD 1983, US survey feet (WKID 2227 / service spatial reference 102643). The layer has two coded values: CFZ and SFZ. The County GIS service also exposes a Query operation whose output format options include **KMZ** and **GeoJSON**.

Source service:
`https://sccgis.santacruzcountyca.gov/server/rest/services/gisweb/MapServer/133`

Query endpoint:
`https://sccgis.santacruzcountyca.gov/server/rest/services/gisweb/MapServer/133/query`

This discovery changes the original plan: a separate GIS conversion program may **not** be necessary for this layer. The County's ArcGIS REST Query operation can potentially produce KMZ directly.

## First-Experiment Procedure

### 1. Open the County layer

Open the County REST page for **Mapped County and State Fault Zones (ID 133)**.

### 2. Open Query

Use the layer's **Query** operation.

### 3. Request all features

Use:

- Where: `1=1`
- Out Fields: `*`
- Return Geometry: True
- Output Spatial Reference: `4326` (WGS 84)
- Format: KMZ

The choice of WGS 84 is deliberate because it is the normal geographic coordinate reference used by Google Earth.

### 4. Download the KMZ

Save the resulting file locally with a provenance-preserving name such as:

`SantaCruz_Mapped_County_State_Fault_Zones_CountyGIS_YYYY-MM-DD.kmz`

Record:

- County GIS service URL
- Layer ID 133
- Query parameters
- access/download date
- original coordinate system (WKID 2227 / service 102643)
- output coordinate system (WGS 84 / EPSG 4326)
- output format (KMZ)

### 5. Open in Google Earth

Google Earth supports KML/KMZ geographic data. Google documents importing KML/KMZ into Earth projects and opening local KML/KMZ files. For the web version, use the file/project import or local KML workflow available in the current interface. Google Earth Pro can open KML/KMZ directly.

### 6. Verify the first import

Do not yet treat the map as scientifically validated.

Check:

- Does the layer appear in the correct geographic location?
- Does the entire County extent appear?
- Are the CFZ/SFZ polygons present?
- Do the boundaries visually correspond to the County GISWeb display?
- Does the layer remain usable when Google Earth terrain/imagery is turned on?
- Can the feature information/attributes be inspected?
- Is the file small enough for practical Google Earth use?

## Why This Is Useful

This first experiment establishes a potentially much simpler pipeline:

**County GIS REST Feature Layer**
→ **Query**
→ **WGS 84**
→ **KMZ**
→ **Google Earth**

rather than:

**County GIS**
→ download shapefile
→ GIS conversion software
→ reproject
→ KML/KMZ
→ Google Earth

The simpler route should be preferred when it preserves geometry, attributes, provenance, and reproducibility.

## Important Limitation

The Query page and layer metadata establish that KMZ is an available output format, but the assistant has not independently verified the final downloaded KMZ file inside the user's Google Earth account. The final import is therefore a user-side verification step.

If the direct KMZ route fails, fall back to GeoJSON or another downloadable format and perform an explicit conversion.

## Research Layer Separation

The County fault-zone layer is **source data**, not the research conclusion.

It should remain separate from the future research interpretation layer.

Later layers may include:

- Geologic Unit
- Geologic Structures - Faults
- State Fault Traces
- County Landslide Map
- Mapped Small Landslides and Debris Flows
- Liquefaction
- Soils
- Geologic Hazard Screening Areas
- GeoPaleo
- Mineral Resources

These should initially be examined independently rather than collapsed into a single score.

## Workflow

### Stage 1 — Inventory the County GIS

Identify relevant existing layers and record source, description, extent, scale/resolution, date/version, coordinate system, attributes, accuracy/limitations, and service/export endpoint.

### Stage 2 — Determine the Actual Data Access Method

Prefer the simplest authoritative export that preserves the needed geometry and attributes. For Layer 133, direct KMZ output is available through the Query operation.

### Stage 3 — Obtain a Working Copy

Acquire the selected source data without altering County authoritative data. Preserve provenance.

### Stage 4 — Convert for Google Earth

Only convert when the County does not provide a suitable Google Earth-compatible output. For Layer 133, test direct KMZ first.

### Stage 5 — Load Into Google Earth

Import/open the KMZ and verify alignment, completeness, scale behavior, terrain relationship, and attributes.

### Stage 6 — Create the Research Layer

Construct experimental research layers independently from source data.

### Stage 7 — Overlay and Compare

Compare research layers against County geological/hazard layers without prematurely combining unlike evidence.

### Stage 8 — Document Every Transformation

Preserve source, date, format, coordinate systems, queries, conversion tools, filtering, transformations, and limitations.

### Stage 9 — Revise the Workflow

Replace theoretical steps with the procedure actually used.

### Stage 10 — Generalize to California

Separate universal workflow components from Santa Cruz-specific components and reuse the resulting framework for the remaining 57 counties.

## Research Principles

### Separate data from interpretation

County GIS data should not be silently converted into conclusions.

### Preserve provenance

Every derived map should be traceable to its original source.

### Preserve uncertainty

Accuracy, scale, age, coverage, and limitations should remain visible.

### Avoid premature scoring

Do not create a single "good land/bad land" score until the underlying variables have been separately examined.

### Treat the landscape as a dynamic geological system

The research may examine the ground as the product of deposition, erosion, tectonic deformation, seismic shaking, rockfall, landsliding, hydrologic processes, and other geological mechanisms rather than treating "land" as a uniform substrate.

## Related Reading

- William B. Bull — *Tectonic Geomorphology of Mountains: A New Approach to Paleoseismology*
- David D. Alt and Donald W. Hyndman — *Roadside Geology of Oregon*
- Lawrence Robb — *Oreforming Processes*

These books are conceptual/background sources rather than substitutes for the County's spatial datasets.

## Current Next Experiment

After the Layer 133 KMZ import is verified, test one layer that is closer to the physical-ground question—particularly **Geologic Unit (Layer 140)** or **County Landslide Map / Mapped Small Landslides and Debris Flows**—and compare its behavior in Google Earth.

## Archive Note

This document is an evolving record of the workflow. Update it as the actual procedure changes.

The `apo` repository is being used as an archive/reference record for this work, not as the GIS project itself.
