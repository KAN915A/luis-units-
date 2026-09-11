# Week 1 — Topic 13: Fig. 1.12 — Four Classes of Information Systems (TPS, MIS, DSS, ES)

**Source:** `Week_One_Lecture_For_Software_Analysis_and_Design.pdf`, page 34 of 47 (Figure 1.12).
**Learning Aim:** A — Investigate systems analysis and design methodologies.
**Criteria:** P / M / D.

> Overview figure. Puts the four classic classes of business information system on one page and shows how they **feed each other** (data from TPS → MIS; MIS + DSS support managers; ES supports specialists). ES was covered in Topic 12; this topic introduces **TPS, MIS, DSS** and ties all four together.

## Slide content (verbatim)

**Figure 1.12 — Depictions of Four Classes of Information Systems: TPS, MIS, DSS, and ES**

Illustrations show:
- **Transaction Processing Systems (TPS)** — cashier at a point-of-sale + a call-centre agent — data flowing into a computer.
- **Management Information Systems (MIS)** — a manager reviewing "Last month's sales…" reports. Arrow labelled **(from TPS)** feeds MIS.
- **Decision Support Systems (DSS)** — a manager asking "What if?" over charts and graphs.
- **Expert Systems (ES)** — a specialist reading a diagnosis: "There is a .78 probability that the infection is streptococcus."

---

## Pass evidence — describe / identify (P)

### The four classes at a glance

| Class    | Full name                          | Who uses it                                 | What it does                                                               | Example                                       |
| -------- | ---------------------------------- | ------------------------------------------- | -------------------------------------------------------------------------- | --------------------------------------------- |
| **TPS**  | Transaction Processing System      | Operational staff (cashiers, clerks)        | Captures the day-to-day transactions of the business.                       | Point-of-sale, order entry, payroll run.       |
| **MIS**  | Management Information System      | Middle managers                              | Aggregates TPS data into **routine reports** for monitoring performance.    | Monthly sales report, weekly stock report.     |
| **DSS**  | Decision Support System            | Managers making non-routine decisions       | Provides **interactive analysis** (what-if, sensitivity, models) to support decisions. | Pricing model, capacity planner, forecasting tool. |
| **ES**   | Expert System                      | Non-experts / specialists in a narrow domain | **Replicates expert reasoning** using rules and knowledge representation.    | Medical triage, credit scoring, fault-finder.  |

(ES is covered in depth in [Topic 12](./12-types-of-information-systems-expert-systems.md).)

### How they feed each other (the arrows on Fig 1.12)

```
       Operational events
              │
              ▼
        ┌───────────┐   (from TPS)
        │    TPS    │ ─────────────┐
        └────┬──────┘              │
             │                     ▼
             │              ┌───────────┐
             │              │    MIS    │  ← routine reports
             │              └────┬──────┘
             │                   │
             │                   ▼
             │              ┌───────────┐
             └─────────────▶│    DSS    │  ← "What if?"
                            └───────────┘

        ┌───────────┐
        │    ES     │  ← specialist decision aid
        └───────────┘   (largely standalone; may consume TPS or DBs)
```

The single most examined idea in Fig 1.12: **data captured by the TPS is what feeds MIS and (often) DSS**. Without the TPS, higher-level systems have nothing to report on.

---

## Pass evidence — describe / identify (P), per class

### Transaction Processing System (TPS)

- **Purpose:** capture and record the routine business transactions — orders, payments, deliveries, timesheets, stock movements.
- **Users:** operational staff.
- **Volume:** high — thousands or millions of transactions per day.
- **Response requirement:** fast, reliable, 24/7 where the business operates round-the-clock.
- **Design priorities:** integrity, throughput, availability, auditability.

### Management Information System (MIS)

- **Purpose:** turn TPS-captured data into **routine, structured reports** — daily/weekly/monthly summaries and dashboards.
- **Users:** middle managers monitoring the business.
- **Reports are pre-defined** (last month's sales by region, top-10 products, cash position).
- **Data source:** TPS (mostly); may pull from other operational systems.
- **Nature of the decisions supported:** structured, recurring, "how are we doing?" questions.

### Decision Support System (DSS)

- **Purpose:** support **non-routine, semi-structured decisions** where the manager needs to explore alternatives — "what if we lowered the price by 5%?", "what if demand grew 20% next quarter?".
- **Users:** managers and analysts.
- **Interactive** — the user changes inputs and sees outcomes ("what-if" scenarios); often includes charts, sensitivity analysis, models.
- **Data source:** TPS + external data (market prices, forecasts) + user-supplied assumptions.
- **Nature of the decisions supported:** one-off, exploratory, model-driven.

---

## Merit evidence — analyse / compare (M)

### Where the classes sit on the "level of decision" scale

| Level                | Class     | Question the user is asking                                     |
| -------------------- | --------- | --------------------------------------------------------------- |
| Operational          | **TPS**   | *"Record this sale."*                                            |
| Tactical             | **MIS**   | *"How are we doing this month vs last?"*                         |
| Strategic / analytic | **DSS**   | *"What happens if we change X?"*                                 |
| Specialist / expert  | **ES**    | *"Given these symptoms, what should I conclude and why?"*        |

### Why the TPS is the foundation

- Every higher-level system depends on the **quality and completeness of the TPS data**. Rubbish in, rubbish out.
- If the TPS misses a transaction or records it wrong, the MIS report shows wrong totals and the DSS what-if is meaningless.
- A well-run TPS is the invisible plumbing — dull to build, essential to trust.

### Why MIS and DSS are distinct (a very common exam question)

| Feature                | MIS                                          | DSS                                                         |
| ---------------------- | -------------------------------------------- | ----------------------------------------------------------- |
| Report type            | Fixed, routine, pre-defined                   | Ad-hoc, exploratory                                          |
| User interaction       | View / drill down                             | Actively change inputs, see outcomes                        |
| Question shape         | *"What happened?"*                            | *"What if?"*                                                 |
| Decision type supported | Structured, recurring                        | Semi-structured, one-off                                    |
| Frequency of use        | Daily / weekly / monthly                     | As-needed, when a decision is being taken                    |
| Time horizon            | Past / present                                | Future scenarios                                             |

### Why ES stands slightly to the side

- ES is not driven by TPS data volume — it's driven by **encoded expert rules**.
- Its users are often *non-managers* (a doctor, a mortgage clerk, a helpdesk agent) applying an expert's reasoning.
- Its distinctive feature is an **explanation facility** (Topic 12) — MIS/DSS don't need this because their users are already experts in interpreting the numbers.

### Link back to earlier topics

- **Topic 3 (data / data flow / processing logic):** each of the four classes weights the three components differently — TPS is heavy on **data + data flows**; DSS is heavy on **processing logic + models**; ES is heavy on **processing logic (rules)**.
- **Topic 7 (Process-Oriented Approach):** TPS design fits process-oriented analysis very well — workflows dominate.
- **Topic 8 (Data-Oriented Approach):** MIS + DSS benefit hugely from a **shared enterprise data model** (Topic 9) — one canonical Customer/Product/Order used by all reporting and analytic tools.
- **Topic 10 (analyst role):** the analyst decides *which class the client actually needs* — a common failure is building an MIS when the client really wanted a DSS.

---

## Distinction evidence — evaluate / justify (D)

**Strengths of separating the classes in analysis:**
- **Clarity of purpose** — each system has a defined user, question, and design priority. A TPS built as if it were a DSS is slow and unreliable; a DSS built as if it were a TPS is inflexible.
- **Feeds directly into the sourcing decision** (bespoke build vs off-the-shelf package): TPS = often mature packages; MIS = reporting tools or BI stack; DSS = spreadsheet or bespoke; ES = niche.
- **Makes the data pipeline visible** — the "from TPS" arrow shows where data must flow *between* systems.

**Weaknesses / trade-offs:**
- The **boundaries blur in real life** — a modern point-of-sale platform bundles TPS + real-time dashboards (MIS) + basic what-if (DSS) in one product. Rigidly labelling every feature is not always useful.
- Emphasising the four classes as separate systems can lead to **data silos** (Topic 8's application-tied data problem). Modern architectures fix this with a shared data model or data warehouse feeding both MIS and DSS.
- ES has evolved into machine-learning-based decision aids, blurring the line with modern AI — use the term carefully in current writing.

**Justified judgement (the D-level move):**

For any assignment scenario, ask **which of the four classes does the client actually need**, and evaluate:

1. **Volume + reliability requirement** → is it a TPS? If yes, prioritise integrity and throughput.
2. **Do managers need routine reports?** → MIS on top of the TPS data.
3. **Do managers need "what-if" analysis or scenario modelling?** → DSS, backed by TPS data plus external inputs.
4. **Is there a narrow domain where an expert's reasoning could be captured as rules?** → consider an ES component (Topic 12 conditions apply).

**Recommend** designing the four classes **around a shared data model** (Topic 9) rather than as isolated systems — otherwise the "TPS → MIS" arrow in Fig 1.12 becomes an expensive integration project. Justify with Table 1.1 (Topic 8): data-oriented design gives enduring, low-duplication foundations across all four classes.

For GreenLeaf-style scenarios, the OOS itself is a **TPS**, immediately followed by an **MIS** (weekly sales dashboard). Adding a **DSS** (menu-mix pricing model) later is a natural evolution; an **ES** would fit only for the narrow allergen-recommender use case.

---

## Applied to a scenario — GreenLeaf Cafés

| Class | GreenLeaf realisation                                                                                                    | Why this class fits                                       |
| ----- | ------------------------------------------------------------------------------------------------------------------------ | --------------------------------------------------------- |
| TPS   | The **Online Ordering System (OOS)** — captures every order, payment and confirmation across all 12 branches.             | High volume, real-time, reliability critical.             |
| MIS   | **Daily branch sales dashboard + weekly management pack** — pulls from OOS transactions.                                  | Routine, pre-defined reports for branch and area managers.|
| DSS   | **Menu-mix pricing model** — spreadsheet with what-if: "if we drop bacon roll to £4, forecast revenue impact by branch."   | Non-routine, exploratory, "what if?" decisions.           |
| ES    | **Allergen-safe recommender** (Topic 12) — encodes the food-safety expert's rules to recommend safe menu items.            | Narrow domain, rule-based, needs explanation to customer. |

## Exam-answer phrases to use

- "Figure 1.12 shows the four classic classes of information system — TPS, MIS, DSS and ES — and how transaction data captured by the TPS is fed into the MIS (labelled 'from TPS' in the figure)."
- "A TPS answers *record this transaction*; an MIS answers *what happened?*; a DSS answers *what if?*; an ES answers *given these facts, what should I conclude and why?*"
- "The MIS and DSS both depend on the quality of the TPS data — the TPS is the foundation of the reporting and analytic layers."
- "The core distinction between an MIS and a DSS is that an MIS produces **routine, pre-defined reports** whereas a DSS supports **ad-hoc, what-if analysis**."

## Common trap / examiner feedback

- Confusing MIS and DSS — memorise the "what happened?" vs "what if?" split.
- Forgetting to mention the **feeder arrow** — Fig 1.12 explicitly shows MIS fed *from TPS*; markers look for this data-flow point.
- Treating the four classes as competing options — they are **complementary**; a well-run business runs all four.
- Saying "any decision-support tool is a DSS" — a routine dashboard is an MIS, not a DSS. DSS implies **interactive modelling** or **what-if analysis**.
- Ignoring the shared-data-model recommendation — leads back to the Topic 7 application-tied-data weakness.

## Key vocabulary

**Transaction Processing System (TPS), Management Information System (MIS), Decision Support System (DSS), Expert System (ES), routine report, ad-hoc analysis, what-if analysis, sensitivity analysis, structured decision, semi-structured decision, operational level, tactical level, strategic level, data warehouse, business intelligence (BI).**
