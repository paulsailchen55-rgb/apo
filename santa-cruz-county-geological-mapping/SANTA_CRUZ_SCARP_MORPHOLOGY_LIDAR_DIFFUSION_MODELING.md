# Santa Cruz County Scarp Morphology, LiDAR, and Diffusion-Model Research

## Purpose

This document preserves a new methodological branch of the Santa Cruz County geological-mapping project:

> **Use high-resolution topography, scarp morphology, orientation, vegetation/microclimate observations, and quantitative landform-evolution models to investigate whether present-day landscape form can preserve measurable evidence of past geomorphic and tectonic processes.**

The immediate focus is **scarps** and scarp-like landforms. The research is not limited to tectonic scarps. Candidate origins include:

- Tectonic/fault scarps
- Fluvial terrace risers and related river-cut features
- Lacustrine shoreline scarps or terrace risers
- Wave-cut/coastal scarps
- Landslide-related scarps
- Human-made or modified scarps

The important methodological point is that **morphology alone does not establish origin**. Origin must be cross-checked against geological units, faults, drainage, terraces, shoreline/coastal context, landslide mapping, field evidence, and other authoritative sources.

---

# The Mathematical Idea: Scarp Diffusion

The mathematical direction identified in the reading is the use of a **diffusion equation to model the degradation of a scarp through time**.

USGS literature describes the basic model as a landform-evolution problem in which mass is conserved and downslope transport is related to surface slope. In the simplest linear model, scarp morphology evolves according to a diffusion equation.

A representative form is:

$$
\frac{\partial z}{\partial t}=\kappa\frac{\partial^2 z}{\partial x^2}
$$

where:

- $z$ = elevation
- $x$ = horizontal distance across the scarp
- $t$ = time
- $\kappa$ = diffusivity coefficient with dimensions of length²/time

The product $\kappa t$ is commonly described as **diffusion age** or **morphologic age**. It represents the amount of diffusive modification expressed in the landform, not automatically a calendar age unless the diffusivity is independently constrained.

USGS and related literature emphasize that solutions to this equation can reproduce the evolution of scarp profiles and can therefore be used to investigate the relationship between scarp shape and time. citeturn0search2turn0search6turn0search10

### Important limitation

The simple diffusion equation is a model, not a universal law of scarp evolution.

Observed scarps can be affected by:

- Drainage incision
- Soil wash
- Landsliding
- Rockfall
- Vegetation
- Soil moisture
- Lithology
- Climate
- Aspect/orientation
- Initial scarp geometry
- Multiple faulting events
- Continuing tectonic deformation
- Human modification

Therefore the research should first ask **whether a candidate scarp behaves sufficiently like the assumptions of the selected model** before attempting to infer an age.

---

# Key Reference: Height, Orientation, Microclimate, and Vegetation

A particularly relevant USGS study is:

**K. L. Pierce and Steven M. Colman (1986), “Effect of height and orientation (microclimate) on geomorphic degradation rates and processes, late-glacial terrace scarps in central Idaho.”**

The study used terrace scarps as a natural laboratory and examined scarp height and orientation while holding other variables as constant as possible. It found that the observed degradation rate varied with scarp height and orientation, and that south-facing scarps were less vegetated and more degraded than north-facing scarps in the studied environment. The authors related orientation effects to differences in solar radiation, freeze-thaw cycles, soil moisture, and vegetation. citeturn0search0turn0search1

This is directly relevant to the proposed Santa Cruz workflow because the research question is not simply:

> “What is the height of this scarp?”

It is closer to:

> **“How does scarp morphology vary with height, orientation, material, vegetation, moisture, drainage, and local environmental conditions?”**

The Idaho results should **not** be transferred numerically to Santa Cruz. They are a methodological reference showing why orientation and environmental controls need to be measured rather than ignored.

---

# A More Specific Mathematical Research Direction

The research should investigate several levels of model complexity rather than immediately choosing one equation.

## Level 1 — Morphometric description

Extract from a high-resolution elevation surface:

- Scarp height
- Scarp width
- Maximum slope
- Mean slope
- Curvature
- Crest position
- Toe position
- Upper-surface slope
- Lower-surface slope
- Across-scarp profile
- Scarp orientation/aspect
- Length along strike or along the feature
- Local relief

This is the basic measurement layer.

## Level 2 — Linear diffusion model

Test whether the cross-scarp elevation profile is reasonably represented by a linear diffusion solution.

Possible output:

- Best-fit diffusion-age parameter $\kappa t$
- Residual/error between observed and modeled profile
- Sensitivity to profile placement
- Sensitivity to assumed initial geometry

This should be treated as a **model fit**, not automatically as an earthquake date.

## Level 3 — Environmental controls

Add variables that may alter the effective degradation rate:

- Aspect
- Solar exposure
- Scarp height
- Slope
- Vegetation/plant cover
- Soil type
- Lithology/geologic unit
- Drainage proximity
- Moisture/wetness indicators
- Coastal exposure where applicable

The purpose is to investigate whether apparent differences in diffusion behavior can be explained by environmental conditions rather than by age alone.

## Level 4 — Nonlinear or process-specific models

Where the linear model fails systematically, investigate models with:

- Nonlinear slope-dependent transport
- Threshold behavior
- Drainage incision
- Multiple disturbance events
- Different transport laws
- Spatially varying diffusivity

Recent work on fluvial terrace risers explicitly examines nonlinear diffusion formulations for steep risers, illustrating that the simplest linear model is not necessarily sufficient for every landform. citeturn0search14

---

# Cross-Checking Scarp Origin

A central part of the proposed workflow is to classify candidate scarps by **possible origin**, then test that interpretation spatially.

## Tectonic

Compare candidate morphology with:

- County mapped fault zones
- State fault traces
- Geologic structures
- Geologic units
- Strike and dip
- Regional tectonic setting
- USGS fault/geomorphic studies

A feature near a mapped fault is not thereby proven to be a fault scarp.

## Fluvial

Compare with:

- Streams and drainage networks
- Valley geometry
- Terraces
- Alluvial deposits
- Channel position
- Elevation relationships
- Flood/debris-flow information

A terrace riser can have scarp morphology without being a tectonic feature.

## Lacustrine

Where applicable, investigate whether a relatively continuous elevation or geomorphic surface could represent an ancient shoreline or lake-related feature.

This requires external geological evidence because the morphology alone cannot establish a lacustrine origin.

## Coastal / wave-cut

Compare with:

- Coastal bluffs
- Marine terraces
- Shoreline elevation
- Wave-cut surfaces
- Coastal geology
- Sea-level history
- Coastal erosion data

## Landslide / mass movement

Compare with:

- County landslide map
- Mapped small landslides and debris flows
- Landslide direction
- Slope
- Drainage
- Geologic unit
- Terrain morphology

## Human-made

Do not automatically interpret sharp topography as natural.

Compare with:

- Roads
- Excavations
- Building sites
- Quarries
- Terracing
- Grading
- Other mapped infrastructure

---

# LiDAR Is a Major Enabling Dataset

The research now has strong evidence that high-resolution LiDAR exists for Santa Cruz County and is publicly accessible through federal and partner data systems.

This is an important correction to the earlier uncertainty about whether good LiDAR could be obtained freely.

## Santa Cruz County's own GIS already uses LiDAR-derived products

The County's current GIS help documentation states that **CountyWideContours** were derived from elevation data acquired during the **2010 LiDAR survey of Santa Cruz County**, with contours produced at 2-foot and 10-foot intervals. citeturn1search59

The County's GIS services also include a 3-foot-resolution hillshade based on a Digital Terrain Model. County metadata states that this hillshade represents the landscape when **countywide LiDAR data was collected in 2018 and 2020**. citeturn1search10

This means LiDAR-derived terrain is not merely an external research dataset. It is already part of the County's mapping environment.

## 2020 Santa Mateo RCD / Santa Cruz LiDAR

NOAA's data catalog identifies a **2020 San Mateo RCD Lidar: Santa Cruz County, CA** dataset. The dataset consists of classified LAS 1.4 LiDAR points and was used to create related terrain products. citeturn1search14

NOAA also identifies a corresponding **2020 San Mateo RCD Lidar DEM: Santa Cruz County, CA** dataset. Its metadata states:

- Approximately 370 square miles
- 2-foot hydro-flattened raster DEM
- Class 2 ground LiDAR points plus hydro breaklines
- Nominal pulse spacing of 0.35 meters
- NAD 1983 2011 State Plane California III, US survey feet
- NAVD88 Geoid 12b, US survey feet

citeturn1search15

This is highly relevant to scarp-profile work because a 2-foot DEM provides a much more detailed topographic surface than ordinary broad-scale contour mapping.

## NOAA Digital Coast

NOAA's Coastal Topographic LiDAR repository provides downloadable LiDAR point clouds and DEM products from multiple providers. Its documentation says coverage varies by location and that some areas have multiple acquisition dates. It also warns that users must understand dataset-specific limitations and accuracy before using the data for critical applications. citeturn0search13

The NOAA catalog specifically lists the 2020 San Mateo RCD Santa Cruz County project and provides bulk/custom access paths. citeturn1search2

## USGS 3DEP

USGS 3DEP is another major source for LiDAR and elevation products. A current USGS project description states that the Santa Cruz Mountain Stewardship Network and partners are using **QL1/QL2 3DEP LiDAR** for work spanning Santa Cruz, San Mateo, and Santa Clara Counties. citeturn1search0

Therefore the practical research question is no longer:

> “Does free LiDAR exist?”

It is:

> **“Which LiDAR acquisition, derivative, resolution, vertical datum, horizontal datum, and processing level are appropriate for the particular geomorphic question?”**

---

# County GIS → LiDAR → Google Earth → Analysis

The proposed workflow should now expand from the existing GIS-to-Google-Earth process.

## Stage A — County GIS discovery

Use County GIS to identify:

- Fault zones
- Fault traces
- Geologic units
- Landslides
- Debris flows
- Coastal bluffs
- Streams
- Soils
- Hazard layers
- Existing terrain/hillshade products

## Stage B — Identify candidate scarps

Candidate scarps can come from:

- Existing County mapping
- Visible hillshade
- Terrain inspection
- Geological reports
- USGS maps
- Field observation
- Personal observation
- Community reports

The source of the candidate should be recorded.

## Stage C — Acquire the appropriate elevation data

For each candidate, record:

- LiDAR project
- Acquisition year
- Point density / nominal pulse spacing
- DEM resolution
- Vertical datum
- Horizontal datum
- Bare-earth vs surface model
- Processing level
- Coverage
- Accuracy information
- Metadata source

## Stage D — Extract a cross-scarp profile

A profile should be drawn approximately perpendicular to the scarp rather than arbitrarily across it.

Record:

- Distance
- Elevation
- Slope
- Curvature
- Profile orientation
- Scarp height
- Upper/lower surface geometry

Multiple nearby profiles should be considered where the feature is long enough.

## Stage E — Compare profiles

Compare:

- Observed profile
- Idealized initial profile
- Linear diffusion model
- Alternative model where justified

Calculate residuals and document the fitting assumptions.

## Stage F — Add environmental variables

Associate each profile with:

- Aspect
- Solar exposure
- Vegetation
- Soil
- Geologic unit
- Drainage
- Moisture indicators
- Local climate information

This is where the **scarp height + orientation + microclimate + vegetation** concept becomes a measurable GIS problem.

## Stage G — Compare independent evidence

A candidate feature becomes more scientifically interesting when several independent evidence streams can be compared:

**LiDAR morphology + County geology + fault/terrace/coastal/landslide context + USGS literature + field observation + chronological evidence**

No single layer should be treated as sufficient by itself.

---

# Google Earth Role

Google Earth should remain primarily the **visual research and annotation environment**, not the numerical modeling engine.

It is useful for:

- Seeing the candidate landform in geographic context
- Comparing imagery and terrain
- Recording candidate locations
- Drawing approximate profile locations
- Attaching notes
- Linking source documents
- Comparing multiple spatial layers
- Preparing geographically precise questions for County staff

The numerical analysis should be performed separately from the visualization environment, with the resulting measurements or model outputs returned to the research GIS/Google Earth workspace.

This keeps the workflow modular:

**authoritative spatial data → analysis → research interpretation → visualization**

rather than making Google Earth itself responsible for scientific computation.

---

# Possible Program Architecture

A future small program could act as a bridge between the GIS data and the modeling work.

### Input

- LiDAR-derived DEM
- Candidate scarp line/profile
- Optional polygon defining the feature
- Geologic-unit identifier
- Scarp orientation
- Scarp height
- Environmental attributes
- Candidate origin/classification
- External age constraints where available

### Processing

1. Extract elevation profile.
2. Smooth only according to a documented rule.
3. Calculate slope.
4. Calculate curvature.
5. Identify crest/toe.
6. Estimate scarp height.
7. Fit selected diffusion model.
8. Calculate residuals.
9. Compare multiple profiles.
10. Associate environmental variables.
11. Preserve uncertainty and metadata.

### Output

- CSV profile data
- Graph of observed vs modeled profile
- Model parameters
- Residual statistics
- Map coordinates
- KML/KMZ research annotation
- Machine-readable metadata
- Human-readable research note

The first version should be deliberately small.

A good initial experiment is **one known or clearly mapped scarp, one DEM, one cross-scarp profile, one linear diffusion model, and one documented comparison**.

---

# What the Program Must Not Do

The program should not automatically output:

> “This earthquake occurred X years ago.”

That would exceed what the morphology alone can establish.

Instead, it should output something like:

> “This profile is consistent/inconsistent with the selected model under the stated assumptions; the fitted morphologic parameter is X; interpretation is limited by Y and Z.”

If chronological age is eventually estimated, the program should clearly distinguish:

- Morphologic/diffusion age
- Calibrated chronological age
- Independent geological age
- Uncertainty range
- Model assumptions

---

# Human Observation as a Data Source

A significant motivation for this project is the observation that people who live on or repeatedly walk across a landscape can develop extremely detailed knowledge of small changes in it.

A person's observation may be:

- “This slope feels different.”
- “Water is now moving differently here.”
- “This edge has changed.”
- “The ground feels different underfoot.”
- “A drainage path appeared.”
- “Vegetation changed in this particular location.”
- “A small scarp seems to be growing or degrading.”

These observations should not be treated as equivalent to a survey or LiDAR measurement.

But they can serve as **candidate observations** that lead to measurable questions.

The proposed public-facing pathway is therefore:

**person notices change → identifies location → accesses local GIS/elevation information → compares available evidence → contacts appropriate County/city/scientific staff with a geographically specific question**

This is consistent with the larger goal of making scientific information accessible enough that residents can connect their direct observations of place with authoritative public data.

---

# Resilience and Life-Safety Context

The practical motivation is not merely geological curiosity.

The research is interested in whether better access to terrain, geomorphic, hydrologic, and geological information can help communities:

- Recognize changes in the physical environment
- Identify locations that merit investigation
- Improve communication between residents and technical agencies
- Preserve observations before they disappear
- Understand how infrastructure interacts with changing ground conditions
- Support evidence-based hazard and resilience work

This does not mean that every observed change is dangerous. The purpose is to create a **path from observation to verification**, not to generate alarms from unverified observations.

---

# Privacy, Property, and LiDAR Sensitivity

LiDAR has a dual character in public infrastructure.

It can provide extremely valuable information about:

- Terrain
- Drainage
- Vegetation structure
- Erosion
- Infrastructure
- Water movement
- Landscape change

But high-resolution spatial information can also raise legitimate concerns about privacy, property, security, and unwanted visibility of features on private land.

The research workflow should therefore distinguish:

- Public scientific terrain data
- Property-specific information
- Sensitive infrastructure information
- Personal observations
- Data that may expose private conditions

The existence of publicly accessible LiDAR does not eliminate these questions.

The project's public-resilience goal should remain compatible with responsible data governance.

---

# Immediate Research Questions

1. Which Santa Cruz County GIS services expose LiDAR-derived terrain directly?
2. Can the County's 3-foot hillshade be accessed as a direct GIS layer or downloadable raster?
3. Can the County's underlying 2018/2020 Digital Terrain Model be obtained directly?
4. What portions of Santa Cruz County are covered by the 2020 San Mateo RCD LiDAR project?
5. What additional coverage is available through USGS 3DEP?
6. Which DEM is appropriate for scarp profiling?
7. What vertical datum should be preserved in the analysis?
8. What is the actual vertical accuracy of each candidate dataset?
9. How should LiDAR-derived elevation uncertainty propagate into scarp height, slope, and curvature calculations?
10. Which County-mapped features are good candidate scarps?
11. Which candidates are likely tectonic, fluvial, lacustrine, coastal, landslide-related, or anthropogenic?
12. Which candidates have independent age constraints?
13. Can existing Santa Cruz studies provide calibrated diffusivity values?
14. Which geomorphic processes dominate Santa Cruz scarps compared with the Idaho study environment?
15. How should aspect and solar radiation be calculated for candidate scarps?
16. Can vegetation cover be quantified from LiDAR or other imagery?
17. How can drainage incision be identified and excluded from simple diffusion-model profiles?
18. Can multiple profiles from the same scarp distinguish local erosion from broader landform evolution?
19. How should uncertainty be represented in Google Earth annotations?
20. Can a resident's field observation become a structured candidate feature without turning the observation into an unsupported geological conclusion?

---

# Research Sources Identified

## USGS / scientific sources

### Pierce & Colman (1986)

**Effect of height and orientation (microclimate) on geomorphic degradation rates and processes, late-glacial terrace scarps in central Idaho**

USGS Publications Warehouse and GSA Bulletin.

Key relevance:

- Scarp height
- Orientation
- Microclimate
- Vegetation
- Soil moisture
- Solar radiation
- Diffusion-equation modeling
- Scarp degradation

urlUSGS publication recordturn0search0

urlUSGS full publication pageturn0search1

### Hanks (2000)

**The age of scarplike landforms from diffusion-equation analysis**

Key relevance:

- Quantitative scarp geomorphology
- Diffusion-equation development
- Morphologic evolution
- Relationship between topography and time

urlUSGS publication recordturn0search2

### Andrews & Hanks (1985)

**Scarp degraded by linear diffusion: Inverse solution for age**

Key relevance:

- Inverting scarp profiles
- Diffusion age
- Initial scarp shape
- Limits of apparent age

urlUSGS publication recordturn0search11

### Hanks, Bucknam, Lajoie & Wallace

**Modification of wave-cut and faulting-controlled landforms**

Key relevance:

- Cross-strike elevation profiles
- Slope-offset analysis
- Fault and wave-cut landforms
- Diffusion representation

urlUSGS publication recordturn0search7

### Sare (2019)

**Regional-Scale Detection of Fault Scarps and Other Tectonic Landforms: Examples From Northern California**

Key relevance:

- Northern California context
- Regional-scale scarp detection
- DEM/topographic morphology
- Diffusion-equation formulation
- Morphologic age

urlWiley / Journal of Geophysical Research articleturn0search4

---

# LiDAR Sources Identified

### Santa Cruz County GIS

The County GIS program provides more than 100 GIS layers and explicitly supports public access to County geospatial data. citeturn1search7

County GIS help documentation identifies LiDAR-derived CountyWideContours, and County metadata identifies a 3-foot hillshade derived from a Digital Terrain Model representing 2018/2020 countywide LiDAR. citeturn1search59turn1search10

### NOAA Digital Coast

NOAA provides public access to coastal/topographic LiDAR datasets from multiple providers, including the 2020 Santa Cruz County project. citeturn0search13turn1search2

### NOAA InPort

The 2020 San Mateo RCD Santa Cruz County LiDAR dataset and its 2-foot DEM derivative are catalogued by NOAA. citeturn1search14turn1search15

### USGS 3DEP

USGS 3DEP provides additional LiDAR/elevation resources and is actively involved in high-resolution topographic work in the Santa Cruz/San Mateo/Santa Clara region. citeturn1search0

---

# Relationship to the Existing Project Documents

This document should remain separate from the two existing core documents:

1. **SANTA_CRUZ_GIS_TO_GOOGLE_EARTH_WORKFLOW.md**
   - Operational data workflow.

2. **SANTA_CRUZ_GEOLOGICAL_MAPPING_RESEARCH_RECORD.md**
   - Broader research questions, experiments, books, and geological framework.

3. **SANTA_CRUZ_LANDSCAPE_DATING_AND_PROCESS_EVIDENCE_METHODS.md**
   - Stratigraphic, geomorphic, dendrochronologic, and lichenometric evidence methods.

This document adds a fourth layer:

> **High-resolution topography + scarp morphology + quantitative landform-evolution modeling + environmental controls**

The four documents together form a progressively deeper workflow:

**County spatial data → geological/process evidence → chronological methods → quantitative terrain morphology**

---

# Immediate Experimental Path

The next practical experiment should remain small and reversible:

1. Identify one candidate scarp in Santa Cruz County.
2. Determine its likely origin only as a working hypothesis.
3. Obtain the best freely available DEM covering it.
4. Record the DEM's metadata and uncertainty.
5. Draw one or more cross-scarp profiles.
6. Measure height, slope, orientation, curvature, and profile shape.
7. Compare the observed profile with a basic linear diffusion solution.
8. Do not infer age yet.
9. Compare the same feature against County geology, faults, drainage, landslides, and other available evidence.
10. Record where the model fails.
11. Decide whether a more complicated model is justified.
12. Export the candidate and analysis results back into the Google Earth research workspace.
13. Use the geographically specific result to formulate a precise question for County or scientific specialists.

The core principle is:

> **Measure first. Model second. Interpret third. Date only when the evidence and assumptions justify dating.**

---

# Working Statement

> **Use the highest-quality accessible terrain data to measure the morphology of candidate scarps, compare that morphology with geological and geomorphic context, test appropriate landform-evolution models, and preserve the uncertainty and provenance of every inference.**

This is a research method, not yet a validated Santa Cruz County dating technique.
