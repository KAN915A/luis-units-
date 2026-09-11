# Week 1 — Topic 7: Approaches to Systems Development — Process-Oriented Approach

**Source:** `Week_One_Lecture_For_Software_Analysis_and_Design.pdf`, page 24 of 47.
**Learning Aim:** A — Investigate systems analysis and design methodologies.
**Criteria:** P / M / D.

> First of two "approaches" the lecture covers. The Process-Oriented Approach looks at a system through the lens of **what data flows through it and how it is transformed**. (The Data-Oriented Approach — the counterpart — comes on the next slide.)

## Slide content (verbatim)

**Process-Oriented Approach**
- Focus is on flow, use and transformation of data in an information system.
- Involves creating graphical representations such as data flow diagrams and charts.
- Data are tracked from sources, through intermediate steps and to final destinations.
- Natural structure of data is not specified.
- Disadvantage: data files are tied to specific applications.

---

## Pass evidence — describe / identify (P)

- **Process-Oriented Approach** = a way of analysing and designing systems that puts **processes** (the transformations of data) at the centre.
- **Main tools:** Data Flow Diagrams (DFDs), context diagrams, flowcharts, process specifications (structured English / pseudocode).
- **What the analyst asks:** *What data enters the system? How is it transformed? Where does it end up?*
- **Data is tracked** from **source** (external entity) → **intermediate steps** (processes) → **final destination** (data store or external entity).
- **The natural structure of data is not specified** — the approach describes how data moves, but not how it should be stored efficiently or without duplication.
- **Disadvantage:** because data structure follows the processes, **data files become tied to specific applications** — the same customer record may appear in different formats in the sales file and the invoicing file.

## Merit evidence — analyse / compare (M)

### Strengths of the Process-Oriented Approach

- Very good at showing **how a business actually works** — following a sales order from customer to shipment, for example.
- Familiar and intuitive for clients — a DFD is easy to walk a stakeholder through.
- Aligns with the **waterfall SDLC** (Unit 3 D1) — requirements → design → build → test → deploy, each stage producing a set of DFDs and process specifications.
- Good for automating existing manual processes because it mirrors the paperwork flow.

### Weaknesses

- **Application-tied data:** the same real-world "customer" ends up modelled differently in the ordering app, the invoicing app and the CRM app. Result: **duplication**, **inconsistency**, **update anomalies**.
- **Change is expensive:** if a business process changes (a new step, a merged step), the DFD, process specs and data files all move together — many things to change.
- **Data quality suffers** because there is no single owner for "the customer record" — each application owns its own copy.
- **Poor fit for OO / reusable systems** — process-oriented modelling doesn't naturally produce shareable entities.

### Compare — Process-Oriented vs Data-Oriented (preview)

| Question                              | Process-Oriented approach                         | Data-Oriented approach (next slide)               |
| ------------------------------------- | ------------------------------------------------- | ------------------------------------------------- |
| What sits at the centre?              | Processes and data flows.                          | Data structure (entities, relationships).         |
| Main tool                              | Data Flow Diagram (DFD).                           | Entity Relationship Diagram (ERD).                 |
| Best at                                | Modelling business processes.                     | Modelling shared, long-lived data.                 |
| Common weakness                        | Application-tied data files, duplication.          | Weaker at showing dynamic behaviour / triggers.    |
| When to prefer                          | Automating an existing manual process.             | Multiple applications share the same data.         |

### Link back to earlier topics

- **Topic 5 (data flows + processing logic)** — the Process-Oriented Approach *is* the systematic use of DFDs + process specifications.
- **Topic 6 (Fig 1.8)** — the credit-card diagram in Fig 1.8 is a small piece of Process-Oriented analysis.
- **Topic 2 (coupling/cohesion)** — the "data-files-tied-to-applications" weakness is a coupling problem: business processes and their data are tightly coupled, so a change to one drags the other.

---

## Distinction evidence — evaluate / justify (D)

- **Strengths:** intuitive, communicates well with business stakeholders, produces artefacts (DFDs, process specs) that map cleanly to code and test cases, aligns with waterfall stage gates and Unit 3 C4 quality management (testing against each specification).
- **Weaknesses:** encourages duplicated, application-tied data; makes cross-system reporting hard; struggles when the same real-world entity is used in many processes; harder to refactor because process and data change together.
- **Justified judgement (the D-level move):**
  For a **small, self-contained system** that automates one business process (e.g. a single payroll run), the Process-Oriented Approach is proportionate — its intuitive artefacts justify the approach and the duplication risk is small.
  For a **shared, cross-application system** (e.g. a customer database used by ordering, invoicing and support), **do not use Process-Oriented alone** — pair it with a Data-Oriented model, or move to a Data-Oriented / Object-Oriented approach. **Recommend** always producing the **ERD alongside the DFD** even on a process-heavy project, precisely to prevent the data-files-tied-to-applications weakness the slide names.
  Cite Unit 3 D4 (change management) as evidence: systems that couple data to processes generate more change requests over their lifetime because every business tweak triggers a data change too.

---

## Applied to a scenario — small computing project

**Where a Process-Oriented Approach fits GreenLeaf Cafés OOS:**
- The customer's *ordering process* — from cart to confirmation — is a clean workflow well-suited to DFD analysis.
- But the same *customer* is used by loyalty, marketing, GDPR data-subject requests, and post-purchase support. A pure process-oriented approach would end up with a separate "customer" file per app.
- **Best fit here:** hybrid — use the Process-Oriented Approach for the ordering *workflow*, but back it with a shared customer / product ERD so data is owned once.

## Exam-answer phrases to use

- "The Process-Oriented Approach focuses on the flow, use and transformation of data through the system, and uses Data Flow Diagrams as its main modelling tool."
- "A key disadvantage of the Process-Oriented Approach is that data files become tied to specific applications, resulting in duplication and inconsistency."
- "This approach tracks data from its source through intermediate processing steps to its final destination."
- "For a shared-data system I would recommend supplementing the process-oriented DFDs with an ERD, in order to avoid the application-tied-data weakness."

## Common trap / examiner feedback

- Saying the Process-Oriented Approach is "old-fashioned" and dismissing it — it's still the right tool for many business-process automation problems, and BTEC markers expect a balanced evaluation.
- Confusing the Process-Oriented Approach with process-oriented **programming languages** — they're unrelated.
- Missing the specific spec disadvantage: **"data files are tied to specific applications"** — a common exam question asks for this exact weakness.

## Key vocabulary

**Process-oriented approach, data flow diagram (DFD), context diagram, process specification, source, destination, application-tied data, data duplication, waterfall SDLC.**
