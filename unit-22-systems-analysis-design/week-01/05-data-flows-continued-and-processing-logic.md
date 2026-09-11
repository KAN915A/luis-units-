# Week 1 — Topic 5: Data Flows (continued) and Processing Logic

**Source:** `Week_One_Lecture_For_Software_Analysis_and_Design.pdf`, page 22 of 47.
**Learning Aim:** A — Investigate systems analysis and design methodologies.
**Criteria:** P / M / D.

> Completes the "Data and Processes" section. Adds the source/destination rule for **data flows**, and introduces **processing logic** — the third of the three components of an information system.

## Slide content (verbatim)

**Data Flows (Continued):**
- Include description of sources and destination for each data flow.

**Processing Logic:**
- Describe steps that transform data and events that trigger the steps.

---

## Pass evidence — describe / identify (P)

### Data Flows — source and destination rule

- Every data flow on a DFD must name **where the data comes from** (its **source**) and **where it goes** (its **destination**).
- The source and destination of a data flow can only be one of three things:
  - An **external entity** (person or system outside the boundary).
  - A **process** (inside the boundary, transforms data).
  - A **data store** (a database or file inside the boundary).
- A data flow is a directional arrow — head at the destination, tail at the source — and it carries a **named group of data** (see Topic 4).

**Forbidden combinations on a valid DFD:**
- External entity ⇢ external entity (both are outside our system).
- Data store ⇢ data store (data doesn't move by itself — a process must move it).
- Anything that flows **from nowhere** or **to nowhere** (both ends must be identified).

### Processing Logic — steps + triggers

- **Processing logic** describes:
  - **Steps** — the transformations applied to data (calculate, validate, sort, look up, decide, store).
  - **Trigger events** — what causes the steps to run (a user action, a scheduled time, an incoming message from another system, a change to a data store, a system state change).
- Two questions to answer for every process on a DFD:
  1. **When does it run?** (the event that triggers it)
  2. **What does it do to the data?** (the transformation steps)

### Techniques for describing processing logic

| Technique                | What it looks like                                                      | Best for                                     |
| ------------------------ | ----------------------------------------------------------------------- | -------------------------------------------- |
| **Structured English**   | Numbered steps in plain English, one action per line, IF/ELSE/WHILE.     | Sequential logic; readable by clients.       |
| **Decision Table**       | Grid of conditions × actions.                                            | Many combinations of rules (tax bands, pricing tiers). |
| **Decision Tree**        | Branching diagram of conditions.                                         | Nested conditional logic.                    |
| **Flowchart**            | Standard shapes for start/end, process, decision, connector.             | Visual audiences; simple business processes. |
| **Pseudocode**           | Code-like description with variables and control flow.                   | Handover to developers.                      |
| **State diagram**        | States + transitions triggered by events.                                | Objects with a lifecycle (Order: draft → placed → paid → dispatched). |

---

## Merit evidence — analyse / compare (M)

### Why the source/destination rule matters

- Naming the source and destination **forces you to identify the boundary** of the system — anything outside is an external entity, anything inside is a process or store.
- It exposes **missing entities** — if a data flow has no clear source, either the source isn't modelled yet or the flow doesn't exist.
- It supports the loose-coupling principle from Topic 2 — small, well-defined flows between named endpoints are the design equivalent of small, named interfaces.

### Steps vs triggers — why both are needed

- The **steps** tell you *what* happens.
- The **trigger** tells you *when* it happens.
- Miss the trigger and you get a system that computes the right thing… but never runs at the right time (or runs constantly).
- Common trigger types:
  - **User event** — customer clicks "Pay".
  - **Timer / schedule** — nightly report at 02:00.
  - **System event** — new record inserted → notify.
  - **External event** — payment gateway sends a webhook.
  - **State change** — order status becomes "dispatched" → email customer.

### Choosing between processing-logic techniques

| Situation                                       | Prefer                                    | Why                                                      |
| ----------------------------------------------- | ----------------------------------------- | -------------------------------------------------------- |
| A tax rule with 3 conditions × 4 outcomes       | **Decision table**                        | Compact, prevents missed combinations.                    |
| A step-by-step business process for a manager   | **Structured English** or **flowchart**   | Readable by non-technical stakeholders.                   |
| A complex data transformation for a developer   | **Pseudocode**                            | Precise and code-adjacent.                                |
| An order that moves through many statuses       | **State diagram**                         | Makes the lifecycle explicit; catches invalid transitions.|

### Link back to earlier topics

- **Topic 1 (decomposition):** processing logic is what lives *inside* each subsystem box.
- **Topic 2 (cohesion):** high cohesion means each process on a DFD does *one* transformation — describable in a few structured-English steps.
- **Topic 2 (coupling):** low coupling means each data flow carries only the fields the destination process needs — nothing extra.
- **Topic 3 (three components) + Topic 4 (in-depth):** Topics 4 + 5 are just the *how you describe them* for two of the three components — this slide brings processing logic into the same discipline.

---

## Distinction evidence — evaluate / justify (D)

**Strengths of documenting flows with source/destination + processes with steps and triggers:**
- Produces DFDs that are **self-checking** — every arrow has two ends that must both be modelled; nothing "just happens".
- Separates **timing** (triggers) from **behaviour** (steps) — the two most common causes of production bugs are wrong timing and wrong logic; separating them in analysis catches both classes.
- Makes the system **testable at the analysis stage** — you can write test cases straight from a decision table before any code exists (Unit 3 C4 quality management).

**Weaknesses / trade-offs:**
- Multiple notations (structured English, decision tables, decision trees, state diagrams) — inconsistency across the document is worse than any single choice.
- Very fine-grained triggering (every field change fires an event) can lead to systems that are hard to reason about.
- Decision tables get large quickly; if a table has more than ~8 conditions it's usually a sign the rule needs refactoring, not a bigger table.

**Justified judgement (the D-level move):**
For every process on a DFD, produce **both**:
1. A **trigger statement** — one sentence naming the event that starts the process ("triggered when a customer submits the checkout form").
2. A **body** in the notation that best fits the logic — structured English for sequential steps, a decision table for many-condition rules, a state diagram if the entity has a lifecycle.

Pick **one notation per class of problem** and apply it consistently across the whole assignment. **Recommend** cross-checking that every arrow on the DFD has its source and destination named, every process has a trigger, and every field mentioned in the processing logic exists in the data dictionary — three cheap checks that catch most missed requirements before the design phase.

---

## Applied to a scenario — small computing project (GreenLeaf Cafés OOS)

**Data flows with source/destination — DFD fragment:**

| Data flow name           | Source                            | Destination                       | Fields carried                                    |
| ------------------------ | --------------------------------- | --------------------------------- | ------------------------------------------------- |
| `OrderRequest`           | External entity: Customer          | Process: Validate Order            | items, quantities, collection branch, customer id |
| `PaymentAuthorisation`   | Process: Validate Order            | External entity: Stripe            | order id, amount, currency, card token            |
| `AuthResult`             | External entity: Stripe            | Process: Confirm Order             | success/fail, transaction id                      |
| `OrderRecord`            | Process: Confirm Order             | Data store D1: Orders              | full order fields                                 |
| `OrderConfirmation`      | Process: Confirm Order             | External entity: Customer          | reference, ETA, receipt                           |
| `StaffOrderAlert`        | Process: Confirm Order             | External entity: Branch staff app  | order id, items, ETA                              |

**Processing logic for `Process: Validate Order` — structured English:**

```
Trigger: customer submits the checkout form.

1. Load the cart for the customer.
2. IF the cart is empty THEN reject with error "empty cart" AND stop.
3. FOR each line in the cart:
     3.1 Look up the item in the product master.
     3.2 IF the item is out of stock at the selected branch THEN
             reject with error "item X unavailable at branch Y"
             AND stop.
     3.3 Recalculate line total = quantity × current price.
4. Sum all line totals into subtotal.
5. Apply any active discount code (see decision table DT-01).
6. total = subtotal − discount + VAT
     where VAT = subtotal × 0.20 for standard-rated items only.
7. Emit `PaymentAuthorisation` to Stripe.
```

**Decision table DT-01 — discount application:**

| Condition                                  |  R1 |  R2 |  R3 |  R4 |
| ------------------------------------------ | --- | --- | --- | --- |
| Customer is a loyalty member                | Y   | Y   | N   | N   |
| Order total ≥ £15                           | Y   | N   | Y   | N   |
| **Action**                                  |     |     |     |     |
| Apply 10% loyalty discount                   |  ✓  |     |     |     |
| Apply free-delivery voucher                  |     |  ✓  |     |     |
| Apply £2 first-time-customer coupon (once)  |     |     |  ✓  |     |
| No discount                                  |     |     |     |  ✓  |

---

## Exam-answer phrases to use

- "Every data flow on the DFD names its source and destination; a flow without both ends is invalid."
- "The process is triggered when… and its steps are: 1) …, 2) …, 3) … — described in structured English."
- "For the discount rule I have used a decision table because it makes all four condition combinations explicit and prevents missed cases."
- "Separating the trigger from the steps ensures the system runs the right logic *at the right time*, not just with the right output."

## Common trap / examiner feedback

- Drawing data flows that **skip the process** (e.g. external entity straight to a data store). Data doesn't move itself — a process must always sit between an external entity and a store.
- Describing processing logic without stating the **trigger** — the marker cannot tell when the process runs.
- Mixing notations within one process description (half structured English, half flowchart) — pick one.
- Decision tables with overlapping or missing rules (columns that don't fire, or two columns that both fire on the same input).

## Key vocabulary

**Source, destination, external entity, process, data store, trigger, event, step, transformation, structured English, decision table, decision tree, flowchart, pseudocode, state diagram.**
