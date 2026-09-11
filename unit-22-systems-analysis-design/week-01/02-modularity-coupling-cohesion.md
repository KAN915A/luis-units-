# Week 1 — Topic 2: Important System Concepts — Modularity, Coupling, Cohesion

**Source:** `Week_One_Lecture_For_Software_Analysis_and_Design.pdf`, page 18 of 47.
**Learning Aim:** A — Investigate systems analysis and design methodologies.
**Criteria:** P / M / D.

## Slide content (verbatim)

- **Modularity** — Process of dividing a system into modules of a relatively uniform size. Modules simplify system design.
- **Coupling** — Subsystems that are dependent upon each other are coupled.
- **Cohesion** — Extent to which a subsystem performs a single function.

---

## Pass evidence — describe / identify (P)

- **Module** — a self-contained unit of a larger system that performs a specific role (Unit 3 glossary: "part of a large software system that carries out a specific business role" — e.g. HR uses a payroll module).
- **Modularity** = the design property of a system that has been divided into modules.
- **Coupling** = the degree of dependency between two subsystems / modules.
  - If A relies on B's internal details → **tightly coupled**.
  - If A only needs a small, well-defined interface to B → **loosely coupled**.
- **Cohesion** = the degree to which the parts of one subsystem all work towards a single, focused purpose.
  - A subsystem that does one thing well = **high cohesion**.
  - A subsystem that does many unrelated things = **low cohesion**.

**The golden rule of good design: LOW coupling + HIGH cohesion.**

---

## Merit evidence — analyse / compare (M)

### Modularity — why it matters

- Simplifies design: one module can be designed without holding the whole system in your head.
- Enables parallel development, independent testing, easier maintenance and reuse.
- "Uniform size" — modules of similar size make estimation, staffing and progress tracking predictable (feeds Unit 3 C1 scheduling and C2 estimation).

### Coupling — comparison

| Coupling level | What it looks like                                              | Effect                                            |
| -------------- | --------------------------------------------------------------- | ------------------------------------------------- |
| Tight (bad)    | A reads B's internal variables, or shares B's database directly.| Change in B breaks A. Cannot swap B out.          |
| Loose (good)   | A calls B only through a documented interface / API.            | B's internals can change without breaking A.      |

### Cohesion — comparison

| Cohesion level | What it looks like                                              | Effect                                            |
| -------------- | --------------------------------------------------------------- | ------------------------------------------------- |
| Low (bad)      | One subsystem handles login **and** invoicing **and** email.    | Hard to understand, test, or reuse.               |
| High (good)    | Login subsystem does login only. Invoicing does invoicing only. | Easy to name, test, replace, and reason about.    |

### Link back to Figure 1.6 (CD player decomposition)

- Each of the four subsystems (reading, amplifying, control, conversion) does **one job** → high cohesion. ✓
- Interfaces between them are small (a signal in, a signal out) → low coupling. ✓
- That is *why* the decomposition works.

---

## Distinction evidence — evaluate / justify (D)

### Strengths

- High cohesion + low coupling makes systems **easier to understand, test, maintain, replace and reuse**.
- Modularity supports parallel work (Unit 3 C1 parallel task scheduling) and localised fault-fixing (Unit 3 C4 defect removal + D4 change management: change confined to one module).
- Loosely coupled interfaces let you **swap suppliers or technologies** without redesigning the whole system (e.g. change payment provider without changing checkout logic).

### Weaknesses / trade-offs

- Splitting too aggressively creates **many small modules** with **many interfaces** → integration overhead + interface bugs.
- "Relatively uniform size" is an ideal, not always achievable — some responsibilities are naturally bigger than others; forcing uniformity distorts the design.
- High cohesion sometimes conflicts with performance — a fully isolated subsystem may need extra network calls or data copies to talk to others.

### Justified judgement (the D-level move)

Aim for the highest cohesion **and** the lowest coupling **that the problem sensibly allows**. In practice:
1. Decide module boundaries around **business responsibilities** — one module owns one business capability.
2. Define interfaces before writing internals.
3. Review the design by asking "if I change this one thing, how many modules must change?" — if the answer is more than one or two, the boundaries are wrong.
4. **Recommend** documenting each module's interface in the design phase so downstream code cannot rely on internals — this operationalises the loose-coupling principle rather than leaving it to good intentions.

---

## Applied to a scenario — small computing project (online booking system)

| Subsystem      | Single function (cohesion)                      | Talks to (interface — coupling)                            |
| -------------- | ----------------------------------------------- | ----------------------------------------------------------- |
| Authentication | Verifies user identity, issues session tokens.  | Gives a "user id + role" to any subsystem that asks.        |
| Catalogue      | Stores/serves the list of bookable slots.       | Publishes a `getAvailableSlots()` API.                      |
| Booking        | Records a booking, enforces business rules.     | Calls Catalogue (read) + Payment (charge) + Notification.   |
| Payment        | Talks to Stripe, handles refunds.               | Called by Booking through a `charge(amount, orderId)` API.  |
| Notification   | Sends confirmation emails/SMS.                  | Called by Booking with a message payload.                   |

Each row: **one clear job (high cohesion)** and **a small, named interface (low coupling)** — the same pattern as the CD player.

---

## Exam-answer phrases to use

- "Dividing the system into modules of a relatively uniform size simplifies design because…"
- "These two subsystems are tightly coupled because module A depends on internal detail of module B; a design change is recommended so that A only interacts with B through a defined interface."
- "The subsystem exhibits high cohesion because it performs a single, well-defined function (…)."
- "For distinction-level design, the aim is **low coupling and high cohesion**, because this makes the system easier to test, maintain and evolve."

## Common trap / examiner feedback

- Mixing coupling and cohesion up. Remember:
  - **Coupling** is between subsystems (external — how much they depend on each other).
  - **Cohesion** is within a subsystem (internal — how focused it is on one job).
- Saying "coupling is bad" — coupling is inevitable (subsystems must talk). The point is to keep it **loose**.
- Saying "modularity is enough" — a modular system with tight coupling is still fragile.

## Key vocabulary

**Module, modularity, coupling (tight / loose), cohesion (high / low), interface, dependency, encapsulation.**
