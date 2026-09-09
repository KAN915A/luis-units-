# Unit 3 — Planning and Management of Computing Projects

Pearson BTEC Level 3 Extended Diploma in Computing • **Unit code 31760H** • Externally assessed exam.

## Key Info

- **Course:** BTEC Level 3 Extended Diploma in Computing
- **Status:** Main / priority unit
- **Target grade:** Distinction
- **Assessment:** Task-based exam. **Part A** (pre-release scenario given to the centre before the window — read, research, prepare notes on it). **Part B** (supervised exam under Pearson exam conditions, answered in reference to the scenario).
- **Exam window:** 1st week of January
- **Study partner:** Luis

> Notes below scaffold the **published unit content**. As lessons cover each area and the Part A pre-release lands, we drop scenario-specific notes into each section.

## Mark Scheme — Assessment Objectives (AOs)

The exam is graded against four AOs. Distinction depends on hitting **AO3 and AO4**, not just AO1/AO2.

| AO  | What it tests                                                            | Command words                                                             | How to write for it                                                                       |
| --- | ------------------------------------------------------------------------ | ------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------- |
| AO1 | Knowledge & understanding of project planning and management             | identify, state, describe, outline, define                                | Give correct terms and short factual definitions.                                         |
| AO2 | Apply knowledge to the given small computing project scenario            | apply, use, produce, complete, calculate, draw                            | Use the scenario details. Do **not** answer in general — always tie back to the brief.    |
| AO3 | Analyse information, causes, consequences, options in the scenario       | analyse, examine, compare, explain the impact, why                        | Break the issue down. Show cause → effect. Link factors together.                         |
| AO4 | Evaluate and make justified judgements / recommendations                 | evaluate, justify, recommend, assess, to what extent, discuss             | Weigh options, use scenario evidence, give a clear conclusion with reasoning.             |

### Distinction-level checklist (use for every long-answer question)

- [ ] Correct technical vocabulary (AO1)
- [ ] Directly refers to the scenario / stakeholders (AO2)
- [ ] Explains cause and effect, trade-offs, dependencies (AO3)
- [ ] Reaches a **justified judgement or recommendation** (AO4)
- [ ] Considers cost, time, quality, scope, risk, stakeholders
- [ ] Ends with a clear conclusion — no fence-sitting

## Unit Content — the full syllabus

The Pearson spec organises Unit 3 into **three learning aims (A, B, C)**. Everything the exam can ask sits inside one of these.

---

### A — Initiation stages of a small computing project

**A1 — Reasons for undertaking a project**
- Business need / opportunity (new market, competitive pressure, cost saving)
- Legal, regulatory or compliance requirement
- Replacing an obsolete system
- Improving efficiency, security, user experience
- Responding to a client request

**A2 — Feasibility of a project**
- Technical feasibility — can it be built with available tech/skills?
- Economic feasibility — cost vs benefit, ROI, payback period
- Legal feasibility — GDPR, licensing, IP
- Operational feasibility — will the users adopt it, does it fit workflows?
- Scheduling feasibility — can it be delivered in time?

**A3 — Project planning methodologies**
- **Waterfall** — sequential phases, heavy up-front documentation.
- **Agile** — iterative, working software each sprint, welcomes change.
  - **Scrum** — sprints, product backlog, daily stand-ups, roles (PO, SM, Dev).
  - **Kanban** — flow-based, WIP limits, continuous delivery.
  - **XP (Extreme Programming)** — pair programming, TDD, refactoring.
- **PRINCE2** — process-based, seven principles/themes/processes, stage gates.
- **Hybrid** approaches (e.g. Waterfall for hardware, Agile for software).

**A4 — Justifying choice of methodology (AO4 territory)**
Compare methodologies against the scenario: project size, requirement stability, client involvement, risk tolerance, team experience, regulatory context.

---

### B — Planning a small computing project

**B1 — Project planning tools**
- **Work Breakdown Structure (WBS)** — decompose deliverables into tasks.
- **Gantt chart** — tasks along a timeline, shows durations and dependencies.
- **Network diagram (PERT / CPM)** — nodes/arrows, computes the **critical path** (longest dependency chain — the earliest possible finish).
- **Milestone charts** — key checkpoint dates only.
- **RACI matrix** — Responsible / Accountable / Consulted / Informed per task.
- **Kanban board** — To do / Doing / Done, with WIP limits.

**B2 — Project documentation**
- **Business case** — why do the project, options, expected benefits.
- **Project Initiation Document (PID)** — scope, objectives, deliverables, roles, governance.
- **Requirements specification** — functional and non-functional requirements.
- **Risk register / risk log** — risk description, likelihood, impact, owner, mitigation.
- **Issue log** — issues actually occurring (vs risks which are potential).
- **Communication plan** — who gets what info, how often, in what form.
- **Change request / change log** — proposed changes with impact assessment.
- **Project plan** (schedule + resources + budget).

**B3 — Resources, budgeting and scheduling**
- Human resources (roles, skills, availability).
- Physical/tech resources (hardware, licences, cloud services).
- Cost estimation techniques (analogous, parametric, bottom-up).
- Budget contingencies.
- Scheduling — dependencies (finish-to-start etc.), float/slack, resource levelling.

**B4 — Stakeholders**
- Identify stakeholders (client, users, sponsor, dev team, suppliers, regulators).
- Stakeholder analysis — power/interest grid.
- Engagement strategy per group.

**B5 — Risks and mitigation**
- Types: technical, financial, schedule, resource, security, legal.
- Assess: likelihood × impact.
- Response: avoid, transfer, mitigate, accept.
- Contingency plans.

---

### C — Managing a small computing project

**C1 — Monitoring and control**
- Tracking progress vs the plan (Gantt update, burndown).
- Milestones and Key Performance Indicators (KPIs).
- Reporting to stakeholders — status reports, dashboards.
- Escalation paths.

**C2 — Managing quality**
- Quality plan (acceptance criteria, standards).
- Reviews, walkthroughs, inspections.
- Testing (unit, integration, system, UAT).
- Defect logging and rework.

**C3 — Managing change**
- Change request process: log → assess impact (time/cost/scope/risk) → approve/reject → update baseline.
- Version control on documentation and code.
- Scope creep — spot it early, refuse un-approved changes.

**C4 — Managing risks and issues during delivery**
- Regular risk-log reviews.
- Turning realised risks into issues.
- Root-cause analysis, corrective action.

**C5 — Project closure and post-project review**
- Handover to client / operations.
- Final documentation, training, warranty.
- Post-Implementation Review (PIR) / lessons learned.
- Measure benefits realised vs business case.

---

## Common exam-scenario clues (from past series patterns)

Small computing project scenarios usually mention:
- A **small client** with limited budget/skills → biases toward **Agile** and low-ceremony methods.
- A **fixed regulatory deadline** → biases toward **Waterfall/PRINCE2** with strict stage gates.
- **Unclear requirements / new market** → **Agile**, prototype-first.
- **Distributed team / limited meeting time** → strong **communication plan** matters.
- **Legacy replacement** → migration risk, dual-running, data integrity.

## Note Template (used for every lesson topic)

```markdown
### Topic: <name>  •  Area: <A/B/C>  •  Date: <DD/MM/YYYY>

**AO1 — Definition / key facts**
- ...

**AO2 — How it applies to a small computing project scenario**
- ...

**AO3 — Analysis (why it matters, causes/effects, trade-offs)**
- ...

**AO4 — Evaluation (strengths, weaknesses, when to use, justified recommendation)**
- ...

**Exam-answer phrases to use**
- ...

**Common trap / examiner feedback**
- ...
```

## Part A — Pre-release scenario (fills in when released)

<!-- When the January exam Part A is released, drop the scenario summary
     here: client, project, constraints, stakeholders, key risks.
     Every lesson topic below should then be tied back to this scenario. -->

## Lesson Notes

<!-- New lesson entries get added below using the template above -->
