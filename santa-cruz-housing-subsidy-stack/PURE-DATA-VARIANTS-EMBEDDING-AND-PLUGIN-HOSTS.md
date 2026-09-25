# Pure Data Variants, Embedding, and Plugin Hosts

**Status:** RESEARCH / ECOSYSTEM REFERENCE

## Pd Vanilla

Pd Vanilla is the baseline/reference environment for compatibility.

For this project it should be the first target because it minimizes hidden dependencies.

## PlugData

PlugData is a modern Pd environment with a redesigned GUI. Its repository describes it as a plugin wrapper around Pure Data and says it can also be used as a standalone replacement.

Its current build configuration supports multiple plugin formats, including VST3, LV2, CLAP, Audio Unit on Apple platforms, and AAX, as well as standalone builds.

Why it matters:
- demonstrates a modern presentation of the Pd patch model;
- demonstrates standalone and host/plugin deployment;
- provides a possible future packaging layer.

Caution: PlugData is a separate project from Pd Vanilla. A patch depending on PlugData-specific behavior should say so.

## Purr Data

Purr Data is an alternative Pd environment with historical roots in the Pd-Extended ecosystem.

It is useful as evidence that Pd has had multiple interface/distribution approaches.

For current work, avoid assuming that old Pd-Extended packages are the preferred dependency path. Modern library documentation, including Cyclone's, treats the old Pd-Extended distribution as abandoned.

## libpd

libpd embeds Pd into other applications.

Its project describes itself as an embeddable Pure Data audio synthesis library and provides language bindings/glue for environments including C++, C#, Java, Objective-C, and Python, with companion projects for mobile platforms.

The architectural lesson is important:

**Pd patch logic can be separated from the application that hosts it.**

A future housing application could theoretically contain:
- conventional databases;
- GIS;
- accessibility/UI;
- authentication;
- a Pd-based model component.

Pd would not need to be the entire application.

## Camomile

Camomile embeds Pure Data patches into audio plugin formats. Its current repository lists VST3, LV2, and Audio Unit support.

This is primarily an audio technology, so it is not a direct housing requirement.

It is nevertheless useful as an example of:

PATCH → EMBEDDED RUNTIME → EXTERNAL HOST

## Plugin host versus data application

A DAW plugin and a housing application have very different requirements.

Housing requirements would include:
- data access;
- GIS;
- accessibility;
- provenance;
- auditability;
- public records;
- long-term maintainability.

Therefore Pd should not be packaged as an audio plugin merely because that capability exists.

## Possible future deployment models

### A. Pd standalone

DATA FILES → Pd PATCH

Good for research and demonstrations.

### B. Pd plus data service

DATABASE/API → DATA ADAPTER → Pd

Better for live or repeatable demonstrations.

### C. Embedded Pd

HOUSING APPLICATION → EMBEDDED Pd ENGINE

Potentially useful for a custom application.

### D. Pd-inspired implementation

A final system could eventually use another dataflow engine while preserving the Pd research model.

The architecture is more important than permanent allegiance to one runtime.

## Portability principle

Maintain separately:
- portable data;
- portable visualization;
- portable simulation logic.

If Pd disappears, the housing data must remain usable.

If a library changes, the data standard must remain usable.

If a new visual environment becomes better, the same data should be convertible.

## Reproducibility package

A demonstration should record:
- Pd version;
- exact patch files;
- all required abstractions;
- external library versions;
- operating-system target;
- CPU architecture;
- sample data;
- schema version;
- README;
- license information;
- known limitations.

The objective is that another researcher can reproduce the demonstration without guessing which libraries were installed.

## Recommended path for this project

1. Start with Pd Vanilla.
2. Prefer abstractions before custom externals.
3. Add libraries only when a specific need is demonstrated.
4. Maintain a dependency manifest.
5. Keep housing data outside the patch.
6. Test conversion with synthetic data first.
7. Test real public project data only after the data model is documented.
8. Treat PlugData and libpd as later deployment possibilities.

## Evidence status

### KNOWN
- Pd is cross-platform open-source software.
- PlugData provides standalone and plugin-oriented builds.
- libpd embeds Pd.
- Camomile embeds Pd into audio plugin formats.

### PROPOSED
- Use Vanilla as the compatibility baseline.
- Treat the patch as a consumer of standardized housing data.
- Maintain a separate data contract and dependency manifest.

### SPECULATIVE
- A future public-facing housing application could embed Pd or a Pd-derived dataflow engine.
- A browser or other graphical interface could preserve the patch architecture without exposing the Pd editor itself.

## References

- Pure Data: https://github.com/pure-data/pure-data
- PlugData: https://github.com/plugdata-team/plugdata
- libpd: https://github.com/libpd/libpd
- Camomile: https://github.com/pierreguillot/Camomile
- Cyclone: https://github.com/porres/pd-cyclone
