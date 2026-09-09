# 01 — Gantt Chart & Project Schedule

**Spec anchor:** C1 Scheduling and milestones. Also touches C2 (resources), A1 (milestones), D2 (baseline).

## What the examiner is looking for

- A **WBS-driven** task list (not random tasks).
- **Durations, start/end dates, dependencies** for every task.
- **Milestones** placed at stage gates.
- **Critical path** identified.
- **Baseline** captured for later variance measurement.
- **Justified** choice of tool (project planning software vs spreadsheet).
- Evaluation of the schedule: risks, float, resource conflicts, recommendations.

## Blank template

### 1. Scope of the schedule
- Project: <name>
- PM: <name> • Sponsor: <name> • Client: <name>
- Baseline date: <DD/MM/YYYY>
- Working assumptions: <e.g. 5-day week, 7.5 hrs/day, no work bank holidays>

### 2. Work Breakdown Structure (WBS) → Task list

| ID  | Task                          | Predecessor(s) | Owner   | Duration | Start      | Finish     | Type       |
| --- | ----------------------------- | -------------- | ------- | -------- | ---------- | ---------- | ---------- |
| 1   | ...                           |                |         |          |            |            | Task       |
| M1  | ...                           |                |         | 0        |            |            | Milestone  |

### 3. Gantt chart (ASCII / description)

```
Week   :  1  2  3  4  5  6  7  8  9 10 11 12
Task 1 : ██
Task 2 :    ████
Task 3 :        ██████
M1     :             ♦
...
```

### 4. Critical path

Longest chain of dependent tasks: `Task A → Task C → Task E → Task G`
Length: XX working days.

### 5. Resource summary

| Resource     | Total days | Cost rate | Total £ |
| ------------ | ---------- | --------- | ------- |
| PM           |            |           |         |
| Developer 1  |            |           |         |
| Developer 2  |            |           |         |
| Designer     |            |           |         |
| Tester       |            |           |         |

### 6. Baseline

Baseline captured on <date> in <tool>. Version: 1.0.

### 7. Evaluation (distinction move)

- Tool choice + justification: <e.g. MS Project chosen over Excel because…>
- Risk of overrun: which tasks have zero float? What contingency exists?
- Resource conflicts: any double-booked people/weeks?
- Recommendation for how the Gantt will be maintained (frequency, who updates it).

---

## Worked example — GreenLeaf Cafés online ordering system

### 1. Scope
- Project: GreenLeaf Cafés Online Ordering System (OOS)
- PM: A. Kanumetta • Sponsor: Operations Director • Client: IT Manager
- Baseline date: 15/09/2026
- Assumptions: 5-day week, 7.5 hrs/day, UK public holidays excluded.

### 2. WBS → Task list

| ID  | Task                                   | Predecessor  | Owner    | Duration | Start      | Finish     | Type      |
| --- | -------------------------------------- | ------------ | -------- | -------- | ---------- | ---------- | --------- |
| 1   | Requirements gathering (client + users) | –            | PM+UX    | 10 d     | 15/09/2026 | 26/09/2026 | Task      |
| M1  | Requirements signed off                | 1            | –        | 0        | 26/09/2026 | 26/09/2026 | Milestone |
| 2   | UX/UI design (wireframes → mockups)    | M1           | UX       | 10 d     | 29/09/2026 | 10/10/2026 | Task      |
| 3   | Database & API design                  | M1           | Dev1     | 8 d      | 29/09/2026 | 08/10/2026 | Task      |
| M2  | Design signed off                      | 2, 3         | –        | 0        | 10/10/2026 | 10/10/2026 | Milestone |
| 4   | Build — Customer web app               | M2           | Dev1     | 20 d     | 13/10/2026 | 07/11/2026 | Task      |
| 5   | Build — Staff order-fulfilment portal  | M2           | Dev2     | 15 d     | 13/10/2026 | 31/10/2026 | Task      |
| 6   | Payment integration (Stripe)           | 4            | Dev1     | 5 d      | 10/11/2026 | 14/11/2026 | Task      |
| 7   | Unit testing (rolling)                 | 4, 5         | Tester   | 10 d     | 27/10/2026 | 07/11/2026 | Task      |
| 8   | Integration testing                    | 6, 7         | Tester   | 5 d      | 17/11/2026 | 21/11/2026 | Task      |
| 9   | System testing                         | 8            | Tester   | 3 d      | 24/11/2026 | 26/11/2026 | Task      |
| 10  | UAT with 3 pilot branches              | 9            | Client   | 3 d      | 27/11/2026 | 29/11/2026 | Task      |
| M3  | UAT sign-off                           | 10           | –        | 0        | 29/11/2026 | 29/11/2026 | Milestone |
| 11  | Deployment + training                  | M3           | PM+Dev1  | 1 d      | 30/11/2026 | 30/11/2026 | Task      |
| M4  | Go-live                                | 11           | –        | 0        | 01/12/2026 | 01/12/2026 | Milestone |

### 3. Gantt (weeks 1–12; 15/09 → 01/12)

```
Week    :  1  2  3  4  5  6  7  8  9 10 11 12
Task  1 : ████
M1      :      ♦
Task  2 :      ████
Task  3 :      ███▊
M2      :          ♦
Task  4 :          ████████
Task  5 :          ██████
Task  6 :                  ██
Task  7 :                ████
Task  8 :                    ██
Task  9 :                     █▍
Task 10 :                      █▊
M3      :                        ♦
Task 11 :                         ▍
M4      :                          ♦
```

### 4. Critical path

`1 → M1 → 2 → M2 → 4 → 6 → 8 → 9 → 10 → M3 → 11 → M4`
= 10 + 10 + 20 + 5 + 5 + 3 + 3 + 1 = **57 working days**.

Task 3 (database design, 8 d) runs in parallel to Task 2 (design, 10 d) → **2 days float**.
Task 5 (staff portal build, 15 d) runs in parallel to Task 4 (customer app, 20 d) → **5 days float**.

### 5. Resource summary

| Resource    | Total days | Rate      | £        |
| ----------- | ---------- | --------- | -------- |
| PM (0.5 FTE) | ~28 d      | £350/d    | £9,800   |
| Developer 1  | ~33 d      | £300/d    | £9,900   |
| Developer 2  | ~15 d      | £300/d    | £4,500   |
| UX Designer  | ~10 d      | £280/d    | £2,800   |
| Tester       | ~18 d      | £250/d    | £4,500   |
| Stripe fees + hosting (1st yr) | —          | fixed    | £1,500   |
| Contingency (15%)              | —          | —        | £4,950   |
| **Total**                      |            |          | **£37,950** — under £40,000 ✓ |

### 6. Baseline

Captured 15/09/2026 in MS Project as Baseline 1.0. Any future replan saves a new baseline (Baseline 2.0…) so historical variance is preserved.

### 7. Evaluation

- **Tool choice:** MS Project over Excel — because dependencies auto-recalculate and the critical path is re-computed when a task slips. Justified because the schedule has 11 tasks and multiple dependencies; manual recalculation in Excel would be error-prone and slow at every checkpoint.
- **Zero-float tasks (critical path):** requirements → design → customer app build → payment → integration → system test → UAT → deploy. Any one-day slip on these slips go-live. **Mitigation:** weekly checkpoint reports (D2) with variance alerts; developer swing capacity from Task 5 (5 days float) to Task 4 (critical) if needed.
- **Resource conflicts:** Dev1 is on critical path throughout weeks 5–11 with no cover. **Risk (A3):** developer illness. Impact 3 × Probability 2 = severity 6 (amber). **Contingency:** cross-training Dev2 on the customer app early so they can absorb 3 days of Dev1 workload; freelance backup contact on retainer.
- **Recommendation:** Gantt updated every Friday by the PM at the checkpoint meeting, distributed to sponsor and client per the communication plan. Baseline preserved; live plan re-projected. Justify: a Gantt not updated weekly becomes fiction, defeating the purpose of C1 and D2.

## Marker notes — how to write for distinction

- **Show a WBS**, don't just list tasks. Even one sentence explaining decomposition (build split into customer app + staff portal + payments) shows planning depth.
- **Name predecessors** for every task. Missing predecessors = examiner cannot verify the critical path.
- **Compute the critical path explicitly** — write "the critical path is A → C → E → G = X days". Don't just draw it.
- **Cost the schedule** — pulls in C2. A schedule that isn't costed is half a plan.
- **Evaluate** — tool choice, float, risks, maintenance cadence. This is where distinction points live.
- Do **not** forget the baseline. Without it, D2 variance work is impossible.

## Common traps

- Tasks with no owner (who's accountable?).
- Milestones with a duration > 0 (they're 0 by definition).
- Critical path not called out.
- No contingency / no float discussion.
- Ignoring bank holidays and non-working days.
