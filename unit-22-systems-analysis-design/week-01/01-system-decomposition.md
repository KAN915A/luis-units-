# Week 1 — Topic 1: System Decomposition (CD Player example)

**Source:** `Week_One_Lecture_For_Software_Analysis_and_Design.pdf`, page 17 of 47 (Fig. 1.6).
**Learning Aim:** A — Investigate systems analysis and design methodologies.
**Criteria:** P / M / D.

## Concept the slide teaches

A system is not always understood best as one black box. **Decomposition** is the process of breaking a complex system into smaller, connected **subsystems**, each with a defined role, so the system can be understood, designed, built and tested one piece at a time.

## Worked example from the slide — CD Player System

**Before decomposition (whole system view):**
- Input: **CD** + **Control settings** (play, pause, volume, track skip).
- Process: hidden inside one "CD Player System" black box.
- Output: **Music**.

**After decomposition (four subsystems):**

| Subsystem              | Input                                     | Role                                                            | Output to next stage       |
| ---------------------- | ----------------------------------------- | --------------------------------------------------------------- | -------------------------- |
| **Signal Reading**     | CD                                        | Reads the raw digital signal off the CD (laser + optics).       | Raw digital signal.        |
| **Signal Amplifying**  | Raw signal                                | Boosts the weak signal for further processing.                  | Amplified digital signal.  |
| **Signal Control**     | Control settings                          | Applies user controls (track, volume, pause).                   | Control instructions.      |
| **Signal Conversion**  | Amplified signal + control instructions   | Converts the digital signal to analogue audio for the headphones.| **Music** (to headphones). |

**Flow (as shown on the slide):**
```
CD → Signal Reading → Signal Amplifying → Signal Conversion → Music
Control settings → Signal Control → Signal Conversion
```

---

## Pass evidence — describe / identify (P)

- Define a **system** — a set of interacting components that work together to achieve a goal.
- Define a **subsystem** — a smaller system inside a larger one that carries out a specific part of the overall function.
- Identify the four subsystems on the slide: signal reading, signal amplifying, signal control, signal conversion.
- State the CD player's inputs (CD, control settings) and output (music).

## Merit evidence — analyse / compare (M)

**Why decompose?**
- **Manages complexity** — a designer can focus on one subsystem at a time.
- **Enables specialisation** — the reading subsystem is an optics problem; the conversion subsystem is a digital-to-analogue signal problem. Different expertise, different components.
- **Enables parallel development** — teams can work on different subsystems at once (feeds into Unit 3 C1 parallel task scheduling).
- **Enables independent testing** — each subsystem tested against its own specification before integration (links to Unit 3 C4 unit vs integration vs system testing).
- **Improves maintainability** — if the volume control breaks, only the signal control subsystem is suspect, not the whole player.

**Compare whole-system view vs decomposed view:**
- Whole-system view = quick to grasp, no internal detail — useful for the user or in the business case.
- Decomposed view = shows structure and data flow — required for design, build and testing.

**Compare CD player to a software system:**
Exactly the same idea — a booking system decomposes into an authentication subsystem, catalogue subsystem, payment subsystem, notification subsystem, each with its own inputs and outputs.

## Distinction evidence — evaluate / justify (D)

**Strengths of decomposition:**
- Makes complexity tractable.
- Supports parallel work.
- Isolates faults.
- Makes reuse possible (the signal amplifier design could be reused in a different audio product).

**Weaknesses / risks:**
- Subsystems have to talk to each other, so **interfaces** become the risky part.
- Too-fine-grained decomposition creates many interfaces and integration overhead.
- Over-simplified decomposition hides real complexity (e.g. lumping "signal reading" together may miss that error correction is its own concern).

**Justified judgement:**
For a CD player, four subsystems is a proportionate decomposition — enough separation to let specialists design each part, few enough interfaces to keep integration manageable. For a software system, aim for the same balance: decompose until each subsystem has one clear responsibility, then stop before the number of interfaces starts to dominate design effort. **Recommend** that every decomposition diagram is drawn **with the data flow labelled** (as the slide does with the arrows) — a boxes-only diagram hides the coupling and gives a false sense of independence.

## Files / artefacts to produce for the assignment

- A decomposition diagram of the chosen system (like Fig. 1.6) with arrows labelled.
- A subsystem responsibility table (as above).
- A short evaluation paragraph justifying the level of decomposition.

## Common trap / examiner feedback

- Drawing the "after" diagram with boxes only, no arrows — hides the interfaces.
- Making the decomposition purely about **structure** (parts) rather than **function + data flow** (what each part does with what signal).
- Confusing **subsystems** (functional parts of one system) with **separate systems** (independent systems that happen to talk).

## Key vocabulary

**System, subsystem, component, interface, input, process, output, data flow, black box, decomposition.**
