# Sprint 1 planning (simulated) · 2026-10-20

Sources: [sprint-1-backlog.csv](../sprint-1-backlog.csv), [scrum-setup.md](../scrum-setup.md), [burndown.mmd](burndown.mmd), [feature list](../../lab02/features.csv)

Scenario: Tuesday 2026-10-20, 10:00, sprint planning. The four students estimate the seven Must items with planning poker. Sprint 1 runs 2026-10-20 to 2026-11-02 (ten working days).

## Planning poker

| Item | A   | B   | C   | D   | Agreed | Note |
| ---- | --- | --- | --- | --- | -----: | ---- |
| B-01 | 3   | 3   | 5   | 2   |   3   | Highest 5 vs lowest 2 is two Fibonacci steps, so the rule applies: C explains that Docker, Flyway migrations and the CI pipeline are new work for him, D explains that the skeleton is a template from the Software Engineering course; everybody re-estimates and the team settles on 3. |
| B-02 | 3   | 2   | 3   | 3   |   3   | 3 vs 2 is one step, no re-estimate needed; three votes for 3, agreed 3. |
| B-03 | 5   | 8   | 5   | 5   |   5   | 8 vs 5 is one step; B explains the token refresh edge cases, the team agrees that a 12 h expiry needs no refresh flow, so 5. |
| B-04 | 3   | 3   | 3   | 5   |   3   | 5 vs 3 is one step; D explains that there are only two role pages, three votes for 3, agreed 3. |
| B-05 | 5   | 5   | 3   | 5   |   5   | 5 vs 3 is one step; C explains that duplicate-title validation is left out, the team keeps 5 for title, description and visibility. |
| B-06 | 8   |  13  | 8   | 8   |   8   | 13 vs 8 is one step; B explains the drag-and-drop reorder, the team agrees to keep 8 and puts drag-and-drop out of scope (buttons up and down), and 13 would break the 8-point limit of the definition of ready. |
| B-07 | 3   | 2   | 3   | 3   |   3   | 3 vs 2 is one step; multi-answer reuses the same editor, agreed 3. |

Only B-01 had a spread of more than one Fibonacci step (5 against 2), so only B-01 triggered the explain-and-re-estimate rule; what was said is written in its note. The agreed points are the same numbers as in [sprint-1-backlog.csv](../sprint-1-backlog.csv).

## Capacity check

Committed: **30 points** (3 + 3 + 5 + 3 + 5 + 8 + 3) = ~ **75 h of the 80 h** capacity at 1 point ≈ 2.5 h, which leaves 5 h of buffer (4 students x 10 h x 2 weeks = 80 h, so the commitment uses 94 % of capacity).

Sprint goal: **By the end of sprint 1 an instructor account can register, log in with the right role and author single- and multi-answer questions, so the sponsor can play the authoring flow in a live demo at the review on 2026-11-02.**

## Burndown

Day mapping used below: D0 is the reading taken at sprint planning on 2026-10-20 (30 points, before work starts); D1 to D10 are the end-of-day readings of the ten working days 2026-10-20, 10-21, 10-22, 10-23, 10-26, 10-27, 10-28, 10-29, 10-30 and 2026-11-02, so D10 is the sprint review.

Ideal line: 30 points over ten working days = 3 points/day, giving 30, 27, 24, 21, 18, 15, 12, 9, 6, 3, 0. Actual line: 30, 30, 30, 26, 23, 23, 20, 15, 11, 8, 5. Gap (actual minus ideal): 0, 3, 6, 5, 5, 8, 8, 6, 5, 5, 5.

### Answers

- **First two full days behind:** **D2**, the first day whose gap reaches two ideal days (2 x 3 = 6 points): actual 30 against ideal 24, a gap of 6 points; equivalently the team still carried the 30 points the ideal line showed at D0. Under the mapping above D2 is the end of Wednesday 2026-10-21, the second working day, after two days with zero burn.
- **Velocity achieved:** **25 points** of items that met the definition of done (30 committed minus the 5 points still open at D10). **Returned to the product backlog:** **B-05, Create quiz (5 points)**, the one single unfinished item that owns all 5 open points at D10.
- **Forecast sprints 2-4:** the remaining Must + Should backlog is 120 - 25 = **95 points** for three sprints; 95 / 25 = **3.8 sprints needed but only 3 left**, so the team is 0.8 sprint short, i.e. **20 points cannot be delivered** (3 x 25 = 75 of 95). Three ways out: cut 20 points from the remaining backlog (95 -> 75), raise velocity to 95 / 3 = **31.7 points per sprint** (against 25 achieved and 30 planned), or move 20 points of Should work into week 14; even at the planned velocity of 30 the three sprints deliver 90 of 95, so 5 points would still be short.
