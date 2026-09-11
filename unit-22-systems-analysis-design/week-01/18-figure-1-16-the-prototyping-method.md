# Week 1 — Topic 18: Fig. 1.16 — The Prototyping Method

**Source:** `Week_One_Lecture_For_Software_Analysis_and_Design.pdf`, page 44 of 47 (Figure 1.16, adapted from Naumann & Jenkins, MIS Quarterly, 1982).
**Learning Aim:** A — Investigate systems analysis and design methodologies.
**Criteria:** P / M / D.

> Companion figure to Topic 17. Topic 17 defined prototyping and RAD; this figure shows **the prototyping method as a process** — five boxes, five labelled arrows, one loop. Understanding this diagram lets you write a distinction-level answer about how prototyping actually runs.

## Slide content (the diagram)

**Figure 1.16 — The Prototyping Method**

Five boxes (steps) linked by named arrows:

```
                    Initial Requirements
   ┌────────────┐ ────────────────────▶ ┌────────────┐
   │  Identify  │                        │  Develop   │
   │  Problem   │                        │ Prototype  │
   └────────────┘                        └─────┬──────┘
                                               │
                                Working Prototype
                                               │
                                               ▼
   ┌────────────┐                        ┌────────────────────┐    New Requirements
   │ Convert to │◀──── If Prototype ────│  Implement and Use  │◀───────────────────┐
   │Operational │      Inefficient       │      Prototype     │                    │
   │  System    │                        └─────┬──────────────┘                    │
   └────────────┘                              │        ▲                          │
                                          Problems │        │ Next Version           │
                                               ▼        │                          │
                                        ┌───────────────┴───────────┐             │
                                        │ Revise and Enhance         │◀────────────┘
                                        │ Prototype                  │
                                        └────────────────────────────┘
```

**The five steps:**
1. **Identify Problem** — study need and scope (feeds into Topic 15 Planning & Selection).
2. **Develop Prototype** — build the scaled-down working version from initial requirements.
3. **Implement and Use Prototype** — put the prototype in front of users and let them use it.
4. **Revise and Enhance Prototype** — take feedback (problems + new requirements) and improve the prototype; produces the next version, which loops back to step 3.
5. **Convert to Operational System** — when the prototype is inefficient (i.e. cannot be used as-is in production), the settled requirements + design are re-implemented as the real production system.

**The five labelled arrows:**
- `Identify Problem` → `Develop Prototype` — carries **Initial Requirements**.
- `Develop Prototype` → `Implement and Use Prototype` — carries the **Working Prototype**.
- `Implement and Use Prototype` → `Revise and Enhance Prototype` — carries **Problems** discovered by users.
- `Revise and Enhance Prototype` → `Implement and Use Prototype` — carries the **Next Version**.
- `Implement and Use Prototype` → `Convert to Operational System` — taken **If Prototype Inefficient**.
- External: **New Requirements** arrive into `Revise and Enhance Prototype` from outside the loop (change requests, discovered needs).

---

## Pass evidence — describe / identify (P)

- Prototyping is **iterative**, not linear — the diagram is a loop, not a straight line.
- The **inner loop** (Implement and Use ↔ Revise and Enhance) is where user feedback converges the requirements.
- The **exit condition** from the loop is "**If Prototype Inefficient**" — i.e. the prototype is fit for purpose *for eliciting requirements* but not fit for purpose *for production* (performance, robustness, security, scale).
- **New Requirements** can enter at any iteration — the method is designed to accept them, not reject them.

## Merit evidence — analyse / compare (M)

### Why the loop is the whole point

- Each cycle through the inner loop turns *implicit user knowledge* into *explicit requirements* — recorded not as prose but as the prototype's behaviour.
- Loops end when the users stop finding new problems and no new requirements are surfacing — the design has converged.
- The number of iterations is not fixed — that is the strength (matches project uncertainty) and weakness (unpredictable schedule).

### The "if prototype inefficient" branch

- Rarely does a prototype survive to production without a rewrite:
  - Prototypes are usually built on rapid tools (Figma → clickable HTML → sandbox integrations) that are not production-hardened.
  - They typically lack error handling, security, performance tuning and full test coverage.
- Naumann & Jenkins's diagram recognises this: **convert to an operational system** — build the real thing using the settled requirements the prototyping loop produced.
- This is the **throwaway prototype** pattern (Topic 17) — the prototype is the *specification*, not the *deliverable*.

### Compare to Waterfall (Unit 3 D1)

| Step in Waterfall (Unit 3 D1)     | Equivalent in Fig 1.16                                                      |
| --------------------------------- | --------------------------------------------------------------------------- |
| Requirements analysis              | Identify Problem + first pass of Initial Requirements                       |
| Design                             | Develop Prototype (first version), then Convert to Operational System        |
| Construction and testing            | Convert to Operational System's build                                       |
| Acceptance testing                  | Implement and Use Prototype loop (informal) + a formal UAT at the end       |
| Implementation and delivery         | Same                                                                        |

The prototyping method inserts an **elicitation loop** where Waterfall assumes requirements are already known.

### Where each earlier topic sits in the figure

- **Topic 10 (analyst role):** the analyst runs Identify Problem and drives the Implement-and-Use / Revise-and-Enhance loop.
- **Topic 11 (analyst skills):** interpersonal skill runs each iteration; managerial skill decides when the loop has converged.
- **Topic 15 (Planning & Selection):** Identify Problem is the same activity, framed here as the first step of the prototyping cycle.
- **Topic 17 (Prototyping/RAD):** Fig 1.16 is the process behind the definition.

### The "new requirements" side-arrow

- Change is **expected**, not a failure. This is what makes prototyping fit uncertain domains.
- In a Waterfall project the same change would trigger the change management process (Unit 3 D4); here it flows straight into the next iteration.
- But — see Distinction — this only works if there is discipline about **when the loop ends**, otherwise scope creep is unbounded.

---

## Distinction evidence — evaluate / justify (D)

**Strengths of the prototyping method as drawn:**
- Explicit feedback loop → requirements captured against a running artefact (Topic 17's advantage 2).
- **Users involved at every iteration** (Topic 17's advantage 1) → higher adoption at go-live (Topic 10's *People* lever).
- Accepts new requirements gracefully — designed for uncertainty.
- The "if prototype inefficient → convert" step protects the production system from being a rushed prototype.

**Weaknesses / risks:**
- **No stated exit criterion.** The diagram loops without a rule for when to stop. Without a time-box or convergence criterion, projects circle forever.
- **Convert-to-operational step is expensive** — effectively a second build. Sponsors often refuse to fund it and pressure the team to ship the prototype instead → the **prototype-as-production trap** (Topic 17 common failure mode).
- **Documentation lags.** Each iteration produces working code but rarely up-to-date design docs; hurts Operation (Topic 16 maintenance).
- **Scope creep from the New Requirements arrow** — it enters the loop unfiltered.

**Justified judgement (the D-level move):**

Use the prototyping method as Fig 1.16 draws it, **plus three explicit guardrails**:

1. **Exit criterion** — define up front what "prototype done" means (e.g. two consecutive iterations with no new blocking problems and no new blocking requirements). Put it in the PID (Unit 3 B4).
2. **Time-box each iteration** (e.g. 2 weeks). At the end of the box, decide: iterate again, exit to Convert, or stop the project. Prevents unbounded loops.
3. **Change filter on New Requirements** — even in prototyping, new requirements go through a lightweight impact check (fit with scope? cost? affects existing prototype work?). Otherwise scope creep is uncontrollable.

**Recommend** — for GreenLeaf and most small-project scenarios — using Fig 1.16 for the *uncertain user-facing parts* only. The back-end (payment, database, hosting) goes straight into a Waterfall-style Design → Build. This preserves the prototyping benefit where it matters and avoids the "convert to operational system" cost on parts that were already well understood.

Cite Fig 1.16 explicitly in the answer — the marker looks for the five steps, the labelled arrows, and the exit branch.

---

## Applied to a scenario — GreenLeaf Cafés OOS

**Prototyping loop applied to the customer web app checkout flow:**

| Iteration | Step in Fig 1.16                              | GreenLeaf activity                                                                                     |
| --------- | --------------------------------------------- | ------------------------------------------------------------------------------------------------------ |
| —         | Identify Problem                              | Ordering queues at peak; competitor parity; brand refresh.                                             |
| —         | Develop Prototype (v1)                        | Figma click-through of home → menu → cart → checkout → confirmation.                                    |
| 1         | Implement and Use Prototype                   | 3 branch managers + 5 customers walk through v1 on a tablet.                                            |
| 1         | Revise and Enhance Prototype                  | v2: added "collect from" branch picker; enlarged checkout button; clearer allergen icons.                |
| 2         | Implement and Use Prototype                   | Same users test v2; branch managers add "ETA" field they need for staff planning.                       |
| 2         | Revise and Enhance Prototype                  | v3: ETA shown on confirmation; contactless "collect" mode toggle.                                       |
| 3         | Implement and Use Prototype                   | No new blocking problems; no new blocking requirements — exit criterion met.                            |
| —         | Convert to Operational System                 | Front-end rebuilt against the Azure back-end, hardened for PCI-DSS, WCAG 2.1 AA and 4G perf < 2 s.     |

## Exam-answer phrases to use

- "Figure 1.16 shows the prototyping method as an iterative loop: **Identify Problem → Develop Prototype → Implement and Use → Revise and Enhance → Convert to Operational System**."
- "The inner loop (Implement and Use ↔ Revise and Enhance) is where user feedback converts implicit needs into explicit requirements."
- "The exit arrow is labelled '**If Prototype Inefficient**' — meaning the prototype has served its purpose as a specification but must be re-built as an operational system for production."
- "New Requirements enter the loop via the Revise and Enhance step, which is what allows the method to fit uncertain domains."
- "A justified use of the method adds an exit criterion, a per-iteration time-box, and a lightweight change filter on the New Requirements arrow."

## Common trap / examiner feedback

- Drawing the diagram without the **labelled arrows** — the marker checks the four names (Initial Requirements, Working Prototype, Problems, Next Version) and the **If Prototype Inefficient** branch.
- Skipping the **Convert to Operational System** step — treating the prototype as the deliverable. That's the prototype-as-production trap.
- Missing the **New Requirements** arrow — it's what makes the method robust to change.
- Presenting prototyping as a straight line instead of a loop.

## Key vocabulary

**Prototyping method, iteration, prototype v1/v2/v3, working prototype, next version, new requirements, exit criterion, convergence, prototype inefficient, convert to operational system, throwaway prototype, evolutionary prototype, elicitation loop.**
