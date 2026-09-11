# Week 1 — Topic 19: Summary

**Source:** `Week_One_Lecture_For_Software_Analysis_and_Design.pdf`, page 45 of 47.
**Learning Aim:** A — Investigate systems analysis and design methodologies.
**Criteria:** P / M / D.

> The lecture's own recap. Compresses everything covered in Week 1 into two bullets — a definition and the two modern approaches. Use this as a **quick-recall page** before an assignment task or exam question.

## Slide content (verbatim)

**Summary**

- **Information systems analysis and design**
  - Process of developing and maintaining an information system.
- **Modern approach to systems analysis**
  - Process-Oriented
  - Data-Oriented

---

## The two summary bullets, unpacked

### 1. Information systems analysis and design — "process of developing and maintaining an information system"

This is the whole activity of Unit 22, and it has two parts:

- **Developing** — everything from *identifying the need* (Topic 15) through *analysis*, *design* and *implementation* (Topics 14–16, Topic 17 approaches, Topic 18 method).
- **Maintaining** — the **Operation** phase (Topic 16): change to reflect changing conditions, then obsolescence.

Both halves are the analyst's job. Stopping at "developing" misses more than half of a system's lifetime cost.

### 2. Modern approach to systems analysis — Process-Oriented vs Data-Oriented

The two approaches from Topics 7 and 8:

| Approach          | Focus                                             | Main tool                  | Main risk it exposes                             |
| ----------------- | ------------------------------------------------- | -------------------------- | ------------------------------------------------ |
| Process-Oriented  | What the system does and when                     | Data Flow Diagram (DFD)    | Application-tied data, uncontrolled duplication  |
| Data-Oriented     | The data the system needs to operate              | Entity Relationship Diagram (ERD) + shared DB | Slower start; needs governance |

Distinction move: **hybrid** — data-oriented core (Topic 9's shared database and application independence) plus process-oriented artefacts for each workflow.

---

## Everything else Week 1 covered — one-line recall list

Foundation concepts (Topics 1–6):
- **Decomposition** (Topic 1) → break a system into subsystems that each do one job.
- **Modularity + coupling + cohesion** (Topic 2) → aim for **LOW coupling + HIGH cohesion**.
- **Three components of an information system** (Topic 3) → **Data**, **Data Flows**, **Processing Logic**.
- **Data + techniques** (Topic 4) → data dictionary, ERD, normalisation.
- **Data flows + processing logic** (Topic 5) → every flow has a **named source and destination**; every process has a **trigger and steps**.
- **Fig 1.8** (Topic 6) → the three components rendered as one worked example.

Approaches, databases, analyst (Topics 7–11):
- **Process-Oriented Approach** (Topic 7) → what the system does; DFD-driven; application-tied-data risk.
- **Data-Oriented Approach + Table 1.1** (Topic 8) → what the system needs; ERD-driven; enduring design.
- **Databases + application independence** (Topic 9) → shared, multi-user, centrally managed, subject-designed; data and its definition are separated from applications.
- **Role of the systems analyst** (Topic 10) → three levers: **People + Methods + Information Technology**.
- **Skills of the systems analyst** (Topic 11) → **Managerial + Interpersonal** (this slide's list is Part 1 — analytical + technical typically come later).

Types of information system + SDLC (Topics 12–17):
- **Expert Systems** (Topic 12) → replicates decision-making; knowledge representation.
- **Four classes** (Topic 13, Fig 1.12) → **TPS → MIS**, **DSS**, **ES**.
- **SDLC** (Topic 14) → **Analysis → Design → Implementation → Maintenance**.
- **SDLC Phases Part 1** (Topic 15) → **Planning & Selection** + **Systems Analysis** (with alternatives + recommendation).
- **SDLC Phases Part 2** (Topic 16) → **Operation** (change to reflect changing conditions + obsolescence).
- **Approaches to development** (Topic 17) → **Prototyping** + **Rapid Application Development (RAD)**.
- **Prototyping method** (Topic 18, Fig 1.16) → 5-step iterative loop with an *If Prototype Inefficient → Convert to Operational System* exit branch.

## Distinction-level habits Week 1 has embedded

- Every analysis references the scenario, not the theory only.
- Every design choice is justified against **alternatives**.
- Every model (ERD, DFD, prototype) is **cross-checked** against the others.
- Every recommendation ends with a **justified conclusion** and a **next-step recommendation**.
- Every artefact considers **People + Methods + Technology** together, not just technology.

## The one-page mental map to leave Week 1 with

```
                       Types of IS
                    (TPS · MIS · DSS · ES)
                             │
                             ▼
              A SYSTEMS ANALYST'S JOB
        study problem → three levers (People,
        Methods, IT) → define requirements
                             │
                             ▼
        APPROACH:  Process-Oriented  ||  Data-Oriented
        (DFD-led)    ||     (ERD-led, shared DB, application
                     ||      independence)
                             │
                             ▼
          RUN IT THROUGH THE SDLC PHASES
       Planning & Selection → Analysis → Design →
       Implementation → Operation (change → obsolescence)
                             │
                             ▼
       DEVELOPMENT STYLE: Waterfall  ||  Prototyping / RAD
                                   (Fig 1.16 loop)
                             │
                             ▼
              DELIVERED SYSTEM
   modular · high cohesion · low coupling · shared data ·
   application-independent · maintainable · retirable
```

## Common trap / examiner feedback (roll-up)

- Confusing pairs: Data vs Information; Coupling vs Cohesion; MIS vs DSS; SDLC vs Methodology; Prototyping (technique) vs RAD (methodology); Systems analyst vs Project manager.
- Skipping any half of a pair: describing only strengths of an approach; listing only inclusions in scope but no exclusions; producing an ERD without a DFD or vice versa.
- Reaching for the IT lever first (Topic 10 warning).
- Presenting Waterfall or RAD as the only choice — the exam rewards **justified choice** or **hybrid**.

## Key vocabulary (roll-up)

System · subsystem · decomposition · module · modularity · coupling · cohesion · interface · data · information · processing logic · data flow · DFD · data store · external entity · source · destination · trigger · event · step · business rule · data dictionary · ERD · entity · attribute · relationship · normalisation · structured English · decision table · pseudocode · state diagram · process-oriented approach · data-oriented approach · application-tied data · enterprise data model · design stability · database · DBMS · shared data · centrally managed · subject-oriented design · schema · application independence · systems analyst · requirements · functional/non-functional · fact-finding · TPS · MIS · DSS · ES · knowledge base · inference engine · knowledge representation · SDLC · analysis · design · implementation · maintenance · operation · planning and selection · alternatives · recommendation · change management · obsolescence · prototyping · throwaway · evolutionary · RAD · JAD · CASE · time-box · iteration.
