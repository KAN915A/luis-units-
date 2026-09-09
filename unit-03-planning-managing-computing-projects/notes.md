# Unit 3 — Planning and Management of Computing Projects

Pearson BTEC Level 3 National Extended Diploma in Computing • Specification Issue 8 (April 2021) • Externally assessed exam.

## Key Info

- **Course:** BTEC Level 3 Extended Diploma in Computing
- **Status:** Main / priority unit
- **Target grade:** Distinction
- **Assessment:** Task-based exam. **Part A** (pre-release scenario for research/preparation) → **Part B** (supervised exam, answered against the scenario).
- **Exam window:** 1st week of January
- **Study partner:** Luis

## Grade Descriptors (from the spec — the actual bar)

**Level 3 Pass** — Uses knowledge of project planning/management concepts and problem-solving to document requirements. Coverage is limited in scope and may be incomplete. Uses documentation to a minimal level of acceptability. Evaluation is limited.

**Level 3 Distinction (our target)** — **Evaluates the problem**, develops a **detailed and complex documented solution** that **effectively meets ALL scenario requirements**, shows **in-depth understanding** of documentation and how it produces an effective solution, and **evaluates the solution to make justified recommendations** on development and future actions.

### The four verbs that separate Pass from Distinction

| Pass writes                    | Distinction writes                                                          |
| ------------------------------ | --------------------------------------------------------------------------- |
| Describes what X is            | **Evaluates** whether X fits the scenario                                    |
| Fills in a template            | Produces a **detailed and complex** solution                                 |
| Covers most of the requirements | Meets **all** scenario requirements                                          |
| Says which option to pick      | **Justifies** the choice against alternatives + future recommendations       |

---

## A — Project management concepts

### A1 Costs and timescales

**Definitions / key facts**
- **Project budget** — the total financial resource authorised for the project (money for staff, equipment, licences, contingency).
- **Milestones** — significant checkpoints with a date but no duration (e.g. "PID approved", "UAT complete"). Used to prove progress to stakeholders.
- **Deadlines** — the latest date a task or deliverable must be finished by.
- **Interim reviews** — planned check-ins during the project to compare actual vs planned cost, time and quality, and take corrective action.

**Applied to a scenario**
- Break the client budget into staff cost + equipment/licences + contingency (typically 10–15%).
- Place milestones at natural handover points (requirements signed off, prototype delivered, UAT passed).
- Schedule interim reviews after each milestone so slippage is caught early.

**Analysis — why it matters**
- Without milestones the project has no visible progress → sponsor loses confidence → priority drops.
- Missing an interim review means variance compounds — one week of hidden slip turns into three.
- Under-costed budget forces cuts to testing/training later, damaging quality.

**Evaluation — justified judgement**
- Fixed-price + fixed-deadline projects need **tight milestone spacing** (every 1–2 weeks) even if it adds admin cost, because early warning is worth more than the admin overhead.
- For a small client with a small budget, use fewer, meaningful milestones tied to their business events (e.g. new tax year) rather than internal ones.

**Exam phrases to use**
- "This milestone acts as a control point at which…"
- "Setting the review after week 4 gives the project manager time to…"
- "Including a 15% contingency in the budget is justified because…"

**Common trap**
- Confusing milestones with tasks. A milestone has zero duration.

---

### A2 Quality and deliverables

**Definitions / key facts**
- **ISO/IEC 25010:2011** — software quality standard. Eight product-quality characteristics: functional suitability, performance efficiency, compatibility, usability, reliability, security, maintainability, portability.
- **W3C** — web standards body (HTML, CSS, WCAG accessibility). Compliance improves cross-browser support and accessibility.
- **SMART objectives** — Specific, Measurable, Achievable, Realistic, Time-bound.
- **Functional requirements** — what the system must *do* (log in, print invoice, calculate VAT).
- **Non-functional requirements** — how well it must do it (response < 2s, 99.5% uptime, GDPR-compliant, accessible to WCAG 2.1 AA).
- **Product description / product breakdown structure (PBS)** — hierarchical breakdown of the *deliverables* (the "what"), whereas a WBS breaks down the *work* (the "how").

**Applied to a scenario**
- Take a vague client wish ("nice website") and rewrite as SMART: "The homepage loads in under 2 seconds on 4G by 30 Nov, tested with Chrome DevTools."
- List functional vs non-functional against the brief.
- Draw a PBS: top box = "New booking system", children = website, database, admin portal, training material.

**Analysis — why it matters**
- SMART targets remove ambiguity → measurable success at closure (feeds E2).
- ISO/IEC 25010 gives an **external benchmark** the client can hold you to — protects both parties.
- Missing non-functional requirements is the classic cause of "the software works but nobody uses it".

**Evaluation — justified judgement**
- For a public-facing website, W3C + WCAG compliance is not optional — legal risk under the Equality Act. Recommend building accessibility into the design phase, not bolting on at the end (cheaper).
- ISO/IEC 25010 in full is heavy for a small project — use it selectively (e.g. focus on usability + security if it's a customer portal handling personal data).

**Exam phrases**
- "This is a functional requirement because it describes what the system must do…"
- "Rewriting the objective as SMART allows the project manager to…"

**Common trap**
- Writing "the system must be fast" — not measurable, not SMART. Give a number.

---

### A3 Risk

**Definitions / key facts**
- **External risks** — outside the project team's control (supplier failure, regulation change, exchange rate, cyber attack).
- **Internal risks** — inside the project (staff illness, skill gap, scope creep, tool failure).
- **Risk management cycle:**
  1. **Identify** — brainstorm, checklists, lessons learned from past projects.
  2. **Assess severity** — 3-point scale for **impact** (1 low, 2 medium, 3 high) × 3-point scale for **probability** → severity score 1–9.
  3. **Plan response** — **Accept** (low severity), **Contingency** (fallback plan), **Avoid** (redesign to remove the risk).
  4. **Monitor and control** — review risk log at every checkpoint.
- **Issue** — a risk that has actually happened. Handled using the contingency plan.

**Applied to a scenario**
- Pull risks straight from the brief: tight deadline → schedule risk; single supplier → dependency risk; new tech to team → skills risk.
- Score each: e.g. "supplier late" impact 3, probability 2, severity 6 → red.
- Attach a response: "Order 2 weeks early, dual-source hardware" (avoid + contingency).

**Analysis — why it matters**
- Impact × probability lets you *rank* risks — you can only give real attention to a few, so this focuses budget/time on the ones that would actually hurt.
- A red risk with no contingency is a self-inflicted issue.

**Evaluation — justified judgement**
- Recommend a live risk register reviewed weekly, not a document produced once at kick-off and forgotten — the latter is the most common examiner-flagged weakness.
- For an SME client, keep the register short (top 8–10 risks) rather than exhaustive — a 40-risk register nobody reads is worse than a 10-risk one everyone knows.

**Exam phrases**
- "The severity of this risk is 6 (impact 3 × probability 2), classifying it as amber, so contingency planning is required because…"
- "This is an external risk because the project team has no direct control over…"

**Common trap**
- Confusing risk (potential) with issue (already happened). Wrong term = lost marks.

---

### A4 Benefits

**Definitions / key facts**
- Business benefits: saving money, maintaining/increasing profits, improving services, growing the business, increasing market share, improving productivity.
- **Return on Investment (ROI)** = (net benefit / cost) × 100%. Used to **justify** the project up front and **forecast** its success.

**Applied to a scenario**
- Map each project outcome to a business benefit (new booking system → saves 2 admin hours/day → £X saved/year → productivity + cost saving).
- Compute expected ROI: e.g. cost £30k, expected annual saving £12k → payback ~2.5 years, 3-year ROI = 20%.

**Analysis — why it matters**
- Sponsor authorises the project because of expected benefits. If benefits aren't quantified, priority slips when a shinier project appears.
- ROI is the yardstick used at E1/E2 to judge whether the project *succeeded* — not just delivered.

**Evaluation — justified judgement**
- Recommend measuring benefits at 3, 6 and 12 months post-launch, not just at closure — many benefits (increased market share, productivity) only appear over time.
- Where benefits are intangible (staff morale, brand), use a proxy metric (e.g. staff turnover %) rather than dropping them from the case — otherwise they get ignored.

**Exam phrases**
- "The forecast ROI of 20% over three years justifies the project because…"
- "This delivers an improved service benefit as measured by…"

---

### A5 The project life cycle

**Definitions / key facts**
Standard five-then-review structure:
1. **Conception and start-up** — project mandate, client requirements, feasibility study.
2. **Definition** — set up team, produce **PID**.
3. **Planning** — timescales, costs, quality plan, risk plan.
4. **Launch and execution** — carry out the plan, monitor, check progress.
5. **Closure** — handover, UAT, disband team.
6. **Post-project evaluation** — review against success criteria (SMART).

**Applied to a scenario**
- Match each event in the scenario to a life-cycle stage: "the client asks for a website" → conception; "PID signed" → definition ends; "UAT complete" → closure begins.

**Analysis — why it matters**
- Skipping conception (no feasibility) = wasted budget on projects that shouldn't have started.
- Skipping post-project evaluation = no lessons learned = same mistakes next project.

**Evaluation**
- Recommend each stage gate needs sponsor sign-off before moving on — stops "definition creep" where the team starts building before scope is fixed.

---

### A6 Professionalism

**Definitions / key facts**
- **APM** (Association for Project Management) — UK's chartered project management body. Code of professional conduct.
- **BCS** (British Computer Society) — chartered institute for IT. Its Code of Conduct covers public interest, professional competence, duty to profession, duty to employer/client.
- **PMI** (Project Management Institute) — global body; publishes PMBOK and a Code of Ethics (responsibility, respect, fairness, honesty).
- **Communication and presentation** must be: audience-appropriate, meaning-preserving, graphics-supported, fluent English + correct technical terms, appropriate tone.

**Applied to a scenario**
- Following BCS code = declaring a conflict of interest, protecting client data, not overstating skills.
- Reports to sponsor: formal tone, executive summary; developer standups: informal, technical.

**Analysis — why it matters**
- A breach damages professional reputation and can lead to legal or contractual consequences.
- Poor communication is the single biggest cause of project failure (misunderstood requirements, missed changes).

**Evaluation**
- Recommend adopting BCS code as team baseline plus a documented communication style guide for the project — cheaper than fixing a compliance breach or a miscommunicated requirement.

---

## B — Starting up a computing project

### B1 Interpreting the business case

**Definitions / key facts**
The business case drives the project. It contains: **reasons**, **options considered**, **expected benefits**, **timescale + major milestones**, **budget available**, **major risks**.

**Applied to a scenario**
- Extract each of the six elements from the client brief and quote them back.
- If an element is missing (e.g. no options considered), flag it — a distinction answer catches that.

**Analysis**
- Options considered is what separates a *decided* project from a *justified* project. Without alternatives listed, you can't prove the chosen path is best.

**Evaluation**
- Recommend the PM re-reads the business case at every stage gate. If reality no longer matches (benefits shrunk, costs ballooned), escalate — don't push on out of momentum. This is the classic distinction move: linking business case back into monitoring (D2).

---

### B2 Stakeholders

**Definitions / key facts (memorise the roles)**
- **Project manager** — defines, plans, controls, leads.
- **Technical teams** — perform the project tasks.
- **Team managers** — follow company policies, provide resources.
- **Project sponsor** — provides authority, guidance, maintains project priority.
- **Client** — provides product requirements and project finance.
- **Suppliers** — provide materials/equipment.
- **Contractors** — specialist work.
- **General public** — may be affected.

**Applied to a scenario**
- Draw a stakeholder table from the brief: name → role → responsibility → communication frequency.

**Analysis**
- Sponsor and client are often confused: sponsor = internal authority; client = pays for it. In some scenarios they're the same person, in others not.
- Missing a stakeholder in planning = missing requirements = late scope changes.

**Evaluation**
- Recommend a **power/interest grid** (although not named in the spec, it's a good tool): high power + high interest → manage closely (client, sponsor); low both → monitor. Justifies communication effort allocation.

---

### B3 Identifying assumptions and constraints

**Definitions / key facts**
- **Assumptions** — things you take as true because you can't confirm them yet. Treated as **low-level risks** in the risk log.
- **Constraints** — hard limits the project must live within:
  - deadlines / time available
  - funds (including contingency)
  - staff availability
  - equipment availability
  - technical expertise in the team
  - technology limits

**Applied to a scenario**
- Pull constraints straight from the brief (deadline, budget, "team of three developers").
- Every "we assume the API will be available" is an assumption → add to risk log.

**Analysis**
- An assumption that turns false becomes a risk realised = issue. Documenting them up front means when they break, it's not a surprise.
- Constraints often conflict — cheap + fast + high quality: pick two. The PM's job is to make that trade-off explicit.

**Evaluation**
- Distinction answer: when constraints conflict, recommend which to relax and justify (e.g. "extending deadline by two weeks is a lower business impact than cutting testing scope, therefore recommend a two-week extension").

---

### B4 The Project Initiation Document (PID)

**Definitions / key facts — memorise this list**
A PID contains:
- document details
- approvals
- distribution
- purpose of PID
- project background (fit in organisation)
- objectives (as SMART)
- **scope** — what IS and what IS NOT in
- business case
- assumptions
- constraints
- risk management strategy
- deliverables
- project quality strategy
- stakeholders
- project management team structure (org chart with roles)
- project plan
- communication plan
- document management

**Applied to a scenario**
- The PID is your one-stop reference. In the exam, if asked to "produce a section of a PID for X", write **the section heading, then bullet content, all traceable to scenario facts**.

**Analysis**
- The PID is the **contract** between PM and sponsor. Once approved, changes go through change management (D4) — not "I'll just add it".
- Scope exclusions ("what is NOT included") are as important as inclusions — they prevent scope creep.

**Evaluation**
- Recommend a **living PID** — updated at each stage gate under version control. A frozen PID becomes fiction. Justify: reduces disputes, keeps sponsor informed, feeds directly into E2 review.

**Exam phrases**
- "Including scope exclusions in the PID protects the project against…"
- "The communication plan section of the PID is essential because…"

---

## C — Project planning

### C1 Scheduling and milestones

**Definitions / key facts**
- **Work Breakdown Structure (WBS)** — decompose the *work* hierarchically. Leaves = tasks that can be estimated and assigned.
- **Task precedence** — serial (B needs A finished) vs parallel (A and C independent).
- **Critical Path Analysis (CPA)** — longest dependency chain from start to finish. Any slip on the critical path slips the project. Non-critical tasks have **float/slack** = spare capacity.
- **Gantt chart** — timeline bar chart, tracks tasks + dependencies + progress against baseline.

**Applied to a scenario**
- Break the deliverables into ~10–20 tasks. Estimate durations. Identify precedence. Draw a Gantt or network diagram. Highlight the critical path.

**Analysis**
- Ignoring the critical path = optimising the wrong tasks. Speeding up a non-critical task saves zero project time.
- Serial tasks that could have been parallelised = wasted schedule.

**Evaluation**
- For a small team, **project planning software** (MS Project, GanttProject, Trello with dates) beats a spreadsheet Gantt because it recalculates dependencies automatically. For a very small project, a spreadsheet is proportionate and cheaper.

**Exam phrases**
- "Task X sits on the critical path, so any slippage will delay the project completion date."
- "Task Y has 3 days of float, meaning it can start up to 3 days later without impacting…"

---

### C2 Resources and budgeting

**Definitions / key facts**
- **Resource allocation** — assign people, equipment, materials to tasks.
- **Pro rata costing** — cost proportional to time used (e.g. developer £300/day × 5 days = £1,500).
- **Estimation techniques:**
  - **Bottom-up** — estimate each task, sum. Most accurate, most effort.
  - **Parametric** — use a formula (e.g. function points × cost per point). Fast; needs historical data.
  - **Top-down** — start with a total, allocate down. Fast; least accurate.
- **Budget planning + cash flow** — when money goes out, when it comes in. Prevents cash-flow crisis mid-project.
- **Tools** — spreadsheets, project planning software.

**Applied to a scenario**
- Use bottom-up for detailed planning, top-down for the initial pitch, parametric for a rough sanity check.

**Analysis**
- Over-estimation loses the bid; under-estimation loses money. The estimation choice must match how much is known.
- Cash-flow matters even when the total budget is fine — a positive-total, negative-mid-project cash flow can kill a small firm.

**Evaluation**
- Recommend bottom-up as the primary technique once the WBS is done, cross-checked by parametric (function points) as a sanity check. Justify: catches order-of-magnitude estimation errors that bottom-up misses when a task is forgotten.

---

### C3 Risk management strategy

**Definitions / key facts**
- Risk analysis: **severity = impact × probability**.
- **Risk matrix** — green (low, accept/monitor) / amber (medium, contingency required) / red (high, avoid or heavy contingency).
- **Contingency planning** for major (red/amber) risks.
- **Documenting risks** with a standard template (ID, description, impact, probability, severity, owner, response, status).
- **Issues log** — records risks that have happened; cross-references the risk matrix.

**Applied to a scenario**
- Build a risk register table from the brief. For each red risk, write the contingency in words ("If supplier misses week-4 delivery, switch to backup supplier X, cost +£800, delay +3 days").

**Analysis**
- Risks change over time — one that was red in planning may go green after mitigation. The matrix must be re-scored, not frozen.
- The issues log without cross-referencing to risks is disconnected — you lose the ability to check whether a risk you predicted actually fired (feeds lessons learned).

**Evaluation**
- Recommend risk owners named per risk (not "the team"), reviewed weekly, escalated to sponsor when a red risk trends worse. Justify: named ownership triples the chance of mitigation being executed.

---

### C4 Quality management

**Definitions / key facts**
- **Defect removal:**
  - **Desk checking + proofreading** — read your own work carefully.
  - **Peer review** — a colleague reviews.
  - **Inspection / walkthrough** — formal group review to a checklist.
- **Testing strategy:**
  - **Unit test** vs unit specification.
  - **Integration test** vs designs.
  - **System test** vs requirements.
  - **Regression test** — checks a change didn't re-break something already working.
- Use of quality standards (ISO/IEC 25010, W3C) as an **external benchmark**.

**Applied to a scenario**
- Match each defect-removal technique to when it's used: desk check during development, peer review before commit, walkthrough before UAT.
- Match testing levels to deliverables: unit → each function; integration → modules together; system → whole system against the business requirements.

**Analysis**
- Cost of fixing a defect grows ~10× per stage it survives (design → build → test → live). Early defect removal (desk check, peer review) is the cheapest quality investment.
- Regression testing is what makes changes safe in D4 — without it, every fix risks introducing two new bugs.

**Evaluation**
- Recommend automated regression tests where possible: high setup cost, but pays back after ~3 change cycles. For a small project with few changes, manual regression may be more proportionate — justify per scenario.

---

### C5 Communications

**Definitions / key facts**
- Methods: meetings, memos/notices, phone/video, email/IM, forums/discussion groups, collaborative tools (Teams, Slack, shared drives).
- **Communication plan** — frequency, target audience, agendas + minutes, comms/presentation requirements.

**Applied to a scenario**
- Build a table: audience → what they need → method → frequency (e.g. sponsor → status → email + monthly meeting; devs → tasks → daily stand-up).

**Analysis**
- Wrong medium = ignored message. A technical bug list mailed to the sponsor as email = ignored. A budget overrun buried in a Slack channel = missed.
- Frequency too high = ignored (fatigue); too low = surprises.

**Evaluation**
- Recommend written + verbal for critical decisions: verbal for buy-in, written for the record. Justify: verbal only = "you never told me"; written only = missed nuance.

---

## D — Executing and monitoring a project

### D1 The waterfall software development life cycle model

**Definitions / key facts**
Sequential stages:
1. **Requirements analysis** — what the system must do.
2. **Design** — how it will do it.
3. **Construction and testing** — build and unit/integration test.
4. **Acceptance testing** — client checks against requirements.
5. **Implementation and delivery** — deploy.

**Applied to a scenario**
- Map each planned activity in the brief to a waterfall stage.
- The waterfall stages inform the WBS at C1.

**Analysis**
- Strengths: clear stage gates, easy to plan up front, works when requirements are stable.
- Weaknesses: expensive to change once past a stage; late user feedback (only at acceptance testing) means late surprises.

**Evaluation**
- Waterfall fits scenarios with fixed regulatory scope, well-understood requirements, and low expected change (payroll upgrade, compliance system). Poor fit for a startup MVP where the requirements will move — but the spec asks about waterfall specifically here, so justify its use for the given scenario.

---

### D2 Monitoring and tracking progress

**Definitions / key facts**
- **Project baseline** — the approved plan (scope, schedule, budget) at kick-off. Everything is measured against it.
- **Variance** — actual − baseline. Positive schedule variance = ahead; negative = behind.
- **Checkpoint reports** — records what was achieved by a milestone (also feeds sponsor comms).
- Monitoring risks + managing issues (feeds A3/C3).
- Recording **quality management activity** — which reviews/tests were done, results, sign-off.

**Applied to a scenario**
- At each checkpoint: compare Gantt actual vs baseline, compute schedule + cost variance, update risk log, log issues, write a checkpoint report.

**Analysis**
- Variance without action = data. The point is to **decide** — rebase, add resource, cut scope, escalate.
- Recording quality activity is the audit trail — protects the PM in disputes.

**Evaluation**
- Recommend a one-page weekly checkpoint (RAG status: red/amber/green per objective + top-3 risks + variance number) rather than a 20-page monthly report. Justify: read every week beats read never.

---

### D3 Managing issues

**Definitions / key facts**
- **Categorising issues:**
  - **Request for change** — stakeholder wants something different.
  - **Off-specification** — deliverable doesn't meet spec.
  - **Problem or concern** — anything else blocking progress.
- **Management by exception** — the PM only escalates *unforeseen* issues (outside agreed tolerances) to the sponsor, with potential impact. Frees the sponsor from noise.
- **Lessons learned** recorded as issues are resolved.

**Applied to a scenario**
- Route each event in the brief: user asks for extra field → request for change; missing button that was speced → off-specification; supplier gone quiet → problem/concern.

**Analysis**
- Miscategorising an issue routes it wrongly. A "request for change" pushed through as "just a fix" = uncontrolled scope creep = D4 breakdown.
- Management by exception only works if tolerances (±10% cost, ±1 week schedule) are agreed in the PID.

**Evaluation**
- Recommend agreed tolerances in the PID + a documented escalation path. Justify: makes management-by-exception real, not just a phrase.

---

### D4 Change management

**Definitions / key facts**
- Impact assessed against: entire project vs stage(s) only.
- **Change of scope** affects: requirements/quality, costs, timescales — the classic triangle.
- Development changes — modifications to designs.
- Faults — analysis/design defects, software errors.
- **Change management process:**
  1. Change request submitted by project manager.
  2. Review by management team.
  3. Assess feasibility of the change of scope.
  4. Approval or rejection.
  5. Implementation by project team.

**Applied to a scenario**
- Client asks for a new report — PM raises a change request, includes time/cost/quality impact, mgmt team decides, if approved: rebase plan (D2), if rejected: log decision.

**Analysis**
- Uncontrolled changes = scope creep = missed deadlines/budget.
- Rejected changes must still be **recorded** — a "no" today may be a "yes" next quarter.

**Evaluation**
- Recommend a change board (PM + sponsor + tech lead) meeting weekly rather than ad-hoc email approvals. Justify: forces impact-thinking, cuts email tennis, keeps a decision log.

---

### D5 Implementation strategy

**Definitions / key facts**
Delivery options (choice depends on size + complexity):
- **Direct changeover** — old off, new on, one date. Cheap, fast, highest risk (no fallback).
- **Parallel running** — old + new together for a period. Safe, expensive (double work, double cost).
- **Pilot changeover** — new system in one team/site first. Good compromise, limited risk exposure.
- **User acceptance testing (UAT)** — client tests against requirements; formal sign-off before go-live.

**Applied to a scenario**
- Payroll system (critical, monthly cycle) → parallel run for one cycle.
- New internal booking tool (low risk if it fails) → direct changeover after UAT.
- Multi-branch retail system → pilot in one branch first.

**Analysis**
- Direct changeover with weak UAT = disaster on day one.
- Parallel running is safest but doubles operational cost for the overlap.

**Evaluation**
- Recommend the strategy that matches business risk, not developer convenience. Justify with cost of failure vs cost of the strategy.

**Exam phrases**
- "Parallel running is justified here because a payroll error would have severe financial and legal impact…"
- "Pilot changeover reduces the blast radius of any defect to one branch…"

---

## E — Project closure and post-project review

### E1 Closing a live project

**Definitions / key facts**
- Move into operation and maintenance.
- Assess benefits delivered + plan a follow-up review.
- Close down risk log, issue log, quality log.
- Summarise and review lessons learned.

**Applied to a scenario**
- Formal handover: signed acceptance certificate, all documentation transferred, warranty period defined, support contact assigned.

**Analysis**
- Un-closed logs live on and confuse the maintenance team.
- Skipping the lessons-learned summary = same mistakes next time (feeds A5 post-project evaluation).

**Evaluation**
- Recommend a formal closure meeting with all stakeholders — reduces disputes about "was it delivered". Justify: forces sign-off, formalises transition to support.

---

### E2 Review of project success

**Definitions / key facts**
Success measured against key factors, SMART objectives, stakeholder views.
- Review of lessons learned.
- Performance vs **baseline** and objectives.
- Final cost, delivery date, quality delivered.
- Feedback from: sponsor, clients, end users, development team.
- **Feedback methods** and pros/cons:
  - **Interviews** — deep insight, low volume; costly, interviewer bias.
  - **Questionnaires** — high volume, quantitative; shallow, low response rates.
  - **Surveys** — quick pulse, broad reach; superficial.
  - **Observation** — sees what people do, not what they say; time-consuming, observer effect.
- Recommendations for future actions.
- Communication and presentation requirements for reviews.

**Applied to a scenario**
- For a system used by many end users → questionnaire/survey for breadth + follow-up interviews for depth.
- For a small stakeholder set → interviews only.
- For a process-improvement project → observation is the honest measure.

**Analysis**
- Feedback method chosen must match audience + info needed. Mismatch = wrong conclusions.
- Comparing against **SMART objectives** is what turns "we think it went well" into an evidenced judgement.

**Evaluation — the distinction move**
- Recommend a **mixed-methods** review: quantitative (variance vs baseline, benefits realised vs forecast, questionnaire scores) plus qualitative (interviews with the sponsor and dev team). Justify: quantitative alone hides *why*, qualitative alone hides *how much*. Feed the lessons learned into the next project's risk register — that closes the improvement loop.

**Exam phrases**
- "The project met SMART objective 2 (99% uptime) but missed objective 3 (2-second load time actual was 3.4s), so overall success is qualified…"
- "Interviews with end users are recommended over questionnaires because…"
- "Based on this review, the recommendation for future projects is…"

---

## Note Template (used for any new lesson topic)

```markdown
### Topic: <name>  •  Section: <A1..E2>  •  Date: <DD/MM/YYYY>

**Definition / key facts (knowledge)**
- ...

**Applied to a scenario (small computing project)**
- ...

**Analysis — why it matters, causes/effects, trade-offs**
- ...

**Evaluation — strengths, weaknesses, when to use, justified recommendation**
- ...

**Exam-answer phrases to use**
- ...

**Common trap / examiner feedback**
- ...
```

## Part A — Pre-release scenario (fills in when released)

<!-- When Pearson releases the January exam Part A scenario, paste it here.
     Every section above then gets a scenario-specific mini-answer under
     "Applied to a scenario". -->

## Lesson Notes (dated log)

<!-- New lesson entries go below using the template above -->

---

## Key Terms Glossary (from the spec — use these exact definitions)

| Term                     | Definition                                                                                                                                                                                                                                       |
| ------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **Function point**       | A way of measuring the amount of work taken to implement part of a software system, e.g. it might take 10 developer hours to implement a search function.                                                                                        |
| **Gantt chart**          | A bar chart which provides a graphical illustration of a schedule that helps to plan, coordinate and track all the tasks in a project against a baseline.                                                                                        |
| **Lessons learned**      | A summary report which brings together any insights gained during a project that can be usefully applied on future projects — factors and actions that supported success, and learning from what did not go well.                                |
| **Modules**              | Part of a large software system that carries out a specific business role (e.g. HR uses a payroll module). Each module is likely to be built and tested independently, often by different groups of developers and testers.                       |
| **Operating system**     | Software that manages computer hardware and software resources and provides common services for computer programs.                                                                                                                                |
| **Project kick-off**     | The official launch of the project; the point at which details of the project are promoted. Only happens after initial investigation shows the project is viable (can the client afford it, can it be done in the timescale, is it technically possible). |
| **Regression testing**   | Software testing to uncover new bugs, or regressions in existing functional and non-functional areas, after changes such as enhancements, patches or configuration changes.                                                                       |
| **Resource list**        | A list of all the staff, equipment and raw materials required for a project with associated costs. Staff usually have an hourly rate or annual salary; equipment and materials are usually fixed costs.                                          |
| **Server**               | Hardware and software that provides centrally managed services on a computer network, such as a database or email system.                                                                                                                         |
| **Stakeholder**          | Anyone with an interest in the project — those with an interest in, or who can affect / are affected by, the computing project. Can be internal or external, at senior or junior levels.                                                          |
