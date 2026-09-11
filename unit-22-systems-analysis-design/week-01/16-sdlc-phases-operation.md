# Week 1 — Topic 16: SDLC Phases (Part 2) — Systems Operation

**Source:** `Week_One_Lecture_For_Software_Analysis_and_Design.pdf`, page 40 of 47.
**Learning Aim:** A — Investigate systems analysis and design methodologies.
**Criteria:** P / M / D.

> Continues the expanded SDLC phase-by-phase list started in Topic 15 (Planning & Selection + Systems Analysis). Slide 39 (likely covering **Systems Design** + **Systems Implementation**) was not captured in the lesson feed — a note is added below so we come back to it if it appears later.
>
> This slide covers the final phase: **Systems Operation** — what happens *after* go-live.

## Slide content (verbatim)

**Systems Development Life Cycle**

- **Operation**
  - System changed to reflect changing conditions
  - System obsolescence

---

## Pass evidence — describe / identify (P)

### Systems Operation — definition

The phase that starts **after go-live** and lasts until the system is retired. The system is now in production; the project team disbands (Unit 3 A5 closure), and the operations team owns it (Unit 3 E1 handover).

Two things happen in Operation:

1. **System changed to reflect changing conditions** — the world moves, so the system must move with it:
   - Business rule changes (new tax rates, promo codes, workflow tweaks).
   - Regulatory changes (GDPR updates, PCI-DSS revisions).
   - Technology changes (browser upgrades, OS end-of-life, dependency updates).
   - Volume changes (more users, more data — performance tuning).
   - Defect fixes (bugs that only appear in production).
2. **System obsolescence** — every system eventually reaches the end of its useful life:
   - Newer/better alternatives are available.
   - Business direction has changed and the system no longer fits.
   - Underlying technology is no longer supported.
   - Cost of continued maintenance exceeds the value the system delivers.
   - Time to **retire** the system in an organised way.

### The four maintenance types (standard IT vocabulary)

Operation-phase changes usually fall into one of four categories — worth memorising:

| Type          | What it fixes / changes                                                  | Example                                      |
| ------------- | ------------------------------------------------------------------------ | -------------------------------------------- |
| **Corrective** | Fixes defects reported in production.                                    | Live bug causing wrong VAT calc.              |
| **Adaptive**   | Adapts to changes in the environment (OS, dependencies, regulation).     | Upgrade to a new Stripe API version.          |
| **Perfective** | Improves the system based on user feedback (usability, performance).     | Faster page load, cleaner checkout flow.      |
| **Preventive** | Refactors or hardens the system to prevent future problems.               | Refactor a fragile module; add monitoring.    |

## Merit evidence — analyse / compare (M)

### Why Operation is the longest phase

- Analysis + Design + Implementation of a business system typically take months.
- Operation typically lasts **years to decades**.
- Most of a system's total cost is spent in Operation — often **60–80%** of lifetime cost.
- Consequences of neglecting Operation are therefore expensive.

### Why "changing conditions" is not optional

- The business is not frozen: sales campaigns change, tax rates change, regulations change, customer expectations change.
- If the system doesn't change too, it becomes wrong first, then embarrassing, then abandoned.
- Change goes through **change management** (Unit 3 D4) — request → impact assessment → approval → implementation → regression testing.
- Regression testing (Unit 3 C4) is what keeps Operation-phase change from breaking things that used to work.

### Why obsolescence must be planned, not stumbled into

- Systems that **run past** their sensible end-of-life become risks: unsupported dependencies, no one who knows the code, shadow workarounds by users.
- Planned retirement includes: data migration to the replacement, archival, decommissioning, communications to users.
- Signals a system is approaching obsolescence: rising defect rate, rising cost of change, users routing around it, dependencies going end-of-life.

### Link to earlier topics + Unit 3

- **Unit 3 E1 (closing a live project):** the project closure moves the system *into* Operation.
- **Unit 3 E2 (post-project review):** the review checks that Operation-phase support and benefits realisation are set up.
- **Unit 3 D4 (change management):** the Operation phase is where change management lives long-term.
- **Unit 3 D5 (implementation strategy):** decisions like *parallel running* or *pilot changeover* buy safe entry into Operation.
- **Topic 9 (databases + application independence):** application independence pays back in Operation — you can upgrade or replace one application without touching the data.

---

## Distinction evidence — evaluate / justify (D)

**Strengths of a well-run Operation phase:**
- The system stays fit for purpose as the world changes → business benefits keep flowing (Unit 3 A4).
- Defects are found and fixed with regression tests, so trust in the system stays high.
- Retirement is planned, not sudden → no data loss, no rushed replacement.
- Total cost of ownership stays predictable.

**Weaknesses / risks in Operation:**
- **No named owner** post-go-live → nobody accepts change requests; the system rots.
- **Change bureaucracy** either too heavy (nothing gets fixed) or too light (unmanaged change breaks things).
- **No monitoring / feedback loop** → the team doesn't know the system is failing until users leave.
- **No retirement plan** → the system runs on far past its sensible end-of-life, accumulating security and dependency risk.

**Justified judgement (the D-level move):**

Plan Operation **before go-live**, not after. Concretely, the recommendation for any assignment scenario:

1. **Name the operational owner** in the closure email (Unit 3 E1) — not just "IT Ops" but a role and person.
2. Define a **change management process** in the PID (Unit 3 B4 + D4) — how a change request is raised, assessed, approved, tested, released.
3. Establish a **regression test suite** during Implementation so future changes are safe (Unit 3 C4).
4. Set up **monitoring + user feedback channels** so "changing conditions" surface early.
5. Define an **end-of-life trigger** — the condition under which the system will be reviewed for retirement (e.g. cost of maintenance > cost of replacement; dependency going end-of-life; a strategic replacement is approved).

This turns Operation from a passive "keep it running" into an actively managed phase, and it's what a distinction-level answer describes.

---

## Applied to a scenario — GreenLeaf Cafés OOS in Operation

**Post-01/12/2026 go-live:**

| Aspect                        | Plan                                                                                          |
| ----------------------------- | --------------------------------------------------------------------------------------------- |
| Operational owner              | Head of IT Operations.                                                                        |
| Support route                  | it-support@greenleafcafes.co.uk, Mon–Sun 07:00–21:00.                                          |
| Warranty                       | 3 months (until 01/03/2027) — corrective changes at no extra cost.                             |
| Adaptive changes (planned)     | Stripe API annual review; Chromium updates monthly; menu changes each quarter.                 |
| Perfective changes             | Feedback captured through the app + branch managers; roadmap reviewed monthly.                 |
| Preventive changes             | Add monitoring dashboards; quarterly dependency audit.                                         |
| Monitoring                    | Uptime + order flow success rate + payment success rate + WCAG scan.                          |
| Obsolescence trigger           | Any of: EPOS integration approved (Phase 2), native mobile app approved, or dependency EOL.    |

## Exam-answer phrases to use

- "In the Operation phase, the system is **changed to reflect changing conditions** — business rules, regulation, technology, demand — until eventually **system obsolescence** occurs and the system is retired."
- "Operation typically consumes 60–80% of a system's lifetime cost — poorly managed Operation is where most system value is lost."
- "Operation-phase change should be routed through a documented change management process (see Unit 3 D4), with regression testing to protect what already works (Unit 3 C4)."
- "A justified plan for Operation names the operational owner, the change management route, the monitoring and feedback channels, and the trigger for reviewing the system for obsolescence."

## Common trap / examiner feedback

- Treating Operation as a passive "keep it running" phase — the spec names both **change** and **obsolescence** as active concerns.
- Forgetting the four maintenance types (corrective, adaptive, perfective, preventive) — a common exam probe.
- Skipping the retirement plan — obsolescence is on the spec; it must appear.
- Assuming the project team stays on for Operation — usually the project team disbands (Unit 3 A5 closure); operations takes over. Handover must be planned.

## Key vocabulary

**Operation phase, maintenance (corrective / adaptive / perfective / preventive), change management, regression testing, monitoring, service-level agreement (SLA), warranty, obsolescence, retirement, decommissioning, total cost of ownership (TCO), dependency end-of-life.**

---

## Note

Slide 39 (likely covering **Systems Design** and **Systems Implementation**) was **not captured** in the lesson feed. When it appears, add a new topic (17) covering those two phases so the SDLC-phases arc (Topics 15 → 17) is complete: Planning & Selection + Analysis → Design + Implementation → Operation.
