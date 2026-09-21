# Santa Cruz County Geological Mapping — Landscape-Dating and Process-Evidence Methods

## Purpose

This document records a new methodological branch arising from the reading of William B. Bull's *Tectonic Geomorphology of Mountains: A New Approach to Paleoseismology*.

The key idea is to investigate how different kinds of geological evidence can preserve information about the age, sequence, and effects of past processes, and then determine which observations can be represented, located, compared, or eventually tested using Santa Cruz County GIS, USGS data, field observations, and Google Earth.

This is a research-method document, not a claim that every method can be extracted directly from existing GIS layers.

The working question is:

> **How can stratigraphic, geomorphic, dendrochronologic, and lichenometric evidence be connected to spatial datasets so that the County GIS becomes a starting map for further observation rather than the entire evidence base?**

---

# Four Evidence Approaches to Investigate

## 1. Stratigraphic approach

### Basic idea

Stratigraphy studies the arrangement, relationships, and sequence of geological layers or deposits.

For this project, the important question is not simply "what geological unit is mapped here?" It is:

> **What sequence of materials or deposits is represented, and what does that sequence tell us about the history of the ground?**

### Possible Santa Cruz GIS connections

Investigate whether County GIS contains or links to:

- Geologic Unit
- Geologic Reports
- Soil information
- Landslide/debris-flow mapping
- Geomorphic or paleontological information
- Geologic contacts
- Depositional or erosional features

### What GIS may provide

GIS may provide:

- location;
- mapped unit boundaries;
- polygons;
- attributes;
- source references;
- spatial relationships between units.

### What GIS may not provide by itself

A GIS polygon does not automatically provide:

- a complete stratigraphic section;
- exact deposit age;
- vertical sequence at a specific exposure;
- field observations;
- laboratory dating.

Those may require geological reports, USGS material, field observation, samples, or other specialist datasets.

### Research extraction question

For each useful mapped unit:

1. What is mapped?
2. What is its stated geological meaning?
3. What lies above/below or adjacent to it?
4. What evidence establishes its age?
5. What process could have produced the observed sequence?
6. Can the relationship be represented spatially in Google Earth?

---

# 2. Geomorphic approach

## Basic idea

Geomorphology examines landforms and the processes that create and modify them.

For this project, geomorphic evidence may be especially useful because the research is concerned with what has happened to the physical ground, not merely its geological name.

### Possible evidence

Examples to investigate include:

- Terraces
- Scarps
- Landslides
- Debris-flow deposits
- Rockfall accumulations
- Erosion surfaces
- Stream channels
- Alluvial/depositional surfaces
- Coastal bluffs
- Drainage changes
- Fault-related landforms
- Other recognizable landform patterns

### GIS connection

The County GIS can serve as the first spatial index:

**County GIS layer → location → Google Earth → imagery/terrain inspection → external source → field observation**

The goal is to use the map to identify places where a geomorphic hypothesis can be examined.

### Research extraction question

For each candidate landform:

1. Where is it?
2. What is the mapped feature?
3. What process could have produced it?
4. What evidence supports that interpretation?
5. What evidence could contradict it?
6. Is its age known or bounded?
7. Can its spatial extent be measured?
8. Does it correspond with another County or USGS layer?

---

# 3. Dendrochronologic approach

## Basic idea

Dendrochronology uses tree-ring sequences to establish or constrain the timing of events or environmental changes where suitable trees and records exist.

For this project, the important question is:

> **Can trees provide independent chronological evidence for geological events that are also visible in the landscape?**

Potential applications could include investigation of:

- landslide disturbance;
- rockfall disturbance;
- flood/debris-flow disturbance;
- channel migration;
- erosion;
- other disturbance events that leave datable effects on trees.

### GIS connection

GIS would generally provide the where, while tree-ring work could provide additional information about when.

Potential workflow:

**GIS feature → candidate location → tree/stand context → dendrochronologic investigation → dated disturbance evidence → return result to spatial research layer**

### Important limitation

Dendrochronology is not simply a GIS attribute that can be downloaded from the County map. It may require field sampling, specialist analysis, existing scientific studies, or another external dataset.

Therefore it should be treated as an external evidence layer/method, not assumed to be available in County GIS.

### Research questions

- Are there existing dendrochronologic studies relevant to Santa Cruz County?
- Which tree species and environments are suitable?
- What geological disturbances can produce identifiable growth responses?
- Can an event be dated to a year or bounded interval?
- Can independent tree-ring evidence be compared with mapped landslides, floods, faults, or other features?
- How should uncertainty be represented?

---

# 4. Lichenometry

## Basic idea

Lichenometry is a method that can use the growth or colonization history of lichens on exposed surfaces to estimate the relative or approximate age of suitable surfaces or deposits.

For this project, it should initially be treated as a method to investigate rather than as an automatic dating tool.

Potential applications may include suitable:

- rock surfaces;
- rockfall deposits;
- exposed surfaces;
- disturbed or newly exposed substrate.

### GIS connection

The spatial workflow could be:

**Mapped feature → candidate exposed surface → imagery/terrain review → field verification → lichen observation/measurement → age estimate or relative chronology → research GIS layer**

### Important limitations to investigate

Lichenometry can depend strongly on:

- lichen species;
- local growth rates;
- climate;
- substrate;
- exposure;
- colonization history;
- calibration data.

Therefore an age estimate should not be treated as a universal clock without appropriate local calibration and uncertainty.

### Research questions

- Is lichenometry applicable to Santa Cruz County environments?
- Which substrates and lichen species are relevant?
- Are local calibration curves available?
- What geological surfaces could plausibly preserve useful lichen records?
- How would the uncertainty of a lichenometric estimate be represented in GIS?
- Can lichenometric evidence independently constrain the age of mapped geomorphic features?

---

# The Four Methods as Complementary Evidence

These approaches answer different questions.

| Method | Primary information | Typical question |
|---|---|---|
| Stratigraphy | Sequence and relationship of materials | What came before/after what? |
| Geomorphology | Landforms and processes | What happened to the landscape? |
| Dendrochronology | Tree-ring chronology | When did a disturbance affect living trees? |
| Lichenometry | Surface colonization/growth chronology | How long may a suitable exposed surface have existed? |

They should not automatically be treated as interchangeable dating systems.

The research goal is to see where independent evidence can converge.

For example:

**Mapped landslide**
→ geomorphic interpretation

**Deposit/relationship**
→ stratigraphic interpretation

**Tree disturbance**
→ dendrochronologic constraint

**Exposed rock/deposit surface**
→ possible lichenometric constraint

If several independent lines of evidence point toward a compatible history, the spatial interpretation becomes more testable.

---

# County GIS, USGS, and Google Earth as Different Roles

A major practical insight is that no single source needs to contain the entire investigation.

## Santa Cruz County GIS

Best initial role:

- local spatial index;
- County-specific layers;
- easy visual exploration;
- local layer names and classifications;
- starting points for candidate locations;
- direct GIS-to-KMZ experiments.

Its limitation is that the County system does not necessarily contain the depth of scientific documentation or every type of chronology needed for paleoseismic or geomorphic research.

## USGS and other scientific sources

Potential role:

- geological maps;
- scientific reports;
- earthquake studies;
- landslide research;
- geomorphic studies;
- topographic information;
- lidar/elevation products;
- geologic ages;
- field studies;
- published scientific interpretations.

The practical problem is discoverability and workflow complexity: USGS resources can be harder to navigate than the County GIS for a local exploratory user.

The solution is not to abandon USGS data. Instead:

> **Use the County GIS as the local spatial starting point, then use USGS and other authoritative scientific sources when the research question requires deeper evidence.**

The workflow should preserve the source of every imported layer.

## Google Earth

Google Earth can serve as the research visualization and annotation environment.

Potential functions:

- place County GIS-derived layers;
- compare layers visually;
- inspect terrain and imagery;
- mark candidate sites;
- attach notes;
- organize observations;
- place external scientific observations at geographic locations;
- prepare a visual discussion with County staff or other researchers.

Google Earth is not itself the scientific authority. It is the workspace through which geographically referenced evidence can be assembled and discussed.

---

# Proposed Multi-Source Evidence Pipeline

The evolving workflow is:

**County GIS**
↓
identify candidate feature/place
↓
**Google Earth**
↓
inspect terrain, imagery, and spatial relationships
↓
identify unanswered question
↓
**USGS / scientific reports / other authoritative sources**
↓
obtain geological, geomorphic, chronological, or methodological evidence
↓
if appropriate, field observation or specialist measurement
↓
return geographically referenced result to research layer
↓
compare with other independent evidence

This is intentionally different from trying to force every source into one database at the beginning.

---

# From Map to Conversation With the County

One intended use of the Google Earth research workspace is to turn abstract questions into geographically specific observations.

Instead of asking only:

> "Could the County study this?"

the workflow can eventually produce something more concrete:

> "This particular mapped feature appears here. These other layers overlap it here. The terrain/imagery shows this condition. Could we investigate this location or this type of feature more closely?"

That creates a bridge between:

**GIS mapping → observation → research question → County discussion**

The County GIS remains the source for its own authoritative mapped data. The research layer identifies questions for further investigation rather than silently changing the County's data.

---

# Extraction Strategy

The phrase "extract it from the GIS" should be understood in several different senses.

## Type A — Direct spatial extraction

Download or query:

- polygons;
- lines;
- points;
- attributes;
- coordinate information.

## Type B — Spatial relationship extraction

Determine:

- overlap;
- adjacency;
- distance;
- intersection;
- elevation relationship;
- position relative to faults, units, landslides, streams, coast, etc.

## Type C — Visual/geomorphic extraction

Use Google Earth or imagery/terrain to identify:

- scarps;
- terraces;
- channels;
- exposed surfaces;
- deposits;
- apparent mass movement;
- other candidate landforms.

These observations should be labeled as observations/interpretations rather than confused with authoritative GIS classifications.

## Type D — External evidence attachment

Attach:

- USGS studies;
- scientific papers;
- geological reports;
- dated observations;
- dendrochronologic results;
- lichenometric results;
- field observations.

The result is a research evidence layer, not necessarily a new official County layer.

---

# Experimental Questions for the Next Phase

1. Can Layer 140 (Geologic Unit) be exported directly to KMZ?
2. Which County layers provide the clearest geomorphic evidence?
3. Can landslide/debris-flow layers be combined visually with terrain without implying causation?
4. Which USGS datasets complement the County layers most directly?
5. Can USGS data be obtained in formats that Google Earth can use without excessive conversion?
6. Which stratigraphic observations are available in County or USGS reports?
7. Are there existing dendrochronologic studies relevant to Santa Cruz County?
8. Is lichenometry applicable to any candidate Santa Cruz County landforms?
9. Which observations require field verification?
10. How should dated evidence and uncertainty be represented in the research layer?
11. Can multiple independent evidence types be attached to the same geographic feature?
12. Can the resulting Google Earth workspace produce precise, useful questions for County GIS/geology staff?

---

# Methodological Rule

Do not assume that a mapped feature has a known age merely because it has a name.

For each proposed process or feature, distinguish:

**mapped location**
from
**geological interpretation**
from
**chronological evidence**
from
**research hypothesis**.

That separation is central to the project's reliability.

---

# Relationship to the Other Archive Documents

This methods document belongs beside:

- SANTA_CRUZ_GIS_TO_GOOGLE_EARTH_WORKFLOW.md
- SANTA_CRUZ_GEOLOGICAL_MAPPING_RESEARCH_RECORD.md

The three documents have different jobs:

### Workflow
How to obtain and move spatial data.

### Research Record
Why the project exists, what experiments and concepts have been developed, and how the books and settlement question fit together.

### Landscape-Dating and Process-Evidence Methods
How geological evidence from different disciplines might be connected to the GIS/Google Earth workflow.

---

# Current Status

This is a **method-development document**.

The presence of a method here does not mean the method has been validated for Santa Cruz County.

The next stage is to determine, one method at a time, which evidence already exists, which can be extracted from GIS, which requires external sources, and which would require field or specialist work.

The immediate practical principle is:

> **Start with the easiest authoritative local spatial source, use it to locate questions, then reach outward to deeper scientific sources and return geographically useful evidence to the research workspace.**
