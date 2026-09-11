# Unit 22 — Systems Analysis and Design

Assignment-based unit on the **BTEC Level 3 Extended Diploma in Computing**. Notes and evidence are structured to the P / M / D mark scheme.

## Mark Scheme — Pass, Merit, Distinction

BTEC internally-assessed units grade against criteria that build on top of each other. To hit **Distinction**, all Pass **and** Merit criteria must first be met.

| Grade       | Depth of thinking            | Command words                                                     | What the evidence must show                                                                                       |
| ----------- | ---------------------------- | ----------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------- |
| Pass        | Describe / identify / produce | describe, identify, produce, outline, explain (basic)             | Correct facts, definitions, a produced artefact. Shows the "what".                                                |
| Merit       | Analyse / compare             | analyse, compare, discuss, examine                                | Breaks the topic down, links causes and effects, compares options. Shows the "why" and "how".                     |
| Distinction | Evaluate / justify            | evaluate, justify, assess, recommend, to what extent              | Makes a reasoned judgement using evidence from the scenario. Weighs strengths vs weaknesses. Reaches a conclusion.|

### Distinction-level checklist (use for every task)

- [ ] All Pass criteria fully met (nothing missing)
- [ ] All Merit criteria fully met (analysis, not just description)
- [ ] Judgement is **justified** with reasons and evidence
- [ ] Alternatives are considered and compared
- [ ] Refers directly to the assignment scenario/client
- [ ] Uses correct technical vocabulary throughout
- [ ] Concludes with a clear recommendation

## Learning Aims (typical structure)

Assignment tasks will map to learning aims. Standard shape:

- **A.** Investigate systems analysis and design methodologies
- **B.** Carry out a structured analysis of a system
- **C.** Design a system to meet a client brief
- **D.** Review the proposed design

## Assignment Task Template

```markdown
### Task <n>: <title>  •  Learning Aim: <A/B/C/D>  •  Criteria: <P?/M?/D?>

**Brief / what the task asks for**
- ...

**Pass evidence (describe / produce)**
- ...

**Merit evidence (analyse / compare)**
- ...

**Distinction evidence (evaluate / justify)**
- ...

**Files / artefacts submitted**
- ...

**Status**: not started / in progress / draft / submitted / feedback received
```

## Lesson Notes

<!-- Topic notes go here using the same criteria breakdown -->

### Lesson — Week 1 (11/09/2026, with Luis)
Source: `Week_One_Lecture_For_Software_Analysis_and_Design.pdf`, page 17 of 47 (Fig. 1.6).

---

#### Topic: System decomposition (CD player example)  •  Learning Aim: A  •  Criteria: P / M / D

**Concept the slide teaches**
A system is not always understood best as one black box. **Decomposition** is the process of breaking a complex system into smaller, connected **subsystems**, each with a defined role, so the system can be understood, designed, built and tested one piece at a time.

**Worked example from the slide — CD Player System**

*Before decomposition (whole system view):*
- Input: **CD** + **Control settings** (play, pause, volume, track skip).
- Process: hidden inside one "CD Player System" black box.
- Output: **Music**.

*After decomposition (four subsystems):*

| Subsystem                 | Input           | Role                                                      | Output to next stage       |
| ------------------------- | --------------- | --------------------------------------------------------- | -------------------------- |
| **Signal Reading**        | CD              | Reads the raw digital signal off the CD (laser + optics). | Raw digital signal.        |
| **Signal Amplifying**     | Raw signal      | Boosts the weak signal for further processing.            | Amplified digital signal.  |
| **Signal Control**        | Control settings | Applies user controls (track, volume, pause).            | Control instructions.      |
| **Signal Conversion**     | Amplified signal + control instructions | Converts the digital signal to analogue audio the headphones can play. | **Music** (to headphones). |

Flow (as shown on the slide):
`CD → Signal Reading → Signal Amplifying → Signal Conversion → Music`
`Control settings → Signal Control → Signal Conversion`

---

**Pass evidence — describe / identify (P)**
- Define a **system** — a set of interacting components that work together to achieve a goal.
- Define a **subsystem** — a smaller system inside a larger one that carries out a specific part of the overall function.
- Identify the four subsystems on the slide: signal reading, signal amplifying, signal control, signal conversion.
- State the CD player's inputs (CD, control settings) and output (music).

**Merit evidence — analyse / compare (M)**
- **Why decompose?**
  - **Manages complexity** — a designer can focus on one subsystem at a time.
  - **Enables specialisation** — the reading subsystem is an optics problem; the conversion subsystem is a digital-to-analogue signal problem. Different expertise, different components.
  - **Enables parallel development** — teams can work on different subsystems at once (feeds into the Unit 3 concept of parallel task scheduling).
  - **Enables independent testing** — each subsystem tested against its own specification before integration (links to Unit 3 C4 unit vs integration vs system testing).
  - **Improves maintainability** — if the volume control breaks, only the signal control subsystem is suspect, not the whole player.
- **Compare** whole-system view vs decomposed view:
  - Whole-system view = quick to grasp, no internal detail — useful for the user or in the business case.
  - Decomposed view = shows structure and data flow — required for design, build and testing.
- **Compare** the CD player example to a software system: exactly the same idea — a booking system decomposes into an authentication subsystem, catalogue subsystem, payment subsystem, notification subsystem, each with its own inputs and outputs.

**Distinction evidence — evaluate / justify (D)**
- **Strengths of decomposition** — makes complexity tractable, supports parallel work, isolates faults, makes reuse possible (the signal amplifier design could be reused in a different audio product).
- **Weaknesses / risks** — subsystems have to talk to each other, so **interfaces** become the risky part; a decomposition that is too fine-grained creates many interfaces and integration overhead; over-simplified decomposition hides real complexity (e.g. lumping "signal reading" together may miss that error correction is its own concern).
- **Justified judgement** — for a CD player, four subsystems is a proportionate decomposition: enough separation to let specialists design each part, few enough interfaces to keep integration manageable. For a software system aim for the same balance — decompose until each subsystem has one clear responsibility, but stop before the number of interfaces starts to dominate design effort. Recommend that every decomposition diagram is drawn **with the data flow labelled** (as the slide does with the arrows), because a boxes-only diagram hides the coupling and gives a false sense of independence.

**Files / artefacts to produce for the assignment**
- A decomposition diagram of the chosen system (like Fig. 1.6) with arrows labelled.
- A subsystem responsibility table (as above).
- A short evaluation paragraph justifying the level of decomposition.

**Common trap / examiner feedback**
- Drawing the "after" diagram with boxes only, no arrows — hides the interfaces.
- Making the decomposition purely about **structure** (parts) rather than **function + data flow** (what each part does with what signal).
- Confusing **subsystems** (functional parts of one system) with **separate systems** (independent systems that happen to talk).

**Key vocabulary to memorise**
- **System, subsystem, component, interface, input, process, output, data flow, black box, decomposition.**

---

#### Topic: Important System Concepts — Modularity, Coupling, Cohesion  •  Learning Aim: A  •  Criteria: P / M / D

Source: `Week_One_Lecture_For_Software_Analysis_and_Design.pdf`, page 18 of 47.

**Slide content (verbatim)**
- **Modularity** — Process of dividing a system into modules of a relatively uniform size. Modules simplify system design.
- **Coupling** — Subsystems that are dependent upon each other are coupled.
- **Cohesion** — Extent to which a subsystem performs a single function.

---

**Pass evidence — describe / identify (P)**
- **Module** — a self-contained unit of a larger system that performs a specific role (glossary of Unit 3: "part of a large software system that carries out a specific business role" — e.g. HR uses a payroll module).
- **Modularity** = the design property of a system that has been divided into modules.
- **Coupling** = the degree of dependency between two subsystems / modules. If A relies on B's internal details, they are **tightly coupled**. If A only needs a small, well-defined interface to B, they are **loosely coupled**.
- **Cohesion** = the degree to which the parts of one subsystem all work towards a single, focused purpose. A subsystem that does one thing well = **high cohesion**. A subsystem that does many unrelated things = **low cohesion**.

**The golden rule of good design:** **LOW coupling + HIGH cohesion.**

---

**Merit evidence — analyse / compare (M)**

*Modularity — why it matters*
- Simplifies design: one module can be designed without holding the whole system in your head.
- Enables parallel development, independent testing, easier maintenance and reuse.
- "Uniform size" — modules of similar size make estimation, staffing and progress tracking predictable (feeds Unit 3 C1 scheduling and C2 estimation).

*Coupling — comparison*

| Coupling level | What it looks like                                      | Effect                                               |
| -------------- | ------------------------------------------------------- | ---------------------------------------------------- |
| Tight (bad)    | A reads B's internal variables, or shares B's database directly. | Change in B breaks A. Cannot swap B out.       |
| Loose (good)   | A calls B only through a documented interface / API.    | B's internals can change without breaking A.         |

*Cohesion — comparison*

| Cohesion level | What it looks like                                      | Effect                                               |
| -------------- | ------------------------------------------------------- | ---------------------------------------------------- |
| Low (bad)      | One subsystem handles login **and** invoicing **and** email. | Hard to understand, test, or reuse.               |
| High (good)    | Login subsystem does login only. Invoicing does invoicing only. | Easy to name, test, replace, and reason about. |

*Link back to Figure 1.6 (CD player decomposition)*
- Each of the four subsystems (reading, amplifying, control, conversion) does **one job** → high cohesion. ✓
- Interfaces between them are small (a signal in, a signal out) → low coupling. ✓
- That is *why* the decomposition works.

---

**Distinction evidence — evaluate / justify (D)**

- **Strengths:**
  - High cohesion + low coupling makes systems **easier to understand, test, maintain, replace and reuse**.
  - Modularity supports parallel work (Unit 3 C1 parallel task scheduling) and localised fault-fixing (Unit 3 C4 defect removal + D4 change management: change confined to one module).
  - Loosely coupled interfaces let you **swap suppliers or technologies** without redesigning the whole system (e.g. change payment provider without changing checkout logic).

- **Weaknesses / trade-offs:**
  - Splitting too aggressively creates **many small modules** with **many interfaces** → integration overhead + interface bugs.
  - "Relatively uniform size" is an ideal, not always achievable — some responsibilities are naturally bigger than others; forcing uniformity can distort the design.
  - High cohesion sometimes conflicts with performance — a fully isolated subsystem may need extra network calls or data copies to talk to others.

- **Justified judgement (the D-level move):**
  Aim for the highest cohesion **and** the lowest coupling **that the problem sensibly allows**. In practice: decide module boundaries around **business responsibilities** (one module owns one business capability), define interfaces before writing internals, and review the design by asking "if I change this one thing, how many modules must change?" — if the answer is more than one or two, the boundaries are wrong. Recommend also documenting each module's interface in the design phase so downstream code cannot rely on internals — this operationalises the loose-coupling principle rather than leaving it to good intentions.

---

**Applied to a scenario — small computing project (e.g. online booking system)**

| Subsystem      | Single function (cohesion)                       | Talks to (interface — coupling)                            |
| -------------- | ------------------------------------------------ | ----------------------------------------------------------- |
| Authentication | Verifies user identity, issues session tokens.   | Gives a "user id + role" to any subsystem that asks.        |
| Catalogue      | Stores/serves the list of bookable slots.        | Publishes a `getAvailableSlots()` API.                      |
| Booking        | Records a booking, enforces business rules.      | Calls Catalogue (read) + Payment (charge) + Notification.   |
| Payment        | Talks to Stripe, handles refunds.                | Called by Booking through a `charge(amount, orderId)` API.  |
| Notification   | Sends confirmation emails/SMS.                   | Called by Booking with a message payload.                   |

Each row: **one clear job (high cohesion)** and **a small, named interface (low coupling)**. Same pattern as the CD player.

---

**Exam-answer phrases to use**
- "Dividing the system into modules of a relatively uniform size simplifies design because…"
- "These two subsystems are tightly coupled because module A depends on internal detail of module B; a design change is recommended so that A only interacts with B through a defined interface."
- "The subsystem exhibits high cohesion because it performs a single, well-defined function (…)."
- "For distinction-level design, the aim is **low coupling and high cohesion**, because this makes the system easier to test, maintain and evolve."

**Common trap / examiner feedback**
- Mixing coupling and cohesion up. Remember:
  - **Coupling** is between subsystems (external — how much they depend on each other).
  - **Cohesion** is within a subsystem (internal — how focused it is on one job).
- Saying "coupling is bad" — coupling is inevitable (subsystems must talk). The point is to keep it **loose**.
- Saying "modularity is enough" — a modular system with tight coupling is still fragile.

**Key vocabulary to memorise**
- **Module, modularity, coupling (tight / loose), cohesion (high / low), interface, dependency, encapsulation.**

## Assignment Tracker

<!-- Assignment tasks and progress go here -->
