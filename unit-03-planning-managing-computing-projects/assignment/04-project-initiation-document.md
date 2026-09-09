# 04 — Project Initiation Document (PID)

**Spec anchor:** B4 The Project Initiation Document. Pulls in every content area — the PID is the master document.

## What the examiner is looking for

- **All 18 sections present** (see checklist below). Missing any = capped marks.
- **SMART objectives** with numbers, dates, acceptance criteria.
- **Scope stated with inclusions AND exclusions.**
- **Business case elements** — reasons, options, benefits, timescale, budget, risks.
- **Risk strategy** — process, matrix, contingency, ownership (not just a list of risks).
- **Org chart** for the project team with roles.
- **Communication plan** — audience × method × frequency.
- **Document management** — version control, storage, access.
- **Communication + presentation requirements** — audience-appropriate, fluent English, graphics where they help (A6).

## 18-section checklist (mark against your PID)

- [ ] 1. Document details
- [ ] 2. Approvals
- [ ] 3. Distribution
- [ ] 4. Purpose of PID
- [ ] 5. Project background (org fit)
- [ ] 6. Objectives (SMART)
- [ ] 7. Scope (in / not in)
- [ ] 8. Business case
- [ ] 9. Assumptions
- [ ] 10. Constraints
- [ ] 11. Risk management strategy
- [ ] 12. Deliverables
- [ ] 13. Project quality strategy
- [ ] 14. Stakeholders
- [ ] 15. Project management team structure (org chart)
- [ ] 16. Project plan
- [ ] 17. Communication plan
- [ ] 18. Document management

## Blank template

```markdown
# PROJECT INITIATION DOCUMENT
Project: <name>
Version: 1.0        Status: Draft / Approved
Date: <DD/MM/YYYY>  Author: <PM name>

---
## 1. Document details
| Field    | Value          |
| Title    |                |
| Version  |                |
| Date     |                |
| Author   |                |
| Owner    |                |

## 2. Approvals
| Role    | Name | Signature | Date |
| Sponsor |      |           |      |
| Client  |      |           |      |
| PM      |      |           |      |

## 3. Distribution
List of stakeholders receiving a copy + access level.

## 4. Purpose of PID
One paragraph on why this document exists (baseline for the project; contract
between PM and sponsor; reference for monitoring, change control, closure).

## 5. Project background
How the project fits into the organisation: strategic context, why now.

## 6. Objectives (SMART)
Numbered list of SMART objectives.

## 7. Scope
### In scope
- ...
### NOT in scope (exclusions)
- ...

## 8. Business case
- Reasons for the project
- Options considered (option A, B, C — do nothing)
- Expected business benefits (measurable)
- Timescale + major milestones
- Budget available
- Major risks (see §11)

## 9. Assumptions
Numbered list; each assumption is also entered as a low-level risk in the risk log.

## 10. Constraints
- Time / deadline
- Funds / contingency
- Staff availability
- Equipment availability
- Technical expertise in the team
- Technology limits

## 11. Risk management strategy
- Process: identify → assess (I × P severity) → plan (accept / contingency / avoid) → monitor.
- Risk matrix (RAG).
- Ownership per risk.
- Review cadence.

## 12. Deliverables
Product breakdown structure or list of tangible outputs.

## 13. Project quality strategy
- Standards used (ISO/IEC 25010, W3C, WCAG…).
- Defect-removal techniques (desk check, peer review, walkthroughs).
- Testing levels (unit, integration, system, regression, UAT).
- Sign-off rules.

## 14. Stakeholders
Table: name → role → interest/power → communication needs.

## 15. Project management team structure
Org chart showing PM, team leads, sponsors, client — with roles.

## 16. Project plan
- WBS + Gantt (link/attachment).
- Milestones and stage gates.
- Budget summary.

## 17. Communication plan
Table: audience × information × method × frequency × owner.

## 18. Document management
- Location of the PID and supporting docs.
- Version control rules.
- Access rights.
- Change control for the PID itself.
```

## Worked example — GreenLeaf Cafés Online Ordering System PID (extract)

Full PID would be ~12–20 pages; below is a **distinction-level worked extract** showing the shape and depth for each section. In the exam you'd write a similar level per section that's asked.

### 1. Document details

| Field   | Value                                                |
| ------- | ---------------------------------------------------- |
| Title   | GreenLeaf Cafés Online Ordering System — PID         |
| Version | 1.0                                                  |
| Date    | 15/09/2026                                           |
| Author  | A. Kanumetta (PM)                                    |
| Owner   | Operations Director (Sponsor)                        |

### 2. Approvals

| Role       | Name            | Signature | Date       |
| ---------- | --------------- | --------- | ---------- |
| Sponsor    | J. Pearson      | ______    | 15/09/2026 |
| Client     | R. Singh (IT)   | ______    | 15/09/2026 |
| PM         | A. Kanumetta    | ______    | 15/09/2026 |

### 3. Distribution

Sponsor, Client, Team Manager – Development, Team Manager – QA, all project team members (read-only), Finance Director (read-only), Head of Operations (read-only).

### 4. Purpose of PID

This document baselines the GreenLeaf OOS project. It is the reference against which scope, cost, quality and schedule variance are measured (D2), and forms the agreement between PM and sponsor. Any change after approval is subject to change control (D4).

### 5. Project background

GreenLeaf Cafés (12 UK branches) faces peak-hour queueing that limits per-branch revenue and damages customer satisfaction. Competitor chains (Pret, Costa) already offer online pre-order and pay. OOS supports the FY26 strategic aim of "digital-enabled customer experience".

### 6. Objectives (SMART)

1. Deliver OOS live to all 12 branches by **01/12/2026**.
2. Average customer order flow (start → payment confirmation) ≤ **90 seconds** on 4G, measured with Chrome DevTools throttling.
3. Reduce peak-hour in-store queue length by **≥ 20%** within 3 months of go-live, measured by branch manager stopwatch samples (4 samples × 12 branches × 4 weeks).
4. Deliver within a budget of **£40,000** (inc. contingency).
5. All deliverables comply with **W3C HTML5 / WCAG 2.1 AA** and **PCI-DSS** requirements for payment.

### 7. Scope

**In scope:**
- Customer web app (mobile + desktop) with menu browsing, order, pre-pay.
- Staff order-fulfilment portal (per branch).
- Stripe payment integration.
- Deployment to all 12 branches.
- Staff training (in-person + video).
- 3-month post-go-live warranty.

**NOT in scope (exclusions):**
- Native mobile apps (iOS/Android) — web app only in this phase.
- Loyalty points / rewards programme (deferred to Phase 2).
- Integration with the existing POS EPOS system (deferred to Phase 2).
- Delivery / courier integration.

### 8. Business case

- **Reasons:** peak-hour queueing lost revenue est. £62k/yr; competitor parity; brand modernisation.
- **Options considered:**
  - A: Bespoke build (chosen) — full control, integrates with brand.
  - B: Off-the-shelf platform (e.g. Deliveroo add-in) — faster but 8% transaction fees + weak brand.
  - C: Do nothing — falls further behind competitors.
- **Expected business benefits:** productivity (fewer manual takings), improved service (queue reduction), increased market share (regain footfall from Pret).
- **Timescale:** 15/09/2026 → 01/12/2026 (11 weeks). Major milestones: requirements sign-off (26/09), design sign-off (10/10), UAT (27–29/11), go-live (01/12).
- **Budget:** £40,000 inc. 15% contingency.
- **Major risks:** payment integration, developer availability on critical path, branch-staff resistance to change (see §11).
- **ROI:** cost £40k; forecast annual saving £62k → ~7-month payback; 3-year ROI ≈ 365%.

### 9. Assumptions

1. Stripe live-mode keys will be issued by client finance by 17/11/2026.
2. All branches have stable 4G / Wi-Fi at counter (verified by IT walkround).
3. Menu data is available in CSV form from head office by 26/09/2026.

Each assumption is entered as a low-level risk in the risk log (R-A1, R-A2, R-A3).

### 10. Constraints

- **Deadline:** 01/12/2026 non-negotiable (Christmas trading).
- **Funds:** £40,000 including contingency.
- **Staff availability:** Dev1 booked full-time; Dev2 3 days/week; UX 50%; Tester 4 days/week.
- **Equipment:** each branch has one existing tablet at counter — must fit.
- **Expertise:** no Stripe experience in team (see risk R05 mitigation: pair Dev1 with external Stripe expert consultant, 2 days).
- **Technology:** existing hosting is Azure App Service — reuse (avoids procurement).

### 11. Risk management strategy

- Impact and probability each on 1–3 scale; **severity = I × P**.
- Matrix: 1–3 green (accept / monitor), 4–6 amber (contingency), 7–9 red (avoid / heavy contingency).
- Risk register maintained in the project SharePoint, reviewed **every Friday** at the checkpoint meeting; every risk has a **named owner**.
- Realised risks become issues in the issues log with a cross-reference to the originating risk.
- Red risks escalated to sponsor under management by exception.

Sample entries:

| ID  | Description                             | I | P | Sev | RAG | Owner | Response                            |
| --- | --------------------------------------- | - | - | --- | --- | ----- | ----------------------------------- |
| R01 | Dev1 illness on critical path           | 3 | 2 | 6   | A   | PM    | Cross-train Dev2; freelancer on retainer |
| R02 | Stripe live keys delayed                | 3 | 3 | 9   | R   | PM    | Escalate to sponsor by 10/11        |
| R03 | Branch staff resist new process         | 2 | 2 | 4   | A   | Ops   | Early demo + 1-hr training per staff |

### 12. Deliverables (Product Breakdown Structure — top level)

- OOS
  - Customer web app
  - Staff portal
  - Stripe payment integration
  - Deployment package (all 12 branches)
  - Documentation (user manual, admin guide)
  - Training materials
  - Test summary report

### 13. Project quality strategy

- Standards: **ISO/IEC 25010** (usability, reliability, security, performance efficiency); **W3C HTML5 + WCAG 2.1 AA**; **PCI-DSS** for payment.
- **Defect removal:** desk checking + peer review on all commits; formal walkthrough of the database schema and the payment flow.
- **Testing:** unit vs unit spec; integration vs designs; system vs requirements; regression after every change; UAT with 3 pilot branches against SMART criteria.
- **Sign-off rules:** each stage-gate milestone requires sponsor sign-off; UAT requires client sign-off.

### 14. Stakeholders

| Name          | Role                     | Power | Interest | Communication                       |
| ------------- | ------------------------ | ----- | -------- | ----------------------------------- |
| J. Pearson    | Sponsor (Ops Director)   | High  | High     | Weekly checkpoint email + monthly meeting |
| R. Singh      | Client (IT Manager)      | High  | High     | Weekly checkpoint email + weekly call |
| Team Manager – Dev | Provides devs        | Med   | Med      | Fortnightly 1:1                     |
| Team Manager – QA  | Provides tester      | Med   | Med      | Fortnightly 1:1                     |
| Branch Managers × 12 | End users            | Low   | High     | Fortnightly newsletter + UAT invite for 3 pilot branches |
| Finance Director | Budget approver      | High  | Low      | Milestone reports only              |
| Customers     | End users                | Low   | High     | Launch communications post-go-live  |

### 15. Project management team structure

```
              +-------------------+
              |    Sponsor        |
              |  (Ops Director)   |
              +---------+---------+
                        |
              +---------v---------+
              |  Project Manager  |
              |  (A. Kanumetta)   |
              +----+----+----+----+
                   |    |    |
     +-------------+    |    +-------------+
     |                  |                  |
+----v-----+     +------v------+     +-----v-----+
| Dev Team |     |  UX Design  |     |   QA /    |
| Dev1, D2 |     |  (1 person) |     |  Tester   |
+----------+     +-------------+     +-----------+
```

### 16. Project plan

- WBS + Gantt: see attachment `OOS_ProjectPlan_v1.0.mpp`.
- 11-week schedule, critical path 57 working days, go-live 01/12/2026.
- Budget summary: £37,950 planned + £4,950 contingency ≈ £40,000.

### 17. Communication plan

| Audience           | What                              | Method               | Frequency               | Owner |
| ------------------ | --------------------------------- | -------------------- | ----------------------- | ----- |
| Sponsor            | Checkpoint report (RAG + numbers) | Email + monthly mtg   | Weekly + monthly        | PM    |
| Client (IT Manager)| Progress + open items             | Email + weekly call   | Weekly                  | PM    |
| Team Managers      | Resource + escalation             | 1:1 meeting           | Fortnightly             | PM    |
| Project team       | Task assignments, blockers        | Daily stand-up + Teams| Daily                   | PM    |
| Branch Managers    | Feature previews, training        | Newsletter + video    | Fortnightly             | UX    |
| Finance            | Spend vs budget                   | Milestone email       | At each milestone       | PM    |

### 18. Document management

- All docs stored on GreenLeaf SharePoint `Projects > OOS`.
- PID version control: semantic version (major.minor). Major = scope/objective change; minor = clarifications.
- Change to the PID after approval requires a change request under D4 (see §11 process).
- Read access: distribution list (§3). Edit access: PM and Sponsor.
- Retention: 7 years post-closure per company policy.

## Marker notes — how to write for distinction

- **All 18 sections present** — the biggest single cause of missed marks is a "trimmed" PID.
- **SMART objectives with numbers** — 90 seconds, £40,000, WCAG 2.1 AA. Not "fast", "affordable", "accessible".
- **Scope exclusions explicit** — the section that stops scope creep in D4.
- **Business case with real options** — "do bespoke, do off-the-shelf, do nothing" — otherwise there's no justification for the chosen route.
- **Risk register embedded** with severity scoring + owner + response — not just a bulleted list of "risks might happen".
- **Communication plan as a table** with audience × method × frequency — proves it's actionable.
- **Document management** — version control rules for the PID itself. Meta-governance = distinction.

## Common traps

- Missing sections — especially "distribution", "approvals", "document management", "purpose".
- Objectives not SMART — the single most flagged weakness in examiner reports.
- Scope with inclusions only, no exclusions.
- Business case without options considered.
- No org chart, or an org chart without roles.
- Communication plan as prose ("we'll email people") instead of a structured table.
