# Week 1 — Topic 4: Data and Data Flows in depth

**Source:** `Week_One_Lecture_For_Software_Analysis_and_Design.pdf`, page 21 of 47.
**Learning Aim:** A — Investigate systems analysis and design methodologies.
**Criteria:** P / M / D.

> Continues the "Data and Processes" section (Topic 3, slide 20). Where Topic 3 introduced the three components (Data, Data Flows, Processing Logic), this slide **drills into Data and Data Flows** — how they are described in analysis, and what "flow" really means.

## Slide content (verbatim)

**Data:**
- Understanding the source and use of data is key to good system design.
- Various techniques are used to describe data and the relationship amongst data.

**Data Flows:**
- Groups of data that move and flow through the system.

---

## Pass evidence — describe / identify (P)

### Data — "source and use"

- **Source of data** = *where the data comes from* (external entity, user input, sensor, another system, existing database).
- **Use of data** = *what the system does with it* (store it, transform it, present it back, hand it off).

For every field the system stores you must be able to answer:
1. **Where does it come from?** (source)
2. **How is it validated / cleaned on entry?** (data quality)
3. **Who reads it and why?** (use)
4. **How long do we keep it and how is it disposed of?** (data lifecycle — feeds GDPR compliance, Unit 3 A2 non-functional / A6 professionalism).

### Techniques for describing data and its relationships

| Technique                     | What it shows                                                        | Where in the project            |
| ----------------------------- | -------------------------------------------------------------------- | ------------------------------- |
| **Data Dictionary**           | Every field: name, type, size, allowed values, source, meaning.       | Analysis, before design.        |
| **Entity Relationship Diagram (ERD)** | Entities (things we store) + their relationships + cardinality (1:1, 1:many, many:many). | Analysis → data design.  |
| **Class diagram** (UML)       | For OO systems — classes, attributes, methods and relationships.       | Design.                         |
| **Normalisation (1NF, 2NF, 3NF)** | Removes duplication and update anomalies from a data model.        | Data design.                    |
| **Data model narrative**      | Prose description of the data model for non-technical stakeholders.    | Analysis + review.              |

### Data Flows — "groups of data that move and flow through the system"

- A **data flow** is not one field — it's a **named group** of data that travels together (a "packet") from one part of the system to another.
- Examples:
  - `Order` = { customer id, item id, quantity, price, timestamp } — moves from Customer to Order Processor.
  - `PaymentAuthorisation` = { order id, amount, currency, card token } — moves from Order Processor to Payment Gateway.
- Modelled with **Data Flow Diagrams (DFDs)**:
  - **External entities** (source or sink of data — customer, supplier).
  - **Processes** (transform data).
  - **Data stores** (databases, files).
  - **Data flows** (arrows connecting the above).

---

## Merit evidence — analyse / compare (M)

### Why "source and use" is key to good design

- **Source** determines the shape of validation. Data typed by a human = messy (typos, missing values, wrong format). Data from another system = clean but may drift in schema. Design accordingly.
- **Use** determines the shape of storage and indexes. Data that is written once and read a million times (a product catalogue) is designed differently to data written and read equally (an order log).
- If you don't know where a field comes from or who uses it, **you don't know why it's there** — a data-dictionary review often uncovers fields that survived from an old system and no one reads any more.

### Techniques — how to choose

| If you need to…                                          | Reach for…                                       |
| -------------------------------------------------------- | ------------------------------------------------ |
| Agree the *meaning* of every field with the client        | Data dictionary                                  |
| Show *how entities relate* (one customer → many orders)   | ERD                                              |
| Prove there is no duplication or update anomaly           | Normalisation to 3NF                             |
| Model behaviour + data together (OO)                      | Class diagram                                    |
| Explain the model to a non-technical stakeholder          | Narrative + a simplified ERD                     |

### Data Flows — comparing "field" vs "flow" vs "store"

| Concept       | What it is                          | How long it lives                      | Example                          |
| ------------- | ----------------------------------- | -------------------------------------- | -------------------------------- |
| Field         | One value                            | Whatever the store's lifecycle is.     | `customer_email = "a@b.com"`     |
| **Data flow** | A named group of fields **moving**   | The moment it's in transit.            | `Order = {id, items, total}` on its way to the DB. |
| Data store    | A resting place for data             | Long-lived (until archived/deleted).   | The `orders` table.              |

### Link back to Topic 2 (coupling)

- A well-designed data flow carries **only the fields the receiver needs**. That is loose coupling applied to data.
- A data flow that carries "everything about the customer" to a component that only needs an email → over-sharing → hidden dependencies → tighter coupling.

### Link back to Topic 3 (three components)

- Topic 3 named the components; Topic 4 says *how you actually describe them* on paper: **data dictionary + ERD for data**, **DFD for data flows**, **structured English / decision tables for processing logic** (comes in later slides).

---

## Distinction evidence — evaluate / justify (D)

**Strengths of using these techniques:**
- Data dictionary + ERD + DFD together give a **complete analysis** view of an information system — data at rest (ERD), data in motion (DFD), data at the field level (dictionary).
- They can all be **client-reviewable** — even a non-technical stakeholder can sanity-check an ERD once entities are named in business language.
- They **feed directly into implementation** — the ERD becomes the database schema, the DFD becomes the module boundaries, the data dictionary becomes the input-validation rules.

**Weaknesses / risks:**
- Any one technique used alone is incomplete: an ERD without a DFD hides how data actually moves; a DFD without an ERD hides what is stored.
- The techniques can generate **a lot of paper** — over-modelling on a small project wastes time; under-modelling on a large project creates rework.
- They model the **as-is** system as easily as the **to-be** system — clarity about which one you're drawing is critical (mislabelled diagrams cause requirements confusion).

**Justified judgement (the D-level move):**
On any information-system project, produce **at minimum**:
1. A **data dictionary** for every stored field (source, type, use, retention).
2. An **ERD** (or class diagram for OO systems) for entities and relationships, normalised to at least 3NF unless there is a documented performance reason not to.
3. A **level-0 context DFD** + a **level-1 DFD** for the main data flows.

Cross-check the three: every entity on the ERD must have a data flow that populates it and one that reads it; every data flow must carry fields defined in the dictionary. **Recommend** that this cross-check is done during a walkthrough with the client (Unit 3 C4 defect removal) — the vast majority of missed requirements are caught at this step, and fixing them here costs a fraction of what it costs at UAT (Unit 3 D5).

---

## Applied to a scenario — small computing project (GreenLeaf Cafés OOS)

**Sample data dictionary entry:**

| Field                | Type     | Length | Allowed values           | Source                   | Use                                                | Retention |
| -------------------- | -------- | ------ | ------------------------ | ------------------------ | -------------------------------------------------- | --------- |
| `customer_email`     | string   | 254    | valid email format        | Web checkout form         | Send confirmation; look up loyalty account          | 7 years   |
| `order_total_gbp`    | decimal  | 10,2   | ≥ 0                       | Calculated from lines     | Show to customer; charge to Stripe                  | 7 years   |
| `allergen_flags`     | string[] | 10     | from allergen master list | Product master data       | Display warnings if in customer's alert list        | Live only |

**Sample data flows (level-1 DFD in words):**

```
[Customer] --(Order request: cart, delivery/collect, customer id)--> [Process: Validate Order]
[Process: Validate Order] --(PaymentAuthorisation: total, currency, card token)--> [Stripe]
[Stripe] --(AuthResult: success/fail, transaction id)--> [Process: Confirm Order]
[Process: Confirm Order] --(Order record)--> [D1: Orders store]
[Process: Confirm Order] --(Order confirmation: reference, ETA, receipt)--> [Customer]
[Process: Confirm Order] --(Order notification)--> [Branch staff portal]
```

Each arrow is a data flow. Each name in `{}` above matches an entry in the data dictionary. Each `[D#]` in `[]` is a data store defined in the ERD.

---

## Exam-answer phrases to use

- "Understanding the source of the data determines the validation strategy — data typed by users needs stricter validation than data received from a trusted system."
- "The relationship between Customer and Order is one-to-many, shown on the ERD by a crow's-foot notation, and is enforced in the database by a foreign key on `orders.customer_id`."
- "A data flow is a named group of data moving through the system — for example, the `PaymentAuthorisation` flow carries the order id, amount, currency and card token from the order processor to the payment gateway."
- "During analysis I would produce a data dictionary, an ERD and a level-1 DFD, and cross-check them so that every entity has a flow that populates and reads it."

## Common trap / examiner feedback

- Treating **fields** and **data flows** as the same thing — a data flow is a *group of fields moving together*, not a single field.
- Drawing a DFD that doesn't match the ERD (entities without matching stores; flows carrying fields that aren't defined). Inconsistent models = capped marks.
- Under-specifying the **source** of data — just saying "user" is not enough for validation design.
- Skipping normalisation, then blaming duplication problems on the code.

## Key vocabulary

**Data dictionary, entity relationship diagram (ERD), entity, attribute, relationship, cardinality, normalisation (1NF/2NF/3NF), data flow, data flow diagram (DFD), data store, external entity, process, source, sink, retention.**
