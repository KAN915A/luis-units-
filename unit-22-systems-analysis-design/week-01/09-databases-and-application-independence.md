# Week 1 — Topic 9: Databases and Application Independence

**Source:** `Week_One_Lecture_For_Software_Analysis_and_Design.pdf`, page 27 of 47.
**Learning Aim:** A — Investigate systems analysis and design methodologies.
**Criteria:** P / M / D.

> Explains how the **Data-Oriented Approach** (Topic 8) is actually realised in practice: through a shared, subject-designed **database** and the principle of **application independence** — separating data (and its definition) from the applications that use it.

## Slide content (verbatim)

**Database**
- Shared collection of logically related data.
- Organized to facilitate capture, storage and retrieval by multiple users.
- Centrally managed.
- Designed around subjects — e.g. Customers, Suppliers.

**Application Independence**
- Separation of data and definition of data from applications.

---

## Pass evidence — describe / identify (P)

### Database — every clause unpacked

- **Shared collection of logically related data** — one store used by many applications; the data inside is connected (customers ↔ orders ↔ products), not just piled together.
- **Organised to facilitate capture, storage and retrieval by multiple users** — designed for concurrent read/write by many users at once (locking, transactions, indexes).
- **Centrally managed** — a Database Management System (DBMS) — Oracle, SQL Server, PostgreSQL, MySQL — provides a single point of administration for backups, security, integrity and performance.
- **Designed around subjects, not applications** — the tables model *things the business cares about* (Customer, Supplier, Product, Order) rather than *screens or forms in one app*.

### Application Independence — the principle

- **Separation of data and definition of data from applications.**
- Two things are separated from the app code:
  1. **The data itself** — sits in the database, not embedded in the application.
  2. **The definition of the data** (the schema — tables, columns, constraints, relationships) — held by the DBMS, not hard-coded into any application.
- So the same data + schema serve every application; each application knows about the shared model, but nothing app-specific pollutes it.

---

## Merit evidence — analyse / compare (M)

### Why "designed around subjects" matters

- Business subjects (Customer, Product) live for **decades**; individual applications (the 2018 order-entry app, the 2024 mobile app) live for **years** and are replaced.
- Designing around subjects makes the database **outlive** any single application — you can retire and replace apps without redesigning the data.
- Compare Topic 7: the Process-Oriented Approach designs files per application → files die when the app dies.

### Application Independence — what changes vs the process-oriented style

| Concern                              | Application-tied files (Process-Oriented) | Database + application independence (Data-Oriented) |
| ------------------------------------ | ----------------------------------------- | ---------------------------------------------------- |
| Where does the data live?             | Inside each app's own files.               | In one shared database.                              |
| Where does the schema live?           | Hard-coded per app.                        | In the DBMS's data dictionary.                       |
| What happens if the app is retired?   | Data structure is lost / needs migrating.  | Data + schema stay; new app can attach.               |
| What if two apps need the same field? | Two copies; drift.                         | One column; both apps read/write the same value.     |
| Who administers backups/security?     | Each app team.                             | The DBA, centrally.                                  |

### Why "shared + centrally managed" matters

- **Consistency** — everyone sees the same customer record; no divergent copies.
- **Integrity** — DBMS constraints (primary keys, foreign keys, check constraints) enforce business rules once, not in every application.
- **Security + audit** — access control and audit logging in one place.
- **Backup + recovery** — one plan, tested once.

### Link back to earlier topics

- **Topic 2 (coupling/cohesion):** application independence is loose coupling between applications and data — apps depend only on the *interface* to the data (the schema), not on internal storage or on each other.
- **Topic 4 (data + techniques):** the data dictionary and ERD produced in analysis become the *schema* of the shared database in design.
- **Topic 8 (Data-Oriented Approach):** this slide is *how* Table 1.1's "enterprise data files" and "controlled duplication" get delivered in practice — via a shared database with application independence.

---

## Distinction evidence — evaluate / justify (D)

**Strengths of a shared database with application independence:**
- One source of truth → **data consistency** across the organisation.
- **Data quality** improves because constraints live in one place.
- **Reduced duplication** and reduced storage cost.
- **Faster new-app development** — new applications reuse the existing schema instead of designing their own storage.
- **Easier compliance** (GDPR data-subject requests, retention policies) — you know where every field lives.

**Weaknesses / trade-offs:**
- **Central bottleneck** — the DBMS becomes critical infrastructure; downtime affects every application.
- **Governance overhead** — schema changes need coordination across every application that uses them; slower to change.
- **Performance concerns** — one shared DB has to serve every workload; may need read replicas, caches, or partitioning.
- **Political friction** — no single application team "owns" the data model; requires a data steward.

**Justified judgement (the D-level move):**

For any system with **more than one application touching the same real-world subject** (customer, product, order), a **shared database with application independence** is the right answer. Justify with Table 1.1 rows 3–4: enterprise data organisation + controlled duplication are only achievable with a shared, centrally managed database.

For a truly one-off single-app system, an embedded / per-app store is proportionate — but the moment a second application appears (mobile app, reporting, integration) the data-oriented approach earns back its up-front cost.

**Recommend** three concrete practices in the assignment:
1. Publish and version the **schema** as the interface — applications code against it, not against each other's tables.
2. Enforce integrity in the **DBMS** (constraints, foreign keys, checks), not in each app.
3. Nominate a **data steward** for each subject (Customer, Product) responsible for approving schema changes and setting quality rules.

These operationalise application independence — otherwise it stays an ideal on a slide.

---

## Applied to a scenario — GreenLeaf Cafés OOS

**Database designed around subjects, not apps:**

| Subject       | Sample attributes                                            | Applications that use it                            |
| ------------- | ------------------------------------------------------------ | --------------------------------------------------- |
| **Customer**  | id, name, email, loyalty tier, marketing preferences.         | Ordering app, marketing, support portal, GDPR tool. |
| **Product**   | id, name, price, allergens, active flag, category.            | Ordering app, menu display, procurement, reporting. |
| **Order**     | id, customer id, branch id, items, total, status, timestamps. | Ordering app, staff portal, reporting, finance.     |
| **Branch**    | id, name, address, opening hours.                             | Ordering app, staff portal, HR.                     |
| **Payment**   | id, order id, amount, provider ref, status.                   | Ordering app, finance, refunds.                     |

**Application independence in action:**
- The Ordering app **reads/writes** Customer and Order.
- The Marketing tool **reads** Customer (loyalty tier, marketing preferences).
- The GDPR export tool **reads** every subject and produces a per-customer export.
- No app owns any subject exclusively; the schema is the shared contract.

**Recommendation:** run this on a managed relational DBMS (PostgreSQL or SQL Server) with a documented ERD, versioned schema migrations, and a nominated data steward for Customer and Product. Justify: without these three the theoretical benefit collapses into practice-tied files (Topic 7 disadvantage).

## Exam-answer phrases to use

- "A database is a shared collection of logically related data, organised to facilitate capture, storage and retrieval by multiple users, and centrally managed."
- "Databases are designed around subjects — for example customers or suppliers — so that the data outlives any single application."
- "Application Independence is the separation of the data, and the definition of the data, from the applications that use it."
- "Application independence is the practical mechanism by which the Data-Oriented Approach (Table 1.1) achieves enterprise-wide data organisation and controlled duplication."

## Common trap / examiner feedback

- Defining a database as "a file that stores information" — misses the four spec bullets (shared, multi-user, centrally managed, designed around subjects).
- Confusing **database** with **database management system (DBMS)** — the database is the *data*; the DBMS is the *software* that manages it.
- Treating application independence as just "putting data in a separate file" — the point is that the **definition of the data** (the schema) is also separated, so many apps can share it.
- Failing to name the subjects — the spec explicitly lists Customers and Suppliers as examples; use them.

## Key vocabulary

**Database, shared data, centrally managed, subject-oriented design, database management system (DBMS), schema, data dictionary, application independence, data steward, primary key, foreign key, constraint, integrity.**
