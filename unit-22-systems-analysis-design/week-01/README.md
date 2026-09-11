# Unit 22 — Week 1

Source: `Week_One_Lecture_For_Software_Analysis_and_Design.pdf` (Luis's copy).

## Topics covered

| # | Topic                                                                | Slide(s) | File                                                     |
| - | -------------------------------------------------------------------- | -------- | -------------------------------------------------------- |
| 1 | System decomposition (CD player example)                             | p. 17    | [`01-system-decomposition.md`](./01-system-decomposition.md) |
| 2 | Important system concepts — modularity, coupling, cohesion           | p. 18    | [`02-modularity-coupling-cohesion.md`](./02-modularity-coupling-cohesion.md) |
| 3 | Data and Processes — 3 components + data vs information              | p. 20    | [`03-data-and-processes.md`](./03-data-and-processes.md) |
| 4 | Data and Data Flows in depth (source/use; techniques)                | p. 21    | [`04-data-and-data-flows-in-depth.md`](./04-data-and-data-flows-in-depth.md) |
| 5 | Data Flows (continued) + Processing Logic (steps + triggers)         | p. 22    | [`05-data-flows-continued-and-processing-logic.md`](./05-data-flows-continued-and-processing-logic.md) |
| 6 | Fig. 1.8 — Differences among Data, Data Flow, and Processing Logic   | p. 23    | [`06-figure-1-8-worked-example.md`](./06-figure-1-8-worked-example.md) |
| 7 | Approaches to Systems Development — Process-Oriented Approach        | p. 24    | [`07-process-oriented-approach.md`](./07-process-oriented-approach.md) |

## Learning aim mapping

All Week 1 topics support **Learning Aim A — Investigate systems analysis and design methodologies** (foundation content).

## Key vocabulary from Week 1

System, subsystem, component, interface, input, process, output, data flow, black box, decomposition, module, modularity, coupling (tight / loose), cohesion (high / low), dependency, encapsulation, data, information, processing logic, data flow diagram (DFD), data store, external entity, source, destination, business rule, data dictionary, entity relationship diagram (ERD), entity, attribute, relationship, cardinality, normalisation (1NF/2NF/3NF), trigger, event, step, transformation, structured English, decision table, decision tree, flowchart, pseudocode, state diagram, retention, process-oriented approach, application-tied data, data duplication, context diagram, process specification, waterfall SDLC.

## The rules to leave Week 1 with

1. **LOW coupling + HIGH cohesion.** Coupling is *between* subsystems; cohesion is *within* one.
2. Every information system has three components: **data**, **data flows**, **processing logic** — model all three.
3. **Information = Data + Context + Organisation** — the two words are not interchangeable.
4. Every data flow has a **named source** and a **named destination** — no orphans on a DFD.
5. Every process has both a **trigger** (when it runs) and **steps** (what it does).
6. The **Process-Oriented Approach** puts DFDs at the centre — great for workflows, but risks **application-tied data** and duplication. Pair with an ERD for shared data.
