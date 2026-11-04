# Retrospective · Realtime Quiz · filled template for sprint 1

Sources: [sprint-1-planning.md](sprint-1-planning.md), [burndown.mmd](burndown.mmd), [scrum-setup.md](../scrum-setup.md)

How to reuse this file: copy it for the next sprint, keep the same six sections, fill the Data section from the burndown before the meeting and close the actions of the previous retrospective first.

## Sprint

Sprint 1 · 2026-10-20 to 2026-11-02 · retrospective on Monday 2026-11-02, 15:30, 1.5 h · sprint goal: by the end of sprint 1 an instructor account can register, log in with the right role and author single- and multi-answer questions, so the sponsor can play the authoring flow in a live demo at the review.

## Attendees

Student A (product owner and developer), Student B (Scrum master and developer), Student C (developer), Student D (developer). The project manager (lecturer) is not in the retrospective; he receives the action list with the weekly highlight report.

## Data (velocity, burndown observations)

- Velocity achieved: 25 points of the 30 committed (83 %); the 5 open points belong to B-05, which returns to the product backlog.
- Ideal burn 3 points/day; actual burn 25 points over ten working days = 2.5 points/day.
- No burn at all on D0, D1 and D2: the team first closed points on D3, so the gap reached 6 points (two ideal days) at D2, on 2026-10-21.
- The gap never fell below 5 points again after D2 (largest gap 8 points at D5 and D6), and the sprint ended 5 points behind the ideal line.
- Observations: the flat start is the CI, Docker and Flyway setup on day 1-2; the zero-burn day at D5 is the day the question reorder was blocked; the burn from D7 to D10 (15 -> 5) shows the team worked in one large batch at the end.

## What went well

- Planning poker produced one re-estimate only (B-01) and a commitment of 30 points that matched the stated velocity.
- Five items met the definition of done, and the CI pipeline stayed green on every merge.
- The sponsor saw a working demo at the review on 2026-11-02, inside the sprint.

## What to improve

- The first two working days closed no points, so the burndown was flat until D3.
- One 8-point item and one 5-point item were still open at the end, which is why 5 points were carried over.
- The remaining points were not updated on D5, so the burndown showed a zero-burn day with no explanation.

## Actions (action, owner, due, check in next retrospective)

| Action | Owner | Due | Check in next retrospective |
| ------ | ----- | --- | --------------------------- |
| Split every item above 5 points into tasks of at most 3 points before sprint planning, so that closures appear on the burndown from day 1 instead of after D2 | Student A (PO) | 2026-10-29 (refinement) | 2026-11-16 (sprint 2 retrospective) |
| Update the remaining points of the board at every daily scrum, so that a zero-burn day such as D5 is explained in one line | Student B (SM) | 2026-10-23 (first week of sprint 2) | 2026-11-16 |
| Re-order B-05 to the top of sprint 2 and split it into "create quiz" and "visibility settings" so that a 5-point item cannot ride to the last day again | Student A (PO) | 2026-11-03 (sprint 2 planning) | 2026-11-16 |

Both burndown-derived actions (the flat start after D2 and the unexplained zero-burn day at D5) have an owner, a date and a check in the next retrospective.
