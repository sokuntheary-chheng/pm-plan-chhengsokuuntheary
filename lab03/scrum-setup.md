# Scrum setup · Realtime Quiz

Sources: [charter](../lab01/project-charter.md), [MoSCoW list](../lab02/moscow.md), [feature list](../lab02/features.csv), [project profile](project-profile.md), [life cycle](life-cycle.mmd)

## Roles

| Role            | Person                                   | Accountable for                                                                 | Not responsible for                                                        |
| --------------- | ---------------------------------------- | ------------------------------------------------------------------------------- | -------------------------------------------------------------------------- |
| Product owner   | Student A                                | the order of the product backlog, the sprint goal wording, acceptance of items against their acceptance criteria at the review, FR ids and MoSCoW classes | technical design, estimating alone, gate decisions, approving his own stories without a second developer |
| Scrum master    | Student B                                | the Scrum process: events held inside their timeboxes, impediments removed, the burndown updated every day, facilitation of every event | backlog priority, budget and gate decisions, the technical design of the increment |
| Developers      | Students A-D                             | delivering the increment to the definition of done, planning-poker estimates, the sprint plan, the technical quality of the code | backlog priority, changing the agreed timeboxes, gate, budget and acceptance decisions |
| Project manager | Tal Tongsreng (lecturer, outside Scrum)  | gates G1-G4, budget and hours against 560 h, stakeholder communication, the risk register, the weekly highlight report | day-to-day backlog order, sprint events, technical design, acceptance of single items |
| Sponsor         | Head of the IT department                | the business case, gate decisions, written approval of scope changes, cash above the 25 USD reserve, acceptance of the pilot | backlog ordering, technical design, the daily scrum, the day-to-day process |

Student A is both product owner and developer, so his own work is never accepted by himself: every item he develops is demonstrated against its acceptance criteria by a second developer and signed off at the sprint review, Student B (Scrum master) facilitates all events so that no single voice sets the agenda, and Student A's planning-poker estimate for his own item is replaced by the estimate the team agrees on.

## Sprint goal (sprint 1, weeks 4-5)

By the end of sprint 1 an instructor account can register, log in with the right role and author single- and multi-answer questions, so the sponsor can play the authoring flow in a live demo at the review on 2026-11-02.

## Event calendar · sprint 1 (weeks 4-5, 2026-10-20 to 2026-11-02)

| Event             | Date(s)                                        | Time   | Timebox                                                        | Attendees                              | Output                                     |
| ----------------- | ---------------------------------------------- | ------ | -------------------------------------------------------------- | -------------------------------------- | ------------------------------------------ |
| Sprint planning   | Tue 2026-10-20                                 | 10:00  | 2 h (half of the 4 h Scrum Guide maximum for a one-month sprint) | PO, SM, all four developers            | sprint goal, sprint backlog (30 points)    |
| Daily scrum       | Mon-Fri 2026-10-20 to 2026-11-02 (10 working days) | 09:00 | 15 min (the fixed Scrum Guide maximum)                          | all four developers (+ SM)             | plan for the day, updated burndown         |
| Backlog refinement | Thu 2026-10-22 and Thu 2026-10-29             | 16:00  | 1 h each, 2 h total (10 % of the 80 h sprint capacity)         | PO, SM, all four developers            | refined items with FR id, estimate, sketch |
| Sprint review     | Mon 2026-11-02                                 | 14:00  | 1 h (half of the 4 h Scrum Guide maximum for a one-month sprint) | team, PM, sponsor (invited)            | feedback, updated product backlog         |
| Sprint retrospective | Mon 2026-11-02                              | 15:30  | 1.5 h (half of the 3 h Scrum Guide maximum for a one-month sprint) | four developers, SM (facilitates)      | action list with owner and due date       |

Every timebox is at or below the Scrum Guide 2020 maximum scaled to a two-week sprint: planning 2 h of 4 h, daily scrum 15 min, review 1 h of 4 h, retrospective 1.5 h of 3 h, refinement 2 h of the 8 h (10 %) allowed.

## Sprint schedule (must match the gantt bars)

| Sprint   | Dates                            | Review        | Gate after it |
| -------- | -------------------------------- | ------------- | ------------- |
| Sprint 1 | 2026-10-20 to 2026-11-02 (14 d)  | 2026-11-02    | G1 before it, on 2026-10-19 |
| Sprint 2 | 2026-11-03 to 2026-11-16 (14 d)  | 2026-11-16    | G2 on 2026-11-16 |
| Sprint 3 | 2026-11-17 to 2026-11-30 (14 d)  | 2026-11-30    | none (inside stage 3) |
| Sprint 4 | 2026-12-01 to 2026-12-14 (14 d)  | 2026-12-14    | G3 on 2026-12-14 |

After sprint 4: hardening weeks 12-13 (2026-12-15 to 2026-12-28), pilot week 14 (2026-12-29 to 2027-01-04) and G4 on 2027-01-04, exactly as in [life-cycle.mmd](life-cycle.mmd).

## Definition of ready

1. The item carries at least one FR id from the ranges in [lab02/features.csv](../lab02/features.csv), so it is traceable to a Must feature.
2. The item has acceptance criteria in Given/When/Then form agreed with the product owner.
3. The item has a Fibonacci estimate of 8 points or less agreed by the team in planning poker.
4. Dependencies are named and every item it depends on is already in the sprint or already done.
5. A sketch (wireframe or data-flow drawing) is attached to the item so the developers do not guess.

## Definition of done

1. The change is merged through a pull request that at least one other developer approved.
2. The CI pipeline is green on the merge commit: build and unit tests pass. (CI)
3. Line coverage of the new code is >= 80 % in the JaCoCo report produced by CI. (CI)
4. Static analysis (SpotBugs) reports no new high-severity finding on the changed files. (CI)
5. The integration test suite runs against the test database in CI and passes. (CI)
6. No secret, token or credential is present in the repository, verified by the CI secret scan. (CI)
7. The item's acceptance criteria are demonstrated in the staging environment to the product owner.
8. The interface behaves at a 360 px and a 1280 px viewport, checked in the browser before the merge.
9. Changes to configuration or API are documented in the README of the affected module.
10. Remaining work is re-estimated in the backlog and the burndown is updated for the day.

Criteria 2, 3, 4, 5 and 6 are checked by the CI pipeline; none of the ten criteria mentions a specific feature, so they apply to every item.

## Definition of ready, checked for the sprint 1 backlog

| Item | FR id (from lab02/features.csv)        | Acceptance criteria | Estimate | Dependencies                          | Sketch                       |
| ---- | -------------------------------------- | ------------------- | -------- | ------------------------------------- | ---------------------------- |
| B-01 | FR-S5 (F05 range FR-S5)                | Given/When/Then     | 3        | none                                  | pipeline and compose sketch  |
| B-02 | FR-A1 (F06 range FR-A1..FR-A4)         | Given/When/Then     | 3        | B-01 (migrations and CI)              | registration form sketch     |
| B-03 | FR-A2 (F06 range FR-A1..FR-A4)         | Given/When/Then     | 5        | B-02 (registered account)             | login form sketch            |
| B-04 | FR-A3 (F06 range FR-A1..FR-A4)         | Given/When/Then     | 3        | B-03 (session and role claim)         | page access sketch           |
| B-05 | FR-Q1 (F01 range FR-Q1..FR-Q7)         | Given/When/Then     | 5        | B-04 (instructor session)             | quiz form sketch             |
| B-06 | FR-Q2 (F01 range FR-Q1..FR-Q7)         | Given/When/Then     | 8        | B-01 (seeded demo quiz), B-04         | question list sketch         |
| B-07 | FR-Q4 (F01 range FR-Q1..FR-Q7)         | Given/When/Then     | 3        | B-06 (question editor)                | answer type sketch           |

All seven items meet the five criteria above, which is why all seven were accepted into sprint planning.

## Planning velocity and capacity

Planning velocity: **30 points** · capacity: 4 x 10 h x 2 weeks = 80 h · 30 points x 2.5 h = 75 h, leaving 5 h of buffer inside the 80 h.

The sprint backlog total is 3 + 3 + 5 + 3 + 5 + 8 + 3 = **30 points**, equal to the planning velocity of 30 points and equal to the sum of the `points` column in [sprint-1-backlog.csv](sprint-1-backlog.csv).
