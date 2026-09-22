# Workflow Archive — Three Interfaces, One Underlying System

**Date:** 2026-09-22  
**Project:** Open Community Resource Access & No-Line Navigator  
**Folder:** `open-food-access-no-line-pantry/`  
**Evidence status:** Conversation insight = **KNOWN**; generalized architecture = **PROPOSED**; implementation details = **PROPOSED / EXPERIMENTAL**  
**Purpose:** Preserve the detailed reasoning that established the project's three-interface model. This is a historical workflow archive, not a replacement for the current architecture or build prompt.

---

## 1. Why this archive exists

The project began with food access, but the conversation reached an important architectural conclusion: the underlying problem is broader than food.

The system is not fundamentally a "food pantry app." Food is the first concrete use case for a more general community-resource access system.

The key realization was:

> **There are three interfaces to one underlying system, not three separate projects.**

The three interfaces are:

1. **Photograph/upload a guide**
2. **Text-first backup wayfinding**
3. **Continue the journey after arrival**

They share the same underlying resource records, provenance, verification, access evaluation, conversational state, and next-action logic.

---

## 2. Interface 1 — Photograph or upload a community guide

A person may already have useful information in a paper or digital guide.

The desired path is:

**photo → OCR/document extraction → resource records → provenance → verification/status → concise next action**

A person could photograph a paper community-resource guide with a normal smartphone and send the image through MMS or another supported media-ingestion path.

The system should preserve the original guide as a source. AI extraction is an interpretation of the source; it must not silently replace the source.

The extracted information should be structured into reusable resource records. A record may contain, as appropriate:

- resource name;
- category;
- address or service location;
- landmark;
- hours;
- service days;
- eligibility;
- documentation requirements;
- language/accessibility information;
- transportation information;
- contact method;
- temporary/seasonal status;
- source document;
- publisher;
- publication/version date;
- retrieval date;
- page or section;
- extraction confidence;
- verification state;
- notes about uncertainty.

The system could then answer something like:

> "I found 14 resources. Which one do you want?"

That interaction is important because the guide itself may contain more information than the person needs at that moment.

### Important boundary

**Found is not verified.**

A photographed guide may be old. OCR may be wrong. A place may have moved. Hours may have changed. Eligibility language may be incomplete.

Therefore:

**Uploaded is not verified.**  
**Extracted is not verified.**  
**Discovered is not verified.**

The original source and its provenance remain important.

---

## 3. Interface 2 — Text-only backup wayfinding

The second interface is not intended to replace Google Maps or other full mapping systems.

The central distinction developed in the conversation was:

> **Maps tells you where. This system tells you what to do.**

The system can operate through ordinary text messaging where possible.

A person can describe a location using:

- a landmark;
- a store;
- a bus stop;
- an intersection;
- a neighborhood;
- a familiar local phrase;
- another meaningful location clue.

The system should interpret the clue as a hypothesis rather than pretending it is precise GPS.

A possible interaction:

1. User gives a landmark.
2. System identifies candidate locations/resources.
3. System asks for only the clarification needed.
4. System gives a small next action.
5. User can continue by text.
6. User may report arrival with a simple message such as `HERE`.

Possible instructions include:

- walk toward a named landmark;
- continue a certain number of blocks;
- look for a particular entrance;
- use a particular side of a building;
- follow a short sequence of landmarks;
- text `HERE` when the person arrives.

### Landmark is not GPS

A landmark can identify a useful area without proving the user's exact location.

The system must therefore distinguish:

- described location;
- inferred/candidate location;
- GPS-supported location, if available;
- user-reported arrival.

It must not claim exact arrival without evidence.

---

## 4. Interface 3 — Continue the journey after arrival

The third interface was a major extension of the original concept.

The system should not have to stop being useful merely because the person reached the resource.

A person may arrive and discover a real-world obstacle:

> "I'm here. They said I need something I don't have. What do I do?"

The same number can continue the conversation.

The system may already know:

- which resource the person selected;
- what service they were seeking;
- what published requirements were associated with that resource;
- what alternatives were previously identified;
- what step of the journey the person was on.

That context can allow the system to provide a concise next action without forcing the person to restart from the beginning.

For example, if a person reaches a food resource and learns that a particular item is required, the system can help identify:

- whether another resource has fewer requirements;
- whether another service time is available;
- whether a proxy/trusted-person option exists;
- whether delivery or volunteer assistance is available;
- whether a different resource can meet the same underlying need.

The important architectural lesson is:

> **The point of service is part of the access pathway.**

The system is therefore not merely a directory and not merely a map.

---

## 5. The "raisins" lesson

The original food-access problem included an example involving receiving food that was not useful to the person, including raisins.

The architectural lesson is larger than raisins.

A person can technically receive something while still failing to obtain useful access.

That distinction is:

**resource offered ≠ need met**

The same principle applies outside food.

A resource can exist, be open, and be nearby while still failing to provide the requested service because of:

- documentation;
- eligibility;
- hours;
- capacity;
- transportation;
- physical access;
- language;
- service mismatch;
- required materials;
- temporary closure;
- another point-of-service obstacle.

The navigator therefore needs to model **practical access**, not merely existence.

---

## 6. One underlying resource-access engine

The three interfaces should converge on one underlying system.

Conceptually:

```
                 ┌──────────────────────────┐
                 │  COMMUNITY RESOURCE DATA │
                 │  + PROVENANCE + STATUS   │
                 └────────────┬─────────────┘
                              │
                  ┌───────────▼───────────┐
                  │ RESOURCE ACCESS ENGINE │
                  │                       │
                  │ discovery             │
                  │ verification          │
                  │ eligibility            │
                  │ time/status            │
                  │ practical access      │
                  │ next action            │
                  │ alternatives           │
                  │ journey/session state  │
                  └───────┬───────┬───────┘
                          │       │
             ┌────────────┘       └─────────────┐
             ▼                                  ▼
   ┌──────────────────┐               ┌──────────────────┐
   │ GUIDE INGESTION  │               │ TEXT WAYFINDING  │
   │ photo / document │               │ SMS / simple UI  │
   └──────────────────┘               └────────┬─────────┘
                                               │
                                               ▼
                                    ┌────────────────────┐
                                    │ POST-ARRIVAL HELP  │
                                    │ same session/number│
                                    └────────────────────┘
```

This diagram is conceptual. It does not assert that these components must be implemented in this exact technical form.

---

## 7. Relationship to SMS and MMS

The conversation later connected the three-interface model to communications infrastructure.

### SMS

SMS is useful for:

- ordinary text requests;
- location clues;
- resource selection;
- short instructions;
- appointment/request exchanges;
- arrival messages such as `HERE`;
- continuing the conversation after arrival.

### MMS

MMS can add:

- photographs of paper guides;
- screenshots;
- other authorized media inputs.

This makes MMS a possible bridge between a paper community guide and a machine-readable resource database.

### Important separation

The transport layer should remain separate from the resource-navigation engine.

Conceptually:

**SMS/MMS transport → message/session handling → resource-navigation engine → response → SMS/MMS**

A future implementation might use a phone/SIM or gateway connected to a local computer running OCR and/or edge AI. That remains an experimental architecture, not a claim of public-service scalability.

---

## 8. Why this is not three separate apps

Creating three independent applications would risk duplicating:

- resource data;
- verification;
- eligibility interpretation;
- privacy rules;
- session state;
- accessibility logic;
- alternatives;
- failure recovery.

Instead, the interfaces should be understood as different doors into the same system.

A person may enter through one door and continue through another.

For example:

**Door 1:** photograph a guide  
→ select a resource  
→ receive text instructions  
→ arrive  
→ encounter an obstacle  
→ continue by text.

That is one journey.

---

## 9. No forced closure

The conversation also established that the system should not require the person to declare success.

A person may simply stop responding.

Silence may mean:

- they succeeded;
- they became busy;
- their phone lost service;
- they ran out of battery;
- they decided not to continue;
- they found another solution;
- they no longer needed help;
- something else happened.

Therefore:

**No response is not proof of success.**  
**Hang-up is not proof of failure.**

The system should not infer satisfaction or failure merely from silence.

If explicit feedback is offered, it should remain optional.

A minimal keypad pattern discussed elsewhere is:

- `1–5` = current numbered choices;
- `*` = explicit "This isn't working" feedback/exit;
- `0` = neutral exit/navigation;
- `#` = confirm/continue;
- hang-up = session ended, reason unknown.

These controls are navigation primitives, not sentiment labels.

---

## 10. Low-burden interaction

The three-interface model reinforces the project's low-burden design goals.

The system should:

- ask only for information needed for the current step;
- provide one meaningful action at a time where possible;
- preserve context;
- allow correction;
- allow backtracking;
- avoid making the user repeat the entire story;
- offer alternatives rather than dead ends;
- support ordinary phones;
- avoid requiring an app download when possible;
- avoid requiring account creation for seekers when possible;
- support multilingual and locally meaningful language;
- avoid unnecessary identity questions;
- minimize retained personal information.

The objective is not maximum conversational sophistication.

The objective is a useful path through a real-world problem.

---

## 11. Travel and access are part of the same calculation

Distance alone is not enough.

A resource that is physically close may be practically inaccessible because:

- the person cannot reach it during open hours;
- the route is difficult;
- transportation is unavailable;
- the service is not appropriate;
- required documentation is unavailable;
- the resource has a relevant eligibility restriction;
- the resource is temporarily unavailable.

Conversely, a somewhat farther resource may be the practical option if transportation, delivery, proxy pickup, or another assistance path exists.

Therefore:

**travel capability is part of access evaluation, not a separate gate.**

---

## 12. Temporary and seasonal information

Community-resource information changes.

The system may encounter:

- seasonal programs;
- holiday changes;
- temporary closures;
- temporary distribution sites;
- harvest or food-season signals;
- outdated printed guides;
- newly published guides.

Time-sensitive information therefore needs explicit status and provenance.

A historical guide can still be useful, but historical information must not be silently presented as current.

---

## 13. Community correction and provenance

A generalized community-resource navigator needs a correction path.

Possible states discussed in the project include:

**DISCOVERED → EXTRACTED → NEEDS REVIEW → VERIFIED → ACTIVE → EXPIRED/WITHDRAWN**

A community member or authorized maintainer may identify:

- a wrong address;
- changed hours;
- changed eligibility;
- changed service;
- closure;
- duplicate;
- translation problem;
- extraction error.

Corrections should preserve provenance and version history rather than silently erasing the previous state.

---

## 14. Security implication of guide photographs

A photographed guide is untrusted input.

The system should treat OCR output as data, not as instructions to the AI or operating system.

For media ingestion:

- validate file type;
- impose size limits;
- safely decode media;
- isolate processing where practical;
- scan inputs as appropriate;
- do not execute embedded code;
- preserve source identity/provenance;
- minimize retention;
- separate extracted text from system instructions;
- require verification before treating extracted information as authoritative.

This is particularly important for an open-source system intended to accept community-provided media.

---

## 15. Capacity remains an empirical question

A one-phone/one-computer gateway may be useful for an experiment.

It is not automatically a system for hundreds or thousands of simultaneous users.

Potential bottlenecks include:

- carrier/MMS throughput;
- anti-abuse controls;
- phone/modem limitations;
- USB connection;
- operating-system behavior;
- OCR throughput;
- AI inference;
- CPU/RAM;
- storage;
- image processing;
- database performance;
- outbound messaging limits.

The project principle is:

> **Capacity must be measured, not guessed.**

Concurrency testing is therefore a later implementation task.

---

## 16. What changed in the project

Before this insight, it was easy to describe the project primarily as:

**"a no-line food pantry navigator."**

After the insight, the more accurate architectural description is:

**"an open community-resource access navigator whose first concrete use case is food."**

Food remains important. It is the initial test case because the problem is concrete and the access obstacles are easy to demonstrate.

But the underlying interface should not be hard-coded around food.

---

## 17. Evidence classification

### KNOWN
- The three-interface model was explicitly developed in the project conversation.
- The interfaces were understood as access points to one underlying system.
- The post-arrival continuation requirement emerged from a real point-of-service obstacle example.
- The distinction between a directory/map and practical next-action guidance is a core project understanding.

### PROPOSED
- General resource schema serving all three interfaces.
- Shared resource-access engine.
- Photograph-to-OCR-to-structured-record workflow.
- Text-only backup wayfinding.
- Same-number post-arrival continuation.
- Community correction/verification workflow.
- Cross-interface journey/session state.

### EXPERIMENTAL / PROPOSED
- MMS guide-photo ingestion.
- Phone/SIM or gateway connected to a local computer.
- Local/edge OCR and AI processing.
- USB-connected phone as one possible prototype transport.

### UNKNOWN
- Real-world carrier limits for the intended deployment.
- Safe and reliable MMS ingestion characteristics across providers.
- Practical OCR accuracy on arbitrary community guides.
- Human verification workload at scale.
- Real-world concurrency capacity.
- Current accuracy of any particular historical guide.
- Whether every desired SMS/MMS gateway configuration is supported by every carrier/device.

### NOT CLAIMED
- This archive does not claim that the architecture is already production-ready.
- It does not claim that AI can independently verify community-resource information.
- It does not claim a universal maximum number of SMS choices.
- It does not claim that text navigation can replace precise mapping/GPS.
- It does not claim that a single local computer can serve a large public population.

---

## 18. Relationship to the AI coding build prompt

The separate `AI-CODING-BUILD-PROMPT.md` is an implementation-oriented artifact.

This archive has a different purpose.

**Build prompt:** tells a future AI what to build and how to work in the repository.

**Workflow archive:** preserves how and why the three-interface architecture emerged.

Both should remain.

A future AI should read the repository before changing the implementation and should treat this archive as historical project context rather than automatically converting every proposal into a validated requirement.

---

## 19. Immediate architectural waypoint

The next useful implementation boundary is not "build the whole national service."

It is a small end-to-end demonstration of the shared architecture:

1. receive one guide image;
2. preserve the original;
3. extract text;
4. create one or more structured resource records;
5. preserve provenance;
6. mark extracted information as needing review;
7. verify one resource with a human;
8. query that resource through text;
9. provide a short practical next action;
10. allow the same session/number to continue after arrival;
11. simulate a point-of-service obstacle;
12. provide an alternative next action;
13. record only minimal test-state data.

This demonstrates the architectural claim without pretending the entire system is solved.

---

## 20. Core principles preserved

The three-interface insight should be read together with the project's broader principles:

> **Preserve the possibility before deciding what it is.**

> **Reconcile before extending.**

> **Preserve the local guide; generalize the interface.**

And, for this particular architecture:

> **Maps tells you where. This system tells you what to do.**

> **One underlying system, multiple interfaces.**

> **The point of service is part of the access pathway.**

> **Resource offered is not necessarily need met.**

> **No dead ends.**

> **No forced closure.**

> **Capacity must be measured, not guessed.**

---

## 21. Archive integrity note

This file is intentionally separate from earlier generalized-resource archives.

It does not overwrite or replace:

- `WORKFLOW-ARCHIVE-2026-09-22-GENERALIZED-RESOURCE-NAVIGATOR.md`;
- `MMS-AND-EDGE-AI-INGESTION.md`;
- `AI-CODING-BUILD-PROMPT.md`;
- other dated workflow archives.

The existence of overlapping archives is intentional when they preserve different reasoning or implementation boundaries.

No historical material should be deleted, merged, or silently rewritten merely because a later document summarizes it.
