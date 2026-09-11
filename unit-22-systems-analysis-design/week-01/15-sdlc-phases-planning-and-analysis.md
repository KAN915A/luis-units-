# Week 1 — Topic 15: SDLC Phases (Part 1) — Systems Planning & Selection, Systems Analysis

**Source:** `Week_One_Lecture_For_Software_Analysis_and_Design.pdf`, page 38 of 47.
**Learning Aim:** A — Investigate systems analysis and design methodologies.
**Criteria:** P / M / D.

> Topic 14 named the SDLC's four **compact** phases (Analysis → Design → Implementation → Maintenance). This slide expands them into a more detailed sequence, starting with two phases that come *before* the build:
> 1. **Systems Planning and Selection** (identify + scope)
> 2. **Systems Analysis** (study, requirements, alternatives, recommendation)
> The remaining phases (Design, Implementation, Maintenance) will come on later slides.

## Slide content (verbatim)

**Phases of the Systems Development Life Cycle**

- **Systems Planning and Selection**
  - Two main activities:
    - Identification of need
    - Investigation and determination of scope

- **Systems Analysis**
  - Study of current procedures and information systems
    - Determine requirements
    - Generate alternative designs
    - Compare alternatives
    - Recommend best alternative

---

## Pass evidence — describe / identify (P)

### Systems Planning and Selection

The **first** phase — decides *whether* to run the project and *what* it should broadly cover.

- **Identification of need** — what business problem or opportunity has triggered this? Aligns with Unit 3 A1 (project mandate) and Unit 3 B1 (business case).
- **Investigation and determination of scope** — a preliminary study to set the boundary:
  - What is IN this project?
  - What is NOT in this project?
  - Feasibility (technical / economic / operational / schedule) — Unit 3 A2 feasibility.
  - Preliminary cost/benefit and timescale.
- **Output:** a project proposal / feasibility report / preliminary PID that the sponsor uses to authorise (or refuse) the next phase.

### Systems Analysis

The **second** phase — decides *what exactly* the new system must do and *which design option* is best.

Four activities:
1. **Determine requirements** — elicit, document, categorise (functional vs non-functional; SMART).
2. **Generate alternative designs** — produce **more than one** candidate solution (bespoke build vs off-the-shelf package vs process change vs hybrid).
3. **Compare alternatives** — evaluate each against the requirements, cost, risk, feasibility, strategic fit.
4. **Recommend best alternative** — a written, justified recommendation to the sponsor.

- **Output:** a signed-off requirements specification and a recommendation for which alternative to build (feeds into the Design phase — next slide).

## Merit evidence — analyse / compare (M)

### Why Planning & Selection comes first

- Prevents wasted effort on projects that shouldn't happen — the "**do nothing**" option is a valid outcome of feasibility.
- Sets **scope explicitly**, which prevents scope creep during the build (Unit 3 D4).
- Produces the **first cost/timescale estimate**, which the PM uses to plan (Unit 3 C1/C2).
- Feeds directly into the Project Initiation Document (Unit 3 B4) — many of the PID's sections come from this phase.

### Why analysis has four activities, not one

- **Determine requirements** alone is not enough — many projects fail because the *first* solution people think of gets built without comparison.
- Generating **multiple alternatives** forces you to think about the problem, not just the one solution you're wedded to. Options should include the "do nothing" or "change the process only" alternatives (Topic 10 — People / Methods / Technology).
- **Compare alternatives** produces the evidence for the choice — cost, benefit, risk, fit, strategic alignment.
- **Recommend best alternative** — with justification — is the analyst's deliverable to the sponsor.

### "Study of current procedures and information systems" — the As-Is view

- Before designing the To-Be, the analyst studies the As-Is: how the work is currently done, what systems currently exist, where the pain is.
- Techniques (from Topic 10): interviews, document analysis, observation, questionnaires, prototyping.
- Skipping the As-Is means designing on assumption — a common source of missed requirements.

### Link to earlier topics + Unit 3

- **Unit 3 A5 (project life cycle):** Systems Planning & Selection aligns with *Conception and start-up + Definition*; Systems Analysis aligns with *Planning*.
- **Unit 3 B1 (business case), B3 (assumptions/constraints), B4 (PID):** all fed from these two phases.
- **Topic 8 (approaches):** "generate alternative designs" is where the choice between **Process-Oriented / Data-Oriented / hybrid** is made.
- **Topic 10 (analyst role):** these two phases are where the analyst's job — study problems, evaluate approaches, help users define requirements — visibly happens.
- **Topic 11 (analyst skills):** managerial skill runs Planning & Selection to time and budget; interpersonal skill drives the requirements elicitation in Analysis.

### Compare with Unit 3 D1 (Waterfall)

- Unit 3 D1's Waterfall model has "Requirements analysis" as its first phase. This slide splits Waterfall's "Requirements" step into **Planning & Selection** (should we do it? how big?) + **Systems Analysis** (what exactly, and which alternative?). Same territory, more granular.

---

## Distinction evidence — evaluate / justify (D)

**Strengths of running these two phases properly:**
- Kills bad projects before they consume budget (do-nothing outcome is a success, not a failure).
- Sets a defensible scope + preliminary estimate — prevents scope creep and estimate-shock later.
- Produces a signed-off requirements spec — the baseline for testing (Unit 3 C4) and closure (Unit 3 E1).
- Produces a **justified** choice of alternative — audit-trail for the sponsor's investment.
- Aligns the SDLC's first steps with the PM's project life cycle steps (Unit 3 A5) — one team, two disciplines, one plan.

**Weaknesses / risks:**
- **Analysis paralysis** — endless requirement gathering with no build. Set a time-box.
- **Requirements-freeze fallacy** — Waterfall-style "sign off the requirements once and never change them" fails when requirements evolve; use iteration or Agile within these phases if change is expected.
- **Single-alternative bias** — the team writes up their preferred solution as if it were the only option. This slide **explicitly requires alternatives**; ignoring that is a common examiner-flagged weakness.
- **As-Is-only bias** — modelling the existing system in perfect detail without designing anything new; the study is a means, not the end.

**Justified judgement (the D-level move):**

Treat **Planning & Selection** and **Analysis** as the phases where the project **earns its right to spend money**. Concretely:

1. Time-box Planning & Selection (e.g. 1–2 weeks for a small project) with a **go / no-go** decision at the end.
2. In Analysis, always produce at least **three** alternatives: change nothing, change the process only, build/buy a system. Compare on **cost / benefit / time / risk / strategic fit**.
3. Requirements must be **SMART** (Unit 3 A2) and **categorised** (functional vs non-functional).
4. The recommendation is **written**, references the alternatives it beat, and is **signed off** by the sponsor before design starts.

**Recommend** carrying the requirements spec, the alternatives comparison, and the recommendation as living documents into the PID (Unit 3 B4) — otherwise the analyst's work is invisible to the marker and to the sponsor.

---

## Applied to a scenario — GreenLeaf Cafés OOS

### Systems Planning & Selection

- **Identification of need** — peak-hour queues cause ~£62k/yr lost revenue; competitors (Pret, Costa) offer online ordering; brand modernisation.
- **Scope investigation:**
  - IN: customer web app, staff portal, Stripe integration, deployment to all 12 branches, staff training, 3-month warranty.
  - NOT IN: native mobile apps, loyalty rewards (phase 2), EPOS integration (phase 2), delivery.
  - Feasibility: technical (yes, existing Azure), economic (£40k cost, £62k/yr benefit — ROI positive), operational (branch staff willing given training), schedule (11 weeks feasible).
- **Output:** feasibility report + preliminary PID → sponsor authorises Analysis.

### Systems Analysis

- **Determine requirements:**
  - Functional: order flow, payment, staff order queue, branch selection, training materials.
  - Non-functional: 90-second order flow, WCAG 2.1 AA, PCI-DSS, 99.5% uptime.
- **Generate alternatives:**
  - A: Bespoke build (chosen).
  - B: Off-the-shelf platform (Deliveroo add-in) — quick, 8% transaction fees, weak brand.
  - C: Do nothing — falls further behind competitors.
- **Compare alternatives:** ROI over 3 years, brand control, integration cost, staff training cost, risk.
- **Recommend:** Option A — bespoke build — because ROI is highest over 3 years, brand control is retained, and existing Azure hosting reduces incremental cost.
- **Output:** signed requirements specification + written recommendation → sponsor signs off, Design phase can start.

## Exam-answer phrases to use

- "Systems Planning and Selection has two main activities: **identification of need** and **investigation and determination of scope**."
- "Systems Analysis studies current procedures and information systems, then in four steps: **determine requirements**, **generate alternative designs**, **compare alternatives**, and **recommend the best alternative**."
- "Generating alternative designs — and comparing them — is what turns Analysis from a description of the problem into a justified recommendation, and evidences the distinction-level requirement to *evaluate*."
- "Skipping Planning & Selection risks running a project that shouldn't have started; skipping Analysis risks building the wrong system."

## Common trap / examiner feedback

- Listing Planning & Selection as one bullet — the spec names **two** activities (identification of need; investigation and determination of scope). Both must appear.
- Analysis with only **one** alternative — a lecture-classic missed mark. The slide explicitly requires *alternative designs* (plural), *compare alternatives*, *recommend* the best.
- Confusing Analysis with Design — Analysis says *what* is needed and *which* alternative wins; Design says *how* to build the chosen alternative.
- Skipping the **As-Is study** — the slide says "study of current procedures and information systems"; the As-Is is not optional.

## Key vocabulary

**Systems Planning and Selection, identification of need, investigation and determination of scope, feasibility, Systems Analysis, requirements determination, alternative designs, comparison of alternatives, recommendation, As-Is / To-Be, requirements specification.**
