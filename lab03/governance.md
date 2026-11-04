# Governance · Realtime Quiz hybrid life cycle

Sources: [tailoring decision record](tailoring-decision-record.md), [life cycle](life-cycle.mmd), [charter](../lab01/project-charter.md), [constraint analysis](../lab02/constraints.md), [scrum setup](scrum-setup.md)

Stage budgets used below: stage 1 (W1-3) 120 h, stage 2 (W4-7) 160 h, stage 3 (W8-11) 160 h, stage 4 (W12-14) 120 h, together the 560 h cap of the Lab-02 recap. The four gate dates are identical to the four `:milestone` dates in [life-cycle.mmd](life-cycle.mmd) and to the gates table of [tailoring-decision-record.md](tailoring-decision-record.md).

## Stage gates

### G1 · Plan approved · end of week 3 (2026-10-19)

- [ ] Scope baseline lists all 17 features with their MoSCoW class and hours (evidence: lab02/features.csv, 504 h planned)
- [ ] Milestone schedule shows G1-G4 and four sprints of 14 days (evidence: life-cycle.mmd)
- [ ] Budget in hours is <= 560 h with >= 56 h contingency (evidence: budget table in the plan)
- [ ] The four known risks each have an owner and a response (evidence: risk register)
- [ ] Capacity confirmed as 4 students x 10 h/week = 40 h/week (evidence: signed charter, section 5)
Inputs: charter, scope statement, WBS, milestone schedule, budget in hours
Decision maker: sponsor with the PM · Outcomes: continue / continue with changes / stop / repeat

### G2 · MVP checkpoint · end of week 7 (2026-11-16)

- [ ] 8 of 8 Must features demonstrated at the MVP demo (evidence: demo script signed at the sprint 2 review)
- [ ] CI green on 100 % of merges in sprints 1-2 and line coverage >= 70 % at G2 (evidence: JaCoCo report in CI)
- [ ] Broadcast latency p95 <= 700 ms on the staging VPS, tightening to <= 500 ms by G3 (evidence: load test report)
- [ ] Hours used <= 308 h of the 280 h planned for stages 1-2 (evidence: timesheet total)
- [ ] 0 blocking defects open against Must features (evidence: defect list)
Inputs: sprint 1 and sprint 2 reviews, CI report, load test report, timesheet
Decision maker: sponsor with the PM · Outcomes: continue / continue with changes / stop / repeat

### G3 · Release candidate · end of week 11 (2026-12-14)

- [ ] All Must and >= 80 % of Should items meet the definition of done (evidence: backlog export)
- [ ] Line coverage >= 80 % on service and realtime code (evidence: JaCoCo report in CI)
- [ ] Load test with 100 simulated students, p95 broadcast < 500 ms (evidence: load test report)
- [ ] Security checklist signed and no secret in the repository (evidence: checklist file and CI secret scan)
- [ ] Hours used <= 476 h of the 440 h planned for stages 1-3 (evidence: timesheet total)
Inputs: sprint 4 review notes, CI report, load test report, risk register
Decision maker: sponsor with the PM · Outcomes: continue / continue with changes / stop / repeat

### G4 · Acceptance and closure · week 14 (2027-01-04)

- [ ] Pilot with 50 students completed with 0 blocking defects (evidence: attendance list and defect list)
- [ ] Line coverage >= 80 % and CI green on the release tag (evidence: JaCoCo report and CI run for tag v1.0)
- [ ] p95 broadcast latency <= 500 ms measured during the pilot (evidence: monitoring export)
- [ ] Hours <= 560 h and cash <= 200 USD (evidence: timesheet total and expense list)
- [ ] Runbook rehearsed once, repository tagged and VPS credentials handed over (evidence: hand-over sign-off)
Inputs: pilot results, final CI report, timesheet, closure checklist
Decision maker: sponsor · Outcomes: continue / continue with changes / stop / repeat

## Tolerances (manage by exception)

| Tolerance    | Stage 1 (W1-3) | Stage 2 (W4-7) | Stage 3 (W8-11) | Stage 4 (W12-14) |
| ------------ | -------------- | -------------- | --------------- | ---------------- |
| Time         | G1 slips at most +3 working days (by 2026-10-22) | each sprint slips at most +2 days (sprint 2 ends by 2026-11-18) | each sprint slips at most +2 days (sprint 4 ends by 2026-12-16) | 0 days (pilot starts 2026-12-29, fixed) |
| Cost (hours) | +10 %, at most 132 h of 120 h | +10 %, at most 176 h of 160 h | +5 %, at most 168 h of 160 h | 0 %, at most 120 h, cumulative <= 560 h |
| Scope        | 0 Must features removed, 0 Should items added before G1 | at most 1 Should item descoped per sprint, 0 Must removed | at most 2 Should items descoped in total, 0 Must removed | 0 changes (change freeze 2026-12-29 to 2027-01-04) |
| Quality      | CI green on 100 % of merges, coverage >= 50 % | coverage >= 70 %, p95 latency <= 700 ms | coverage >= 80 %, p95 latency <= 500 ms, 0 blocking defects | coverage >= 80 %, 0 blocking defects in the pilot, p95 latency <= 500 ms |
| Risk         | at most 1 risk scored >= 15 (5 x 3) without an owner | at most 2 high risks open, each with a dated response | at most 1 high risk open, SockJS fallback tested once | 0 high risks open without a response |

Escalation: developers -> scrum master -> PM -> sponsor

Exception report when: any cell above is exceeded (for example a sprint ends more than 2 days late, a stage passes its hours limit, a Must feature is proposed for removal, coverage falls below the stage floor, or a risk scored >= 15 has no owner). The report is raised within 1 working day of the measurement and goes to the PM, who forwards it to the sponsor when the stage tolerance is the one breached.

## Reporting

- **Weekly highlight report:** every Friday at 16:00, maximum 1 page of 10 lines, with the four headings **Done**, **Next**, **Risks**, **Tolerance status**. The PM sends it to the sponsor and the Scrum master supplies the burndown and the hours used.
- **Sprint review as checkpoint for the PM:** at each review (2026-11-02, 2026-11-16, 2026-11-30, 2026-12-14) the PM checks the milestone table against the backlog, the hours used against the stage budget and the open risks; the reviews on 2026-11-16 and 2026-12-14 are the gates G2 and G3.
- **Exception report (three lines):** Deviation: what number is outside which tolerance, by how much and since when. Options: at least two, with hours and date impact. Recommendation: one option with the date it must be decided by.

## Closure criteria

| Area                   | Criterion                                                                 | Verified by                        | Owner                     |
| ---------------------- | ------------------------------------------------------------------------- | ---------------------------------- | ------------------------- |
| Acceptance             | 8 of 8 Must features accepted, pilot with 50 students, 0 blocking defects, p95 latency <= 500 ms, coverage >= 80 % | Sponsor signs the acceptance note at the pilot review | PM (Tal Tongsreng)        |
| Hand-over              | Git repository tagged v1.0 and archived, Linode VPS credentials handed over in a sealed note, runbook with deploy and rollback steps rehearsed once | Sponsor's IT operations checks the rehearsal and the tag | Scrum master (Student B)  |
| Lessons learned        | The 4 sprint retrospective action lists are archived and a closure workshop produces at least 5 written actions | PM reads the workshop notes        | Scrum master (Student B)  |
| Administrative closure | Timesheet closed at <= 560 h, spend reconciled at <= 200 USD, all course accounts and VPS access revoked or transferred, change requests and DR-01 marked closed | PM checks the totals, sponsor confirms the cash | PM (Tal Tongsreng)        |
