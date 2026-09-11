# Week 1 — Topic 14: Systems Development Life Cycle (SDLC)

**Source:** `Week_One_Lecture_For_Software_Analysis_and_Design.pdf`, page 35 of 47.
**Learning Aim:** A — Investigate systems analysis and design methodologies.
**Criteria:** P / M / D.

> The lecture now moves from *types* of information system to *how you build one*. The **Systems Development Life Cycle (SDLC)** is the standard four-phase framework: **Analysis → Design → Implementation → Maintenance**. Everything you build in this unit follows some SDLC variant.

## Slide content (verbatim)

**Systems Development Life Cycle**

- **System Development Methodology**
  - Standard process followed in an organisation.
  - Consists of:
    - Analysis
    - Design
    - Implementation
    - Maintenance

---

## Pass evidence — describe / identify (P)

### System Development Methodology — definition

A **standard process** an organisation uses to develop information systems. It sets the phases, the deliverables per phase, the roles, and the sign-offs. Following a methodology gives every project the same shape so people can join, hand over, and audit without re-learning the process.

### The four phases (this slide's version of the SDLC)

| # | Phase              | What happens                                                                                                     | Typical deliverables                                             |
| - | ------------------ | ---------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------- |
| 1 | **Analysis**       | Study the problem; elicit requirements; model the current and proposed systems.                                   | Requirements specification, DFDs, ERD, data dictionary, use cases. |
| 2 | **Design**         | Turn requirements into a technical blueprint — architecture, database schema, screens, module specs, data flows. | System design document, database schema, screen designs, module specs. |
| 3 | **Implementation** | Build the system (code, configure), test it, install it, train users, go live.                                    | Working code, test reports, user manual, trained users, live system. |
| 4 | **Maintenance**    | Keep the live system running and fit for purpose — fix defects, apply enhancements, retire when replaced.        | Change requests, patch releases, support tickets, retirement plan. |

> Some frameworks split these further (Planning → Analysis → Design → Implementation → Testing → Maintenance). This slide uses the compact four-phase version.

## Merit evidence — analyse / compare (M)

### Why "standard process" matters

- **Consistency across projects** — every new project has the same phase gates, deliverables and sign-offs; staff move between projects without re-learning.
- **Governance** — sponsors know when and how to review progress (feeds Unit 3 A5 project life cycle and D2 checkpoint reports).
- **Predictability** — estimating (Unit 3 C2), scheduling (Unit 3 C1) and risk (Unit 3 C3) work better when the shape of the project is known.
- **Audit and compliance** — regulated industries need a documented development process.

### The four phases in a nutshell — cause and effect

- **Analysis** answers *what* the system must do. Skimped analysis → wrong system built.
- **Design** answers *how* it will do it. Skimped design → high defect rate in implementation.
- **Implementation** turns design into a running, accepted system. Skimped implementation → live but broken.
- **Maintenance** keeps it fit for purpose. Skimped maintenance → the system rots, becomes untrusted, gets abandoned early.

### Link to Unit 3 (project life cycle vs SDLC)

- **Unit 3 A5 project life cycle** = *how a project is managed* (Conception → Definition → Planning → Launch/Execution → Closure → Post-project review).
- **Unit 22 SDLC** = *how a system is developed within (or across) projects* (Analysis → Design → Implementation → Maintenance).
- **They interlock:** the SDLC's Analysis/Design/Implementation happens inside the project life cycle's Launch and Execution phase; SDLC Maintenance sits *after* the project closes.

### Link to Unit 3 D1 (Waterfall)

- The Waterfall model in Unit 3 D1 (Requirements analysis → Design → Construction and testing → Acceptance testing → Implementation and delivery) is one specific way of ordering the SDLC phases.
- **SDLC = the phases**. **Methodology (Waterfall, Agile, iterative) = the way you order and iterate them.** Don't confuse the two.

### Where the earlier Week 1 topics live in the SDLC

| Earlier topic                                            | Fits in phase              |
| -------------------------------------------------------- | -------------------------- |
| Decomposition (Topic 1)                                  | Analysis + Design          |
| Modularity / coupling / cohesion (Topic 2)                | Design                     |
| DFD, ERD, data dictionary (Topics 3–6)                    | Analysis                   |
| Process-Oriented / Data-Oriented approach (Topics 7–8)    | Analysis + Design          |
| Database + application independence (Topic 9)             | Design                     |
| Analyst role + skills (Topics 10–11)                      | Analysis (mostly)          |
| TPS/MIS/DSS/ES classes (Topics 12–13)                     | Analysis (pick class first)|

Every artefact you produce belongs in one of the four phases.

---

## Distinction evidence — evaluate / justify (D)

**Strengths of following a defined SDLC methodology:**
- Repeatable, auditable, teachable process.
- Aligns with **quality management** (Unit 3 C4) — each phase has defined defect-removal (reviews) and testing activities.
- Aligns with **risk management** (Unit 3 A3, C3) — risks change by phase; the methodology tells you when to look for them.
- Aligns with **project management** (Unit 3 A5) — natural stage gates for sponsor sign-off (Unit 3 D2 checkpoint reports).
- Makes **maintenance planning** explicit — the fourth phase is not an afterthought.

**Weaknesses / risks:**
- A methodology followed without judgement becomes bureaucratic overhead — small projects need lighter versions.
- A **linear (waterfall) SDLC** assumes requirements are stable; when they aren't, it fits poorly — an **iterative** or **Agile** methodology may be a better ordering of the same four phases.
- Skipping **Maintenance planning** at the outset is common; the resulting system has no owner post-launch, and quality decays.
- Treating "Implementation" as just coding — it's also **testing, training, deployment and cut-over** (Unit 3 D5 implementation strategy).

**Justified judgement (the D-level move):**

Choose the **methodology (Waterfall / Agile / iterative / hybrid)** to fit the project, but keep the four SDLC phases as a checklist:

1. Never skip Analysis — no build without a signed requirements spec.
2. Never skip Design — no code without an architecture and data model, however lightweight.
3. Implementation is *build + test + train + deploy*, not just code.
4. Plan Maintenance **before go-live** — support owner, warranty period, defect route, retirement horizon (Unit 3 E1 closure).

**Recommend** documenting the chosen methodology + tailoring decisions in the PID (Unit 3 B4) so sponsor and team share one version. For a small project (like GreenLeaf OOS), a light Waterfall with short review cycles fits; for a project with evolving requirements, iterate the SDLC in short cycles (Agile-style) — but the four phases are still there each cycle.

---

## Applied to a scenario — GreenLeaf Cafés OOS

| SDLC phase       | GreenLeaf activity                                                                                            | Sign-off                              |
| ---------------- | ------------------------------------------------------------------------------------------------------------- | ------------------------------------- |
| Analysis         | Interviews, DFD, ERD, data dictionary, SMART requirements. Weeks 1–2.                                          | Client + sponsor sign requirements.   |
| Design           | Architecture (Azure hosting), DB schema, UI screens, Stripe integration design, staff-portal design. Weeks 3–4. | Sponsor signs design doc.             |
| Implementation   | Build (weeks 5–8) + system test + UAT with pilot branches + staff training + go-live 01/12/2026.                | Client signs UAT + go-live cert.      |
| Maintenance      | 3-month warranty + IT Ops support (email + SLA) + quarterly review + rule-base updates for the ES component.   | Handover email + benefits review at 3 months. |

## Exam-answer phrases to use

- "A **systems development methodology** is a standard process followed by an organisation to develop information systems, giving every project the same shape."
- "The Systems Development Life Cycle (SDLC) consists of four phases: **Analysis, Design, Implementation and Maintenance**."
- "The SDLC phases describe *what* is done at each stage; the methodology (Waterfall, Agile, iterative) describes *how* those phases are ordered and iterated."
- "Following a defined SDLC produces auditable, repeatable projects and aligns naturally with the project management activities of Unit 3."

## Common trap / examiner feedback

- Confusing **SDLC** with **methodology** — SDLC is the phases; methodology is how you order them (Waterfall, Agile, etc.).
- Skipping **Maintenance** in the answer — the spec explicitly lists it; markers check.
- Treating **Implementation** as coding only — it is build + test + train + deploy.
- Confusing the **project life cycle** (Unit 3 A5) with the **SDLC** — the project life cycle manages the *project*; the SDLC develops the *system*.

## Key vocabulary

**Systems Development Life Cycle (SDLC), methodology, phase, analysis, design, implementation, maintenance, stage gate, sign-off, deliverable, waterfall, iterative, agile, tailoring, standard process.**
