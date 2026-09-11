# Unit 22 — Assignment 22.1 — Task 1: Brief

**Source:** `L3 Assignment 22.1.pdf`, page 1 of 4 (bottom of page).

## Task 1 — as shown so far

> "The Project Manager has asked you to present a report to the client that explores software development models and **systems analysis tools and techniques** [and applies them to] the new e-card system business [needs / requirements]…"

*(The bottom of page 1 cuts off. The full statement and the P/M/D criteria for this task are on page 2. Add them to this file when captured.)*

## What we can already tell about Task 1

Task 1 is a **written report** aimed at the client (Say-It-With-Cards), authored by us (the junior analyst at ViraMedia). The report is to:

1. **Explore software development models.**
2. **Explore systems analysis tools and techniques.**
3. Apply them to the **new e-card system**.

This is a classic Learning Aim A task — the "investigate methodologies" learning aim. Everything we did in Week 1 feeds directly into it.

## Content the report will almost certainly need (planning list)

Based on Week 1 lecture content and the visible task wording, the report is likely to require:

### On software development models

- **Waterfall SDLC** (Unit 3 D1 + Topic 14 SDLC + Topic 15 phases).
- **Prototyping** as a technique (Topic 17).
- **Rapid Application Development (RAD)** as a methodology (Topic 17 + Topic 18 Fig 1.16 method).
- Possibly **iterative / Agile** as a general contrast — check page 2 for the exact scope.
- **Comparison** across the models (strengths, weaknesses, best-fit projects).
- **Justified recommendation** of which model fits the Say-It-With-Cards e-card project.

### On systems analysis tools and techniques

- **Data Flow Diagrams (DFDs)** — context (level 0) + level 1 for the e-card system (Topic 5, Topic 7).
- **Entity Relationship Diagrams (ERDs)** — entities for Customer, Card, DiaryEvent, AddressBookContact, Order/Receipt, Payment (Topic 4, Topic 8).
- **Data dictionary** — one entry per field (Topic 4).
- **Decomposition** of the e-card system into subsystems (Topic 1).
- **Coupling / cohesion** analysis of the proposed subsystems (Topic 2).
- **Process-Oriented vs Data-Oriented approach** — Table 1.1 comparison + a justified choice (Topics 7, 8).
- **Databases and application independence** (Topic 9).
- **Prototyping method** (Fig 1.16, Topic 18) as an analysis/design tool.
- **Fact-finding techniques** used to elicit the requirements from the customer bullet list (interviews, observation, questionnaires, prototyping) — Topic 10 + Unit 3 E2.

### Applied to the e-card system business

Every model / tool / technique above is described **in the context of Say-It-With-Cards**. Generic descriptions score at Pass; scenario-tied ones score at Merit; scenario-tied *with justified recommendations* score at Distinction.

## Suggested report skeleton (draft — refine when page 2 lands)

1. **Introduction**
   - Purpose of the report (per the brief).
   - Audience (Say-It-With-Cards client).
   - Overview of the e-card system and the customer needs (bullet list from the scenario).

2. **Part A — Software development models**
   - Overview of what a software development model is.
   - **Waterfall SDLC** — phases, strengths, weaknesses, example.
   - **Prototyping** — technique, advantages, throwaway vs evolutionary.
   - **Rapid Application Development (RAD)** — Fig 1.16 method, JAD, time-boxing.
   - Comparison table.
   - **Justified recommendation** for the e-card project — likely a **hybrid**: RAD-style prototyping for the customer-facing UX (personalisation, diary, address book) + Waterfall discipline for the back-end (payment, login, database). Justify with the scenario's mix of *uncertain UX* and *regulated payment / secure login*.

3. **Part B — Systems analysis tools and techniques**
   - Decomposition of the e-card system into subsystems (Card Catalogue, Personalisation, Diary, Address Book, Reminders, Social Media Link, Payment, Login).
   - Coupling / cohesion notes.
   - Data Flow Diagram — level 0 context + level 1 of the ordering / sending flow.
   - Entity Relationship Diagram — entities, attributes, relationships, cardinality.
   - Data dictionary (extract).
   - Fact-finding techniques used (or that would be used).
   - Process-Oriented vs Data-Oriented choice — justified.

4. **Part C — Applied to the e-card system**
   - How each model / tool addresses the specific customer needs listed in the scenario.
   - Trace each requirement in the brief to the model artefact that captures it.
   - Risk analysis (Unit 3 A3 / C3) — technical, security (payment + login), UX, delivery.

5. **Conclusion + justified recommendation**
   - Chosen methodology + why.
   - Chosen analysis approach + why.
   - Next steps for the project team.

6. **Appendices**
   - Full DFDs, ERD, data dictionary, prototype wireframes.

## Grade band prompts (to sharpen against page 2 when it arrives)

- **Pass (describe / produce)** — describe each software development model and each analysis tool; produce the diagrams.
- **Merit (analyse / compare)** — compare models; analyse trade-offs; explain why each analysis tool matters to the e-card system.
- **Distinction (evaluate / justify)** — evaluate the models against the scenario; make a **justified recommendation**; consider alternatives; conclude with a clear next-step recommendation.

## What we still need

- The **rest of Task 1** (full wording of the requirement).
- The **P/M/D criteria** for Task 1 (the exact command words for each grade band).
- Any **word count / format** requirements (Word doc, presentation, poster?).
- Any **further tasks** (Task 2, Task 3…) — likely on pages 2–4.

Ask Luis / the tutor for a clean PDF of the whole 4-page brief so we can plan the workload against the **02 October 2026** deadline properly.
