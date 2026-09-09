# 02 — Project Checkpoint Report

**Spec anchor:** D2 Monitoring and tracking progress. Pulls in A1 (interim reviews), A3/C3 (risks + issues), C4 (quality activity), D3 (management by exception).

## What the examiner is looking for

- **Baseline vs actual** stated with numbers (schedule variance + cost variance).
- **Milestones achieved** in the period.
- **Risks + issues** update (not just "no issues" — real content).
- **Quality activity recorded** (reviews done, tests passed).
- **RAG status** with reasoning.
- **Escalations** under management by exception (D3).
- **Next-period plan** — concrete actions.
- Uses appropriate audience tone + fluent English (A6).

## Blank template

```
CHECKPOINT REPORT
=================
Project:            <name>
Report No.:         <n>            Reporting period: <from> → <to>
Author (PM):        <name>          Distribution: <sponsor, client, team managers, ...>
Date issued:        <DD/MM/YYYY>    Baseline reference: <baseline version + date>

1. Overall status
-----------------
| Objective/Workstream | RAG | Trend | Note                             |
| ...                  | G/A/R |  ↑↔↓  | ...                              |

2. Progress against baseline
----------------------------
Milestones planned this period : ...
Milestones achieved            : ...
Milestones missed / at risk    : ...

Schedule variance : +/- <days>   (baseline finish <date>; forecast <date>)
Cost variance     : +/- £<amount> (baseline £<x>; actual to date £<y>)

3. Quality management activity
------------------------------
- Reviews conducted           : ...
- Tests run + results         : ...
- Defects raised / closed     : ...

4. Risks
--------
| ID | Description | I | P | Sev | RAG | Change since last | Response       |
| .. |             |   |   |     |     |                   |                |

5. Issues
---------
| ID | Description | Category (RFC / off-spec / prob) | Impact | Owner | Action | Status |

6. Escalations (management by exception)
----------------------------------------
- <Issue/risk> escalated to sponsor because <it exceeds agreed tolerance>.
- Requested decision / action:

7. Next period plan
-------------------
- Tasks planned:
- Milestones due:
- Attention required from sponsor:

Author signature: ____________________     Date: __________
```

## Worked example — GreenLeaf Cafés Online Ordering System, Report #6

```
CHECKPOINT REPORT
=================
Project:            GreenLeaf Cafés Online Ordering System (OOS)
Report No.:         6            Reporting period: 09/11/2026 → 13/11/2026
Author (PM):        A. Kanumetta  Distribution: Ops Director (sponsor), IT Manager (client),
                                                Team Manager – Development, Team Manager – QA
Date issued:        13/11/2026   Baseline reference: Baseline 1.0, 15/09/2026

1. Overall status
-----------------
| Objective/Workstream            | RAG | Trend | Note                                             |
| Deliver customer web app        |  A  |   ↑   | 2-day slip vs baseline, recoverable this week    |
| Deliver staff order portal      |  G  |   ↔   | Complete, in system test                          |
| Payment (Stripe) integration    |  A  |   ↔   | Live-mode key still pending from client finance   |
| Testing / quality               |  G  |   ↔   | All unit + integration tests to plan             |
| Budget                          |  G  |   ↔   | £24,300 spent of £37,950 planned to date         |

2. Progress against baseline
----------------------------
Milestones planned this period : none (mid-build).
Milestones achieved            : Payment integration build complete (Task 6).
Milestones at risk             : M3 UAT sign-off (29/11) — depends on Stripe key arriving by 17/11.

Schedule variance : -2 days on Task 4 (customer app). Forecast finish 09/11 → 11/11.
                    Critical path finish 01/12 unchanged (2 days of contingency absorbed).
Cost variance     : +£450 (extra dev time on Task 4). Well within 15% contingency.

3. Quality management activity
------------------------------
- 3 peer reviews of database schema (C4 defect removal) — 5 defects raised, 5 closed.
- Unit tests: 142 total, 138 passing, 4 failing (payment edge cases — under fix).
- Integration test run 1 complete against designs — 1 blocking defect (checkout redirect), fix in progress.

4. Risks
--------
| ID  | Description                              | I | P | Sev | RAG | Change   | Response                                            |
| R01 | Dev1 illness on critical path            | 3 | 2 |  6  |  A  |  ↔       | Cross-training Dev2 (in progress)                    |
| R02 | Stripe live key delayed by client finance| 3 | 3 |  9  |  R  |  ↑ new   | Escalated (see §6). Contingency: sandbox demo at UAT |
| R03 | Requirements creep from branch staff     | 2 | 2 |  4  |  A  |  ↔       | Change requests go through change board (D4)         |

5. Issues
---------
| ID  | Description                              | Category  | Impact                | Owner  | Action                          | Status  |
| I04 | Checkout redirects to homepage on failure | Off-spec | UAT block if unfixed  | Dev1   | Fix + regression test by 16/11 | Open    |
| I05 | Branch manager asked for loyalty points   | RFC      | Scope, +5 days if in  | PM     | Formal CR raised, board 14/11  | Pending |

6. Escalations (management by exception)
----------------------------------------
Escalating R02 (Stripe live key) to the sponsor: exceeds agreed schedule tolerance if key arrives after 17/11.
Requested decision: sponsor to obtain the live-mode Stripe key from client finance by close of business
17/11, or approve running UAT in Stripe sandbox with go-live rescheduled by 3 working days.

7. Next period plan
-------------------
- Task 4 completion (customer app), Task 8 (integration testing) start 17/11.
- Milestones due: none this period; M3 (UAT sign-off) tracked to 29/11.
- Attention required from sponsor: R02 decision by 17/11 (see §6).

Author signature: A. Kanumetta                Date: 13/11/2026
```

## Marker notes — how to write for distinction

- **Numbers, not adjectives.** "Two days late, £450 over" beats "slightly behind schedule".
- **RAG with trend arrows** — shows the direction of travel, not just the snapshot.
- **Every risk and issue traced** back to the risk register / issue log, with an owner and action.
- **Escalation is explicit** — you name what's escalated, why (tolerance breach), and what decision you want. That is management by exception done properly.
- **Quality activity recorded** with counts — reviews, tests, defects. Missing this = missing D2 requirement.
- **Tone appropriate to a mixed audience** — sponsor + client + managers. Concise, factual, no jargon without expansion (A6).

## Common traps

- No baseline reference in the header (you must state which baseline).
- Vague variance ("a bit behind") — quantify.
- Absent risk/issue update ("nothing to report") in a mid-project week — implausible; the examiner infers you didn't check.
- Nothing under "next period plan" — makes the report a status update, not a control tool.
