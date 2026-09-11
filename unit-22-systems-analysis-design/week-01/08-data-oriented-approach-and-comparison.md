# Week 1 — Topic 8: Data-Oriented Approach & the Process vs Data comparison (Table 1.1)

**Source:** `Week_One_Lecture_For_Software_Analysis_and_Design.pdf`, page 26 of 47 (Table 1.1).
**Learning Aim:** A — Investigate systems analysis and design methodologies.
**Criteria:** P / M / D.

> Pairs with Topic 7 (Process-Oriented Approach). This slide is **Table 1.1** — the side-by-side comparison of the two approaches on four characteristics. Together, Topics 7 + 8 cover the classic two-approach dichotomy at the start of Unit 22.

## Slide content (verbatim) — Table 1.1

**Key Differences between the Process-Oriented and Data-Oriented Approaches to Systems Development**

| Characteristic       | Process Orientation                                                                              | Data Orientation                                                                |
| -------------------- | ------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------- |
| **System focus**     | What the system is supposed to do and when                                                       | Data the system needs to operate                                                |
| **Design stability** | Limited, because business processes and the applications that support them change constantly    | More enduring, because the data needs of an organization do not change rapidly  |
| **Data organization**| Data files designed for each individual application                                              | Data files designed for the enterprise                                          |
| **State of the data**| Much uncontrolled duplication                                                                    | Limited, controlled duplication                                                 |

---

## Pass evidence — describe / identify (P)

### Data-Oriented Approach — what it is

- A way of analysing and designing systems that puts the **data** at the centre — the entities the organisation cares about (customer, product, order, employee) and their relationships.
- **Main tools:** Entity Relationship Diagrams (ERDs), data dictionaries, normalisation, class diagrams.
- **What the analyst asks:** *What entities exist, what attributes do they have, how do they relate, and how can they be stored once and used by many applications?*
- The **enterprise** — not any single application — owns the data model. Applications are consumers of the shared data.

### The four characteristics in one line each

- **System focus:** Process = *what the system does and when*. Data = *the data the system needs to operate*.
- **Design stability:** Process = *unstable* (business processes change constantly). Data = *more enduring* (data needs change slowly).
- **Data organisation:** Process = *per-application files*. Data = *enterprise-wide files*.
- **State of the data:** Process = *much uncontrolled duplication*. Data = *limited, controlled duplication*.

## Merit evidence — analyse / compare (M)

### Why each row matters

**System focus** — the choice of focus decides the *primary modelling artefact*:
- Process focus → DFDs, process specs, structured English.
- Data focus → ERDs, data dictionaries, normalisation, class diagrams.
Neither is wrong; the fit depends on whether the *processes* or the *data* is the harder-to-get-right part of the problem.

**Design stability** — this is the killer argument for a data-oriented approach on any long-lived system:
- Business rules change often (promotions, tax rates, workflow tweaks).
- Data needs change slowly (a customer is still a customer with a name, address and contact preferences in five years).
- A design that is **stable at the data layer** and **flexible at the process layer** ages better than the other way round.

**Data organisation — enterprise vs application:**
- **Application-tied data** (process approach): sales app has its own customer file, invoicing app has its own, CRM has its own. Same real-world customer, three inconsistent copies.
- **Enterprise data** (data approach): one canonical customer entity, used by every application through a shared data store or database.

**State of the data — controlled vs uncontrolled duplication:**
- The data-oriented approach does not eliminate duplication (some is necessary for performance, reporting, or offline use). It **controls** it: where a copy exists, who owns the source, how it is synchronised.
- The process-oriented approach **doesn't reason about duplication at all** — it just appears as a by-product of each application designing its own files.

### Link back to earlier topics

- **Topic 2 (coupling/cohesion):** the data-oriented approach reduces coupling between applications (they all talk to the same shared data model) and increases cohesion within the data model itself (each entity has one clear responsibility).
- **Topics 4–5 (data + processing logic):** the data-oriented approach doesn't drop processing logic — it just moves it into services that operate on the shared data, not into the data files themselves.
- **Topic 7 (Process-Oriented Approach):** Table 1.1 is essentially a formal statement of the weaknesses named on slide 24 ("data files tied to specific applications") and their remedy.

---

## Distinction evidence — evaluate / justify (D)

**Strengths of the Data-Oriented Approach:**
- **Design endures.** Business processes change every year; data needs change every decade.
- **Reduces duplication and inconsistency** — one canonical customer record, one canonical product record.
- **Enables cross-application reporting** — you can query "all orders by all customers across all channels" because it's all in the same model.
- **Fits modern architectures** — a shared database, service layer, data warehouse — all rely on an enterprise data model.

**Weaknesses / trade-offs:**
- **Slower to start.** Modelling the entire enterprise's data takes analysis time before any single application delivers value — pushback from stakeholders who want a quick win.
- **Weaker at describing *dynamic* behaviour** — ERDs show what is stored, not what happens or when. You still need process modelling on top.
- **Change ownership is political.** Who "owns" the customer record when Sales, Marketing and Support all use it? Requires governance.

**Justified judgement (the D-level move):**

For a **small, one-off application** that doesn't share data with anything else (e.g. a single-use booking system for one event), a **Process-Oriented Approach is proportionate** — the design-stability weakness doesn't have time to bite.

For **any long-lived, multi-application enterprise system** (e.g. a customer database used by ordering, invoicing, marketing, support) the **Data-Oriented Approach is the right primary approach**, backed by process-oriented artefacts (DFDs, structured English) for the workflows on top.

In practice, most real projects use a **hybrid**: a Data-Oriented core (ERD, normalised data model, single source of truth) with Process-Oriented artefacts for each workflow (DFDs, process specs). **Recommend** starting an assignment with a **data model first** so the enterprise view is captured, then adding DFDs *per workflow* — this maximises design stability (Table 1.1 row 2) while keeping the DFD's readability for stakeholders (Topic 7).

Cite the four Table 1.1 rows explicitly in the justification — the marker rewards direct use of the spec.

---

## Applied to a scenario — small computing project (GreenLeaf Cafés OOS)

**How Table 1.1 plays out at GreenLeaf:**

| Characteristic       | If GreenLeaf goes pure Process-Oriented                                  | If GreenLeaf goes Data-Oriented                                                     |
| -------------------- | ----------------------------------------------------------------------- | ----------------------------------------------------------------------------------- |
| System focus         | Focus on the *ordering workflow* (cart → pay → confirm).                 | Focus on *customer, product, order, payment* entities.                              |
| Design stability     | New promo? Loyalty tier changes? Rebuild ordering workflow every time.   | Add promotion / loyalty entities to the model; workflow taps them.                  |
| Data organisation    | Ordering app has one customer file; marketing app has another; support has a third. | One customer entity, used by ordering, marketing, support alike.                    |
| State of the data    | Three copies of every customer, all drifting.                            | One canonical customer, cached copies where needed with a documented refresh rule.  |

**Recommendation for GreenLeaf:** hybrid — Data-Oriented core (single customer, product, order, payment ERD) plus Process-Oriented DFDs for the ordering workflow and staff fulfilment workflow. Justify with Table 1.1 rows 2–4: for a 12-branch chain expecting future add-ons (loyalty, delivery), the shared data model earns its cost within the first change request.

## Exam-answer phrases to use

- "The Process-Oriented Approach focuses on *what the system does and when*, whereas the Data-Oriented Approach focuses on *the data the system needs to operate* (Table 1.1)."
- "Data-oriented designs are more enduring because the data needs of an organisation do not change rapidly, while the business processes that use the data change constantly (Table 1.1 row 2)."
- "The process-oriented approach organises data files per individual application, causing much uncontrolled duplication; the data-oriented approach organises data files for the enterprise, keeping duplication limited and controlled."
- "I would recommend a hybrid — a data-oriented core supported by process-oriented workflows — because it maximises design stability while retaining stakeholder-friendly process diagrams."

## Common trap / examiner feedback

- Treating the two approaches as **opposites you must pick between** — the exam rewards a *hybrid* recommendation, justified.
- Copying the Table 1.1 rows without linking them to a scenario — the marker wants you to *use* the table, not restate it.
- Saying "data-oriented is better" without qualifying it — for a genuinely one-off application, process-oriented is still the right choice.
- Forgetting to name the four characteristics (system focus, design stability, data organisation, state of the data) — these are the rows the marker will look for.

## Key vocabulary

**Data-oriented approach, enterprise data model, entity, relationship, normalisation, canonical record, single source of truth, controlled duplication, application-tied data, design stability, governance, hybrid approach.**
