# Week 1 — Topic 3: Data and Processes

**Source:** `Week_One_Lecture_For_Software_Analysis_and_Design.pdf`, page 20 of 47.
**Learning Aim:** A — Investigate systems analysis and design methodologies.
**Criteria:** P / M / D.

## Slide content (verbatim)

**Three key components of an information system:**
- Data
- Data Flows
- Processing Logic

**Data vs. Information:**
- **Data** — Raw facts.
- **Information** — Derived from data; Organised in a manner that humans can understand.

---

## Pass evidence — describe / identify (P)

**The three key components of an information system:**

| Component            | Definition                                                                                                | Example (an online shop)                                              |
| -------------------- | --------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------- |
| **Data**             | The raw facts held by the system. Individual values without context.                                       | `product_id = 4711`, `price = 12.50`, `customer_email = a@b.com`.     |
| **Data Flows**       | The movement of data between people, processes and data stores in the system.                              | Customer submits an order → order data flows from the web form to the orders database and to the warehouse system. |
| **Processing Logic** | The rules/decisions/calculations that transform data into new data or information.                         | "If stock < 5, mark as low stock"; VAT = price × 0.20; total = subtotal + VAT − discount. |

**Data vs Information — the exact distinction:**

| Property                | Data                                     | Information                                                   |
| ----------------------- | ---------------------------------------- | ------------------------------------------------------------- |
| What it is              | Raw facts.                                | Data that has been processed and organised.                   |
| Has context?            | Not necessarily.                         | Yes — arranged so a human can understand it.                  |
| Useful on its own?      | Rarely.                                   | Yes — supports decisions/actions.                             |
| Example (retail)        | `27, 33, 41, 29, 30`                     | "Average daily orders last week = 32."                        |
| Example (student data)  | `A, B, A, D, C, B, A`                    | "70% of the class achieved grade B or above."                 |

**In one line:** *Information = Data + Context + Organisation.*

---

## Merit evidence — analyse / compare (M)

**Why the three components matter to systems analysis and design:**

- **Data** — you cannot design a system without knowing what facts it stores. Data drives the database design (tables, fields, data types).
- **Data flows** — show *movement*. You use these to draw **Data Flow Diagrams (DFDs)** — where does the data come from, who processes it, where does it end up? Missed data flows = missed requirements.
- **Processing logic** — the *rules* of the business. Without it, the system stores facts but doesn't do anything useful with them.

**Chain of transformation:**
```
Data  →  Processing Logic  →  Information
(facts)   (business rules)    (usable output)
```

**Compare — Data vs Information as design concerns:**

| Design question                        | Data view                                    | Information view                                    |
| -------------------------------------- | -------------------------------------------- | --------------------------------------------------- |
| What does the database store?          | Raw fields, normalised.                       | (Not applicable — information is a view of data.)  |
| What does the user see on screen?       | Rarely raw data.                             | Reports, dashboards, summaries.                    |
| Who's the audience?                    | Machines / other systems.                     | Humans.                                             |
| When do we transform?                  | On the way in (validation, storage).          | On the way out (report generation, aggregation).   |

**Link back to earlier Week 1 topics:**
- The **CD player decomposition** (Topic 1) showed subsystems moving *signals* — Fig. 1.6 is essentially a data-flow view.
- **High cohesion** (Topic 2) is exactly the principle that each processing-logic module should have one clear rule to compute — a "calculate VAT" module does VAT only.
- **Loose coupling** applies to data flows too: pass a small, well-defined payload between subsystems, not their whole internal state.

---

## Distinction evidence — evaluate / justify (D)

**Strengths of thinking in Data / Data Flow / Processing Logic:**
- Forces the designer to separate **what is stored** from **how it moves** from **what rules apply** — the three questions that together fully describe an information system.
- Makes assumptions visible: every processing rule can be reviewed with the client for correctness; every data flow can be checked for security/privacy.
- Directly supports **DFD** and **ERD** modelling — the two main analysis tools in later Unit 22 weeks.

**Weaknesses / risks:**
- The distinction between "data" and "information" is context-dependent — one system's information is another system's data (e.g. a monthly sales total is *information* to a manager but *data* to a strategy dashboard). Sloppy use of the words causes confusion in requirements documents.
- Focusing only on data flows can miss **non-functional** requirements (performance, security, usability — Unit 3 A2 non-functional requirements).
- Processing logic can hide business assumptions — if the rule is not documented, the system silently encodes a business decision.

**Justified judgement (the D-level move):**
For any small computing project, **model all three components before writing code**:
1. Build the **data model** (fields, types, validation) so the database is right first time.
2. Draw the **data-flow diagram** (level 0 context + level 1 detail) so nothing is missed.
3. Write processing logic as **explicit business rules** in the requirements — one rule per line, testable ("VAT rate is 20% for standard-rated items").

**Recommendation:** treat every screen/report the user asks for as *information* and trace it back to the *data* it comes from and the *processing logic* that produces it. If any of the three is missing, the requirement is incomplete. This is the single fastest way to catch missed requirements at the analysis stage — cheaper than finding them in UAT (Unit 3 D5).

---

## Applied to a scenario — small computing project (GreenLeaf Cafés OOS)

| Component            | Example from GreenLeaf                                                             |
| -------------------- | ---------------------------------------------------------------------------------- |
| **Data**             | Menu items, prices, ingredients, customer email, order line, payment token.        |
| **Data flows**       | Customer chooses items → order → payment gateway → confirmation email; staff portal reads pending orders. |
| **Processing logic** | Total = sum(line) + VAT − discount; allergen warning if any ingredient in customer's alert list; loyalty +1 point per £1. |
| **Information (out)**| The order-summary screen; the staff "orders due next" list; the monthly sales report by branch. |

---

## Exam-answer phrases to use

- "The three key components of an information system are data, data flows and processing logic, each of which must be modelled during analysis."
- "Data are the raw facts stored by the system, whereas information is data that has been processed and organised so that humans can understand it."
- "The processing logic for calculating VAT is: total × 0.20, applied only to standard-rated items — this rule was elicited from the client during requirements gathering."
- "Data flows are shown using a Data Flow Diagram (DFD), which makes the movement of data between processes, external entities and data stores visible for review."

## Common trap / examiner feedback

- Treating **data and information as the same thing** — the two terms have precise meanings in systems analysis; using them interchangeably loses marks.
- Listing only **data** in the analysis and forgetting **data flows** and **processing logic** — that's a partial answer.
- Confusing **processing logic** (business rules) with **program code** — logic is the *rule*; code is one *implementation* of it.

## Key vocabulary

**Data, information, data flow, processing logic, information system, raw facts, data flow diagram (DFD), data store, external entity, business rule.**
