# Week 1 — Topic 12: Types of Information Systems — Expert Systems (ES)

**Source:** `Week_One_Lecture_For_Software_Analysis_and_Design.pdf`, page 33 of 47.
**Learning Aim:** A — Investigate systems analysis and design methodologies.
**Criteria:** P / M / D.

> Opens a new section: **Types of Information Systems and Systems Development**. The lecture works through the standard categories one at a time. This slide introduces the first — **Expert Systems (ES)**. Other types (TPS, MIS, DSS, EIS, Office Automation) come on later slides.

## Slide content (verbatim)

**Expert Systems (ES)**
- Replicates decision-making process.
- Knowledge representation describes the way an expert would approach the problem.

---

## Pass evidence — describe / identify (P)

### Expert System — definition

An **Expert System (ES)** is a computer system that *replicates the decision-making process of a human expert* in a narrow, specialised domain. It applies rules and stored knowledge to input facts to reach a conclusion or recommendation.

### The two building blocks named on the slide

1. **Decision-making process** — the sequence of reasoning steps an expert would follow to reach a conclusion.
2. **Knowledge representation** — the way the system encodes what the expert *knows*, in a form the computer can reason over.

### Typical architecture (context — helps at Merit/Distinction level)

- **Knowledge base** — the rules and facts elicited from the human expert (often IF–THEN rules).
- **Inference engine** — the reasoning mechanism that applies rules to input facts.
- **User interface** — how a non-expert user asks questions and receives answers, often with an **explanation facility** ("why did you conclude that?").
- **Knowledge acquisition module** — the tools the knowledge engineer uses to capture and edit the knowledge base.

### Classic examples

- Medical diagnosis assistants (rule-based diagnosis from symptoms).
- Loan / credit approval systems (encoded lending rules).
- Fault-finding wizards (guided troubleshooting for helpdesk staff).
- Configuration systems (recommending a product setup given user requirements).

## Merit evidence — analyse / compare (M)

### Why "replicates the decision-making process" is a strong claim

- The ES doesn't just retrieve data — it applies **reasoning** encoded from a human expert to reach a *decision*.
- It captures the expert's **know-how**, not just their facts. Facts alone would be a database; know-how + reasoning is what makes it "expert".

### Why knowledge representation matters

- The expert's knowledge often lives as **experience, intuition and rules of thumb** — hard to write down.
- **Knowledge representation** turns that tacit knowledge into a form the computer can reason over — typically:
  - **Rules** (IF the symptom is X AND the test result is Y THEN diagnosis is Z with confidence C).
  - **Frames** (structured records of concepts and their attributes).
  - **Ontologies** (formal descriptions of the domain's concepts and relationships).
  - **Decision trees / tables** (compact for narrow rule sets — links to Topic 5).

### Comparison with a regular information system

| Concern             | Regular information system                          | Expert System                                                 |
| ------------------- | --------------------------------------------------- | ------------------------------------------------------------- |
| What it does         | Captures, stores, retrieves and reports data.       | Replicates an expert's decision-making.                       |
| Knowledge inside     | Data + processing logic for known transactions.     | Rules encoding an expert's reasoning about a narrow domain.   |
| Output               | Reports, screens, records.                          | Recommendations, diagnoses, decisions, explanations.          |
| Handles ambiguity?    | Poorly — designed for known inputs.                | Better — can weigh uncertain evidence via confidence factors. |

### Link back to earlier topics

- **Topic 3 (data / information / processing logic):** an ES is unusual in that most of its value sits in the *processing logic* (the rules), not the data.
- **Topic 5 (steps + triggers):** an ES's rules are a highly structured form of processing logic — closer to a decision table than to a workflow.
- **Topic 10 (analyst role):** analysts for ES projects are often called **knowledge engineers** — their fact-finding technique of choice is **structured interviewing** of the domain expert.
- **Unit 3 A2 (quality):** ES quality is judged not by uptime alone but by **decision accuracy** vs the human expert; test scenarios come from real historical cases.

---

## Distinction evidence — evaluate / justify (D)

**Strengths of Expert Systems:**
- **Consistency** — the system applies the same rules every time; no bad-day judgement calls.
- **Availability** — 24/7 access to expert-quality reasoning without the human being present.
- **Scale** — one captured expert can serve thousands of users simultaneously.
- **Explainability (traditionally)** — rule-based ES can *explain* their reasoning ("Because rule R42 fired given symptoms S1 and S3") — an important advantage over black-box AI models in regulated domains.
- **Knowledge preservation** — captures know-how that would otherwise leave the organisation when the expert retires.

**Weaknesses / risks:**
- **Narrow domain.** ES perform poorly outside the domain they were built for; edge cases they weren't shown break them silently.
- **Knowledge-acquisition bottleneck.** Extracting rules from a busy expert takes months, and experts often can't articulate their tacit reasoning.
- **Rule-base rot.** Rules go stale as regulations, products or best practices change; needs a maintenance owner.
- **Over-reliance risk.** Users may trust the ES's recommendation without checking, particularly non-experts — dangerous in medical or financial contexts.
- **Ethical/legal accountability.** Who is responsible when the ES's recommendation is wrong? Often unclear.

**Justified judgement (the D-level move):**

Expert Systems are the right choice when **all four** of the following hold:
1. The domain is **narrow and well-defined** (medical triage, credit scoring, fault-finding — not "give me business advice").
2. There is a real human expert whose reasoning can be **explicitly captured** in rules.
3. The decisions the system produces need to be **consistent, explainable, and auditable** (regulated industries in particular).
4. There is a **maintenance owner** who will keep the rule base current.

If any of the four is missing, an ES is a poor choice — either a simpler information system will do, or the problem needs full machine learning rather than rule-based ES.

**Recommend** always designing an ES with:
- An **explanation facility** so users can see why a recommendation was made — needed for auditability and for user trust.
- A **human-in-the-loop** for decisions with significant consequences (loan denial, medical diagnosis).
- A **rule-base review cadence** (e.g. quarterly) baked into operations (Unit 3 E1 move into operation and maintenance).

These operationalise the strengths and mitigate the weaknesses.

---

## Applied to a scenario — GreenLeaf Cafés OOS (where an ES might fit)

**Not obvious for the ordering system itself** — but an ES-style component could be added:

- **Allergen-safe recommender** — given a customer's allergen profile (e.g. gluten, dairy), the ES recommends menu items that are safe, escalating to a human when confidence is low.
  - **Knowledge base:** allergen master list × ingredient list × menu item mapping + rules ("if item contains any of the customer's flagged allergens, do not recommend").
  - **Inference:** filter menu × justify each exclusion by rule.
  - **Explanation facility:** "The Bacon Roll is excluded because it contains gluten (rule A17) and egg (rule A22)."
  - **Human-in-the-loop:** where a menu change hasn't been fully classified, refer to the branch manager rather than recommend.

## Exam-answer phrases to use

- "An Expert System replicates the decision-making process of a human expert, using knowledge representation to describe the way the expert would approach the problem."
- "Expert Systems are best suited to narrow, well-defined domains where the expert's reasoning can be captured as explicit rules — for example medical triage or credit scoring."
- "A key strength of Expert Systems is their **explanation facility**, which allows the system to justify its recommendation — important for auditable decisions."
- "The single biggest limitation of an Expert System is the **knowledge-acquisition bottleneck** — capturing tacit expert reasoning as explicit rules is time-consuming and often incomplete."

## Common trap / examiner feedback

- Calling every AI system an "expert system" — the spec definition is specific: **replicates decision-making**, uses **knowledge representation**. Machine learning and large language models don't fit this rule-based definition.
- Missing the two spec bullets exactly — "replicates decision-making process" and "knowledge representation describes the way an expert would approach the problem" — mark these as key phrases.
- Confusing an ES with a database — data alone is not know-how; the difference is the *reasoning*.
- Forgetting to mention the **narrow domain** limitation — a common exam probe.

## Key vocabulary

**Expert System (ES), knowledge base, inference engine, knowledge representation, rules (IF/THEN), frames, ontology, decision-making process, explanation facility, knowledge engineer, knowledge acquisition, tacit knowledge, confidence factor, human-in-the-loop.**
