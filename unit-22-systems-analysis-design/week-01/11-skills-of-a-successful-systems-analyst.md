# Week 1 — Topic 11: Skills of a Successful Systems Analyst (Part 1 — Managerial + Interpersonal)

**Source:** `Week_One_Lecture_For_Software_Analysis_and_Design.pdf`, page 31 of 47.
**Learning Aim:** A — Investigate systems analysis and design methodologies.
**Criteria:** P / M / D.

> Pairs with Topic 10 (the analyst's role). Topic 10 said *what* the analyst does; Topic 11 says *what skills they need to do it well*. This slide covers the first two skill families — **Managerial** and **Interpersonal**. The remaining skill families are on later slides.

## Slide content (verbatim)

**Skills of a Successful Systems Analyst**

- **Managerial**
  - Ability to manage projects, resources, risk and change.
- **Interpersonal**
  - Effective written and oral communication skills.

---

## Pass evidence — describe / identify (P)

### Managerial skills

The analyst must be able to manage:
- **Projects** — plan phases, sequence tasks, meet milestones (Unit 3 A5 project life cycle, C1 scheduling).
- **Resources** — people, equipment, materials, budget (Unit 3 C2).
- **Risk** — identify, assess (impact × probability), plan responses, monitor (Unit 3 A3, C3).
- **Change** — handle change requests, assess impact on scope/cost/time, get approval (Unit 3 D4).

Even when the analyst is not the project manager, they collaborate with the PM and must think in these four dimensions.

### Interpersonal skills

- **Written communication** — requirements documents, meeting minutes, reports, emails, the PID (Unit 3 B4).
- **Oral communication** — interviews, workshops, presentations to sponsors, walkthroughs with users and developers.
- **Effective** = appropriate for the audience (Unit 3 A6), conveys the intended meaning, uses fluent English + correct technical language, sets the right tone.

## Merit evidence — analyse / compare (M)

### Why managerial skills matter to the analyst

- Analysis work is scheduled, budgeted and reviewed like any other work — miss the schedule and downstream design/build slips too.
- Resource awareness stops "gold-plating" — an analyst who ignores cost produces beautiful requirements the project cannot afford.
- Risk sensitivity turns assumptions (Unit 3 B3) into logged risks with owners.
- Change discipline stops "just add this one thing" requests eroding scope during analysis.

### Why interpersonal skills matter — the analyst's real job is translation

- Users describe their world in **business language**; developers need **technical specifications**. The analyst is the two-way translator between them.
- A brilliant model that nobody can read is worthless — communication skill is what turns a diagram into a shared understanding.
- Oral: interviews and workshops are where requirements are *gathered*. Written: PID, requirements spec, DFDs and ERDs are where they are *baselined*.
- Poor interpersonal skill is the single biggest cause of missed requirements → rework → cost overrun.

### Compare the two families

| Skill family     | What it protects the project from                                | Failure mode when weak                                      |
| ---------------- | ---------------------------------------------------------------- | ----------------------------------------------------------- |
| Managerial       | Missed deadlines, blown budget, unmanaged risk, uncontrolled change | Analysis phase overruns; scope creep; late risk surprises   |
| Interpersonal    | Misunderstood requirements, alienated stakeholders               | Delivered system doesn't match what the users needed        |

### Link back to earlier topics

- **Unit 3 A5 (project life cycle):** managerial skills operate at every stage — conception, definition, planning, execution, closure.
- **Unit 3 A6 (professionalism):** the interpersonal bullet is essentially the A6 communication requirements applied to the analyst's day-to-day.
- **Unit 3 B2 (stakeholders):** the analyst uses interpersonal skills to elicit requirements from *every* stakeholder group, not just the client.
- **Unit 3 C5 (communications) + Unit 3 B4 (PID communication plan):** written outputs the analyst produces feed straight into these.
- **Topic 10 (role):** interpersonal skill is how the analyst pulls the *People* lever; managerial skill is how they support the whole project.

---

## Distinction evidence — evaluate / justify (D)

**Strengths of a managerially + interpersonally strong analyst:**
- Analysis phase finishes on time and on budget → project stays on plan.
- Requirements are unambiguous, testable, agreed → fewer defects at UAT (Unit 3 D5), fewer change requests (Unit 3 D4).
- Sponsor confidence stays high → project keeps its priority in the organisation (Unit 3 A4).
- The system that gets delivered is one the users actually *use* — the People lever (Topic 10) is pulled deliberately.

**Weaknesses / risks in this dimension:**
- Managerial focus without interpersonal skill → punctual delivery of the *wrong* requirements.
- Interpersonal focus without managerial skill → warm relationships but a slipped analysis phase.
- Written skill without oral skill → excellent documents no one reads.
- Oral skill without written skill → verbal agreements no one can baseline.

**Justified judgement (the D-level move):**

A successful analyst evidences **both families concurrently on every deliverable**:
- Every requirements document has a **clear owner, deadline, and change-control note** (managerial), and is **written to the audience's reading level with correct technical vocabulary** (interpersonal).
- Every stakeholder interview is **scheduled, minuted, and followed up in writing** (managerial + interpersonal together).

**Recommend** that the analyst adopts three practical habits in the assignment:
1. Keep a **risk / assumption log** open from day one of analysis (managerial).
2. **Write minutes within 24 hours** of every interview or workshop (managerial + interpersonal).
3. **Walk the model back to the client** — read the ERD and DFD out loud with them and correct on the spot (interpersonal, and cheaper than fixing it at UAT — Unit 3 C4 defect removal).

These operationalise the two skill families and evidence them for a marker; abstract claims of "good communication skills" score less than concrete practices.

---

## Applied to a scenario — GreenLeaf Cafés OOS

**Managerial:**
- Analysis phase planned for 2 weeks with milestones: requirements draft (day 5), stakeholder review (day 8), signed-off spec (day 10).
- Risk log opened at kick-off; top risk "menu data not available in CSV until day 6" logged with the IT Manager as owner.
- Every change to the requirements after day 8 goes through a change request (Unit 3 D4).

**Interpersonal:**
- One-hour interviews with: Operations Director (sponsor), IT Manager (client), 2 branch managers, 3 counter staff, 1 barista, 3 sample customers.
- Weekly written update to sponsor + client (per Unit 3 C5 communication plan).
- Walkthrough of the DFD + ERD with the IT Manager on day 8 — annotated live, changes captured in minutes.
- Language matched: prose + screenshots for branch staff; ERD + DFD + data dictionary for the IT Manager.

## Exam-answer phrases to use

- "A successful systems analyst combines managerial skill — the ability to manage projects, resources, risk and change — with interpersonal skill, effective written and oral communication."
- "Managerial ability keeps the analysis phase on time and on budget; interpersonal ability ensures the requirements produced are the ones the users actually need."
- "Effective written communication for the systems analyst includes the requirements specification, meeting minutes and the PID; effective oral communication covers interviews, workshops and stakeholder walkthroughs."
- "Weakness in either family leads to a specific failure mode: managerial weakness overruns the analysis phase, interpersonal weakness produces requirements no one recognises."

## Common trap / examiner feedback

- Listing skills without saying **what each skill protects the project from** — generic answers score at Pass level, not Distinction.
- Confusing "communication skills" with "being friendly" — the spec says *effective written and oral*, which is a specific professional competence (A6 in Unit 3).
- Treating managerial skill as "the PM's problem" — the analyst uses managerial skill inside the analysis phase, even when a separate PM exists.
- Writing about only one of the two families when the question asks about both.

## Key vocabulary

**Managerial skills, project management, resource management, risk management, change management, interpersonal skills, written communication, oral communication, requirements elicitation, walkthrough, minutes, audience-appropriate.**
