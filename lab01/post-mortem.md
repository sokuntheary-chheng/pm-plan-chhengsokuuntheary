# Post-mortem: CampusPay wallet (fictional case from Lab-01)

## 1. Timeline and sources

| #   | When | Event | Source |
| --- | ---- | ----- | ------ |
| 1   | Semester start | The university asks its IT unit to build a cashless payment app for canteen payments and library fines in one semester | fictional case from Lab-01 |
| 2   | Initiation | The head of finance "sponsors" the effort by e-mail and never attends a review | fictional case from Lab-01 |
| 3   | Initiation | The lead developer takes on both the project manager and the coder roles | fictional case from Lab-01 |
| 4   | Planning | Success is defined as "launch in September", with no other criteria | fictional case from Lab-01 |
| 5   | Mid-build | After a staff survey, requirements grow to include bus tickets and parking | fictional case from Lab-01 |
| 6   | Pre-launch | No test is run with the real card terminals | fictional case from Lab-01 |
| 7   | Launch day (September) | The terminals reject 40 % of payments and the canteen queue doubles | fictional case from Lab-01 |
| 8   | Launch + 3 days | The app is withdrawn; it relaunches five months later for the canteen only | fictional case from Lab-01 |

## 2. Classification and organisation

Project / programme: it was one project (a temporary endeavour with a unique app), but the post-survey expansion into bus tickets and parking turned it into several uncoordinated initiatives that a programme structure or a real sponsor should have refused or coordinated.
Structure and PM authority: the acting PM was the lead developer in a weak setup with no formal authority — one person coding and managing, with nobody above them who could say no.
Sponsor, charter, PMO: the head of finance was a nominal sponsor who never accepted the role in person; there was no signed charter and no PMO to enforce scope control or quality gates.

## 3. Success criteria

Stated: "launch in September" — a date and nothing else.
Missing measurable criteria: payment success rate, terminal-compatibility pass rate, queue-time impact, rollback plan, and capacity.
Ignored dimensions (benefits, users, operations, team): the cash-saving benefit was never quantified; users bore a doubled queue on day one; operations had no tested terminal integration; the team had one person doing two jobs with no buffer.

## 4. Process groups and knowledge areas

| Process group              | What went wrong or was skipped |
| -------------------------- | ------------------------------ |
| Initiating                 | No signed charter; the head of finance never truly accepted the sponsor role, so nobody could refuse the bus-ticket scope. |
| Planning                   | No test plan, no risk plan and no estimated schedule — the September date replaced planning. |
| Executing                  | The lead developer split time between coding and managing, and no independent test with the real card terminals was run before launch. |
| Monitoring and controlling | Progress was reported as "on schedule" without a single end-to-end test (the invisibility trap), and requirement growth had no change control. |
| Closing                    | The withdrawal after three days was unplanned; lessons were only drawn at the relaunch five months later. |

Knowledge areas most responsible: **scope management** — requirements grew from canteen payments and library fines to bus tickets and parking with no change control (timeline events 1 and 5); **risk management** — the untested card-terminal compatibility became a 40 % rejection rate on day one (events 6 and 7); **stakeholder management** — a sponsor-by-e-mail who attended no review left no authority for scope refusals or a go/no-go decision (events 2 and 3).

## 5. Ethics

Decision examined: launching on the fixed September date with no test against the real card terminals.
- **Responsibility:** the acting PM was responsible for the daily payment flow of canteen users and failed to run the one test that would have caught the 40 % rejection rate.
- **Respect:** shipping an untested app treated students and canteen staff as test subjects, and the doubled queue showed disregard for their time.
- **Fairness:** the costs of the failure (wasted queue time, rejected payments) fell on users who had no say in the date, while the date sat with the team and the absent sponsor.
- **Honesty:** reporting "on schedule" without end-to-end evidence overstated readiness to the sponsor and the university.

## 6. What our project will do differently

| #   | Commitment (We will ...) | Measured by | By week | Charter line                      |
| --- | ------------------------ | ----------- | ------- | --------------------------------- |
| 1   | We will hold a signed charter with a named sponsor who attends the week-7 and week-13 gates | signature in the charter approval block and gate minutes | 1 | section 10 approval; section 9 authority |
| 2   | We will treat the week-7 MVP demo as a real gate and will not continue as if it had passed when any Must feature fails | accepted-feature list of 8 of 8 Must features at the demo | 7 | objective O1; milestone week 7 |
| 3   | We will not add features beyond the charter scope without the sponsor's written approval within 5 working days | change log showing zero unapproved scope additions | 14 | section 9 authority; MVP week 7 constraint |
| 4   | We will run a load test with 100 simulated students on the real infrastructure before the pilot | load-test report green (20 sessions of 100 participants, 0 errors) | 13 | milestone week 13; objective O4 |
| 5   | We will judge the pilot by measures, not by a launch date: 50 participants and broadcasts within 500 ms | pilot report against objectives O2 and O3 | 14 | objectives O2 and O3; milestone week 14 |
