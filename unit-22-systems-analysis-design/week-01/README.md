# Unit 22 — Week 1

Source: `Week_One_Lecture_For_Software_Analysis_and_Design.pdf` (Luis's copy).

## Topics covered

| #  | Topic                                                                | Slide(s) | File                                                     |
| -- | -------------------------------------------------------------------- | -------- | -------------------------------------------------------- |
| 1  | System decomposition (CD player example)                             | p. 17    | [`01-system-decomposition.md`](./01-system-decomposition.md) |
| 2  | Important system concepts — modularity, coupling, cohesion           | p. 18    | [`02-modularity-coupling-cohesion.md`](./02-modularity-coupling-cohesion.md) |
| 3  | Data and Processes — 3 components + data vs information              | p. 20    | [`03-data-and-processes.md`](./03-data-and-processes.md) |
| 4  | Data and Data Flows in depth (source/use; techniques)                | p. 21    | [`04-data-and-data-flows-in-depth.md`](./04-data-and-data-flows-in-depth.md) |
| 5  | Data Flows (continued) + Processing Logic (steps + triggers)         | p. 22    | [`05-data-flows-continued-and-processing-logic.md`](./05-data-flows-continued-and-processing-logic.md) |
| 6  | Fig. 1.8 — Differences among Data, Data Flow, and Processing Logic   | p. 23    | [`06-figure-1-8-worked-example.md`](./06-figure-1-8-worked-example.md) |
| 7  | Approaches to Systems Development — Process-Oriented Approach        | p. 24    | [`07-process-oriented-approach.md`](./07-process-oriented-approach.md) |
| 8  | Data-Oriented Approach & Process vs Data comparison (Table 1.1)      | p. 26    | [`08-data-oriented-approach-and-comparison.md`](./08-data-oriented-approach-and-comparison.md) |
| 9  | Databases and Application Independence                                | p. 27    | [`09-databases-and-application-independence.md`](./09-databases-and-application-independence.md) |
| 10 | Role of the Systems Analyst (People + Methods + Technology)           | p. 28    | [`10-role-of-the-systems-analyst.md`](./10-role-of-the-systems-analyst.md) |
| 11 | Skills of a Successful Systems Analyst (Managerial + Interpersonal)   | p. 31    | [`11-skills-of-a-successful-systems-analyst.md`](./11-skills-of-a-successful-systems-analyst.md) |
| 12 | Types of Information Systems — Expert Systems (ES)                    | p. 33    | [`12-types-of-information-systems-expert-systems.md`](./12-types-of-information-systems-expert-systems.md) |
| 13 | Fig 1.12 — Four Classes of Information Systems (TPS, MIS, DSS, ES)    | p. 34    | [`13-figure-1-12-four-classes-of-information-systems.md`](./13-figure-1-12-four-classes-of-information-systems.md) |
| 14 | Systems Development Life Cycle (Analysis, Design, Implementation, Maintenance) | p. 35 | [`14-systems-development-life-cycle.md`](./14-systems-development-life-cycle.md) |
| 15 | SDLC Phases (Part 1) — Planning & Selection + Systems Analysis        | p. 38    | [`15-sdlc-phases-planning-and-analysis.md`](./15-sdlc-phases-planning-and-analysis.md) |
| 16 | SDLC Phases (Part 2) — Systems Operation (change + obsolescence)      | p. 40    | [`16-sdlc-phases-operation.md`](./16-sdlc-phases-operation.md) |

> **Gap noted:** slide 39 (likely **Systems Design** + **Systems Implementation**) was not captured. Add as topic 17 when the slide appears.

## Learning aim mapping

All Week 1 topics support **Learning Aim A — Investigate systems analysis and design methodologies** (foundation content).

## Key vocabulary from Week 1

System, subsystem, component, interface, input, process, output, data flow, black box, decomposition, module, modularity, coupling (tight / loose), cohesion (high / low), dependency, encapsulation, data, information, processing logic, data flow diagram (DFD), data store, external entity, source, destination, business rule, data dictionary, entity relationship diagram (ERD), entity, attribute, relationship, cardinality, normalisation (1NF/2NF/3NF), trigger, event, step, transformation, structured English, decision table, decision tree, flowchart, pseudocode, state diagram, retention, process-oriented approach, application-tied data, data duplication, context diagram, process specification, waterfall SDLC, data-oriented approach, enterprise data model, canonical record, single source of truth, controlled duplication, design stability, governance, hybrid approach, database, DBMS, shared data, centrally managed, subject-oriented design, schema, application independence, data steward, primary key, foreign key, constraint, integrity, systems analyst, requirements, functional/non-functional, fact-finding, interview, observation, questionnaire, prototyping, business process, adoption.

## The rules to leave Week 1 with

1. **LOW coupling + HIGH cohesion.** Coupling is *between* subsystems; cohesion is *within* one.
2. Every information system has three components: **data**, **data flows**, **processing logic** — model all three.
3. **Information = Data + Context + Organisation** — the two words are not interchangeable.
4. Every data flow has a **named source** and a **named destination** — no orphans on a DFD.
5. Every process has both a **trigger** (when it runs) and **steps** (what it does).
6. **Process-Oriented** = focus on what the system does; DFD-driven; risks application-tied data.
7. **Data-Oriented** = focus on the data the system needs; ERD-driven; more enduring design.
8. A **database** is shared, multi-user, centrally managed and designed around **subjects** (Customer, Supplier), not applications.
9. **Application independence** = separation of the *data* and the *definition of the data* from the applications.
10. A **systems analyst** pulls **three levers**: **People**, **Methods**, **Information Technology** — never just IT.
