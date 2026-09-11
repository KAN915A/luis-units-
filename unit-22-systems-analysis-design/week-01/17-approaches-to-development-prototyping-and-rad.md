# Week 1 — Topic 17: Approaches to Development — Prototyping & RAD

**Source:** `Week_One_Lecture_For_Software_Analysis_and_Design.pdf`, page 42 of 47.
**Learning Aim:** A — Investigate systems analysis and design methodologies.
**Criteria:** P / M / D.

> Opens a new section: **Approaches to Development**. The SDLC (Topics 14–16) is the *what* — the phases. Approaches to development are the *how* — the styles / methodologies used to run those phases. This slide covers **Prototyping** and **Rapid Application Development (RAD)**.

## Slide content (verbatim)

**Approaches to Development**

- **Prototyping**
  - Building a scaled-down working version of the system.
  - Advantages:
    - Users are involved in design.
    - Captures requirements in concrete form.

- **Rapid Application Development (RAD)**
  - Utilises prototyping to delay producing system design until after user requirements are clear.

---

## Pass evidence — describe / identify (P)

### Prototyping — definition

Building a **scaled-down working version** of the system so users can see, touch and react to it, *before* the full system is built. A prototype is not the final system — it's a demonstration used to elicit clearer requirements.

**Two named advantages (from the spec):**
1. **Users are involved in design** — they don't just read requirements documents, they interact with a working model.
2. **Captures requirements in concrete form** — feedback comes on a real thing, not on an abstract description; "make this button bigger" is easier to say than "improve usability".

**Two common prototype types (context — helps at Merit/Distinction):**
- **Throwaway prototype** — built to explore requirements, then discarded; the real system is built afterwards.
- **Evolutionary prototype** — refined iteratively until it becomes the delivered system.

### Rapid Application Development (RAD) — definition

A development approach that **uses prototyping** to hold off producing the formal system design **until user requirements are clear**. In effect: don't spend weeks on design when the requirements are still moving — build a prototype, get user reactions, converge the requirements, *then* do the design.

**Typical RAD techniques:**
- Time-boxed development cycles (e.g. 60–90 days end-to-end).
- Joint Application Development (JAD) workshops — users + analysts + developers together.
- Heavy use of prototyping tools and code generators.
- CASE tools (Computer-Aided Software Engineering) for models and code stubs.

## Merit evidence — analyse / compare (M)

### Why prototyping "captures requirements in concrete form"

- Users struggle to describe what they want abstractly ("I need a search feature"), but they can immediately react to a running screen ("this search is too slow / needs a filter for date").
- A prototype makes **implicit assumptions explicit** — the analyst sees what users pick up and what they miss.
- The written requirement produced *after* the prototype is much more accurate than the one produced from interviews alone (Unit 3 A2 SMART objectives).
- Reduces requirements churn later, which reduces change requests (Unit 3 D4) and rework.

### Why RAD "delays design until requirements are clear"

- Traditional (Waterfall) SDLC produces a full formal design based on the initial requirements — if those requirements are wrong, the design is wrong too.
- RAD says: don't spend heavy design effort on foggy requirements. Prototype first, clarify, *then* design.
- This is the same idea as Agile's short iterations — RAD was one of its predecessors.

### Compare with Waterfall (Unit 3 D1)

| Concern                             | Waterfall SDLC                                      | Prototyping / RAD                              |
| ----------------------------------- | --------------------------------------------------- | ---------------------------------------------- |
| Requirements assumed to be...        | Stable and fully known up front.                    | Uncertain — will emerge through prototype use. |
| User involvement in design           | Reviews documents.                                   | Interacts with a working prototype.            |
| Design produced                       | Once, before build.                                  | After requirements have stabilised.            |
| Change during build                   | Expensive (change control).                          | Expected and welcomed.                         |
| Best fit for                          | Stable, well-understood, regulated projects.        | Novel, uncertain, user-experience-driven.      |
| Risk it manages                       | Change of scope during build.                        | Requirements uncertainty.                      |
| Risk it exposes                       | Late user feedback.                                  | Prototype becoming production without hardening. |

### Compare Prototyping (technique) vs RAD (methodology)

- **Prototyping** is a **technique** — building a scaled-down working model.
- **RAD** is a **methodology** — a whole way of running a project that *uses* prototyping as its central technique.
- You can use prototyping inside Waterfall (for requirements clarification only), inside Agile, or inside RAD. RAD is a specific commitment to the prototyping-first approach.

### Link to earlier topics + Unit 3

- **Unit 3 A5 project life cycle:** RAD compresses the Definition + Planning stages; more work happens iteratively during Execution.
- **Unit 3 A3 risk / C3 risk strategy:** RAD reduces requirements risk; increases scope-drift risk. Trade one for the other.
- **Unit 3 A2 quality / C4 quality management:** a prototype that becomes production without proper testing = quality risk.
- **Unit 3 D1 (Waterfall):** RAD is the alternative approach.
- **Topic 10 (analyst role):** prototyping is a **requirements-elicitation technique** the analyst wields — alongside interviews, observation, questionnaires.
- **Topic 11 (analyst skills):** the interpersonal + written communication skills matter more in RAD because feedback loops with users are constant.

---

## Distinction evidence — evaluate / justify (D)

**Strengths of Prototyping / RAD:**
- **Better requirements** — captured against a running artefact, not an abstract description.
- **Higher user buy-in** — users who shape the prototype adopt the final system more readily (Topic 10's *People* lever).
- **Faster time-to-value** — a working (if incomplete) system reaches users sooner.
- **Reduced late-stage change requests** — because the changes happened during the prototype, not after go-live (Unit 3 D4).
- **Good fit for uncertain domains** — new markets, new user experiences, unfamiliar business processes.

**Weaknesses / trade-offs:**
- **Prototype-as-production trap** — pressure to ship the prototype as the real system, without the hardening (security, performance, error handling) that a designed system has.
- **Scope creep** — every prototype demo generates new requests; without discipline the project never converges.
- **Under-documented systems** — RAD's speed can leave gaps in analysis and design documentation that hurt Operation (Topic 16 maintenance).
- **Fits some projects poorly** — a payroll compliance system with fixed regulations does *not* benefit from prototyping-first; a Waterfall SDLC is more proportionate.
- **Team + tool intensive** — RAD needs users, analysts, developers together (JAD sessions) plus rapid-development tooling — expensive to run for a small team.

**Justified judgement (the D-level move):**

Choose the development approach on the **shape of the risk**, not on trend:

- **Requirements clear + stable + regulated?** → Waterfall SDLC (Topics 14–16, Unit 3 D1) is proportionate.
- **Requirements unclear, user-experience-driven, novel product?** → Prototyping and/or RAD reduces the biggest risk (getting the requirements wrong).
- **Requirements clear but the technology or performance is uncertain?** → Prototype the risky part inside a Waterfall design phase (hybrid).

**Recommend** — for any RAD or prototyping project — three practical guardrails:

1. **Decide up-front** whether the prototype is *throwaway* or *evolutionary*. A throwaway prototype must be discarded when the real build starts (put the decision in the PID, Unit 3 B4).
2. **Time-box** each prototype cycle (e.g. 2 weeks) with a sign-off gate — otherwise scope creep is inevitable.
3. **Retain a lightweight design + test discipline** even when moving fast — enough architecture and regression tests to survive Operation (Topic 16).

These operationalise Prototyping/RAD and evidence the distinction-level requirement to *evaluate* and *make justified recommendations*.

---

## Applied to a scenario — GreenLeaf Cafés OOS

**Where prototyping / RAD fits GreenLeaf:**

- The **customer web app checkout flow** is uncertain — how many steps, what wording, what mobile behaviour. Prototype it in Figma → clickable HTML → interactive Stripe-sandbox demo, before finalising design. Users: 3 branch managers + 5 sample customers.
- The **staff fulfilment portal** is well understood (essentially a queue). No prototype needed; go straight to design + build.
- Payment integration, hosting architecture, database schema — all Waterfall-style design first because they have hard constraints (PCI-DSS, Azure).

**Recommendation for GreenLeaf:** **hybrid** — RAD-style prototyping for the customer-facing UX; Waterfall SDLC for the back-end and payment layers. Justify: the risk on the front end is *requirements* (users don't know what they want until they see it); the risk on the back end is *compliance* (regulated, must be right first time). Different risks, different approaches. Document the split in the PID (Unit 3 B4) with a note that the front-end prototype is **throwaway** — final build starts from clean architecture.

## Exam-answer phrases to use

- "**Prototyping** is building a scaled-down working version of the system to involve users in design and capture requirements in concrete form."
- "**Rapid Application Development (RAD)** utilises prototyping to delay producing the formal system design until user requirements are clear."
- "Prototyping is a *technique*; RAD is a *methodology* that centres on prototyping."
- "Prototyping and RAD reduce **requirements risk** (Unit 3 A3) by getting user reactions on a working artefact before design is finalised."
- "For a hybrid recommendation: prototype the uncertain user-facing parts, but keep Waterfall discipline for the regulated back-end layers."

## Common trap / examiner feedback

- Saying **prototyping = RAD** — they are related but distinct: prototyping is a technique used *within* RAD (and elsewhere).
- Forgetting the two named advantages — the spec explicitly lists *user involvement in design* and *capturing requirements in concrete form*.
- The **prototype-as-production trap** — shipping the prototype without design or testing rigour. A common failure mode; markers reward candidates who name and mitigate it.
- Recommending RAD for a payroll or compliance project — wrong risk shape; Waterfall fits better.

## Key vocabulary

**Prototype, prototyping, throwaway prototype, evolutionary prototype, Rapid Application Development (RAD), Joint Application Development (JAD), CASE tools, time-box, requirements risk, hybrid approach, user involvement, iterative development.**
