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

## Assignment Tracker

<!-- Assignment tasks and progress go here -->
