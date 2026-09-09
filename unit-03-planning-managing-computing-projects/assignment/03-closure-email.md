# 03 — Project Closure / Handover Email

**Spec anchor:** E1 Closing a live project. Also A6 (professionalism + communication), E2 (feeds review of success), C5 (communication method + audience).

## What the examiner is looking for

- **Correct email structure** — subject, salutation, purpose, body, close, signature.
- **All closure content present** — deliverables done, UAT signed, handover to operations, support route, warranty, documentation, next review date.
- **Audience-appropriate tone** — formal, professional (A6). Match technical detail to reader.
- **Fluent English, correct technical terms**, no jargon without explanation.
- **Effective use of structure** — headings, bullet points where a chunk needs to be scannable (A6 "effective use of graphics to support meaning" — headings and lists count).
- Links (or references) to the final documentation.
- **Next steps** — post-project review, benefits-realisation review date.
- **Ends professionally** with a named contact for any queries.

## Blank template

```
From:    <PM email>
To:      <sponsor>, <client>
Cc:      <team managers>, <operations owner>, <dev lead>
Subject: <Project Name> — Project Closure and Handover to Operations

Dear <Sponsor name> and <Client name>,

I am writing to formally confirm the closure of the <Project Name> project,
which reached its final milestone on <DD/MM/YYYY>.

**Summary of delivery**
- Deliverable 1: <status vs PID>
- Deliverable 2: <status vs PID>
- ...
- User Acceptance Testing: completed on <date>, signed off by <client name>.

**SMART objectives — outcome**
- Obj 1 (…): met / partially met / not met — evidence: …
- Obj 2 (…): ...

**Handover to operations**
The system moved into the operation and maintenance phase on <date>.
- Operational owner: <team / person>
- Support contact: <name, email, phone>
- Warranty period: <n> months from go-live, ending <date>.
- Service-level agreement: <link or attachment>.

**Final documentation**
The following documents are stored in <location / SharePoint link>:
- Final Project Initiation Document (v <n>)
- Final Gantt / project plan
- Final risk log, issue log, quality log (now closed)
- User manual and training materials
- Test summary report
- Lessons-learned report

**Next steps**
- Post-project review meeting: <date> at <time>, <location>.
- Benefits-realisation review scheduled for <date> (typically 3–6 months post go-live).

Thank you to <sponsor>, <client> and the project team for your support and
collaboration throughout the project. Please contact me at <email> if you have
any questions.

Kind regards,

<Full name>
Project Manager, <Project Name>
<Email>  •  <Phone>
```

## Worked example — GreenLeaf Cafés Online Ordering System

```
From:    a.kanumetta@greenleafcafes.co.uk
To:      j.pearson@greenleafcafes.co.uk (Operations Director / Sponsor)
         r.singh@greenleafcafes.co.uk    (IT Manager / Client)
Cc:      Team Manager – Development
         Team Manager – QA
         Head of IT Operations
Subject: GreenLeaf Cafés Online Ordering System — Project Closure and Handover to Operations

Dear Jane and Ravi,

I am writing to formally confirm the closure of the GreenLeaf Cafés Online
Ordering System (OOS) project, which reached its final milestone (Go-Live)
on 01/12/2026, in line with the approved Project Initiation Document.

**Summary of delivery**
- Customer web app (order + pre-pay): delivered as specified.
- Staff order-fulfilment portal: delivered as specified.
- Stripe payment integration (live keys): delivered and PCI-compliant.
- Pilot UAT across the 3 nominated branches (Kensington, Islington, Camden):
  completed on 29/11/2026 and formally signed off by yourself, Ravi, on the
  same day.
- Training: 24 branch staff trained across all 12 branches (in-person + video
  handover).

**SMART objectives — outcome**
- Deliver OOS live to all 12 branches by 01/12/2026: **met** (go-live 01/12).
- Average customer order flow completes in ≤ 90 seconds: **met** — measured
  at 68 seconds (95th percentile) during UAT.
- Reduce in-store queuing at peak by 20% within 3 months of go-live: **to be
  measured** at the benefits review (see below).
- Solution delivered within the £40,000 budget: **met** — final spend
  £38,120 (95.3% of budget; £1,880 contingency returned).

**Handover to operations**
The OOS moved into the operation and maintenance phase on 01/12/2026.
- Operational owner: Head of IT Operations.
- Support contact: it-support@greenleafcafes.co.uk (Mon–Sun 07:00–21:00).
- Warranty period: 3 months from go-live, ending 01/03/2027 — defect fixes
  covered under the project contract with no additional cost.
- Service-level agreement: attached (SLA_OOS_v1.0.pdf).

**Final documentation**
All final artefacts are stored in the project SharePoint site
(SharePoint > Projects > OOS > Closure Pack):
- Final Project Initiation Document, v3.2
- Final Gantt / project plan (Baseline 1.0 + Actual)
- Risk log, issue log, quality log — all now closed
- User manual (customer app) and staff quick-reference guide
- Test summary report + regression pack
- Lessons-learned report (highlights: earlier engagement with client finance
  on Stripe keys; a formal branch-staff RFC channel from week 1)

**Next steps**
- Post-project review meeting: 08/12/2026 at 14:00, Head Office Meeting Room 2
  (agenda to follow). Attendance requested from yourselves, dev lead and
  QA lead. Feedback will also be collected from sponsor, clients, end users
  and the development team using a combination of questionnaires and
  interviews (E2).
- Benefits-realisation review: 01/03/2027 to measure queue-time reduction
  and repeat order rate against the business case.

Thank you both, and the wider team, for the support and clear direction
throughout the project. Please contact me at a.kanumetta@greenleafcafes.co.uk
or 020 7946 0158 for any queries during the warranty period.

Kind regards,

Akhil Kanumetta
Project Manager, GreenLeaf Cafés Online Ordering System
a.kanumetta@greenleafcafes.co.uk  •  020 7946 0158
```

## Marker notes — how to write for distinction

- **Subject line does work** — names the project + "Closure and Handover". Not "FYI" or "Update".
- **Body maps 1:1 to the E1 checklist**: deliverables, UAT sign-off, handover, support route, warranty, closed logs, documentation, next review dates. Missing any = capped.
- **SMART objectives outcome** — literally state each objective and whether it was met, with evidence. This ties E1 to E2 and shows in-depth understanding.
- **Named next reviews with dates** — proves benefits-realisation is planned, not just promised.
- **Audience-tuned language** — formal, no slang, technical terms only where the reader will follow them.
- **Signed off with contact details** — makes the PM the accountable single point of contact during warranty.

## Common traps

- Treating the closure email as a "thanks for your hard work" note. It's a formal, structured communication.
- No warranty period stated → ambiguity about who fixes defects post-go-live.
- No named support contact → tickets go to random developers.
- No benefits-realisation date → no follow-through on business case (A4 → E2).
- Attaching zero references to the final documentation → contradicts "final documentation is available".
