# Lab-03: life cycle and methodology · Realtime Quiz

This lab selects the **hybrid** life cycle for the Realtime Quiz project: an approved predictive plan with four phase gates (G1-G4) wrapped around four two-week Scrum sprints, followed by two weeks of hardening and the week-14 pilot. It was chosen because it scored **4.05** against 3.45 for pure Scrum and 3.30 for waterfall on the five criteria of the project profile (profile value 3.05, hybrid band), so it is the only candidate that is strong on both dominating criteria, technical uncertainty and contract/governance constraints; the full reasoning is in the [tailoring decision record](tailoring-decision-record.md).

The sponsor controls the project with the four gates on 2026-10-19, 2026-11-16, 2026-12-14 and 2027-01-04, each with five measurable checklist criteria and the outcomes continue / continue with changes / stop / repeat, with numeric per-stage tolerances on time, hours, scope, quality and risk that are managed by exception, and with a one-page weekly highlight report plus a three-line exception report when a tolerance is breached; the whole scheme is written down in [governance.md](governance.md).

## Files

| File                               | What it contains (one line) |
| ---------------------------------- | --------------------------- |
| lab03/project-profile.md           | five scored selection criteria, weights summing to 100 and the profile value 3.05 (hybrid band) |
| lab03/approach-comparison.md       | waterfall vs pure Scrum vs hybrid with risks, sponsor control, first working quiz and sensitivity tests |
| lab03/approach-scoring.csv         | weighted scoring sheet, Task 1 weights reused, last line holds the three computed scores |
| lab03/tailoring-decision-record.md | ADR-style record: context, options, decision, consequences, tailoring table and the gates table |
| lab03/life-cycle.mmd               | Mermaid gantt of the 14 weeks with the four sprints of 14 days and the four `:milestone` gates |
| lab03/life-cycle.svg               | exported diagram of life-cycle.mmd |
| lab03/scrum-setup.md               | roles, sprint goal, sprint 1 event calendar, DoR, DoD, sprint schedule and velocity |
| lab03/sprint-1-backlog.csv         | seven Must items with FR ids, Fibonacci points, owners and Given/When/Then criteria, 30 points |
| lab03/governance.md                | four gate checklists, numeric tolerances per stage, reporting and closure criteria |
| lab03/challenge/sprint-1-planning.md | planning poker for B-01 to B-07 and the burndown analysis with the four answers |
| lab03/challenge/burndown.mmd       | xychart-beta of the ideal and actual remaining points for D0 to D10 |
| lab03/challenge/retrospective-template.md | retrospective sections filled once for sprint 1 with burndown-derived actions |
| lab03/challenge/prince2-comparison.md | twelve hybrid elements mapped to PRINCE2 7 plus what PRINCE2 adds and what it makes heavier |

## Inputs reused

| Input                        | Version / tag |
| ---------------------------- | ------------- |
| lab01/project-charter.md     | ce1fad2       |
| lab01/stakeholders.md        | d6aba49       |
| lab02/moscow.md              | 50513d9       |
| lab02/constraints.md         | 27f8687       |
| lab02/features.csv           | 9e12826       |

The Lab-02 file names differ from the names used in the lab text: `moscow.md` is the MoSCoW list, `constraints.md` is the constraint analysis, `stakeholders.md` is the stakeholder list, and the FR ids of the sprint backlog come from `features.csv`. Version column is the short commit hash from `git log -1 --format=%h -- <file>`.

## Change log

| Date      | Version | Change                                                    |
| --------- | ------- | --------------------------------------------------------- |
| 2026-11-03 | 0.1     | Lab-03 · life cycle selection, Scrum setup and governance added |
