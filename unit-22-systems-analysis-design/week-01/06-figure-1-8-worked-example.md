# Week 1 — Topic 6: Fig. 1.8 — Differences among Data, Data Flow, and Processing Logic

**Source:** `Week_One_Lecture_For_Software_Analysis_and_Design.pdf`, page 23 of 47 (Figure 1.8).
**Learning Aim:** A — Investigate systems analysis and design methodologies.
**Criteria:** P / M / D.

> Worked example putting the three components (Topic 3) side-by-side so the differences are visible. Reinforces Topics 4–5.

## Slide content

Figure 1.8 shows one example of each component:

### Data (table)

| Name           | Age | Party        |
| -------------- | --- | ------------ |
| John Smith     | 25  | Democrat     |
| Joan Chen      | 42  | Republican   |
| Wilma Alvarez  | 31  | Independent  |

### Processing Logic (pseudocode — a weekly-pay calculation)

```
Event: Hours-Worked = 0
Event Action:
IF Hours-Worked > 40 THEN
    Pay = 40 * Pay-Rate
        + (Hours-Worked - 40) * (1.5 * Pay-Rate)
ELSE
    Pay = Pay-Rate * Hours-Worked
END IF
```

### Data Flow (mini-DFD — credit card statement)

```
                       Account number
                       and transaction data
                                │
                                ▼
                    ┌───────────────────────┐
                    │  Validate Credit      │
                    │  Card Sale (process)  │
                    └───────────┬───────────┘
                                │  Valid account number
                                │  and transaction data
                                ▼
                       ┌──────────────┐
                       │ Transactions │  (data store)
                       └──────┬───────┘
                              │  Account number and transactions
                              ▼
                    ┌───────────────────────┐
                    │  Prepare Statement    │
                    │  (process)            │
                    └───────────┬───────────┘
                                │  Statement
                                ▼
                              (output)
```

---

## Pass evidence — describe / identify (P)

- **Data** in the figure = a **table of raw facts** (people and their party affiliation). No context, no computation — just stored values.
- **Processing logic** in the figure = a **rule** (pay calculation with overtime), written as pseudocode with an event trigger (`Hours-Worked = 0`) and IF/ELSE steps. This maps to Topic 5: **steps + trigger**.
- **Data flow** in the figure = a **mini-DFD** showing account/transaction data moving from a validating process, into a Transactions data store, out to a statement-preparation process, and finally out as a Statement. Demonstrates Topic 5's source/destination rule for every arrow.

## Merit evidence — analyse / compare (M)

**One picture, three different jobs:**

| Component        | What Fig 1.8 shows                                            | Analysis tool it stands for                       |
| ---------------- | ------------------------------------------------------------- | ------------------------------------------------- |
| Data             | Rows and columns of stored values.                             | Data dictionary / ERD.                            |
| Processing logic | Steps + trigger, written in pseudocode.                         | Structured English / pseudocode / decision table. |
| Data flow        | Boxes, arrows, and a data store.                                | Data Flow Diagram (DFD).                          |

**Why the pay-calc pseudocode is a good example of processing logic:**
- It names a **trigger** (`Hours-Worked = 0` — i.e. a new pay period starts).
- It applies a **rule** with two cases (overtime vs. no overtime).
- It's **computable and testable** — you can pick any pair `(Hours-Worked, Pay-Rate)` and get one deterministic `Pay`.

**Why the credit-card DFD is a good example of a data flow:**
- Every arrow is a **named group of data** ("Account number and transaction data", "Valid account number and transaction data", "Statement").
- The **Transactions** data store sits between two processes — data doesn't move on its own; a process always sits either side of a store (Topic 5 rule).
- The **source** and **destination** of every arrow are named — no orphans.

**Compare — same customer story told three ways:**
- **Data** shows *what* is stored.
- **Data flow** shows *how* it moves and where it rests.
- **Processing logic** shows *what happens to it and when*.
Miss any one of the three and the analysis is incomplete.

## Distinction evidence — evaluate / justify (D)

- **Strengths** of Fig 1.8 as an analysis pattern: it shows every reader (client, designer, developer) *the same system* from three complementary angles. The client can spot missing rules, the designer can spot missing entities, the developer can spot missing triggers.
- **Weaknesses:** each notation on its own hides part of the picture — a database schema without a DFD hides how the data got in; a DFD without processing logic hides *why* data changes shape; pseudocode without a data model hides *what* it's operating on.
- **Justified judgement:** for every process on a system's DFD, produce a **matching pseudocode / structured English body** and **entries in the data dictionary** for every field it touches. Cross-check: every field in the pseudocode should exist in the dictionary; every data flow should be defined; every process should have a trigger. **Recommend** using Figure 1.8 as a template for the assignment — showing one small worked example of each of the three views is often more persuasive to a marker than a wall of text about the theory.

## Applied to a scenario — GreenLeaf Cafés OOS "Fig 1.8" fragment

**Data (products data store):**

| product_id | name             | price_gbp | vat_rate | allergens          |
| ---------- | ---------------- | --------- | -------- | ------------------ |
| 4711       | Latte, regular   | 3.20      | 0.20     | milk               |
| 4712       | Oat latte        | 3.60      | 0.20     | (none)             |
| 5901       | Bacon roll       | 4.50      | 0.20     | gluten, egg        |

**Processing logic (loyalty discount, pseudocode):**

```
Event: PlaceOrder submitted
Event Action:
IF customer.is_loyalty_member AND order.subtotal >= 15.00 THEN
    discount = order.subtotal * 0.10
ELSE IF NOT customer.is_loyalty_member AND order.first_time THEN
    discount = 2.00
ELSE
    discount = 0.00
END IF
order.total = order.subtotal - discount + order.vat
```

**Data flow (mini-DFD):**

```
Customer ──(OrderRequest)──▶ Validate Order ──(PaymentAuth)──▶ Stripe
                                    │
                                    ▼
                            ┌──────────────┐
                            │ Orders store │
                            └──────┬───────┘
                                   │
                                   ▼
                            Prepare Confirmation ──(Confirmation)──▶ Customer
```

## Exam-answer phrases to use

- "Figure 1.8 makes the three components of an information system concrete: **data** as a table of stored facts, **processing logic** as pseudocode with a trigger and IF/ELSE steps, and a **data flow** shown as a mini-DFD with named arrows."
- "The processing logic includes a trigger event (`Hours-Worked = 0`) and step-by-step transformations — meeting the Topic 5 requirement that every process has both."
- "Every arrow on the credit-card DFD names its source and destination, so no data flow is orphaned."

## Common trap / examiner feedback

- Describing Figure 1.8 as "one diagram of the system" — it isn't; it's three different views placed next to each other.
- Ignoring the **trigger** in the pseudocode — the pay calculation is meaningless without a "when".
- Confusing the **Transactions** store with a process — it's a store (data at rest), not a process (data being transformed).

## Key vocabulary

**Data table, pseudocode, event, trigger, IF/ELSE, process, data store, data flow, named data flow.**
