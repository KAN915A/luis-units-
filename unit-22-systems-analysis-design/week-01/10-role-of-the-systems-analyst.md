# Week 1 — Topic 10: Role of the Systems Analyst

**Source:** `Week_One_Lecture_For_Software_Analysis_and_Design.pdf`, page 28 of 47.
**Learning Aim:** A — Investigate systems analysis and design methodologies.
**Criteria:** P / M / D.

> Names the job you're being trained to do. Everything so far in Week 1 (decomposition, modularity, data + processes, DFDs, ERDs, databases, application independence) is a **tool the systems analyst uses**. This slide sets out what the analyst is actually paid to do.

## Slide content (verbatim)

**Role of the Systems Analyst**
- Study problems and needs of an organisation.
- Determine best approach to improving the organisation through use of:
  - People
  - Methods
  - Information technology
- Help system users and managers define their requirements for new or enhanced systems.

---

## Pass evidence — describe / identify (P)

The three core responsibilities of a **systems analyst**:

1. **Study the problem** — investigate what is going wrong in the organisation now, what the goals are, what the constraints are.
2. **Determine the best approach** — recommend the right combination of **People** (skills, roles, training), **Methods** (business processes, procedures) and **Information Technology** (software, hardware, data) to solve it.
3. **Help users and managers define requirements** — translate what stakeholders *want* into unambiguous **functional and non-functional requirements** for a new or improved system.

**Three levers, not one:** technology is **one of three** — not the whole answer. A new system that ignores the *people* or the *methods* will fail even if the code is perfect.

## Merit evidence — analyse / compare (M)

### The three levers explained

- **People** — who does the work, what skills they have, whether they need training, how roles change once the new system is in.
- **Methods** — the *business processes* themselves (how orders are taken, how complaints are handled). Sometimes the best answer is to *change the process*, not add software.
- **Information technology** — the software, hardware, databases, networks that support the people and the methods.

**Common analyst error:** reaching for the IT lever first. Sometimes the correct recommendation is "no new IT — retrain and redesign the process". A good analyst is willing to say that.

### Study the problem — what "studying" actually looks like

- Fact-finding interviews with users, managers, sponsor, client.
- Document analysis — existing manuals, forms, reports.
- Observation of the current process on the shop floor.
- Questionnaires / surveys for wider stakeholder groups.
- Prototyping or workshops for hard-to-express requirements.

(These are the same feedback methods listed in Unit 3 **E2 Review of project success** — the analyst uses them at the *start*; the PM uses them at the *end*.)

### Helping users define requirements — the analyst's real skill

- Users say what they *want*, not what they *need*. The analyst extracts the underlying **need**, then writes it as an unambiguous requirement.
- Categorises into **functional** (what the system does) and **non-functional** (how well — performance, security, usability). See Unit 3 A2.
- Rewrites as **SMART** objectives (Unit 3 A2/B4) so success can be measured.
- Documents in a Requirements Specification and later folds into the Project Initiation Document (Unit 3 B4).

### Link back to earlier topics

- **Topic 1 (decomposition):** the analyst uses decomposition to break a huge business problem down into subsystems that can be tackled.
- **Topics 4–5 (data + processing logic):** the analyst produces the data dictionary, ERD, DFD and structured English **for someone else to build against**.
- **Topic 7–8 (approaches):** the analyst chooses the appropriate approach (Process-Oriented, Data-Oriented or hybrid) for the problem.
- **Topic 9 (database + application independence):** the analyst decides what should live in the shared database and what belongs to a single application.

---

## Distinction evidence — evaluate / justify (D)

**Strengths of a well-executed analyst role:**
- The organisation gets a **solution matched to the problem** — not "the technology the team happened to know" or "the process the client happened to describe".
- Requirements are unambiguous and testable → fewer defects at UAT (Unit 3 D5) → fewer change requests (Unit 3 D4) → higher project success rate (Unit 3 E2).
- Because People + Methods + Technology are considered together, the delivered system is **actually adopted** — the classic failure mode "the system works but nobody uses it" is avoided.

**Weaknesses / risks in the role:**
- Analyst captured by IT bias → recommends a software project when a process change would be cheaper.
- Analyst captured by the sponsor → misses the users' real needs.
- Requirements gathering skimped → scope creep and rework later (Unit 3 D4).
- Analyst treated as a scribe ("just write down what the client says") rather than a translator.

**Justified judgement (the D-level move):**

The systems analyst is best evaluated **against the three-lever brief**: after the recommendation, can you point to a **specific action per lever**?

- **People** — what training, what role change, what hiring is proposed?
- **Methods** — which business process is being changed, and to what?
- **Information technology** — which software/hardware component is being introduced or replaced?

If any of the three is missing, the recommendation is one-sided. **Recommend** that every analyst deliverable (business case, PID, design report) has a "People / Methods / Technology" section so the three levers are pulled deliberately, not by accident. This directly evidences the slide-28 responsibility and dramatically improves the odds of successful adoption (Unit 3 A4 benefits realisation).

Cite the professional bodies (Unit 3 A6): **BCS**, **APM**, **PMI** codes of conduct all bind the analyst to act in the client's and public's interest — a valid distinction-level point when discussing analyst ethics.

---

## Applied to a scenario — GreenLeaf Cafés OOS

**Analyst's three-lever recommendation:**

| Lever                | Recommendation                                                                                          |
| -------------------- | ------------------------------------------------------------------------------------------------------- |
| **People**           | Train branch staff on the fulfilment portal (1-hour session per branch); nominate 1 "digital champion" per branch. |
| **Methods**          | Change the order-taking process at the counter — customers scan a QR at the door to place an order; counter staff pick it from the fulfilment queue. |
| **Information technology** | Build the customer web app + staff fulfilment portal + Stripe integration on the existing Azure hosting. |

Notice: technology alone would not deliver the benefit — staff training + a re-designed counter process are both needed. That is the analyst's job to identify.

## Exam-answer phrases to use

- "The systems analyst studies the problems and needs of an organisation and recommends the best combination of *People*, *Methods* and *Information Technology* to address them."
- "Rather than recommending a technology-only solution, the analyst evaluates the three levers — for example, in this scenario staff training and a redesigned counter process are needed alongside the new software."
- "One of the analyst's core responsibilities is helping users and managers define unambiguous, testable requirements for the new system."
- "The systems analyst acts as a translator between what users *say they want* and what the system *actually needs to do*."

## Common trap / examiner feedback

- Reducing the analyst to "the person who writes down what the client says" — misses the studying, evaluating and recommending parts of the role.
- Recommending only **IT** and ignoring **People** and **Methods** — the spec lists all three; markers check.
- Blurring analyst with project manager — the analyst *defines* what should be built; the PM *plans and delivers* it (Unit 3 A5).
- Using "system" loosely — remember Topic 1: a system includes people and processes, not just software.

## Key vocabulary

**Systems analyst, requirements, functional requirement, non-functional requirement, people/methods/technology, fact-finding, interview, observation, questionnaire, prototyping, business process, adoption, translator.**
