# TDR-01 · Life cycle and methodology for the Realtime Quiz project

Status: proposed · 2026-10-15 · to be decided by the sponsor and the PM at G1 (2026-10-19)

Sources: [project profile](project-profile.md), [approach comparison](approach-comparison.md), [scoring sheet](approach-scoring.csv), [charter](../lab01/project-charter.md), [MoSCoW list](../lab02/moscow.md), [constraint analysis](../lab02/constraints.md)

## Context

The Realtime Quiz project runs for 14 weeks from 2026-09-29 to a fixed pilot with 50 students in week 14, with 560 h of student capacity (4 students x 10 h/week) and a cash cap of 200 USD. The sponsor (Head of the IT department) demands an approved plan by the end of week 3 and controls scope through the charter rule that any change to scope, to the MVP demo or to the pilot needs written approval within 5 working days. The team of four students is on its first Scrum project and is learning Java and Spring in a parallel course, while the technical core is uncertain: the campus proxy may block WebSocket and Spring Boot 4 examples are scarce. The Must scope is stable (8 features, 300 h of the 504 h planned), but the screens and the exact real-time behaviour are unspecified, so parts of the requirement will only be confirmed when someone plays with a working increment. Task 1 scored this situation at 3.05, inside the hybrid band, and Task 2 scored the three candidates at waterfall 3.30, pure Scrum 3.45 and hybrid 4.05.

## Options considered

1. Waterfall (score 3.30): freeze the scope at G1 and deliver one integrated system in week 7, with change requests for every later change.
2. Pure Scrum (score 3.45): no baseline at all, backlog re-ordered every two-week sprint, the sponsor controls the project only through the sprint reviews.
3. Hybrid (score 4.05): an approved predictive plan with four phase gates G1-G4 around four two-week Scrum sprints, with per-stage tolerances.

## Decision

Adopt the **hybrid** life cycle: a predictive plan approved at G1 on 2026-10-19, four two-week sprints from 2026-10-20 to 2026-12-14, hardening in weeks 12-13 and the pilot in week 14, with gates G2 (2026-11-16), G3 (2026-12-14) and G4 (2027-01-04).

The two strongest reasons: (1) it is the only option that scores high on both dominating criteria of the profile, keeping the two-week feedback loop for the uncertain technical core (technical uncertainty, weight 25, hybrid fit 4) and keeping the plan, gates and tolerances the sponsor demands (contract and governance constraints, weight 20, hybrid fit 5); (2) it protects both fixed dates the charter names, the approved plan in week 3 and the pilot in week 14, because a gate can stop or re-plan the project in week 7 whereas pure Scrum only discovers the problem at the next review and waterfall only at integration in week 7.

## Consequences

+ The sponsor gets a working increment to play at every sprint review from week 5, and still gets the plan approval by the end of week 3 that the charter demands.
+ Four gates with five measurable criteria each turn the sponsor's control into numbers (hours, coverage, latency, defects) instead of opinions, and each stage tolerance lets the PM re-plan inside 560 h without asking for approval (charter section 9).
+ Sprints of 14 days give four measurement points before the pilot, so the burndown and the velocity from sprint 1 (25 of 30 points) already re-shape the plan at G2.
- Two sources of truth, the approved plan and the product backlog, can drift apart -> mitigation: the PM reconciles the milestone table with the backlog at every sprint review, and any change above the stage tolerance goes through the change-request process of Lab-02 (decision record DR-01).
- Gate and ceremony overhead can eat delivery capacity on a 4-student team -> mitigation: a gate is one meeting of at most 1 h with a five-item checklist, and every timebox is scaled to the two-week sprint (planning 2 h, review 1 h, retrospective 1.5 h).
- A first-time Scrum team estimates badly, as sprint 1 showed (30 points committed, 25 delivered) -> mitigation: velocity is re-forecast after every sprint and the remaining hours are re-checked against the 560 h cap at G2.
- Hybrid governance can hide scope creep inside the backlog -> mitigation: every backlog item carries an FR id and a MoSCoW class, and no Should or Could item starts before week 11 without an approved change request (DR-01).

## Tailoring

| Keep from predictive | Keep from agile | Drop |
| -------------------- | --------------- | ---- |
| Charter and scope baseline down to WBS level 2, because the Lab-04 scope baseline needs it | Product backlog with FR ids from lab02/features.csv, because Must/Should must be re-orderable every sprint | Detailed task assignment by the PM, because the developers self-organise the sprint plan |
| Phase gates G1-G4 with measurable evidence and a named decision maker, because the sponsor controls the project that way (charter section 9) | Two-week sprints with a sprint goal and a review demo, because feedback every 14 days is what the unspecified screens need | A signed-off requirements specification before development, because the screens are unspecified and would be re-worked after the first review |
| Budget and hours tracked per stage against 560 h with a tolerance of +10 % / +10 % / +5 % / 0 %, because the charter caps effort | Daily scrum and burndown, because they showed the flat burn of days D0-D2 in sprint 1 two days early | A change control board for small changes, because the PM may swap tasks of equal size inside 560 h |
| Risk register reviewed at every gate (campus proxy, Spring Boot 4, race conditions in late answers) | Definition of done verified by CI (build, tests, coverage >= 80 %), because quality must be checked on every merge | Release documentation written before the pilot, because the runbook is written and rehearsed in hardening weeks 12-13 |

## Phase gates

| Gate | Week / date | Evidence required (2 to 3 measurable items) | Decision maker | Possible outcomes |
| ---- | ----------- | ------------------------------------------- | -------------- | ----------------- |
| G1   | Week 3 · 2026-10-19 | 1. Scope baseline lists all 17 features with MoSCoW class and 504 h. 2. Milestone schedule shows G1-G4 and four sprints of 14 days. 3. Hours budget <= 560 h with >= 56 h contingency. | Sponsor with the PM | continue / continue with changes / stop / repeat |
| G2   | Week 7 · 2026-11-16 | 1. 8 of 8 Must features demonstrated at the MVP demo. 2. CI green on 100 % of merges and line coverage >= 80 %. 3. Hours used <= 308 h of the 280 h planned for stages 1-2. | Sponsor with the PM | continue / continue with changes / stop / repeat |
| G3   | Week 11 · 2026-12-14 | 1. All Must and >= 80 % of Should items meet the definition of done. 2. Load test with 100 simulated students, p95 broadcast < 500 ms. 3. Hours used <= 476 h of the 440 h planned for stages 1-3. | Sponsor with the PM | continue / continue with changes / stop / repeat |
| G4   | Week 14 · 2027-01-04 | 1. Pilot with 50 students, 0 blocking defects. 2. Line coverage >= 80 % and CI green on the release tag. 3. Hours <= 560 h and cash <= 200 USD. | Sponsor | continue / continue with changes / stop / repeat |

The four dates are identical to the four `:milestone` entries in [life-cycle.mmd](life-cycle.mmd) and to the gate sections of [governance.md](governance.md).
