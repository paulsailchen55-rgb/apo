# Santa Cruz County Geological Mapping — Research Record and Experiment Log

## Purpose

This document preserves the broader research conversation behind the Santa Cruz County GIS → Google Earth workflow. It is intentionally separate from the operational workflow document so the archive retains not only how the data is handled, but also why the mapping experiment exists, what questions it investigates, what has already been tried, and how the reading and settlement framework connect to it.

The project begins with Santa Cruz County and is intended to become a repeatable framework for all 58 California counties.

### Core research statement

> **Identify and classify the physical ground conditions and geological processes across Santa Cruz County.**

This is the first task. Questions about human settlement come later.

The research should not begin by assuming that all mapped "land" is equivalent, stable, or mechanically uniform. The purpose is first to understand the physical substrate and the processes that have produced, moved, fractured, deposited, eroded, or otherwise changed it.

---

## What Started the GIS Investigation

The Santa Cruz County GIS/GISWeb system provides a large collection of mapped information about the county. The important discovery was that the County GIS is not simply a single map: it is a collection of different spatial datasets that can be examined separately and then related to one another.

### Broad County GIS inventory

Examples encountered in the County GIS include:

- Parcels
- Building footprints
- Streets
- Elevation and elevation benchmarks
- Water
- Parks
- Fault zones
- Fire hazards
- Flood zones
- Soils
- Groundwater/recharge information
- Watersheds
- Geologic information
- Paleontological information
- Mineral resources
- Geologic hazard screening areas
- Debris-flow hazards
- Coastal hazards and bluffs
- Landslide/geologic information

The point is not that every layer should become part of one composite map. These datasets provide different observations of the same physical county.

The geological question is therefore a **layered comparison problem**.

---

# Research Sequence

## Experiment 1 — Learn the County GIS Map

The first experiment was deliberately simple.

The purpose was to learn how the County GISWeb actually works before attempting to interpret its geological information.

### Tasks

1. Open the County GISWeb map.
2. Examine the disclaimer and map interface.
3. Locate the Layer/Legend controls.
4. Turn on one geological or geological-hazard layer.
5. Turn it off and turn on another.
6. Compare the different layers visually.
7. Click locations on the map to see what information is available.
8. Explore Select & Query.
9. Explore measurement tools.
10. Explore Draw & Print.
11. Learn how the map represents different kinds of information.

### Why Experiment 1 matters

This is an orientation experiment, not a geological conclusion.

It establishes the County's spatial language before building a separate research interpretation.

It also preserves an important historical fact: this is not the user's first exposure to the County GIS. The user had already experimented with the County map at the library years ago, trying to understand and work with the information. The current experiment is different because AI can now help organize the investigation, identify relevant layers, preserve the research trail, and turn repeated exploration into a reproducible workflow.

The current work is therefore a **revisiting and restructuring of an older hands-on investigation**, not the first discovery of GIS.

---

# Experiment 2 — Mapped County and State Fault Zones

## Selected dataset

**Mapped County and State Fault Zones — Layer 133**

This was selected as the first concrete data-export experiment.

The County publishes it as an ArcGIS Feature Layer with polygon geometry.

Source:

https://sccgis.santacruzcountyca.gov/server/rest/services/gisweb/MapServer/133

Query endpoint:

https://sccgis.santacruzcountyca.gov/server/rest/services/gisweb/MapServer/133/query

The layer uses the County service spatial reference associated with California State Plane Zone 3, NAD 1983, US survey feet (WKID 2227 / service spatial reference 102643).

The layer contains the coded values:

- CFZ
- SFZ

## Export experiment

The County Query operation provides a particularly useful discovery: KMZ is an available output format.

The first proposed query is:

- **Where:** 1=1
- **Out Fields:** *
- **Return Geometry:** True
- **Output Spatial Reference:** 4326 / WGS 84
- **Format:** KMZ

This creates the possible direct pipeline:

**County GIS REST Feature Layer → Query → WGS 84 → KMZ → Google Earth**

rather than requiring a separate GIS conversion program.

## Provenance to preserve

For every export, record:

- County GIS service URL
- Layer ID
- Query parameters
- Access/download date
- Original coordinate system
- Output coordinate system
- Output format
- Filename
- Any filtering or transformations

Suggested filename:

SantaCruz_Mapped_County_State_Fault_Zones_CountyGIS_YYYY-MM-DD.kmz

## Important status distinction

The County Query page establishes that KMZ is an available output format. The workflow document records that the final downloaded KMZ still requires user-side verification in Google Earth.

Therefore:

**Service-level discovery is established; final Google Earth import verification is a separate experimental observation.**

The source layer itself is not the research conclusion. Fault zones are one piece of the physical-ground investigation.

---

# Experiment 3 — Move From Structure to Ground Composition

The next experimental direction is to move from a structural/hazard layer toward a layer that more directly describes **what the ground is made of**.

The primary candidate identified was:

**Geologic Unit — Layer 140**

Other nearby candidates include:

- County Landslide Map
- Mapped Small Landslides and Debris Flows
- Geologic Structures — Faults
- State Fault Traces
- Liquefaction
- Soils
- Geologic Hazard Screening Areas
- GeoPaleo
- Mineral Resources
- Strike and Dip of Geologic Units
- Geologic Structures — Folds

The reason for selecting Geologic Unit as the next conceptual step is that the research should distinguish:

**where the ground is**
from
**what the ground consists of**
from
**what has happened to it**
from
**how it behaves**.

---

# Working Geological Research Model

## 1. Physical ground/material

What physically exists beneath and at the surface?

Examples:

- Bedrock
- Sediment
- Soil
- Deposited material
- Weathered material
- Fractured material
- Fill
- Landslide material
- Other mapped geological units

## 2. Geological process/history

What processes created or modified that material?

Examples:

- Tectonic deformation
- Faulting
- Folding
- Uplift
- Deposition
- Erosion
- Weathering
- Hydrologic transport
- Landsliding
- Debris flows
- Seismic shaking
- Rockfall
- Coastal erosion
- Other mass movement

## 3. Mechanical behavior

How does the material behave under relevant forces?

Questions include:

- Does it remain relatively coherent?
- Does it fracture?
- Does it slide?
- Does it erode?
- Does it settle?
- Does water change its behavior?
- Does shaking change its behavior?
- Does the material tend to accumulate, disperse, or migrate?

This is not a single stability score. Different materials and processes can behave differently under different conditions.

## 4. Evidence of past processes

What evidence remains in the landscape?

Examples:

- Fault traces and zones
- Landslide deposits
- Debris-flow paths
- Rockfall distributions
- Erosional forms
- Depositional surfaces
- Geomorphic relationships
- Geologic contacts
- Seismic signatures preserved in the landscape

## 5. Settlement question

Only after the physical ground and geological processes have been separately examined should the project ask how those conditions relate to human settlement.

This preserves the distinction between **describing the ground** and **making a settlement decision**.

---

# Three-Book Synthesis

Three books were identified as complementary conceptual tools for reading the landscape.

## William B. Bull
### *Tectonic Geomorphology of Mountains: A New Approach to Paleoseismology*

### Main research contribution

Bull provides a way to think about geological landscapes as records of tectonic and seismic processes.

A major idea explored in the discussion was that prehistoric seismic shaking can leave measurable landscape evidence, including rockfall and other distributed geomorphic effects.

The developing analogy is that an earthquake can affect a landscape somewhat like a structure being shaken: material can break, detach, move, and accumulate elsewhere. The resulting distribution can become evidence of the event or of repeated processes.

### Questions for this book

- What measurable landscape features can preserve evidence of prehistoric seismic shaking?
- How can rockfall or related deposits be used as evidence rather than merely as isolated observations?
- How can probability-density or other statistical approaches describe a landscape-scale distribution?
- What does the spatial distribution of broken or displaced material tell us about the forces acting on the landscape?
- How can seismic history be separated from ordinary erosion, weathering, and other causes of material movement?
- Which concepts can be translated into GIS layers for Santa Cruz County?

### Connection to the project

Bull is most directly connected to the **process/history → evidence of past forces** part of the research model.

---

## David D. Alt and Donald W. Hyndman
### *Roadside Geology of Oregon*

### Main research contribution

This book provides a practical way of reading a landscape laterally and sequentially.

Road cuts, mountains, valleys, faults, rock units, sedimentary units, volcanic units, and erosional forms can be understood as visible cross-sections through geological history.

The important methodological idea is to stop treating the landscape as a uniform surface and instead ask what the exposed landscape is showing about the material underneath it.

### Questions for this book

- How can a person learn to read geological structure directly from the landscape?
- What can road cuts and exposed surfaces reveal about underlying units?
- How do mountains, valleys, faults, and rock formations relate spatially?
- How can a sequence of observations along a route become a geological cross-section?
- Which observations can be represented spatially in GIS?
- How can this method help interpret Santa Cruz County without assuming that Oregon's geology is directly transferable?

### Connection to the project

Alt and Hyndman are most directly connected to the **physical ground/material → spatial observation → geological history** portion of the framework.

---

## Lawrence Robb
### *Oreforming Processes*

### Main research contribution

Robb provides a broader systems perspective on how geological materials move, concentrate, alter, and interact through geological processes.

The relevant concepts include:

- Fluids
- Pressure
- Temperature
- Fractures
- Permeability
- Deposition
- Concentration
- Alteration
- Chemical interaction
- Geological recycling

This book is farther from the immediate GIS task than Bull or Alt & Hyndman, but it contributes a useful conceptual reminder:

**geological material is part of a moving system.**

A map of what exists at the surface does not by itself explain how the material arrived there or how it may change.

### Questions for this book

- How do fluids and pressure move material through geological systems?
- How do fractures and permeability affect movement?
- How do materials become concentrated or altered?
- What processes move material from one geological environment to another?
- Which processes are relevant to understanding Santa Cruz County's present physical ground?
- How can geological material be understood as part of a continuing system rather than as static matter?

### Connection to the project

Robb is most directly connected to the **process → movement → alteration → material distribution** portion of the framework.

---

# Three-Book Synthesis

Taken together, the three books provide three different ways of reading the same landscape:

| Book | Primary lens | Core question |
|---|---|---|
| Bull — *Tectonic Geomorphology of Mountains* | Tectonic/seismic landscape evidence | What forces acted on the landscape, and what evidence remains? |
| Alt & Hyndman — *Roadside Geology of Oregon* | Spatial/field interpretation | What does the visible landscape reveal about the ground beneath it? |
| Robb — *Oreforming Processes* | Geological material movement | How do fluids, pressure, fractures, chemistry, and other processes move and alter material? |

The synthesis is not intended to prove a single theory. It is a reading framework:

**material → process/history → mechanical behavior → evidence → spatial comparison**

---



# New Methodological Branch — Dating and Process Evidence

The reading of Bull also adds a methodological branch that should not be forced into the basic GIS workflow. A separate methods document now records how to investigate four complementary evidence approaches:

- **Stratigraphic** — sequence and relationships of materials and deposits.
- **Geomorphic** — landforms and the processes that create or modify them.
- **Dendrochronologic** — tree-ring evidence that may constrain the timing of disturbances.
- **Lichenometric** — possible surface-age or relative-chronology evidence from suitable lichen-covered surfaces.

These methods are not assumed to be directly downloadable from County GIS. Instead, the GIS can provide the spatial starting point, while USGS sources, scientific reports, field observations, and specialist measurements can provide additional evidence.

The intended multi-source path is:

**County GIS → candidate location → Google Earth → identify question → USGS/scientific source → field or specialist evidence when appropriate → geographically referenced research layer**

This creates a practical bridge between the easier-to-navigate local County GIS and deeper scientific sources that may be harder to discover or work with directly.

See SANTA_CRUZ_LANDSCAPE_DATING_AND_PROCESS_EVIDENCE_METHODS.md for the detailed questions, extraction strategy, limitations, and proposed workflow.


# Human Settlement Research Flow

The settlement question is deliberately downstream from the geological investigation.

The working conceptual flow is:

**Physical substrate**
↓
**Geological processes and history**
↓
**Mechanical behavior**
↓
**Evidence of seismic / landslide / erosion / deposition / other processes**
↓
**Classification of ground conditions**
↓
**Human settlement analysis**

This ordering is important.

The project is not initially asking:

> "Where should people build?"

It is first asking:

> **"What physical ground exists here, how did it form, and what processes continue to affect it?"**

Only after that description is developed does settlement become a meaningful later question.

---

# Ground as Dynamic Material

One conceptual motivation for the project is the observation that "land" can be misleading as a simple category.

Much of the Earth's surface is solid, but the surface environment also contains material that is:

- Deposited
- Transported
- Compacted
- Weathered
- Fractured
- Eroded
- Reworked
- Saturated
- Displaced
- Accumulated

Therefore the research may use the phrase **physical ground conditions** rather than treating "land" as a single uniform substance.

The phrase "land as a fluid" was explored as a conceptual metaphor, not as a literal claim that ordinary rock is a fluid on human timescales.

The useful scientific question is instead:

> **Which parts of the landscape consist of relatively persistent geological material, and which parts are more strongly shaped by continuing transport, deformation, erosion, deposition, saturation, or mass movement?**

That question can be investigated without prematurely assigning a universal stability score.

---

# Historical and Current Method

## Earlier hands-on phase

The user previously experimented with the Santa Cruz County GIS at the library years ago, attempting to work with the map and understand its layers.

That earlier work established familiarity with the basic idea but did not produce a durable research archive.

## Current AI-assisted phase

The current experiment changes the workflow by using AI to:

- inventory the available GIS layers;
- distinguish source data from interpretation;
- identify relevant geological datasets;
- organize experiments;
- document exact queries;
- preserve provenance;
- connect GIS observations with geological reading;
- maintain a running research record;
- prepare the method for eventual repetition across all 58 California counties.

The purpose is not to replace hands-on observation. It is to make the observation **repeatable, organized, and recoverable**.

---

# Data and Interpretation Rules

## Separate source data from interpretation

County GIS layers should remain identifiable as County source data.

A County classification should not silently become a research conclusion.

## Preserve provenance

Every derived dataset should retain enough information to answer:

- Where did it come from?
- When was it obtained?
- Which layer was used?
- What query was run?
- What coordinate system was used?
- Was anything filtered or transformed?
- What format was produced?

## Preserve uncertainty

Record:

- Map scale
- Spatial resolution
- Accuracy
- Coverage
- Date/version
- Known limitations
- Missing information

## Avoid premature scoring

Do not immediately reduce the geological landscape to a single numerical "good land/bad land" classification.

First understand the individual variables and their relationships.

## Keep experiments reversible

The source dataset should remain intact. Research layers should be separate and reproducible.

---

# Potential Layer Families for Future Comparison

The County GIS inventory suggests several families of evidence.

### Geological structure

- Mapped County and State Fault Zones
- State Fault Traces
- Geologic Structures — Faults
- Geologic Structures — Folds
- Strike and Dip of Geologic Units

### Geological composition

- Geologic Unit
- Soils
- Soil Types
- Expansive Soils
- Mineral Resources

### Mass movement

- County Landslide Map
- Mapped Small Landslides and Debris Flows
- Mapped Landslide Direction

### Groundwater and water-related processes

- Groundwater/recharge information
- Watersheds
- Karst Springs
- Karst Areas

### Hazards

- Liquefaction / Liquefiable Soils
- Geologic Hazard Screening Areas
- Flood zones
- Fire hazards
- Coastal hazards and bluffs

### Geological history and context

- GeoPaleo
- Geologic Reports
- Paleontological information

These families should initially be studied independently and then compared.

---

# Santa Cruz → California Generalization

Santa Cruz County is the initial laboratory.

The long-term objective is a framework that can be repeated across:

**Santa Cruz County → remaining California counties → all 58 California counties**

The eventual statewide workflow should distinguish:

### Universal components

- Layer inventory
- Source/provenance recording
- Coordinate-system handling
- Export/query procedure
- Google Earth visualization
- Research-layer separation
- Uncertainty recording
- Cross-layer comparison
- Documentation

### County-specific components

- Available layers
- Naming conventions
- Geological classifications
- Spatial reference systems
- Data formats
- Coverage
- Mapping scale
- Local geological processes
- Local hazards and limitations

The Santa Cruz experiment therefore serves both as geological research and as a test of the **method itself**.

---

# Archive Relationship

This document belongs beside:

SANTA_CRUZ_GIS_TO_GOOGLE_EARTH_WORKFLOW.md

The workflow document answers primarily:

> **How do we get authoritative County GIS information into a usable research environment such as Google Earth?**

This research record answers:

> **Why are we doing it, what questions are we asking, what experiments have we run, what books inform the questions, and how does the geological investigation connect to the later settlement question?**

The two documents should remain separate but cross-reference one another.

The apo repository is an archive/reference record for this work, not the GIS project itself.

---

# Current Research Direction

The immediate research direction remains:

1. Complete and verify the Layer 133 fault-zone export/import experiment.
2. Test Geologic Unit (Layer 140).
3. Compare geological composition with structural and mass-movement information.
4. Continue building the physical-ground classification framework without prematurely scoring it.
5. Use the three-book synthesis as a set of questions for interpreting the mapped evidence.
6. Keep the human-settlement question downstream from the physical-ground investigation.
7. Revise the method as actual GIS work reveals what is possible.
8. Preserve the resulting workflow so it can eventually be repeated across California.

## Working statement

> **Identify and classify the physical ground conditions and geological processes across Santa Cruz County.**

That statement is the anchor for the first phase of the project.
