# Phase 25 — Documentation for another human

This may be the most important repository layer.

Someone who discovers KINSHIP in another country should be able to understand it without having this conversation.

We eventually need:

### `README.md`

**inside the KINSHIP folder**, not APO's root README.

### `QUICKSTART.md`

### `ARCHITECTURE.md`

### `DESIGN-PARAMETERS.md`

### `GLOSSARY.md`

### `SAFETY.md`

### `KNOWN-LIMITATIONS.md`

### `OPEN-QUESTIONS.md`

### `ROADMAP.md`

### `CONTRIBUTING.md`

### `LICENSE.md`

### `CHANGELOG.md`

### `REFERENCES.md`

And probably a **"Start Here"** document for non-engineers.

---

# Phase 26 — Evidence discipline

I want this to be particularly rigorous.

Every significant statement should eventually fall into one of these categories:

**KNOWN**

supported by established engineering/scientific evidence.

**CALCULATED**

derived from an explicit model.

**TESTED**

demonstrated experimentally.

**PROPOSED**

design hypothesis.

**SPECULATIVE**

interesting but presently unvalidated.

**UNKNOWN**

requires investigation.

That prevents the repository from becoming a giant document where speculation accidentally acquires the appearance of engineering fact.

---

# Phase 27 — Global deployment

Only after the engineering work exists do we ask:

> How could somebody actually build one in Santa Cruz, Kenya, Japan, Bangladesh, Norway, or somewhere else?

That means designing for:

-  different materials; 
-  different climates; 
-  different fabrication capabilities; 
-  different regulations; 
-  different currencies; 
-  different transportation systems; 
-  different environmental hazards. 

The geometry and interfaces should be as universal as possible.

The implementation can be local.

---

# And then the APO folder

When we're finally ready, I would expect something roughly like:

```
```

```
apo/
└── kinship/
    ├── README.md
    ├── 00-origin-and-concept.md
    ├── 01-system-definition.md
    ├── 02-operating-modes.md
    ├── 03-system-requirements.md
    ├── 04-geometry.md
    ├── 05-structural-system.md
    ├── 06-enclosure-and-panel-system.md
    ├── 07-material-testing.md
    ├── 08-buoyant-pod.md
    ├── 09-stabilization.md
    ├── 10-articulated-arm-system.md
    ├── 11-terrestrial-mobility.md
    ├── 12-aquatic-mobility.md
    ├── 13-anchoring-system.md
    ├── 14-networked-habitats.md
    ├── 15-aerial-emergency-concept.md
    ├── 16-airship-transport-concept.md
    ├── 17-human-factors-and-habitability.md
    ├── 18-safety-and-failure-analysis.md
    ├── 19-power-and-energy.md
    ├── 20-manufacturing-system.md
    ├── 21-repair-reuse-and-end-of-life.md
    ├── 22-digital-engineering-package.md
    ├── 23-compliance-and-certification/
    ├── 24-prototype-program.md
    ├── 25-global-deployment.md
    ├── references/
    ├── research/
    ├── simulations/
    ├── test-data/
    └── drawings/
