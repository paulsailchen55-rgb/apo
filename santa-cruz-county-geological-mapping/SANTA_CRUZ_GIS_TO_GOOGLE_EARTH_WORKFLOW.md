# Santa Cruz County GIS → Google Earth Geological Mapping Workflow

## Status

- Stage: Initial workflow formalization
- Geographic starting point: Santa Cruz County, California
- Intended eventual scope: repeatable workflow for all 58 California counties
- Primary county source: Santa Cruz County GIS / GISWeb
- Visualization and research workspace: Google Earth
- Archive repository: `apo` (archive/reference repository, not the project itself)
- Root README: do not modify unless explicitly requested

## Purpose

Develop a repeatable method for taking relevant, authoritative GIS information published by a county, extracting or obtaining the underlying geographic data, converting it into a format usable by Google Earth, and combining it with a separately developed research layer.

The first application is Santa Cruz County.

The broader research question is to investigate how geological structure, tectonic processes, seismic evidence, rockfall/landslide behavior, surface materials, and related physical characteristics can be mapped spatially as part of a longer-term study of where relatively persistent and suitable ground occurs for human settlement.

This is a research/mapping framework, not yet a determination of where cities should be located.

## Core Concept

The workflow separates:

1. **Authoritative county data**
   - County GIS layers
   - Geological and hazard information
   - Parcels/infrastructure where useful
   - Metadata, source, scale, and accuracy information

2. **Research interpretation**
   - A separately constructed layer or set of layers
   - Explicitly documented assumptions
   - Geological/process classifications
   - Confidence and source fields

3. **Google Earth visualization**
   - County-derived data imported as KML/KMZ or another supported format
   - Research layers placed above/beside the source data
   - Terrain and imagery used for visual comparison
   - Saved Google Earth project files for reproducibility

## Workflow

### Stage 1 — Inventory the County GIS

Open Santa Cruz County GISWeb and identify relevant existing layers.

Initial candidates include:

- fault zones
- geologic hazard screening
- GeoPaleo / geological-paleontological information
- soils
- debris-flow hazards
- coastal hazards
- coastal bluffs
- groundwater
- watersheds
- mineral resources
- other geology/geomorphology layers discovered during exploration

For each useful layer, record:

- layer name
- source/agency
- description
- geographic extent
- scale/resolution if provided
- date/version if provided
- coordinate reference system
- attributes available
- stated accuracy/limitations
- download/export/service endpoint, if available

### Stage 2 — Determine the Actual Data Access Method

For each selected layer, determine whether the County provides:

- direct download
- shapefile
- GeoJSON
- KML/KMZ
- feature service
- ArcGIS REST service
- map service
- other export mechanism

Do not assume that a visible map can be directly downloaded as a usable GIS layer.

Preserve the original source information before transforming anything.

### Stage 3 — Obtain a Working Copy

Acquire the selected source data without altering the County's authoritative data.

Create a local/research copy with clear provenance.

Suggested naming pattern:

`county_layer_source_date.ext`

Example:

`SantaCruz_fault_zones_countyGIS_YYYY-MM-DD.ext`

Maintain a simple source record describing where the data came from and what transformations are later performed.

### Stage 4 — Convert for Google Earth

Determine the simplest reliable conversion path for the particular source format.

Likely target formats:

- KML
- KMZ

Possible intermediate formats may include:

- Shapefile
- GeoJSON
- GeoPackage

The conversion should preserve, as far as practical:

- geographic position
- feature geometry
- useful attributes
- source identity
- layer names

The conversion process itself should be documented.

### Stage 5 — Load Into Google Earth

Import the converted County layer into Google Earth.

Confirm:

- geographic alignment
- visible boundaries
- feature completeness
- scale/zoom behavior
- terrain relationship
- labels/attributes where available

Save the imported source layer separately from research-created layers.

### Stage 6 — Create the Research Layer

Construct the first experimental research layer independently.

Possible initial categories:

- geological substrate/material
- tectonic structure
- seismic/earthquake evidence
- rockfall
- landslide/debris-flow evidence
- erosion/coastal processes
- hydrologic behavior
- other mechanically relevant surface conditions

Do not combine unlike evidence into one score prematurely.

Keep source observations and interpretations distinguishable.

### Stage 7 — Overlay and Compare

Place the research layer over the County-derived layers in Google Earth.

Compare spatial relationships.

Questions to investigate include:

- Do mapped hazards cluster with particular geological materials?
- Do rockfall/landslide observations correspond with particular structures or terrain?
- What areas appear repeatedly stable across different data sources?
- Where are the data sparse or contradictory?
- Which conclusions depend heavily on map scale or source accuracy?

### Stage 8 — Document Every Transformation

For every derived layer, preserve:

- original source
- download/access date
- original format
- conversion software/tool
- conversion steps
- target format
- coordinate system
- filtering or selection performed
- transformations performed
- known limitations

The goal is that another person could reproduce the map without relying on undocumented steps.

### Stage 9 — Revise the Workflow

The workflow is expected to change as actual County GIS data are processed.

When a step proves unnecessary, replace it rather than preserving a theoretical procedure.

When a new required step is discovered, add it and record why it became necessary.

The archived workflow should therefore represent the actual procedure eventually used, not merely the initial plan.

### Stage 10 — Generalize to California

After the Santa Cruz County workflow is functional, identify which portions are:

- universal to California county GIS systems
- specific to Santa Cruz County
- dependent on ArcGIS
- dependent on Google Earth
- dependent on a particular data format
- dependent on a particular geological dataset

Then use the resulting framework as a template for the remaining 57 California counties.

## Research Principles

### Separate data from interpretation

County GIS data should not be silently converted into conclusions.

### Preserve provenance

Every derived map should be traceable to its original source.

### Preserve uncertainty

Accuracy, scale, age, coverage, and limitations should remain visible in the research record.

### Avoid premature scoring

Do not create a single "good land/bad land" score until the underlying variables have been separately examined.

### Treat the landscape as a dynamic geological system

The research may examine the ground as the product of deposition, erosion, tectonic deformation, seismic shaking, rockfall, landsliding, hydrologic processes, and other geological mechanisms rather than treating "land" as a uniform substrate.

## Related Reading

The initial conceptual reading set includes:

- William B. Bull — *Tectonic Geomorphology of Mountains: A New Approach to Paleoseismology*
- David D. Alt and Donald W. Hyndman — *Roadside Geology of Oregon*
- Lawrence Robb — *Oreforming Processes*

These books are being used as conceptual/background sources rather than as substitutes for the County's actual spatial datasets.

## Current First Experiment

1. Open Santa Cruz County GISWeb.
2. Identify the first geological/hazard layer worth testing.
3. Determine how that layer can actually be obtained.
4. Record its provenance and limitations.
5. Convert it to KML/KMZ if necessary.
6. Open it in Google Earth.
7. Verify alignment and completeness.
8. Only then begin designing the first research overlay.

## Archive Note

This document is an evolving record of the workflow. Update it as the actual procedure changes.

The `apo` repository is being used as an archive/reference record for this work, not as the GIS project itself.
